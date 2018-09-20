# dronecode_sdk::Camera::CaptureInfo::EulerAngle Struct Reference
`#include: camera.h`

----


Euler angle type. 


All rotations and axis systems follow the right-hand rule. The Euler angles follow the convention of a 3-2-1 intrinsic Tait-Bryan rotation sequence.


For more info see [https://en.wikipedia.org/wiki/Euler_angles](https://en.wikipedia.org/wiki/Euler_angles) 


## Data Fields


float [roll_deg](#structdronecode__sdk_1_1_camera_1_1_capture_info_1_1_euler_angle_1a6b5bdea1769ed1960f5bee1c540e0043)  - Roll angle in degrees, positive is banking to the right.

float [pitch_deg](#structdronecode__sdk_1_1_camera_1_1_capture_info_1_1_euler_angle_1a980476f4be6a120e82f1ced2f968bdad)  - Pitch angle in degrees, positive is pitching nose up.

float [yaw_deg](#structdronecode__sdk_1_1_camera_1_1_capture_info_1_1_euler_angle_1a9aec4606b313f1217a5fdee3ac6fecfd)  - Yaw angle in degrees, positive is clock-wise seen from above.


## Field Documentation


### roll_deg {#structdronecode__sdk_1_1_camera_1_1_capture_info_1_1_euler_angle_1a6b5bdea1769ed1960f5bee1c540e0043}

```cpp
float dronecode_sdk::Camera::CaptureInfo::EulerAngle::roll_deg
```


Roll angle in degrees, positive is banking to the right.


### pitch_deg {#structdronecode__sdk_1_1_camera_1_1_capture_info_1_1_euler_angle_1a980476f4be6a120e82f1ced2f968bdad}

```cpp
float dronecode_sdk::Camera::CaptureInfo::EulerAngle::pitch_deg
```


Pitch angle in degrees, positive is pitching nose up.


### yaw_deg {#structdronecode__sdk_1_1_camera_1_1_capture_info_1_1_euler_angle_1a9aec4606b313f1217a5fdee3ac6fecfd}

```cpp
float dronecode_sdk::Camera::CaptureInfo::EulerAngle::yaw_deg
```


Yaw angle in degrees, positive is clock-wise seen from above.

