<div style="float:right; padding:4px;"><img src="../../assets/site/dronecore_logo_full.png" title="DroneCore Logo" width="400px"/></div>
# Getting Started

This topic explains how to set up a development environment and write a minimal example for all our supported programming languages/platforms.

> **Note** At time of writing all users will need to [build the library](../contributing/build.md) in order to use it. In the near future we'll have binary releases for the wrapper APIs.  Instructions for how to write a simple complete example are covered in [Takeoff and Land](../examples/takeoff_and_land.md). The text below is "aspirational".

## API Overview

API consumers use [DroneCore](../api_reference/classdronecore_1_1_drone_core.md) to discover and manage vehicles ([Device](../api_reference/classdronecore_1_1_device.md) objects), which in turn provide access to all other drone information and control objects (e.g. [Telemetry](../api_reference/classdronecore_1_1_telemetry.md), [Mission](../api_reference/classdronecore_1_1_mission.md) etc.).

> **Tip** [DroneCore](../api_reference/classdronecore_1_1_drone_core.md) is the main library class. API consumers only directly create and destroy a `DroneCore` object. All other objects are returned/owned by the API.

The main classes are described below:

- [DroneCore](../api_reference/classdronecore_1_1_drone_core.md): Discover and connect to vehicles ([Device](../api_reference/classdronecore_1_1_device.md)).
- [Device](../api_reference/classdronecore_1_1_device.md): Represents a connected vehicle (e.g. a copter or VTOL drone). It provides access to vehicle information and control through the classes listed below.
- [Info](../api_reference/classdronecore_1_1_info.md): Basic version information about the hardware and/or software of a device.
- [Telemetry](../api_reference/classdronecore_1_1_telemetry.md): Get vehicle telemetry and state information ([Battery](../api_reference/structdronecore_1_1_telemetry_1_1_battery.md), [EulerAngle](../api_reference/structdronecore_1_1_telemetry_1_1_euler_angle.md), [GPSInfo](../api_reference/structdronecore_1_1_telemetry_1_1_g_p_s_info.md), [GroundSpeedNED](../api_reference/structdronecore_1_1_telemetry_1_1_ground_speed_n_e_d.md), [Health](../api_reference/structdronecore_1_1_telemetry_1_1_health.md), [Position](../api_reference/structdronecore_1_1_telemetry_1_1_position.md), [Quaternion](../api_reference/structdronecore_1_1_telemetry_1_1_quaternion.md), [RCStatus](../api_reference/structdronecore_1_1_telemetry_1_1_r_c_status.md)) and set telemetry update rates.
- [Action](../api_reference/classdronecore_1_1_action.md): Simple drone actions including arming, taking off, and landing.
- [Mission](../api_reference/classdronecore_1_1_mission.md): Waypoint mission creation and upload/download. Missions are created from [MissionItem](../api_reference/classdronecore_1_1_mission_item.md) objects.
- [Offboard](../api_reference/classdronecore_1_1_offboard.md): Control a drone with velocity commands.
- [Logging](../api_reference/classdronecore_1_1_logging.md): Data logging and streaming from the vehicle.
- [include/device_plugin_container.h.in](https://github.com/dronecore/DroneCore/blob/master/include/device_plugin_container.h.in): Auto-generated file that is required for DroneCore plugin development - see [DevicePluginContainer](../api_reference/classdronecore_1_1_device_plugin_container.md).

Other public API types may be found in the sidebar of the [API Reference](../api_reference/README.md).