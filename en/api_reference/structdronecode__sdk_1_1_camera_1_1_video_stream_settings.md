# dronecode_sdk::Camera::VideoStreamSettings Struct Reference
`#include: camera.h`

----


Type for video stream settings. 


Application may call [set_video_stream_settings()](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1a3fb0697f85f6b5c92dff59d7c8bc24ad) before starting video streaming to tell [Camera](classdronecode__sdk_1_1_camera.md) server to use these settings during video streaming.


**See Also:**
- [set_video_stream_settings()](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1a3fb0697f85f6b5c92dff59d7c8bc24ad), [get_video_stream_info()](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1a8a617875ae274b4137ef05e12308ee1f), [start_video_streaming()](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1a62d02486c4a7de09a41384bb5a9c6a23).


## Public Member Functions


Type | Name | Description
---: | --- | ---
void | [set_highest](#structdronecode__sdk_1_1_camera_1_1_video_stream_settings_1a02dd86a754df7d151bec931c9e1927e8) () | Sets to highest possible settings for Resolution, framerate.

## Data Fields


float [frame_rate_hz](#structdronecode__sdk_1_1_camera_1_1_video_stream_settings_1ae4313cf505d9361584e3a7e9b5b80592) = 0.f - Frames per second.

uint16_t [horizontal_resolution_pix](#structdronecode__sdk_1_1_camera_1_1_video_stream_settings_1acda055d74bab1c704147dff88043ff9d) = 0u - Horizontal resolution in pixels.

uint16_t [vertical_resolution_pix](#structdronecode__sdk_1_1_camera_1_1_video_stream_settings_1a45a2a8b0a4e5d059658dcfe69dacc4b7) = 0u - Vertical resolution in pixels.

uint32_t [bit_rate_b_s](#structdronecode__sdk_1_1_camera_1_1_video_stream_settings_1a7378549cc0e4619afbb2b01893d41398) = 0u - Bit rate in bits per second.

uint16_t [rotation_deg](#structdronecode__sdk_1_1_camera_1_1_video_stream_settings_1a97e5405aad9da526afe3bb8cd24edbcf) = 0u - Video image rotation clockwise (0-359 degrees).

std::string [uri](#structdronecode__sdk_1_1_camera_1_1_video_stream_settings_1af93748918c5c506766da0c887351c942) {} - Video stream URI.

## Static Public Attributes


static constexpr const float [FRAME_RATE_HIGHEST](#structdronecode__sdk_1_1_camera_1_1_video_stream_settings_1a9a4b17f4d3beb8f1e30c1d2d2d4b7f9d) = -1.0f - Highest possible framerate.


static constexpr const uint16_t [RESOLUTION_H_HIGHEST](#structdronecode__sdk_1_1_camera_1_1_video_stream_settings_1a9d82f10ba5634804a98b19ec9b3e2f8b) = UINT16_MAX - Highest possible horizontal resolution.


static constexpr const uint16_t [RESOLUTION_V_HIGHEST](#structdronecode__sdk_1_1_camera_1_1_video_stream_settings_1a9a26a88bcd052ec35d5943e285238663) = UINT16_MAX - Highest possible vertical resolution.


static constexpr const uint32_t [BIT_RATE_AUTO](#structdronecode__sdk_1_1_camera_1_1_video_stream_settings_1af7682cc33ee5becff23971d64ee4a2ae) = 0 - Auto settings for Bit rate.


## Member Function Documentation


### set_highest() {#structdronecode__sdk_1_1_camera_1_1_video_stream_settings_1a02dd86a754df7d151bec931c9e1927e8}
```cpp
void dronecode_sdk::Camera::VideoStreamSettings::set_highest()
```


Sets to highest possible settings for Resolution, framerate.


## Field Documentation


### FRAME_RATE_HIGHEST {#structdronecode__sdk_1_1_camera_1_1_video_stream_settings_1a9a4b17f4d3beb8f1e30c1d2d2d4b7f9d}

```cpp
constexpr const float dronecode_sdk::Camera::VideoStreamSettings::FRAME_RATE_HIGHEST = -1.0f
```


Highest possible framerate.


### RESOLUTION_H_HIGHEST {#structdronecode__sdk_1_1_camera_1_1_video_stream_settings_1a9d82f10ba5634804a98b19ec9b3e2f8b}

```cpp
constexpr const uint16_t dronecode_sdk::Camera::VideoStreamSettings::RESOLUTION_H_HIGHEST = UINT16_MAX
```


Highest possible horizontal resolution.


### RESOLUTION_V_HIGHEST {#structdronecode__sdk_1_1_camera_1_1_video_stream_settings_1a9a26a88bcd052ec35d5943e285238663}

```cpp
constexpr const uint16_t dronecode_sdk::Camera::VideoStreamSettings::RESOLUTION_V_HIGHEST = UINT16_MAX
```


Highest possible vertical resolution.


### BIT_RATE_AUTO {#structdronecode__sdk_1_1_camera_1_1_video_stream_settings_1af7682cc33ee5becff23971d64ee4a2ae}

```cpp
constexpr const uint32_t dronecode_sdk::Camera::VideoStreamSettings::BIT_RATE_AUTO = 0
```


Auto settings for Bit rate.


### frame_rate_hz {#structdronecode__sdk_1_1_camera_1_1_video_stream_settings_1ae4313cf505d9361584e3a7e9b5b80592}

```cpp
float dronecode_sdk::Camera::VideoStreamSettings::frame_rate_hz = 0.f
```


Frames per second.


### horizontal_resolution_pix {#structdronecode__sdk_1_1_camera_1_1_video_stream_settings_1acda055d74bab1c704147dff88043ff9d}

```cpp
uint16_t dronecode_sdk::Camera::VideoStreamSettings::horizontal_resolution_pix = 0u
```


Horizontal resolution in pixels.


### vertical_resolution_pix {#structdronecode__sdk_1_1_camera_1_1_video_stream_settings_1a45a2a8b0a4e5d059658dcfe69dacc4b7}

```cpp
uint16_t dronecode_sdk::Camera::VideoStreamSettings::vertical_resolution_pix = 0u
```


Vertical resolution in pixels.


### bit_rate_b_s {#structdronecode__sdk_1_1_camera_1_1_video_stream_settings_1a7378549cc0e4619afbb2b01893d41398}

```cpp
uint32_t dronecode_sdk::Camera::VideoStreamSettings::bit_rate_b_s = 0u
```


Bit rate in bits per second.


### rotation_deg {#structdronecode__sdk_1_1_camera_1_1_video_stream_settings_1a97e5405aad9da526afe3bb8cd24edbcf}

```cpp
uint16_t dronecode_sdk::Camera::VideoStreamSettings::rotation_deg = 0u
```


Video image rotation clockwise (0-359 degrees).


### uri {#structdronecode__sdk_1_1_camera_1_1_video_stream_settings_1af93748918c5c506766da0c887351c942}

```cpp
std::string dronecode_sdk::Camera::VideoStreamSettings::uri {}
```


Video stream URI.

