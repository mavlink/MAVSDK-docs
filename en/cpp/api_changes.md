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


## v0.33.0

There are some changes in how systems are discovered, connected and accessed with this release.
The previous APIs are still available but marked deprecated and they will be removed in the future.
The deprecations are also implemented as compiler warnings.

### Discovery of systems

The 64bit (8 bytes) uuid is deprecated because it needed to be extended to 18 bytes.
For more info, see this [MAVLink pull request](https://github.com/mavlink/mavlink/pull/786).
Therefore, the discovery no longer contains the uuid.
If the uid is required it can be found in the [Info plugin](api_reference/classmavsdk_1_1_info.md#classmavsdk_1_1_info_1a812ed66265b7427bc781faec3f0fa89e).

**Previous way of discovering systems:**
```cpp
Mavsdk mavsdk;

std::promise<void> discover_promise;
auto discover_future = discover_promise.get_future();

mavsdk.register_on_discover([&discover_promise](uint64_t uuid) {
    std::cout << "Discovered system with UUID: " << uuid << '\n';
    discover_promise.set_value();
});

discover_future.wait();
```

**New way of discovering a system:**
```cpp
Mavsdk mavsdk;

auto new_system_promise = std::promise<std::shared_ptr<System>>{};
auto new_system_future = new_system_promise.get_future();
mavsdk.subscribe_on_new_system([&mavsdk, &new_system_promise]() {
    new_system_promise.set_value(mavsdk.systems().at(0));
    mavsdk.subscribe_on_new_system(nullptr);
});

auto system = new_system_future.get();
```

To be notified about a system timing out later, or being discovered again, you can now use:
```cpp
system->subscribe_is_connected([](bool is_connected) {
    if (is_connected) {
        std::cout << "System has been discovered" << '\n';
    } else {
        std::cout << "System has timed out" << '\n';
    }
});
```

If you prefer to use sync APIs / polling, you can use this to wait for a vehicle and connect:
```cpp
Mavsdk mavsdk;

while (mavsdk.systems().size() == 0) {
    std::this_thread::sleep_for(std::chrono::seconds(1));
}

auto system = mavsdk.systems().at(0);
```


### Accessing systems

We aim to make the API of MAVSDK as easy and safe to use as possible.
However, as we'll see below, this still comes with trade-offs.

When designing the API we decided to expose the MAVSDK user a reference to a system `System&`, which means the system will always be instantiated and there won't be any segfaults trying to access a system that is null.
This mostly worked fine, however, had some drawbacks:
- Without an actual system discovered the `System&` is basically a null reference that won't really work.
  This is not really obvious unless you check its system and component IDs for 0.
  This is not very intuitive and also means additional checks inside the plugins are required.
- The ownership model is not very clear as `Mavsdk` owns the `System` but then each plugin only seems to require the `System`.
  Internally, the plugins still require `Mavsdk` to be alive and working but that's not apparent through the API.
- If there are multiple sytems they need to be accessed using the `uuid`.
  This seems like a crutch because essentially we would just like to have a `std::vector` of systems but of course that's not posible with references.

As the API for the uid was about the change anyway (see above) it seemed time to redesign the API to access systems with these considerations in mind.

The basic change is to move away from the reference `System&` to a shared pointer `std::shared_ptr<System>`.

This brings the following advantages:
- No more confusing null reference systems.
- Clearer ownership model as a `System` is now shared between `Mavsdk` and the plugins.
- Nice getter `std::vector<std::shared_ptr<System>> systems()` allowing easier access to all systems.

**Previous way to get a system:**
```cpp
System& system = mavsdk.system();
```

**New way to get a system:**
```cpp
std::shared_ptr<System> system = mavsdk.systems().at(0);
```

Or just:
```cpp
auto system = mavsdk.systems().at(0);
```

> **Note** The `std::vector<std::shared_ptr>` returned by `systems()` might be empty if no system has been discovered yet, and the above call will abort.

## v0.25.0

There are several changes in this release (from v0.24.0) because the C++ plugins are now partially auto-generated from the proto files.
While this causes some painful changes, it has several advantages:
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

  The reasoning behind this change is to avoid clashes with macros.
  For instance we had conflicts with `ERROR` or `SOCKET_ERROR` on Windows ([issue](https://github.com/mavlink/MAVSDK/issues/953)).

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


### Telemetry

#### Types

Some of the types have been renamed for consistency:

- `AccelerationNED` -> `AccelerationFrd`
- `AngularVelocityNED` -> `AngularVelocityFrd`
- `IMUReadingNED` -> `Imu`
- `MagneticFieldNED` -> `MagneticFieldFrd`
- `GroundSpeedNED` -> `VelocityNed`
- `SpeedBody` -> `VelocityBody`

The changes were mostly for consistency, or correctness.

#### Methods

In the same way, some of the methods changed:

- `set_rate_ground_speed` -> `set_rate_velocity_ned`
- `ground_speed_async` -> `subscribe_velocity_ned`


### Mission

#### Classes

The separate class `MissionItem` is now just a POD struct inside `Mission`, so `Mission::MissionItem`.

#### Methods

- `Progress` is now `MissionProgress`:

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

### Offboard

####Types

Matching with the rest, acronyms are not all capitalized anymore, mostly because that's easier to deal with in auto-generation:

`PositionNEDYaw` -> `PositionNedYaw`
`VelocityNED` -> `VelocityNedYaw`
