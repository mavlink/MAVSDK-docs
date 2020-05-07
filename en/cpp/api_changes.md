# API Changes

This page tracks changes between versions.

It covers both breaking (incompatible) and non-breaking changes.

## Semantic Versioning

MAVSDK follows [semver/Semantic Versioning](https://semver.org/) conventions where as possible.

The version number has the format: **major.minor.patch**.
Individual parts of the number are iterated when the:

- **major**: API is changed, or functionality is removed.
- **minor**: API is extended, functionality is added.
- **patch**: API is not changed, functionality is not changed, but a bug is fixed.

This means that breaking changes to the API result in a bump of the major version number (e.g. 1.4.3 to 2.0.0).

> **Note** At time of writing, breaking/incompatible changes *are not* resulting in the major version number being increased!
  We plan to release version 1.0.0 in the near future, after which the above strategy will be adopted (i.e. currently breaking changes can occur in both minor and patch releases).


## v0.25.0

There are several changes in this release (from v0.24.0) because the C++ plugins are now partially auto-generated from the proto files. While this causes some painful changes, it has several advantages:
- Better consistency between C++ and other languages for naming/docs/functionality.
- Automatically propagate features to language wrappers such as Python.

> **Note** It's also worth looking at the integration tests and examples between the versions to see how things changed: [GitHub diff view](https://github.com/mavlink/MAVSDK/compare/v0.24.0...v0.25.0).

The notes below try to give an overview over the changes as well as give some background on why they were deemed to be necessary.

### General Changes

#### Enums

- Enum naming is now `CamelCase` instead of `ALL_UPPERCASE`:

  `Action::RESULT` -> `Action::Result`

  `Telemetry::FLIGHT_MODE` -> `Telemetry::FlightMode`

> **Note** For enums, there is also a [script](https://github.com/mavlink/MAVSDK/blob/v0.25.0/tools/rename-enums-to-camelcase.sh) that you can run to fix them in one batch.

  The reasoning behind this change is to avoid clashse with macros. For instance we had conflicts with `ERROR` or `SOCKET_ERROR` on Windows ([issue](https://github.com/mavlink/MAVSDK/issues/953)).

- Printing of enums is easier:

  Old:
  ```
  std::cout << flight_mode_str(flight_mode);
  ```
  New:
  ```
  std::cout << flight_mode;
  ```

  With auto-generation it is quite easy to make sure everything is printable using streams and we can drop the custom `_str` functions.

  To get a `std::string` from `operator<<` you can use:
  ```
  #include <sstream>

  std::stringstream ss;
  ss << flight_mode;
  std::string str = ss.str();
  ```


#### Callback types

The typedefs for callback types are no longer suffixed with `_t` and in `CamelCase` instead of `all_lower_case`, and they use the more modern `using` syntax rather than `typedef` e.g.:

Old:
```
typedef std::function<void(int)> foo_callback_t;
```

New:
```
using FooCallback = std::function<void(int)>;
```

This change was decided in order to move with the [modern C++ recommendation](https://google.github.io/styleguide/cppguide.html#Aliases) as much as possible and also allow it to be used with templates.

#### Methods

- Methods representing an infinite stream (i.e. that take a callback repeatedly receiving events, until they get unsubscribed) are now prefixed with `subscribe_` instead of being suffixed with `_async`.

  Old:
  ```
  telemetry->position_async(...);
  ```

  New:
  ```
  telemetry->subscribe_position(...);
  ```
  Finite streams keep the `_async` suffix, e.g. `calibrate_magnetometer_async(...)`.

  The reasoning is that it makes infinite streams clearly distinguishable from finite streams and requests which are async. Also, it allows to potentially add `unsubscribe` in the future.

- Methods returning a bool are now mostly prefixed with `is_`. E.g. `is_health_ok` instead of `health_ok`.

### Mission

#### Classes

The separate class `MissionItem` is now just a POD struct inside `Mission`, so `Mission::MissionItem`.

#### Methods

- Progress is now Mission Progress:

  Old:
  ```cpp
  subscribe_progress(progress_callback_t callback);
  ```
  New:
  ```cpp
  subscribe_mission_progress(MissionProgressCallback callback);
  ```

  This makes it clear that the progress is for the mission and not the upload/download.

- The interface to upload a mission no longer uses a `std::vector` of `std::shared_ptr`s but a `std::vector` of the actual structs.
  It is further wrapped inside `MissionPlan` in order to support mission settings.

  Old:
  ```cpp
  typedef std::function<void(Result)> result_callback_t;

  upload_mission_async(std::vector<std::shared_ptr<MissionItem>> items, result_callback_t callback);
  ```
  New:
  ```cpp
  struct MissionPlan {
      std::vector<MissionItem> mission_items;
  }

  upload_mission_async(Mission::MissionPlan mission_plan, ResultCallback callback);
  ```

  Copying all items by value instead of using pointers might seem like overhead, however, there are a few arguments against that:
  - The items were copied anyway inside of the mission plugin in order not to mess with the user's data. This change shows that in the API instead of hiding it.
  - Reference counting in `std::shared_ptr` is also overhead, especially when done for each and every mission item.
  - Only profiling will tell if a vector of pointers or a vector of structs is actually more performant. It depends on the number of items, caches,  etc..
  - Shared ownership of data should be prevented as much as possible, unless really required, and can lead to interesting effects on destruction. Passing by value is often just easier and more intuitive.

- Similarly to download a mission:

  Old:
  ```cpp
  typedef std::function<void(Result, std::vector<MissionItem>)> mission_items_and_result_callback_t;

  download_mission_async(mission_items_and_result_callback_t, callback)
  ```
  New:
  ```cpp
  using DownloadMissionCallback = std::function<void(Result, MissionPlan)>;
  void download_mission_async(const Mission::DownloadMissionCallback& callback);
  ```

  > **Tip** There are now also sync methods to upload and download a mission: `upload_mission` and `download_mission`.

- Some methods now return a `std::pair<Result, bool>` instead of just a `bool` to cover the case where a request fails.

  Old:
  ```cpp
  bool mission_finished();
  ```
  New:
  ```cpp
  std::pair<Result, bool> is_mission_finished();
  ```

  The fields of a pair can be accessed with `.first` and `.second`.

### Calibration

The results `IN_PROGRESS` and `INSTRUCTION` disappear in favor of `Next`. Now, `Success` means that the function finished successfully, `Next` represents a new element of the stream and all the other results mean that the function finished with an error (described by the result).

### Geofence

#### Methods

The naming of the upload method has changed to match the mission and mission_raw plugins:

Old:
```
send_geofence_async(...);
```
New:
```
upload_geofence_async(...);
```
Or:
```
upload_geofence(...);
```

#### Types

Structs are usually no longer nested inside other structs but flatter due to the complexity it would pose for auto-generation:

Old:
```
Geofence::Polygon::Point point;
```
Now:
```
Geofence::Point point;
```

Also, we no longer pass polygons with `std::shared_ptr<Geofence::Polygon>` but by value `Geofence::Polygon`.
