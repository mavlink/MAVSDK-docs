# mavsdk::Camera::VideoStreamSettings Struct Reference
`#include: camera.h`

----


Type for video stream settings. 


**See Also:**
- [get_video_stream_info()](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a6e099070d34896daffae871b5def94e3), [start_video_streaming()](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a6a65321f94db6dd31b91acd399dbbf32).


## Data Fields


float [frame_rate_hz](#structmavsdk_1_1_camera_1_1_video_stream_settings_1ae638dd09c73fb7b375871c37eac54959) = 0.f - Frames per second.

uint16_t [horizontal_resolution_pix](#structmavsdk_1_1_camera_1_1_video_stream_settings_1a1cd0bec414a52f29b17d346f2bb0a213) = 0u - Horizontal resolution in pixels.

uint16_t [vertical_resolution_pix](#structmavsdk_1_1_camera_1_1_video_stream_settings_1a5ea76ae228fc696936627882e26a8bdd) = 0u - Vertical resolution in pixels.

uint32_t [bit_rate_b_s](#structmavsdk_1_1_camera_1_1_video_stream_settings_1af32e3577263d4a94cdc92839e3074d42) = 0u - Bit rate in bits per second.

uint16_t [rotation_deg](#structmavsdk_1_1_camera_1_1_video_stream_settings_1a429d22865d5a1014ac16ef9695200c1b) = 0u - Video image rotation clockwise (0-359 degrees).

std::string [uri](#structmavsdk_1_1_camera_1_1_video_stream_settings_1add3b459a45527b64b21eaf64757d7bf2) {} - Video stream URI.


## Field Documentation


### frame_rate_hz {#structmavsdk_1_1_camera_1_1_video_stream_settings_1ae638dd09c73fb7b375871c37eac54959}

```cpp
float mavsdk::Camera::VideoStreamSettings::frame_rate_hz = 0.f
```


Frames per second.


### horizontal_resolution_pix {#structmavsdk_1_1_camera_1_1_video_stream_settings_1a1cd0bec414a52f29b17d346f2bb0a213}

```cpp
uint16_t mavsdk::Camera::VideoStreamSettings::horizontal_resolution_pix = 0u
```


Horizontal resolution in pixels.


### vertical_resolution_pix {#structmavsdk_1_1_camera_1_1_video_stream_settings_1a5ea76ae228fc696936627882e26a8bdd}

```cpp
uint16_t mavsdk::Camera::VideoStreamSettings::vertical_resolution_pix = 0u
```


Vertical resolution in pixels.


### bit_rate_b_s {#structmavsdk_1_1_camera_1_1_video_stream_settings_1af32e3577263d4a94cdc92839e3074d42}

```cpp
uint32_t mavsdk::Camera::VideoStreamSettings::bit_rate_b_s = 0u
```


Bit rate in bits per second.


### rotation_deg {#structmavsdk_1_1_camera_1_1_video_stream_settings_1a429d22865d5a1014ac16ef9695200c1b}

```cpp
uint16_t mavsdk::Camera::VideoStreamSettings::rotation_deg = 0u
```


Video image rotation clockwise (0-359 degrees).


### uri {#structmavsdk_1_1_camera_1_1_video_stream_settings_1add3b459a45527b64b21eaf64757d7bf2}

```cpp
std::string mavsdk::Camera::VideoStreamSettings::uri {}
```


Video stream URI.

