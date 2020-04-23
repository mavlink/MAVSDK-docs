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
- Missing features for language wrappers such as Python.

### General

#### Enums

- Enum naming is now `CamelCase` instead of `ALL_UPPERCASE`:

  `Action::RESULT` -> `Action::Result`

  `Telemetry::FLIGHT_MODE` -> `Telemetry::FlightMode`

- Printing of enums is easier:

  Old:
  ```
  std::cout << flight_mode_str(flight_mode);
  ```
  New:
  ```
  std::cout << flight_mode;
  ```

#### Methods

Methods returning a bool are now mostly prefixed with `is_`. E.g. `is_health_ok` instead of `health_ok`.

### Mission

#### Classes

The separate class `MissionItem` is now just a POD struct inside `Mission`, so `Mission::MissionItem`.

#### Methods

- To get the mission progress, the method is now named in the same way as subscriptions in the telemetry plugin:

  Old:
  ```cpp
  subscribe_mission_progress(subscribe_mission_callback_t callback);
  ```
  New:
  ```cpp
  mission_progress_async(mission_progress_callback_t callback);
  ```

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

  upload_mission_async(Mission::MissionPlan mission_plan, result_callback_t callback);
  ```

- Similarly to download a mission:

  Old:
  ```cpp
  typedef std::function<void(Result, std::vector<MissionItem>)> mission_items_and_result_callback_t;

  download_mission_async(mission_items_and_result_callback_t, callback)
  ```
  New:
  ```cpp
  typedef std::function<void(Result, MissionPlan)> download_mission_callback_t;
  void download_mission_async(const Mission::download_mission_callback_t& callback);
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

### Calibration

The results `IN_PROGRESS` and `INSTRUCTION` disappear in favor of `Next`. Now, `Success` means that the function finished successfully, `Next` represents a new element of the stream and all the other results mean that the function finished with an error (described by the result).

### Geofence

#### Methods

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
