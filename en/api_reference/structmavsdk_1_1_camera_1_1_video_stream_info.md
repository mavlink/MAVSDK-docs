# mavsdk::Camera::VideoStreamInfo Struct Reference
`#include: camera.h`

----


[Information](structmavsdk_1_1_camera_1_1_information.md) about the video stream. 


## Public Types


Type | Description
--- | ---
enum [Status](#structmavsdk_1_1_camera_1_1_video_stream_info_1a429e643fccbc559bc193dc8e2ae66ed7) | Video stream status type.

## Data Fields


[VideoStreamSettings](structmavsdk_1_1_camera_1_1_video_stream_settings.md) [settings](#structmavsdk_1_1_camera_1_1_video_stream_info_1a11d9b81db8dc7b666ff9cd37d3835ead) {} - Video stream settings.

[Status](structmavsdk_1_1_camera_1_1_video_stream_info.md#structmavsdk_1_1_camera_1_1_video_stream_info_1a429e643fccbc559bc193dc8e2ae66ed7) [status](#structmavsdk_1_1_camera_1_1_video_stream_info_1ac3ee00fe9a52f1dc9df0b7ceaf7b0ed8) {} - Current status of video streaming.


## Member Enumeration Documentation


### enum Status {#structmavsdk_1_1_camera_1_1_video_stream_info_1a429e643fccbc559bc193dc8e2ae66ed7}


Video stream status type.


Value | Description
--- | ---
<span id="structmavsdk_1_1_camera_1_1_video_stream_info_1a429e643fccbc559bc193dc8e2ae66ed7ae457ff7a83d0a8681fa483f898788515"></span> `NotRunning` | Video stream is not running. 
<span id="structmavsdk_1_1_camera_1_1_video_stream_info_1a429e643fccbc559bc193dc8e2ae66ed7a12d868c18cb29bf58f02b504be9033fd"></span> `InProgress` | Video stream is running. 

## Field Documentation


### settings {#structmavsdk_1_1_camera_1_1_video_stream_info_1a11d9b81db8dc7b666ff9cd37d3835ead}

```cpp
VideoStreamSettings mavsdk::Camera::VideoStreamInfo::settings {}
```


Video stream settings.


### status {#structmavsdk_1_1_camera_1_1_video_stream_info_1ac3ee00fe9a52f1dc9df0b7ceaf7b0ed8}

```cpp
Status mavsdk::Camera::VideoStreamInfo::status {}
```


Current status of video streaming.

