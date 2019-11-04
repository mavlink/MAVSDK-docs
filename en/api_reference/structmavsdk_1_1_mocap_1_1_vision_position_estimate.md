# mavsdk::Mocap::VisionPositionEstimate Struct Reference
`#include: mocap.h`

----


Global position/attitude estimate from a vision source type. 


## Data Fields


uint64_t [time_usec](#structmavsdk_1_1_mocap_1_1_vision_position_estimate_1ada844c4f8f0a9599526ec733b56f0618)  - Position frame timestamp UNIX Epoch time.

[PositionBody](structmavsdk_1_1_mocap_1_1_position_body.md) [position_body](#structmavsdk_1_1_mocap_1_1_vision_position_estimate_1a730623cc79240c166f9b38ff7d621350)  - Global Body Position. (m).

[AngleBody](structmavsdk_1_1_mocap_1_1_angle_body.md) [angle_body](#structmavsdk_1_1_mocap_1_1_vision_position_estimate_1a6b6cafb1452c6c3ce2c85c2f917b9479)  - Body angle (rad).

[Covariance](classmavsdk_1_1_mocap.md#classmavsdk_1_1_mocap_1a558daf6f193660cda5539a042ae91beb) [pose_covariance](#structmavsdk_1_1_mocap_1_1_vision_position_estimate_1abba582506ff4046b4293c06380269c75)  - Row-major representation of pose 6x6 ross-covariance matrix upper right triangle.

uint8_t [reset_counter](#structmavsdk_1_1_mocap_1_1_vision_position_estimate_1a0244ce89bb7d5252a7d77f60023c0f48)  - Estimate reset counter.


## Field Documentation


### time_usec {#structmavsdk_1_1_mocap_1_1_vision_position_estimate_1ada844c4f8f0a9599526ec733b56f0618}

```cpp
uint64_t mavsdk::Mocap::VisionPositionEstimate::time_usec
```


Position frame timestamp UNIX Epoch time.


### position_body {#structmavsdk_1_1_mocap_1_1_vision_position_estimate_1a730623cc79240c166f9b38ff7d621350}

```cpp
PositionBody mavsdk::Mocap::VisionPositionEstimate::position_body
```


Global Body Position. (m).


### angle_body {#structmavsdk_1_1_mocap_1_1_vision_position_estimate_1a6b6cafb1452c6c3ce2c85c2f917b9479}

```cpp
AngleBody mavsdk::Mocap::VisionPositionEstimate::angle_body
```


Body angle (rad).


### pose_covariance {#structmavsdk_1_1_mocap_1_1_vision_position_estimate_1abba582506ff4046b4293c06380269c75}

```cpp
Covariance mavsdk::Mocap::VisionPositionEstimate::pose_covariance
```


Row-major representation of pose 6x6 ross-covariance matrix upper right triangle.


### reset_counter {#structmavsdk_1_1_mocap_1_1_vision_position_estimate_1a0244ce89bb7d5252a7d77f60023c0f48}

```cpp
uint8_t mavsdk::Mocap::VisionPositionEstimate::reset_counter
```


Estimate reset counter.

