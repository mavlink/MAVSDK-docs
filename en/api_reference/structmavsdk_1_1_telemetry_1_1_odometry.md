# mavsdk::Telemetry::Odometry Struct Reference
`#include: telemetry.h`

----


[Odometry](structmavsdk_1_1_telemetry_1_1_odometry.md) information with an external interface type. 


## Public Types


Type | Description
--- | ---
enum [MavFrame](#structmavsdk_1_1_telemetry_1_1_odometry_1ae14a60c5ce30809d8de3aafc73e6fa59) | Mavlink frame id [Odometry](structmavsdk_1_1_telemetry_1_1_odometry.md) subset.

## Data Fields


uint64_t [time_usec](#structmavsdk_1_1_telemetry_1_1_odometry_1aa58eb5c15f53acf35333115c8d3673f9) {} - Timestamp (0 to use Backend timestamp).

[MavFrame](structmavsdk_1_1_telemetry_1_1_odometry.md#structmavsdk_1_1_telemetry_1_1_odometry_1ae14a60c5ce30809d8de3aafc73e6fa59) [frame_id](#structmavsdk_1_1_telemetry_1_1_odometry_1a40cde4148b2b495fc5b1d8606978355a) {} - Coordinate frame of reference for the pose data.

[MavFrame](structmavsdk_1_1_telemetry_1_1_odometry.md#structmavsdk_1_1_telemetry_1_1_odometry_1ae14a60c5ce30809d8de3aafc73e6fa59) [child_frame_id](#structmavsdk_1_1_telemetry_1_1_odometry_1a624b96ff786cb7d3498ceb64c10323c7) {} - Coordinate frame of reference for the velocity in free space (twist) data.

[PositionBody](structmavsdk_1_1_telemetry_1_1_position_body.md) [position_body](#structmavsdk_1_1_telemetry_1_1_odometry_1a836f0338481b24874e4dcf7a82bc391b) {} - [Position](structmavsdk_1_1_telemetry_1_1_position.md).

[Quaternion](structmavsdk_1_1_telemetry_1_1_quaternion.md) [q](#structmavsdk_1_1_telemetry_1_1_odometry_1a32f49ead9d8964da05af2b92fd6e2127) {} - [Quaternion](structmavsdk_1_1_telemetry_1_1_quaternion.md) components, w, x, y, z (1 0 0 0 is the null-rotation).

[SpeedBody](structmavsdk_1_1_telemetry_1_1_speed_body.md) [velocity_body](#structmavsdk_1_1_telemetry_1_1_odometry_1a6135a0b5fec73ef3932412e3cc19ed37) {} - Linear speed (m/s).

[AngularVelocityBody](structmavsdk_1_1_telemetry_1_1_angular_velocity_body.md) [angular_velocity_body](#structmavsdk_1_1_telemetry_1_1_odometry_1a023deb0e97bc06d5ea19c5dfc42e230a) {} - Angular body speed (rad/s).

std::array< float, 21 > [pose_covariance](#structmavsdk_1_1_telemetry_1_1_odometry_1a8f84d053274d7126919a0ec5321c312e) {} - Row-major representation of a 6x6 pose cross-covariance matrix upper right triangle. NaN if unknown.

std::array< float, 21 > [velocity_covariance](#structmavsdk_1_1_telemetry_1_1_odometry_1a8e804bf156d462a6dbee741f842d8c90) {} - Row-major representation of a 6x6 velocity cross-covariance matrix upper right triangle. NaN if unknown.

uint8_t [reset_counter](#structmavsdk_1_1_telemetry_1_1_odometry_1abd2bf01d1162ff0942010c8331fa08f9) {} - Estimate reset counter.


## Member Enumeration Documentation


### enum MavFrame {#structmavsdk_1_1_telemetry_1_1_odometry_1ae14a60c5ce30809d8de3aafc73e6fa59}


Mavlink frame id [Odometry](structmavsdk_1_1_telemetry_1_1_odometry.md) subset.


Value | Description
--- | ---
<span id="structmavsdk_1_1_telemetry_1_1_odometry_1ae14a60c5ce30809d8de3aafc73e6fa59ab3f7791472924b0d1530bb9112409c01"></span> `UNDEF` | Stub. 
<span id="structmavsdk_1_1_telemetry_1_1_odometry_1ae14a60c5ce30809d8de3aafc73e6fa59a820d86957feaf94bf2881975208fe64c"></span> `BODY_NED` | Setpoint in body NED frame. This makes sense if all position control is externalized - e.g. useful to command 2 m/s^2 acceleration to the right. 
<span id="structmavsdk_1_1_telemetry_1_1_odometry_1ae14a60c5ce30809d8de3aafc73e6fa59ab03e20895c23a1b01a358b5e07dd0974"></span> `VISION_NED` | [Odometry](structmavsdk_1_1_telemetry_1_1_odometry.md) local coordinate frame of data given by a vision estimation system, Z-down (x: north, y: east, z: down). 
<span id="structmavsdk_1_1_telemetry_1_1_odometry_1ae14a60c5ce30809d8de3aafc73e6fa59a5e60852e210299ef44c6638ffefc6ee4"></span> `ESTIM_NED` | [Odometry](structmavsdk_1_1_telemetry_1_1_odometry.md) local coordinate frame of data given by an estimator running onboard the vehicle, Z-down (x: north, y: east, z: down). 

## Field Documentation


### time_usec {#structmavsdk_1_1_telemetry_1_1_odometry_1aa58eb5c15f53acf35333115c8d3673f9}

```cpp
uint64_t mavsdk::Telemetry::Odometry::time_usec {}
```


Timestamp (0 to use Backend timestamp).


### frame_id {#structmavsdk_1_1_telemetry_1_1_odometry_1a40cde4148b2b495fc5b1d8606978355a}

```cpp
MavFrame mavsdk::Telemetry::Odometry::frame_id {}
```


Coordinate frame of reference for the pose data.


### child_frame_id {#structmavsdk_1_1_telemetry_1_1_odometry_1a624b96ff786cb7d3498ceb64c10323c7}

```cpp
MavFrame mavsdk::Telemetry::Odometry::child_frame_id {}
```


Coordinate frame of reference for the velocity in free space (twist) data.


### position_body {#structmavsdk_1_1_telemetry_1_1_odometry_1a836f0338481b24874e4dcf7a82bc391b}

```cpp
PositionBody mavsdk::Telemetry::Odometry::position_body {}
```


[Position](structmavsdk_1_1_telemetry_1_1_position.md).


### q {#structmavsdk_1_1_telemetry_1_1_odometry_1a32f49ead9d8964da05af2b92fd6e2127}

```cpp
Quaternion mavsdk::Telemetry::Odometry::q {}
```


[Quaternion](structmavsdk_1_1_telemetry_1_1_quaternion.md) components, w, x, y, z (1 0 0 0 is the null-rotation).


### velocity_body {#structmavsdk_1_1_telemetry_1_1_odometry_1a6135a0b5fec73ef3932412e3cc19ed37}

```cpp
SpeedBody mavsdk::Telemetry::Odometry::velocity_body {}
```


Linear speed (m/s).


### angular_velocity_body {#structmavsdk_1_1_telemetry_1_1_odometry_1a023deb0e97bc06d5ea19c5dfc42e230a}

```cpp
AngularVelocityBody mavsdk::Telemetry::Odometry::angular_velocity_body {}
```


Angular body speed (rad/s).


### pose_covariance {#structmavsdk_1_1_telemetry_1_1_odometry_1a8f84d053274d7126919a0ec5321c312e}

```cpp
std::array<float, 21> mavsdk::Telemetry::Odometry::pose_covariance {}
```


Row-major representation of a 6x6 pose cross-covariance matrix upper right triangle. NaN if unknown.


### velocity_covariance {#structmavsdk_1_1_telemetry_1_1_odometry_1a8e804bf156d462a6dbee741f842d8c90}

```cpp
std::array<float, 21> mavsdk::Telemetry::Odometry::velocity_covariance {}
```


Row-major representation of a 6x6 velocity cross-covariance matrix upper right triangle. NaN if unknown.


### reset_counter {#structmavsdk_1_1_telemetry_1_1_odometry_1abd2bf01d1162ff0942010c8331fa08f9}

```cpp
uint8_t mavsdk::Telemetry::Odometry::reset_counter {}
```


Estimate reset counter.

