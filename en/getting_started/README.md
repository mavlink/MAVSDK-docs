# Getting Started

> **Note** At time of writing all users will need to [build the library](../contributing/build.md) in order to use it. In the near future we'll have binary releases for the wrapper APIs.  Instructions for how to write a simple complete example are covered in [Takeoff and Land](../examples/takeoff_and_land.md). The text below is "aspirational".

This topic explains how to set up a development environment and write a minimal example for all our supported programming languages/platforms. 

## API overview

<!-- all these links should go to API ref, once created -->

- [dronecore](https://github.com/dronecore/DroneCore/blob/master/include/dronecore.h) (include/dronecore.h): set up connection, discover devices
- [device](https://github.com/dronecore/DroneCore/blob/master/include/device.h) (include/device.h): a device providing access to modules below using ...
- [info](https://github.com/dronecore/DroneCore/blob/master/plugins/info/info.h) (plugins/info/info.h): general info about a device
- [telemetry](https://github.com/dronecore/DroneCore/blob/master/plugins/telemetry/telemetry.h) (plugins/telemetry/telemetry.h): to receive telemetry data
- [action](https://github.com/dronecore/DroneCore/blob/master/plugins/action/action.h) (plugins/action/action.h): to send commands such as arm, disarm, takeoff, land to drone
- [mission](https://github.com/dronecore/DroneCore/blob/master/plugins/mission/mission.h) (plugins/mission/mission.h)/[mission_item](https://github.com/dronecore/DroneCore/blob/master/plugins/mission/mission_item.h) (plugins/mission/mission_item.h): to upload a waypoint mission
- [offboard](https://github.com/dronecore/DroneCore/blob/master/plugins/offboard/offboard.h)(plugins/offboard/offboard.h): for velocity or position control
- [device_plugin_container.h.in](https://github.com/dronecore/DroneCore/blob/master/include/device_plugin_container.h.in) (include/device_plugin_container.h.in): Auto-generated file that is required for DroneCore plugin development.

