# dronecore::Camera::CaptureInfo Struct Reference
`#include: camera.h`

----


Information about a picture just captured. 


## Data Structures


struct [Position](structdronecore_1_1_camera_1_1_capture_info_1_1_position.md)

struct [Quaternion](structdronecore_1_1_camera_1_1_capture_info_1_1_quaternion.md)

## Data Fields


struct [dronecore::Camera::CaptureInfo::Position](structdronecore_1_1_camera_1_1_capture_info_1_1_position.md) [position](#structdronecore_1_1_camera_1_1_capture_info_1a2de03d19a826d25f7b36e8e88a33fb64)  - [Position](structdronecore_1_1_camera_1_1_capture_info_1_1_position.md) of drone/camera when image was captured.

struct [dronecore::Camera::CaptureInfo::Quaternion](structdronecore_1_1_camera_1_1_capture_info_1_1_quaternion.md) [quaternion](#structdronecore_1_1_camera_1_1_capture_info_1a514c6b516f66a0de2b8339fb7d81d08a)  - [Quaternion](structdronecore_1_1_camera_1_1_capture_info_1_1_quaternion.md) of camera orientation.

uint64_t [time_utc_us](#structdronecore_1_1_camera_1_1_capture_info_1a4ef2a3863cb66423e2953656cc5607ec)  - Timestamp in UTC (since UNIX epoch) in microseconds.

bool [success](#structdronecore_1_1_camera_1_1_capture_info_1a12c7d8c172ce9a8093290ae064568a1d)  - True if capture was successful.

int [index](#structdronecore_1_1_camera_1_1_capture_info_1a23a32ef479c588c3b6626352ffca2778)  - Zero-based index of this image since armed.

std::string [file_url](#structdronecore_1_1_camera_1_1_capture_info_1a18b008a34e2e5cd1667c043a246bb509)  -


## Field Documentation


### position {#structdronecore_1_1_camera_1_1_capture_info_1a2de03d19a826d25f7b36e8e88a33fb64}

```cpp
struct dronecore::Camera::CaptureInfo::Position  dronecore::Camera::CaptureInfo::position
```


[Position](structdronecore_1_1_camera_1_1_capture_info_1_1_position.md) of drone/camera when image was captured.


### quaternion {#structdronecore_1_1_camera_1_1_capture_info_1a514c6b516f66a0de2b8339fb7d81d08a}

```cpp
struct dronecore::Camera::CaptureInfo::Quaternion  dronecore::Camera::CaptureInfo::quaternion
```


[Quaternion](structdronecore_1_1_camera_1_1_capture_info_1_1_quaternion.md) of camera orientation.


### time_utc_us {#structdronecore_1_1_camera_1_1_capture_info_1a4ef2a3863cb66423e2953656cc5607ec}

```cpp
uint64_t dronecore::Camera::CaptureInfo::time_utc_us
```


Timestamp in UTC (since UNIX epoch) in microseconds.


### success {#structdronecore_1_1_camera_1_1_capture_info_1a12c7d8c172ce9a8093290ae064568a1d}

```cpp
bool dronecore::Camera::CaptureInfo::success
```


True if capture was successful.


### index {#structdronecore_1_1_camera_1_1_capture_info_1a23a32ef479c588c3b6626352ffca2778}

```cpp
int dronecore::Camera::CaptureInfo::index
```


Zero-based index of this image since armed.


### file_url {#structdronecore_1_1_camera_1_1_capture_info_1a18b008a34e2e5cd1667c043a246bb509}

```cpp
std::string dronecore::Camera::CaptureInfo::file_url
```


Download URL for captured image.