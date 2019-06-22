# mavsdk::Camera::VideoStreamInfo Struct Reference
`#include: camera.h`

----


[Information](structmavsdk_1_1_camera_1_1_information.md) about video stream. 


## Public Types


Type | Description
--- | ---
enum [Status](#structmavsdk_1_1_camera_1_1_video_stream_info_1a429e643fccbc559bc193dc8e2ae66ed7) | [Status](structmavsdk_1_1_camera_1_1_status.md) type.

## Data Fields


[VideoStreamSettings](structmavsdk_1_1_camera_1_1_video_stream_settings.md) [settings](#structmavsdk_1_1_camera_1_1_video_stream_info_1a11d9b81db8dc7b666ff9cd37d3835ead)  - Video stream settings.

enum [mavsdk::Camera::VideoStreamInfo::Status](structmavsdk_1_1_camera_1_1_video_stream_info.md#structmavsdk_1_1_camera_1_1_video_stream_info_1a429e643fccbc559bc193dc8e2ae66ed7) [status](#structmavsdk_1_1_camera_1_1_video_stream_info_1adea7fdd51fb52a5df5323acc64a58c49)  - Current status of video streaming.


## Member Enumeration Documentation


### enum Status {#structmavsdk_1_1_camera_1_1_video_stream_info_1a429e643fccbc559bc193dc8e2ae66ed7}


[Status](structmavsdk_1_1_camera_1_1_status.md) type.


Value | Description
--- | ---
<span id="structmavsdk_1_1_camera_1_1_video_stream_info_1a429e643fccbc559bc193dc8e2ae66ed7a0d30777007362ccc9e8b2d0d22e4db13"></span> `NOT_RUNNING` | Video stream is not ongoing. 
<span id="structmavsdk_1_1_camera_1_1_video_stream_info_1a429e643fccbc559bc193dc8e2ae66ed7aca69f96c768067fbff6c911ca87bccc9"></span> `IN_PROGRESS` | Video stream in progress. 

## Field Documentation


### settings {#structmavsdk_1_1_camera_1_1_video_stream_info_1a11d9b81db8dc7b666ff9cd37d3835ead}

```cpp
VideoStreamSettings mavsdk::Camera::VideoStreamInfo::settings
```


Video stream settings.


### status {#structmavsdk_1_1_camera_1_1_video_stream_info_1adea7fdd51fb52a5df5323acc64a58c49}

```cpp
enum mavsdk::Camera::VideoStreamInfo::Status  mavsdk::Camera::VideoStreamInfo::status
```


Current status of video streaming.

