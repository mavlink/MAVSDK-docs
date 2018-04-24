# dronecore::Camera::VideoStreamSettings Struct Reference
`#include: camera.h`

----


Type for video stream settings. 


Application may call [set_video_stream_settings()](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1a9a059a12960396051500fa7f4e2710f7) before starting video streaming to tell [Camera](classdronecore_1_1_camera.md) server to use these settings during video streaming.


**See Also:**
- [set_video_stream_settings()](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1a9a059a12960396051500fa7f4e2710f7), [get_video_stream_info()](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1a1137d3b38b134e0e3ba7d88048448a1f), [start_video_streaming()](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1a1abbf7e3287e95c987a6d46b60f4e8fa).


## Public Member Functions


Type | Name | Description
---: | --- | ---
void | [set_highest](#structdronecore_1_1_camera_1_1_video_stream_settings_1a2bbca6d9c18993f75c17c3df6e3b3eef) () | Sets to highest possible settings for Resolution, framerate.

## Data Fields


float [frame_rate_hz](#structdronecore_1_1_camera_1_1_video_stream_settings_1a651d8fdfb8a57d88f806a3c7526ff3bb) = 0.f - Frames per second.

uint16_t [horizontal_resolution_pix](#structdronecore_1_1_camera_1_1_video_stream_settings_1a3b16e43b1234bae0295c91a6edbf20b4) = 0u - Horizontal resolution in pixels.

uint16_t [vertical_resolution_pix](#structdronecore_1_1_camera_1_1_video_stream_settings_1acde5dfe562b1dfe0c6059f6bf93778e9) = 0u - Vertical resolution in pixels.

uint32_t [bit_rate_b_s](#structdronecore_1_1_camera_1_1_video_stream_settings_1aabf8f9d1a65519e913da464119067e86) = 0u - Bit rate in bits per second.

uint16_t [rotation_deg](#structdronecore_1_1_camera_1_1_video_stream_settings_1ae7d8c93ea53a55d997395ae17c1e16fb) = 0u - Video image rotation clockwise (0-359 degrees).

std::string [uri](#structdronecore_1_1_camera_1_1_video_stream_settings_1a89bba86b91591d17728e8433611c5a43) {} - Video stream URI.

## Static Public Attributes


static constexpr const float [FRAME_RATE_HIGHEST](#structdronecore_1_1_camera_1_1_video_stream_settings_1a24f19894429fe370090c40a8a571f6ec) = -1.0f - Highest possible framerate.


static constexpr const uint16_t [RESOLUTION_H_HIGHEST](#structdronecore_1_1_camera_1_1_video_stream_settings_1a0cf857c649209dac2d97b0e2ffbd2212) = UINT16_MAX - Highest possible horizontal resolution.


static constexpr const uint16_t [RESOLUTION_V_HIGHEST](#structdronecore_1_1_camera_1_1_video_stream_settings_1a4c1f727cb64e8a0d1b48acab7e28cc6d) = UINT16_MAX - Highest possible vertical resolution.


static constexpr const uint32_t [BIT_RATE_AUTO](#structdronecore_1_1_camera_1_1_video_stream_settings_1a5112bd1cb0a09b03995147c17f2d639b) = 0 - Auto settings for Bit rate.


## Member Function Documentation


### set_highest() {#structdronecore_1_1_camera_1_1_video_stream_settings_1a2bbca6d9c18993f75c17c3df6e3b3eef}
```cpp
void dronecore::Camera::VideoStreamSettings::set_highest()
```


Sets to highest possible settings for Resolution, framerate.


## Field Documentation


### FRAME_RATE_HIGHEST {#structdronecore_1_1_camera_1_1_video_stream_settings_1a24f19894429fe370090c40a8a571f6ec}

```cpp
constexpr const float dronecore::Camera::VideoStreamSettings::FRAME_RATE_HIGHEST = -1.0f
```


Highest possible framerate.


### RESOLUTION_H_HIGHEST {#structdronecore_1_1_camera_1_1_video_stream_settings_1a0cf857c649209dac2d97b0e2ffbd2212}

```cpp
constexpr const uint16_t dronecore::Camera::VideoStreamSettings::RESOLUTION_H_HIGHEST = UINT16_MAX
```


Highest possible horizontal resolution.


### RESOLUTION_V_HIGHEST {#structdronecore_1_1_camera_1_1_video_stream_settings_1a4c1f727cb64e8a0d1b48acab7e28cc6d}

```cpp
constexpr const uint16_t dronecore::Camera::VideoStreamSettings::RESOLUTION_V_HIGHEST = UINT16_MAX
```


Highest possible vertical resolution.


### BIT_RATE_AUTO {#structdronecore_1_1_camera_1_1_video_stream_settings_1a5112bd1cb0a09b03995147c17f2d639b}

```cpp
constexpr const uint32_t dronecore::Camera::VideoStreamSettings::BIT_RATE_AUTO = 0
```


Auto settings for Bit rate.


### frame_rate_hz {#structdronecore_1_1_camera_1_1_video_stream_settings_1a651d8fdfb8a57d88f806a3c7526ff3bb}

```cpp
float dronecore::Camera::VideoStreamSettings::frame_rate_hz = 0.f
```


Frames per second.


### horizontal_resolution_pix {#structdronecore_1_1_camera_1_1_video_stream_settings_1a3b16e43b1234bae0295c91a6edbf20b4}

```cpp
uint16_t dronecore::Camera::VideoStreamSettings::horizontal_resolution_pix = 0u
```


Horizontal resolution in pixels.


### vertical_resolution_pix {#structdronecore_1_1_camera_1_1_video_stream_settings_1acde5dfe562b1dfe0c6059f6bf93778e9}

```cpp
uint16_t dronecore::Camera::VideoStreamSettings::vertical_resolution_pix = 0u
```


Vertical resolution in pixels.


### bit_rate_b_s {#structdronecore_1_1_camera_1_1_video_stream_settings_1aabf8f9d1a65519e913da464119067e86}

```cpp
uint32_t dronecore::Camera::VideoStreamSettings::bit_rate_b_s = 0u
```


Bit rate in bits per second.


### rotation_deg {#structdronecore_1_1_camera_1_1_video_stream_settings_1ae7d8c93ea53a55d997395ae17c1e16fb}

```cpp
uint16_t dronecore::Camera::VideoStreamSettings::rotation_deg = 0u
```


Video image rotation clockwise (0-359 degrees).


### uri {#structdronecore_1_1_camera_1_1_video_stream_settings_1a89bba86b91591d17728e8433611c5a43}

```cpp
std::string dronecore::Camera::VideoStreamSettings::uri {}
```


Video stream URI.

