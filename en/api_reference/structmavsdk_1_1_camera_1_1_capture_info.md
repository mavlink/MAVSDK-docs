# mavsdk::Camera::CaptureInfo Struct Reference
`#include: camera.h`

----


[Information](structmavsdk_1_1_camera_1_1_information.md) about a picture just captured. 


## Data Structures


struct [EulerAngle](structmavsdk_1_1_camera_1_1_capture_info_1_1_euler_angle.md)

struct [Position](structmavsdk_1_1_camera_1_1_capture_info_1_1_position.md)

struct [Quaternion](structmavsdk_1_1_camera_1_1_capture_info_1_1_quaternion.md)

## Data Fields


struct [mavsdk::Camera::CaptureInfo::Position](structmavsdk_1_1_camera_1_1_capture_info_1_1_position.md) [position](#structmavsdk_1_1_camera_1_1_capture_info_1a3c28426c7f0eb1e2c58315ba9132fab3)  - [Position](structmavsdk_1_1_camera_1_1_capture_info_1_1_position.md) of drone/camera when image was captured.

struct [mavsdk::Camera::CaptureInfo::Quaternion](structmavsdk_1_1_camera_1_1_capture_info_1_1_quaternion.md) [attitude_quaternion](#structmavsdk_1_1_camera_1_1_capture_info_1abd17031cfe9f3b15d2e1515a2a7a79fb)  - [Quaternion](structmavsdk_1_1_camera_1_1_capture_info_1_1_quaternion.md) of camera orientation.

struct [mavsdk::Camera::CaptureInfo::EulerAngle](structmavsdk_1_1_camera_1_1_capture_info_1_1_euler_angle.md) [attitude_euler_angle](#structmavsdk_1_1_camera_1_1_capture_info_1a0257fe9e0d710ad2c11792e8831c449e)  - Euler Angle of camera orientation.

uint64_t [time_utc_us](#structmavsdk_1_1_camera_1_1_capture_info_1ad0e92389ab305025ce3cebe0e35d0b51)  - Timestamp in UTC (since UNIX epoch) in microseconds.

bool [success](#structmavsdk_1_1_camera_1_1_capture_info_1a4b9f88c11dff71f87f6ffde36dcc41ee)  - True if capture was successful.

int [index](#structmavsdk_1_1_camera_1_1_capture_info_1ab061b474df1efc98e641798453c6be56)  - Zero-based index of this image since armed.

std::string [file_url](#structmavsdk_1_1_camera_1_1_capture_info_1a6fa362c6a13fe4fafe40d8cb5043407f)  -


## Field Documentation


### position {#structmavsdk_1_1_camera_1_1_capture_info_1a3c28426c7f0eb1e2c58315ba9132fab3}

```cpp
struct mavsdk::Camera::CaptureInfo::Position  mavsdk::Camera::CaptureInfo::position
```


[Position](structmavsdk_1_1_camera_1_1_capture_info_1_1_position.md) of drone/camera when image was captured.


### attitude_quaternion {#structmavsdk_1_1_camera_1_1_capture_info_1abd17031cfe9f3b15d2e1515a2a7a79fb}

```cpp
struct mavsdk::Camera::CaptureInfo::Quaternion  mavsdk::Camera::CaptureInfo::attitude_quaternion
```


[Quaternion](structmavsdk_1_1_camera_1_1_capture_info_1_1_quaternion.md) of camera orientation.


### attitude_euler_angle {#structmavsdk_1_1_camera_1_1_capture_info_1a0257fe9e0d710ad2c11792e8831c449e}

```cpp
struct mavsdk::Camera::CaptureInfo::EulerAngle  mavsdk::Camera::CaptureInfo::attitude_euler_angle
```


Euler Angle of camera orientation.


### time_utc_us {#structmavsdk_1_1_camera_1_1_capture_info_1ad0e92389ab305025ce3cebe0e35d0b51}

```cpp
uint64_t mavsdk::Camera::CaptureInfo::time_utc_us
```


Timestamp in UTC (since UNIX epoch) in microseconds.


### success {#structmavsdk_1_1_camera_1_1_capture_info_1a4b9f88c11dff71f87f6ffde36dcc41ee}

```cpp
bool mavsdk::Camera::CaptureInfo::success
```


True if capture was successful.


### index {#structmavsdk_1_1_camera_1_1_capture_info_1ab061b474df1efc98e641798453c6be56}

```cpp
int mavsdk::Camera::CaptureInfo::index
```


Zero-based index of this image since armed.


### file_url {#structmavsdk_1_1_camera_1_1_capture_info_1a6fa362c6a13fe4fafe40d8cb5043407f}

```cpp
std::string mavsdk::Camera::CaptureInfo::file_url
```


Download URL for captured image.