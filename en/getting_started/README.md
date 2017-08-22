# Getting Started

## API overview

<!-- all these links should go to API ref, once created -->

- [dronecore](https://github.com/dronecore/DroneCore/blob/master/include/dronecore.h) (include/dronecore.h): set up connection, discover devices
- [device](https://github.com/dronecore/DroneCore/blob/master/include/device.h) (include/device.h): a device providing access to modules below using ...
- [device_plugin_container.h.in](https://github.com/dronecore/DroneCore/blob/master/include/device_plugin_container.h.in) (include/device_plugin_container.h.in) which is auto-generated on build.

- [info](https://github.com/dronecore/DroneCore/blob/master/plugins/info/info.h) (plugins/info/info.h): general info about a device
- [telemetry](https://github.com/dronecore/DroneCore/blob/master/plugins/telemetry/telemetry.h) (plugins/telemetry/telemetry.h): to receive telemetry data
- [action](https://github.com/dronecore/DroneCore/blob/master/plugins/action/action.h) (plugins/action/action.h): to send commands such as arm, disarm, takeoff, land to drone
- [mission](https://github.com/dronecore/DroneCore/blob/master/plugins/mission/mission.h) (plugins/mission/mission.h)/[mission_item](https://github.com/dronecore/DroneCore/blob/master/plugins/mission/mission_item.h) (plugins/mission/mission_item.h): to upload a waypoint mission
- [offboard](https://github.com/dronecore/DroneCore/blob/master/plugins/offboard/offboard.h)(plugins/offboard/offboard.h): for velocity or position control

