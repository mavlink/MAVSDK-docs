## FAQ

### Why was the core of the SDK written in C++?

The aim was to have an API in a language which is cross-platform and has many language bindings.
Additionally, the library needs to be lightweight and fast, so it does not slow down for onboard usage at higher rate messaging.

### Are multiple vehicles supported?

Yes, the core C++ SDK is designed to support multiple vehicles. A vehicle is referred to a system in this SDK. The language wrappers so far only support one vehicle at a time. (However, nothing stops you from instantiating multiple copies of it to deal with multiple systems.)

A system needs to have a specific MAVLink system ID but can consist of multiple components with different component IDs.
An example would be a drone with a gimbal and a camera talking MAVLink with the same system ID but different component IDs.

The limit is in theory 255 vehicles for system IDs ranging from 1 to 255.

### Is MAVLink 1 supported?

No. MAVSDK only supports [MAVLink 2.0](https://mavlink.io/en/guide/mavlink_2.html).

### What sorts of vehicles are supported?

The MAVSDK API is designed for interacting with *aircraft*. It has primarily been tested for use with multicopters, but also has basic support for fixed wing and [VTOL](cpp/guide/vtol.md).

The API *may* "work" with ground-based or other types of vehicles, but some methods will not make sense.
This use-case is mostly unsupported and untested.

### Does MAVSDK support indoor use?

Indoor use is supported, however, some modes such as mission or position control are not available indoor, unless some additional positioning method is available (e.g. optical flow, visual-inertial odometry, a motion capture system, etc.).

Note that PX4 currently does not support missions in "local coordinates" i.e. meters but only "global coordinates i. e. latitude/longitude.

### What UAV flight stacks are supported?

MAVSDK, so far, is optimised for use with the PX4 flight stack and all testing is done against PX4.

While many features should work on other flight stacks there may be implementation differences at the [MAVLink microservices level](https://mavlink.io/en/protocol/overview.html) that mean not every API will work.
For example, PX4 and ArduPilot implement the parameter protocol differently, and vary slightly in the mission upload/download protocol (e.g. ArduPilot uses the 0 entry as the home position).

> **Note** The SDK welcomes contributions to better support flight stacks other than PX4.
> We do however expect contributors to also help with testing and maintenance support for using the SDK with their autopilot.

### Are serial connections supported?

Yes. Serial, TCP, and UDP connections are supported.

### Why is libCURL a dependency?

libCURL will be required to download the camera definition file which is referenced in [CAMERA_INFORMATION](https://mavlink.io/en/messages/common.html#CAMERA_INFORMATION).
It might also come in handy whenever any other REST resources are required.

### How are plugins added?

Check out [contributing/plugins](contributing/plugins.md).

### Can a plugin depend on another one?

Yes - but it should not!
The idea is that plugins don't have any coupling between each other which allows for any plugin to be changed or removed without breaking the rest.
This will lead to some duplication at places, that's an acceptable trade-off.
If the same code is used in many places, it can always be moved to core and get re-used from there.

Over time we have sometimes moved functionality from plugins to the core if it was exposed in multiple plugins (e.g. mission upload/download has been moved to the core so it can be used in the Mission plugin as well as the MissionRaw and Geofence plugins.

### What is the difference between unit and integration tests?

The unit tests are only concerned with one class or function.
The integration tests combine multiple plugins and execute against a real system (e.g. PX4 SITL).

### Can MAVSDK run on an embedded platform / microcontroller

MAVSDK is generally written a bit higher level, geared towards ARM devices such as a Raspberry Pi, smartphone or faster/better.

As it doesn't actually use too much compute, it could in theory be run on a microcontroller such as an ARM Cortex M4, however, it would require the POSIX APIs for serial and networking communication as well as the C++ standard library for things like `std::thread` or `std::vector`.

The recommendation for a microcontroller would be to use the pure [C MAVLink headers](https://mavlink.io/en/mavgen_c/).
