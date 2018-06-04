# dronecore::Camera::VideoStreamInfo Struct Reference
`#include: camera.h`

----


Information about video stream. 


## Public Types


Type | Description
--- | ---
enum [Status](#structdronecore_1_1_camera_1_1_video_stream_info_1a2d081c6a9b50ec958046b5227cf8345c) | [Status](structdronecore_1_1_camera_1_1_status.md) type.

## Data Fields


[VideoStreamSettings](structdronecore_1_1_camera_1_1_video_stream_settings.md) [settings](#structdronecore_1_1_camera_1_1_video_stream_info_1aafae5ed3004543587ddcd4f2ef20170c)  - Video stream settings.

enum [dronecore::Camera::VideoStreamInfo::Status](structdronecore_1_1_camera_1_1_video_stream_info.md#structdronecore_1_1_camera_1_1_video_stream_info_1a2d081c6a9b50ec958046b5227cf8345c) [status](#structdronecore_1_1_camera_1_1_video_stream_info_1ac03881026a5d690846e93dcc6cf75590)  - Current status of video streaming.


## Member Enumeration Documentation


### enum Status {#structdronecore_1_1_camera_1_1_video_stream_info_1a2d081c6a9b50ec958046b5227cf8345c}


[Status](structdronecore_1_1_camera_1_1_status.md) type.


Value | Description
--- | ---
<span id="structdronecore_1_1_camera_1_1_video_stream_info_1a2d081c6a9b50ec958046b5227cf8345ca0d30777007362ccc9e8b2d0d22e4db13"></span> `NOT_RUNNING` | Video stream is not ongoing. 
<span id="structdronecore_1_1_camera_1_1_video_stream_info_1a2d081c6a9b50ec958046b5227cf8345caca69f96c768067fbff6c911ca87bccc9"></span> `IN_PROGRESS` | Video stream in progress. 

## Field Documentation


### settings {#structdronecore_1_1_camera_1_1_video_stream_info_1aafae5ed3004543587ddcd4f2ef20170c}

```cpp
VideoStreamSettings dronecore::Camera::VideoStreamInfo::settings
```


Video stream settings.


### status {#structdronecore_1_1_camera_1_1_video_stream_info_1ac03881026a5d690846e93dcc6cf75590}

```cpp
enum dronecore::Camera::VideoStreamInfo::Status  dronecore::Camera::VideoStreamInfo::status
```


Current status of video streaming.

