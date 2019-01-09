## FAQ

### Why was the SDK written in C++?

The aim was to have an API in a language which is cross-platform and has many language bindings. 
Additionally, the library needs to be lightweight and fast, so it does not fall over for onboard usage with high rate messaging.

### Are multiple vehicles supported?

Yes, the SDK is designed to support multiple vehicles. A vehicle is referred to a system in this SDK.

A system needs to have a specific MAVLink system ID but can consist of multiple components with different component IDs. 
An example would be a drone with a gimbal and a camera talking MAVLink with the same system ID but different component IDs.

The limit is in theory 255 vehicles for system IDs ranging from 1 to 255.

### Is MAVLink 1 supported?

No. The SDK only supports [MAVLink 2.0](https://mavlink.io/en/mavlink_2.html).

### What sorts of vehicles are supported?

The SDK API is designed for interacting with *aircraft*. It has primarily been tested for use with multicopters, but also has basic support for fixed wing and [VTOL](../guide/vtol.md).

The API *may* "work" with ground-based or other types of vehicles, but some methods will not make sense. 
This use-case is unsupported and untested.

### Does the SDK support indoor use?

Indoor use is not supported (at time of writing).

The SDK requires that connected vehicles have a position estimate. 
Currently this means that GPS is required. 
In future we also expect PX4 to support local positioning methods (optical flow or visual-inertial odometry), 
at which point indoor use will also become possible.

### What UAV flight stacks are supported?

The SDK is optimised for use with the PX4 flight stack and all testing is done against PX4.

While many features should work on other flight stacks there may be implementation differences at the [MAVLink microservices level](https://mavlink.io/en/protocol/overview.html) that mean not every API will work. 
For example, PX4 and ArduPilot implement the parameter protocol differently, and use different modes for accepting commands from a companion computer.

> **Note** The SDK welcomes contributions to better support flight stacks other than PX4.
> We do however expect contributors to also help with testing and maintenance support for using the SDK with their autopilot.

### Are serial connections supported?

Yes. Serial, TCP, and UDP connections are supported.

### Why is libCURL a dependency?

libCURL will be required to download the camera definition file which is referenced in [CAMERA_INFORMATION](http://mavlink.org/messages/common#CAMERA_INFORMATION). 
It might also come in handy whenever any other REST resources are required. 

### How are plugins added?

Plugins need to have the correct structure and be placed in the [plugins directory](https://github.com/Dronecode/DronecodeSDK/tree/{{ book.github_branch }}/plugins). It is also possible to create [SDK Extensions](../guide/sdk_extensions.md) that contain plugins outside of the SDK tree.

### Can a plugin depend on another one?

Yes - but it should not! 
The idea is that plugins don't have any coupling between each other which allows for any plugin to be changed or removed without breaking the rest. 
This will lead to some duplication at places, that's an acceptable trade-off. 
If the same code is used in many places, it can always be moved to core and get re-used from there.


### What is the difference between unit and integration tests?

The unit tests are only concerned with one plugin or less. 
The integration tests however might need PX4 SITL running and combine multiple plugins.
