## FAQ

### Why was DroneCore written in C++?

The aim was to have an API in a language which is cross-platform and has many language bindings. Additionally, the library needs to be lightweight and fast, so it does not fall over for onboard usage with high rate messaging.

### Does DroneCore support multiple vehicles?

Yes, DroneCore is designed to support multiple vehicles. A vehicle is called a device in DroneCore.

A device needs to have a specific MAVLink system ID but can consist of multiple components with different component IDs. An example would be a drone with a gimbal and a camera talking MAVLink with the same system ID but different component IDs.

The limit is in theory 255 vehicles for system IDs ranging from 1 to 255.

### What sorts of vehicles does DroneCore support?

The DroneCore API is designed for interacting with *aircraft*. It has primarily been tested for use with copters, but also has basic support for fixed wing and [VTOL](../guide/vtol.md).

The API may "work" with ground based vehicle or other type, but some methods will not make sense, and this use-case is unsupported and untested.

### Does DroneCore support indoor use?

Indoor use is not supported (at time of writing).

DroneCore requires that connected vehicles have a position estimate. Currently this means that GPS is required. 
In future we also expect PX4 to support local positioning methods (optical flow or visual-inertial odometry), at which point indoor use will also become possible. 


### Are serial connections supported?

The architecture has stubs for serial, TCP, and UDP connections. However, only UDP connections are implemented right now.

### Why is libCURL a dependency?

libCURL will be required to download the camera definition file which is referenced in [CAMERA_INFORMATION](http://mavlink.org/messages/common#CAMERA_INFORMATION). It might also come in handy whenever any other REST resources are required. 

### How are plugins added?

Plugins need to have the correct structure and be placed in the [plugins directory](https://github.com/dronecore/DroneCore/tree/{{ book.github_branch }}/plugins). It is also possible to create [DroneCore Extensions](../guide/dronecore_extensions.md) that contain plugins outside of the DroneCore tree.

### Can a plugin depend on another one?

Yes it can but it should not! The idea is that plugins don't have any coupling between each other which allows for any plugin to be changed or removed without breaking the rest. This will lead to some duplication at places, that's an acceptable trade-off. If the same code is used in many places, it can always be moved to core and get re-used from there.


### What is the difference between unit and integration test?

The unit tests are only concerned with one plugin or less. The integration tests however might need PX4 SITL running and combine multiple plugins.
