# mavsdk::Mocap::Odometry Struct Reference
`#include: mocap.h`

----


[Odometry](structmavsdk_1_1_mocap_1_1_odometry.md) information with an external interface type. 


## Public Types


Type | Description
--- | ---
enum [MavFrame](#structmavsdk_1_1_mocap_1_1_odometry_1a9c98852de68b23f07a78a0fc021c8a33) | Mavlink frame id.

## Data Fields


uint64_t [time_usec](#structmavsdk_1_1_mocap_1_1_odometry_1a015fd5755c9953ab7d7be4736fad5300) {} - Timestamp (0 to use Backend timestamp).

[MavFrame](structmavsdk_1_1_mocap_1_1_odometry.md#structmavsdk_1_1_mocap_1_1_odometry_1a9c98852de68b23f07a78a0fc021c8a33) [frame_id](#structmavsdk_1_1_mocap_1_1_odometry_1ab7ce4f3ea27857eb44d2efe7a010e3d3) {} - Coordinate frame of reference for the pose data.

[PositionBody](structmavsdk_1_1_mocap_1_1_position_body.md) [position_body](#structmavsdk_1_1_mocap_1_1_odometry_1af7b586261930981742683b3253fc9989) {} - Body position.

[Quaternion](structmavsdk_1_1_mocap_1_1_quaternion.md) [q](#structmavsdk_1_1_mocap_1_1_odometry_1ae5a8c05815a15250f2cf37e1d5a21be5) {} - [Quaternion](structmavsdk_1_1_mocap_1_1_quaternion.md) components, w, x, y, z (1 0 0 0 is the null-rotation).

[SpeedBody](structmavsdk_1_1_mocap_1_1_speed_body.md) [speed_body](#structmavsdk_1_1_mocap_1_1_odometry_1a123c544d4ea98bf91d0740321aa6bb00) {} - Body linear speed (m/s).

[AngularVelocityBody](structmavsdk_1_1_mocap_1_1_angular_velocity_body.md) [angular_velocity_body](#structmavsdk_1_1_mocap_1_1_odometry_1acf8cf54ebe80fb872250aa0e91b7e721) {} - Body angular speed (rad/s).

[Covariance](classmavsdk_1_1_mocap.md#classmavsdk_1_1_mocap_1a558daf6f193660cda5539a042ae91beb) [pose_covariance](#structmavsdk_1_1_mocap_1_1_odometry_1a38673fa707dfbbd8c195bb743d55d1b7) {} - Row-major representation of a 6x6 pose cross-covariance matrix upper right triangle. Set first to NaN if unknown.

[Covariance](classmavsdk_1_1_mocap.md#classmavsdk_1_1_mocap_1a558daf6f193660cda5539a042ae91beb) [velocity_covariance](#structmavsdk_1_1_mocap_1_1_odometry_1a76cc8691a7aa85e2351b99f1c6b0c126) {} - Row-major representation of a 6x6 velocity cross-covariance matrix upper right triangle. Set first to NaN if unknown.


## Member Enumeration Documentation


### enum MavFrame {#structmavsdk_1_1_mocap_1_1_odometry_1a9c98852de68b23f07a78a0fc021c8a33}


Mavlink frame id.


Value | Description
--- | ---
<span id="structmavsdk_1_1_mocap_1_1_odometry_1a9c98852de68b23f07a78a0fc021c8a33a696b031073e74bf2cb98e5ef201d4aa3"></span> `UNKNOWN` | Unknown frame. 
<span id="structmavsdk_1_1_mocap_1_1_odometry_1a9c98852de68b23f07a78a0fc021c8a33a6832248396c3e9b8de3dc25b7c9d172a"></span> `MOCAP_NED` | [Odometry](structmavsdk_1_1_mocap_1_1_odometry.md) local coordinate frame of data given by a motion capture system, Z-down (x: north, y: east, z: down). 
<span id="structmavsdk_1_1_mocap_1_1_odometry_1a9c98852de68b23f07a78a0fc021c8a33a74c6ebd7d32e25be2113b3447aeb524a"></span> `LOCAL_FRD` | Forward, Right, Down coordinate frame. This is a local frame with Z-down and arbitrary F/R alignment (i.e. not aligned with NED/earth frame). Replacement for MAV_FRAME_MOCAP_NED, MAV_FRAME_VISION_NED, MAV_FRAME_ESTIM_NED. 

## Field Documentation


### time_usec {#structmavsdk_1_1_mocap_1_1_odometry_1a015fd5755c9953ab7d7be4736fad5300}

```cpp
uint64_t mavsdk::Mocap::Odometry::time_usec {}
```


Timestamp (0 to use Backend timestamp).


### frame_id {#structmavsdk_1_1_mocap_1_1_odometry_1ab7ce4f3ea27857eb44d2efe7a010e3d3}

```cpp
MavFrame mavsdk::Mocap::Odometry::frame_id {}
```


Coordinate frame of reference for the pose data.


### position_body {#structmavsdk_1_1_mocap_1_1_odometry_1af7b586261930981742683b3253fc9989}

```cpp
PositionBody mavsdk::Mocap::Odometry::position_body {}
```


Body position.


### q {#structmavsdk_1_1_mocap_1_1_odometry_1ae5a8c05815a15250f2cf37e1d5a21be5}

```cpp
Quaternion mavsdk::Mocap::Odometry::q {}
```


[Quaternion](structmavsdk_1_1_mocap_1_1_quaternion.md) components, w, x, y, z (1 0 0 0 is the null-rotation).


### speed_body {#structmavsdk_1_1_mocap_1_1_odometry_1a123c544d4ea98bf91d0740321aa6bb00}

```cpp
SpeedBody mavsdk::Mocap::Odometry::speed_body {}
```


Body linear speed (m/s).


### angular_velocity_body {#structmavsdk_1_1_mocap_1_1_odometry_1acf8cf54ebe80fb872250aa0e91b7e721}

```cpp
AngularVelocityBody mavsdk::Mocap::Odometry::angular_velocity_body {}
```


Body angular speed (rad/s).


### pose_covariance {#structmavsdk_1_1_mocap_1_1_odometry_1a38673fa707dfbbd8c195bb743d55d1b7}

```cpp
Covariance mavsdk::Mocap::Odometry::pose_covariance {}
```


Row-major representation of a 6x6 pose cross-covariance matrix upper right triangle. Set first to NaN if unknown.


### velocity_covariance {#structmavsdk_1_1_mocap_1_1_odometry_1a76cc8691a7aa85e2351b99f1c6b0c126}

```cpp
Covariance mavsdk::Mocap::Odometry::velocity_covariance {}
```


Row-major representation of a 6x6 velocity cross-covariance matrix upper right triangle. Set first to NaN if unknown.

