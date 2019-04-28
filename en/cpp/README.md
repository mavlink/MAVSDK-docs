<div style="float:right; padding:10px; margin-right:20px;"><a href="https://www.dronecode.org/sdk/"><img src="../../assets/site/sdk_logo_full.jpg" title="Dronecode SDK Logo" width="400px"/></a></div>
# Dronecode SDK C++ Library
[![Slack](https://px4-slack.herokuapp.com/badge.svg)](http://slack.px4.io)&nbsp;[![Discuss](https://img.shields.io/badge/discuss-Dronecode%20SDK-ff69b4.svg)](https://discuss.px4.io/c/sdk) [![jenkins build status](http://ci.px4.io:8080/buildStatus/icon?job=Dronecode/DronecodeSDK/develop)](http://ci.px4.io:8080/blue/organizations/jenkins/Dronecode%2FDronecodeSDK/branches/)
[![travis-ci build status](https://travis-ci.org/Dronecode/DronecodeSDK.svg?branch=develop)](https://travis-ci.org/Dronecode/DronecodeSDK)
[![appveyor build status](https://ci.appveyor.com/api/projects/status/1ntjvooywpxmoir8/branch/develop?svg=true)](https://ci.appveyor.com/project/julianoes/dronecore/branch/develop)
[![Coverage Status](https://coveralls.io/repos/github/Dronecode/DronecodeSDK/badge.svg?branch=develop)](https://coveralls.io/github/Dronecode/DronecodeSDK?branch=develop)

The *Dronecode SDK Core* provides a simple C++ API for managing one or more vehicles via MAVLink.
It enables programmatic access to vehicle information and telemetry, and control over missions, movement and other operations.
The C++ library is very performant, and can be used to enable tasks like computer vision, obstacle avoidance, and route planning.

Developers can extend the SDK, using plugins to add any other required MAVLink API (for example, to integrate PX4 with custom cameras, gimbals, or other hardware over MAVLink).

The core library is used to provide the underlying implementation of the other Dronecode SDK libraries - e.g. [DronecodeSDK-Swift](http://dronecode-sdk-swift.s3.eu-central-1.amazonaws.com/docs/master/index.html).


## Project Status

The Dronecode SDK C++ core is in beta development.


## Getting Started

At time of writing all users will need to [build the library](../contributing/build.md) in order to use it. 
In the near future we'll have binary releases for the wrapper APIs.  

This [Guide](../guide/README.md) explains how to write *Dronecode SDK* apps using C++. 
A simple complete example can be found in [Takeoff and Land](../examples/takeoff_and_land.md).

Developers who want to create plugins and contribute to the API will need to build the C++ library (and other programming language wrappers) from source. 
For more information see the [contributing section](#contributing) below.


## API Overview

[DronecodeSDK](/api_reference/classdronecode__sdk_1_1_dronecode_s_d_k.md) is the main library class. API consumers use [DronecodeSDK](/api_reference/classdronecode__sdk_1_1_dronecode_s_d_k.md) to discover and access vehicles ([System](/api_reference/classdronecode__sdk_1_1_system.md) objects), which in turn provide access to all other drone information and control objects (e.g. [Telemetry](/api_reference/classdronecode__sdk_1_1_telemetry.md), [Mission](/api_reference/classdronecode__sdk_1_1_mission.md) etc.).

The most important classes are:

- [DronecodeSDK](/api_reference/classdronecode__sdk_1_1_dronecode_s_d_k.md): Discover and connect to vehicles ([System](/api_reference/classdronecode__sdk_1_1_system.md)).
- [System](/api_reference/classdronecode__sdk_1_1_system.md): Represents a connected vehicle (e.g. a copter or VTOL drone). It provides access to vehicle information and control through the classes listed below.
- [Info](/api_reference/classdronecode__sdk_1_1_info.md): Basic version information about the hardware and/or software of a system.
- [Telemetry](/api_reference/classdronecode__sdk_1_1_telemetry.md): Get vehicle telemetry and state information ([Battery](/api_reference/structdronecode__sdk_1_1_telemetry_1_1_battery.md), [EulerAngle](/api_reference/structdronecode__sdk_1_1_telemetry_1_1_euler_angle.md), [GPSInfo](/api_reference/structdronecode__sdk_1_1_telemetry_1_1_g_p_s_info.md), [GroundSpeedNED](/api_reference/structdronecode__sdk_1_1_telemetry_1_1_ground_speed_n_e_d.md), [Health](/api_reference/structdronecode__sdk_1_1_telemetry_1_1_health.md), [Position](/api_reference/structdronecode__sdk_1_1_telemetry_1_1_position.md), [Quaternion](/api_reference/structdronecode__sdk_1_1_telemetry_1_1_quaternion.md), [RCStatus](/api_reference/structdronecode__sdk_1_1_telemetry_1_1_r_c_status.md)) and set telemetry update rates.
- [Action](/api_reference/classdronecode__sdk_1_1_action.md): Simple drone actions including arming, taking off, and landing.
- [Mission](/api_reference/classdronecode__sdk_1_1_mission.md): Waypoint mission creation and upload/download. Missions are created from [MissionItem](/api_reference/classdronecode__sdk_1_1_mission_item.md) objects.
- [Offboard](/api_reference/classdronecode__sdk_1_1_offboard.md): Control a drone with velocity commands.
- [Gimbal](/api_reference/classdronecode__sdk_1_1_gimbal.md): Control a gimbal.
- [Camera](/api_reference/classdronecode__sdk_1_1_camera.md): Control a camera.
- [FollowMe](/api_reference/classdronecode__sdk_1_1_follow_me.md): Drone tracks a position supplied by the SDK.
- [Calibration](/api_reference/classdronecode__sdk_1_1_calibration.md):  Calibrate sensors (e.g.: gyro, accelerometer, and magnetometer).
- [LogFiles](/api_reference/classdronecode__sdk_1_1_log_files.md): Download log files from the vehicle.


The following APIs provide more direct access to underlying MAVLink messages/types.
They should only be used where features are missing from the main APIs above.
* [Param](/api_reference/classdronecode__sdk_1_1_param.md): Raw access to get and set parameters.
* [MissionRaw](/api_reference/classdronecode__sdk_1_1_mission_raw.md): Direct access to MAVLink mission items.
* [MavlinkPassthrough](/api_reference/classdronecode__sdk_1_1_mavlink_passthrough.md): Provides full/direct MAVLink access


## Contributing/Extending

The [Contributing](../contributing/README.md) section contains everything you need to contribute to the C++ API, including topics about building the SDK from source code, running our integration and unit tests, and all other aspects of core development. 

