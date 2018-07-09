# dronecode_sdk::Camera::VideoStreamInfo Struct Reference
`#include: camera.h`

----


Information about video stream. 


## Public Types


Type | Description
--- | ---
enum [Status](#structdronecode__sdk_1_1_camera_1_1_video_stream_info_1a69b67b304c04a7d9bb0a8efb43927c85) | [Status](structdronecode__sdk_1_1_camera_1_1_status.md) type.

## Data Fields


[VideoStreamSettings](structdronecode__sdk_1_1_camera_1_1_video_stream_settings.md) [settings](#structdronecode__sdk_1_1_camera_1_1_video_stream_info_1af60d0cb6e3d42889bdb6893205239e71)  - Video stream settings.

enum [dronecode_sdk::Camera::VideoStreamInfo::Status](structdronecode__sdk_1_1_camera_1_1_video_stream_info.md#structdronecode__sdk_1_1_camera_1_1_video_stream_info_1a69b67b304c04a7d9bb0a8efb43927c85) [status](#structdronecode__sdk_1_1_camera_1_1_video_stream_info_1ab6af2652cea12218035b008b8245b77a)  - Current status of video streaming.


## Member Enumeration Documentation


### enum Status {#structdronecode__sdk_1_1_camera_1_1_video_stream_info_1a69b67b304c04a7d9bb0a8efb43927c85}


[Status](structdronecode__sdk_1_1_camera_1_1_status.md) type.


Value | Description
--- | ---
<span id="structdronecode__sdk_1_1_camera_1_1_video_stream_info_1a69b67b304c04a7d9bb0a8efb43927c85a0d30777007362ccc9e8b2d0d22e4db13"></span> `NOT_RUNNING` | Video stream is not ongoing. 
<span id="structdronecode__sdk_1_1_camera_1_1_video_stream_info_1a69b67b304c04a7d9bb0a8efb43927c85aca69f96c768067fbff6c911ca87bccc9"></span> `IN_PROGRESS` | Video stream in progress. 

## Field Documentation


### settings {#structdronecode__sdk_1_1_camera_1_1_video_stream_info_1af60d0cb6e3d42889bdb6893205239e71}

```cpp
VideoStreamSettings dronecode_sdk::Camera::VideoStreamInfo::settings
```


Video stream settings.


### status {#structdronecode__sdk_1_1_camera_1_1_video_stream_info_1ab6af2652cea12218035b008b8245b77a}

```cpp
enum dronecode_sdk::Camera::VideoStreamInfo::Status  dronecode_sdk::Camera::VideoStreamInfo::status
```


Current status of video streaming.

