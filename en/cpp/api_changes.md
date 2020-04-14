# API changes

## General comment

We would like to keep the API of MAVSDK as stable as possible, however, we don't want to stand still and also improve over time. Therefore, sometimes breaking changes are required.

### SemVer

We try to follow the [semver/Semantic Versioning](https://semver.org/) conventions as much as possible.

High level this means that the version number is **major.minor.patch**.

- **major**: Bumping when the API is changed, or functionality is removed.
- **minor**: Bumping when the API is extended, functionality is added.
- **patch**: Bumping when the API is not changed, functionality is not changed, but a bug is fixed.

This means that breaking the API goes with a bump of the major version number (e.g. 1.4.3 to 2.0.0), however, we ignore that until version 1.0.0, so we allow to break the API of 0.y.z.


## Specific transition notices

### v0.24.0 to v0.25.0

There are several changes in this release because the C++ plugins are now partially auto-generated from the proto files. While this causes some painful changes, it has several advantages:
- Better consistency between C++ and other languages for naming/docs/functionality.
- Missing features for language wrappers such as Python.

### General

#### Enums

Enum naming is now `CamelCase` instead of `ALL_UPPERCASE`:

`Action::RESULT` -> `Action::Result`
`Telemetry::FLIGHT_MODE` -> `Telemetry::FlightMode`

Printing of enums is easier,
old:
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

To get the mission progress, the method is now named in the same way as subscriptions in the telemetry plugin,
old:
```
subscribe_mission_progress(subscribe_mission_callback_t callback);
```

New:
```
mission_progress_async(mission_progress_callback_t callback);
```

The interface to upload a mission no longer uses a `std::vector` of `std::shared_ptr`s but a `std::vector` of the actual structs.
It is further wrapped inside `MissionPlan` in order to support mission settings.

Old:
```
typedef std::function<void(Result)> result_callback_t;

upload_mission_async(std::vector<std::shared_ptr<MissionItem>> items, result_callback_t callback);
```

New:
```
struct MissionPlan {
    std::vector<MissionItem> mission_items;
}

upload_mission_async(Mission::MissionPlan mission_plan, result_callback_t callback);
```

Similarly to download a mission:
```
typedef std::function<void(Result, std::vector<MissionItem>)> mission_items_and_result_callback_t;

download_mission_async(mission_items_and_result_callback_t, callback)
```

New:
```
typedef std::function<void(Result, MissionPlan)> download_mission_callback_t;
void download_mission_async(const Mission::download_mission_callback_t& callback);
```

> **Tip** There are now also sync methods to upload and download a mission `upload_mission` and `download_mission`.

Some methods now return a `std::pair<Result, bool>` instead of just a `bool` to cover the case where a request fails, e.g.
old:
```
bool mission_finished();
```

New:
```
std::pair<Result, bool> is_mission_finished();
```
