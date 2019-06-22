# mavsdk::Camera::CaptureInfo::EulerAngle Struct Reference
`#include: camera.h`

----


Euler angle type. 


All rotations and axis systems follow the right-hand rule. The Euler angles follow the convention of a 3-2-1 intrinsic Tait-Bryan rotation sequence.


For more info see [https://en.wikipedia.org/wiki/Euler_angles](https://en.wikipedia.org/wiki/Euler_angles) 


## Data Fields


float [roll_deg](#structmavsdk_1_1_camera_1_1_capture_info_1_1_euler_angle_1a410ec72a64c0cb9e5b02e44b1eb0e2cc)  - Roll angle in degrees, positive is banking to the right.

float [pitch_deg](#structmavsdk_1_1_camera_1_1_capture_info_1_1_euler_angle_1a70f251f9ee5bfe4057a3c928f6c2881d)  - Pitch angle in degrees, positive is pitching nose up.

float [yaw_deg](#structmavsdk_1_1_camera_1_1_capture_info_1_1_euler_angle_1af6e5e5856948f3c7a0a2de8a8f2e8bb4)  - Yaw angle in degrees, positive is clock-wise seen from above.


## Field Documentation


### roll_deg {#structmavsdk_1_1_camera_1_1_capture_info_1_1_euler_angle_1a410ec72a64c0cb9e5b02e44b1eb0e2cc}

```cpp
float mavsdk::Camera::CaptureInfo::EulerAngle::roll_deg
```


Roll angle in degrees, positive is banking to the right.


### pitch_deg {#structmavsdk_1_1_camera_1_1_capture_info_1_1_euler_angle_1a70f251f9ee5bfe4057a3c928f6c2881d}

```cpp
float mavsdk::Camera::CaptureInfo::EulerAngle::pitch_deg
```


Pitch angle in degrees, positive is pitching nose up.


### yaw_deg {#structmavsdk_1_1_camera_1_1_capture_info_1_1_euler_angle_1af6e5e5856948f3c7a0a2de8a8f2e8bb4}

```cpp
float mavsdk::Camera::CaptureInfo::EulerAngle::yaw_deg
```


Yaw angle in degrees, positive is clock-wise seen from above.

