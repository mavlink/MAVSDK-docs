# mavsdk::Camera Class Reference
`#include: camera.h`

----


Can be used to manage cameras that implement the MAVLink [Camera](classmavsdk_1_1_camera.md) Protocol: [https://mavlink.io/en/protocol/camera.html](https://mavlink.io/en/protocol/camera.html). 


Currently only a single camera is supported. When multiple cameras are supported the plugin will need to be instantiated separately for every camera and the camera selected using `select_camera`. 


## Data Structures


struct [CaptureInfo](structmavsdk_1_1_camera_1_1_capture_info.md)

struct [EulerAngle](structmavsdk_1_1_camera_1_1_euler_angle.md)

struct [Information](structmavsdk_1_1_camera_1_1_information.md)

struct [Option](structmavsdk_1_1_camera_1_1_option.md)

struct [Position](structmavsdk_1_1_camera_1_1_position.md)

struct [Quaternion](structmavsdk_1_1_camera_1_1_quaternion.md)

struct [Setting](structmavsdk_1_1_camera_1_1_setting.md)

struct [SettingOptions](structmavsdk_1_1_camera_1_1_setting_options.md)

struct [Status](structmavsdk_1_1_camera_1_1_status.md)

struct [VideoStreamInfo](structmavsdk_1_1_camera_1_1_video_stream_info.md)

struct [VideoStreamSettings](structmavsdk_1_1_camera_1_1_video_stream_settings.md)

## Public Types


Type | Description
--- | ---
enum [Mode](#classmavsdk_1_1_camera_1a02bb5ce37d125ba4c65d43f172cc2d65) | [Camera](classmavsdk_1_1_camera.md) mode type.
enum [Result](#classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcf) | Possible results returned for camera commands.
std::function< void([Result](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcf))> [ResultCallback](#classmavsdk_1_1_camera_1a8d6d59cd8d0a3584ef60b16255b6301f) | Callback type for asynchronous [Camera](classmavsdk_1_1_camera.md) calls.
std::function< void([Mode](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a02bb5ce37d125ba4c65d43f172cc2d65))> [ModeCallback](#classmavsdk_1_1_camera_1a33a7257ab95d9277b786e6de86604931) | Callback type for subscribe_mode.
std::function< void([Information](structmavsdk_1_1_camera_1_1_information.md))> [InformationCallback](#classmavsdk_1_1_camera_1af13455249eebaf152a71d59e32fcbf65) | Callback type for subscribe_information.
std::function< void([VideoStreamInfo](structmavsdk_1_1_camera_1_1_video_stream_info.md))> [VideoStreamInfoCallback](#classmavsdk_1_1_camera_1acd9baf073b816e46c22dbd6b599ece66) | Callback type for subscribe_video_stream_info.
std::function< void([CaptureInfo](structmavsdk_1_1_camera_1_1_capture_info.md))> [CaptureInfoCallback](#classmavsdk_1_1_camera_1a9bf5c20ea0b03ab019057829d1a3441e) | Callback type for subscribe_capture_info.
std::function< void([Status](structmavsdk_1_1_camera_1_1_status.md))> [StatusCallback](#classmavsdk_1_1_camera_1aea925914ce854b81b67e3213840c97ad) | Callback type for subscribe_status.
std::function< void(std::vector< [Setting](structmavsdk_1_1_camera_1_1_setting.md) >)> [CurrentSettingsCallback](#classmavsdk_1_1_camera_1a77484487381b2579460c36d97d367fe6) | Callback type for subscribe_current_settings.
std::function< void(std::vector< [SettingOptions](structmavsdk_1_1_camera_1_1_setting_options.md) >)> [PossibleSettingOptionsCallback](#classmavsdk_1_1_camera_1a78e25614c29cd8bc1bbf26adcf417c2a) | Callback type for subscribe_possible_setting_options.
std::function< void([Result](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcf), [Setting](structmavsdk_1_1_camera_1_1_setting.md))> [GetSettingCallback](#classmavsdk_1_1_camera_1ac233f5688f0b7f1e712bb31dfaeadd85) | Callback type for get_setting_async.

## Public Member Functions


Type | Name | Description
---: | --- | ---
&nbsp; | [Camera](#classmavsdk_1_1_camera_1a186a2853440c879b99ed7e4a726969e9) ([System](classmavsdk_1_1_system.md) & system) | Constructor. Creates the plugin for a specific [System](classmavsdk_1_1_system.md).
&nbsp; | [~Camera](#classmavsdk_1_1_camera_1abd845e6fb2adc386dba7c8860a67f761) () | Destructor (internal use only).
&nbsp; | [Camera](#classmavsdk_1_1_camera_1a3af73f81cf8cd051fe9d7af6f2df6945) (const [Camera](classmavsdk_1_1_camera.md) &)=delete | Copy constructor (object is not copyable).
void | [take_photo_async](#classmavsdk_1_1_camera_1a343217bf38cc71cd258c7e81626dccb5) (const [ResultCallback](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a8d6d59cd8d0a3584ef60b16255b6301f) callback) | Take one photo.
[Result](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcf) | [take_photo](#classmavsdk_1_1_camera_1a44b86cfda6262652a1796661e595003c) () const | Take one photo.
void | [start_photo_interval_async](#classmavsdk_1_1_camera_1ae583f83e163e2b33a8dc4a6fcfebbac6) (float interval_s, const [ResultCallback](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a8d6d59cd8d0a3584ef60b16255b6301f) callback) | Start photo timelapse with a given interval.
[Result](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcf) | [start_photo_interval](#classmavsdk_1_1_camera_1adfa32eb338aabf19675a1218fc28d8bc) (float interval_s)const | Start photo timelapse with a given interval.
void | [stop_photo_interval_async](#classmavsdk_1_1_camera_1a540d94eb58efe02fdd3659994c778203) (const [ResultCallback](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a8d6d59cd8d0a3584ef60b16255b6301f) callback) | Stop a running photo timelapse.
[Result](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcf) | [stop_photo_interval](#classmavsdk_1_1_camera_1a287fa0fd3fcda1dee2cf40ad041d524a) () const | Stop a running photo timelapse.
void | [start_video_async](#classmavsdk_1_1_camera_1a2d5dff782ea3f8346bc53560be368531) (const [ResultCallback](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a8d6d59cd8d0a3584ef60b16255b6301f) callback) | Start a video recording.
[Result](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcf) | [start_video](#classmavsdk_1_1_camera_1ac64e77dee9f5ff9b5c84100d8f007670) () const | Start a video recording.
void | [stop_video_async](#classmavsdk_1_1_camera_1a77d1b1a201164023c5eef3c91cdd4e54) (const [ResultCallback](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a8d6d59cd8d0a3584ef60b16255b6301f) callback) | Stop a running video recording.
[Result](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcf) | [stop_video](#classmavsdk_1_1_camera_1a6062ac1907bd10944d2ddb9655943ddc) () const | Stop a running video recording.
[Result](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcf) | [start_video_streaming](#classmavsdk_1_1_camera_1a8714183c1b03ec4251287911db1492c3) () const | Start video streaming.
[Result](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcf) | [stop_video_streaming](#classmavsdk_1_1_camera_1a9f6ec4e37cdd287f0cbeed40a2602416) () const | Stop current video streaming.
void | [set_mode_async](#classmavsdk_1_1_camera_1a76d98d04885d38d0438da7c8696ef6ab) ([Mode](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a02bb5ce37d125ba4c65d43f172cc2d65) mode, const [ResultCallback](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a8d6d59cd8d0a3584ef60b16255b6301f) callback) | Set camera mode.
[Result](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcf) | [set_mode](#classmavsdk_1_1_camera_1a249755db2eaa8fd3d202ac01ca52448d) ([Mode](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a02bb5ce37d125ba4c65d43f172cc2d65) mode)const | Set camera mode.
void | [subscribe_mode](#classmavsdk_1_1_camera_1a002b03af2331606752aba43da0216503) ([ModeCallback](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a33a7257ab95d9277b786e6de86604931) callback) | Subscribe to camera mode updates.
[Mode](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a02bb5ce37d125ba4c65d43f172cc2d65) | [mode](#classmavsdk_1_1_camera_1a222bce91e70d1ca53bcf5d885bacd418) () const | Poll for 'Mode' (blocking).
void | [subscribe_information](#classmavsdk_1_1_camera_1a64a8d8ac28784b0d304d5a7b1519657a) ([InformationCallback](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1af13455249eebaf152a71d59e32fcbf65) callback) | Subscribe to camera information updates.
[Information](structmavsdk_1_1_camera_1_1_information.md) | [information](#classmavsdk_1_1_camera_1a7feb16f3d913b91d05efc803ce4e396b) () const | Poll for '[Information](structmavsdk_1_1_camera_1_1_information.md)' (blocking).
void | [subscribe_video_stream_info](#classmavsdk_1_1_camera_1a23a43693897e77995d8be6d1b15fe62c) ([VideoStreamInfoCallback](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1acd9baf073b816e46c22dbd6b599ece66) callback) | Subscribe to video stream info updates.
[VideoStreamInfo](structmavsdk_1_1_camera_1_1_video_stream_info.md) | [video_stream_info](#classmavsdk_1_1_camera_1ad466621feff2d4f0f11124a36dda656c) () const | Poll for '[VideoStreamInfo](structmavsdk_1_1_camera_1_1_video_stream_info.md)' (blocking).
void | [subscribe_capture_info](#classmavsdk_1_1_camera_1a26901f1812df6253a39457d7bc230895) ([CaptureInfoCallback](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a9bf5c20ea0b03ab019057829d1a3441e) callback) | Subscribe to capture info updates.
void | [subscribe_status](#classmavsdk_1_1_camera_1ab62186cc3fc79459bde0e4704eb1e768) ([StatusCallback](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1aea925914ce854b81b67e3213840c97ad) callback) | Subscribe to camera status updates.
[Status](structmavsdk_1_1_camera_1_1_status.md) | [status](#classmavsdk_1_1_camera_1a0bb78c2b665c28b314f00f11a0f676b1) () const | Poll for '[Status](structmavsdk_1_1_camera_1_1_status.md)' (blocking).
void | [subscribe_current_settings](#classmavsdk_1_1_camera_1a460cf8f9810417e63ce2643df9ed014a) ([CurrentSettingsCallback](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a77484487381b2579460c36d97d367fe6) callback) | Get the list of current camera settings.
void | [subscribe_possible_setting_options](#classmavsdk_1_1_camera_1abd8c5e18e165b319aaae9815c735b683) ([PossibleSettingOptionsCallback](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a78e25614c29cd8bc1bbf26adcf417c2a) callback) | Get the list of settings that can be changed.
std::vector< [SettingOptions](structmavsdk_1_1_camera_1_1_setting_options.md) > | [possible_setting_options](#classmavsdk_1_1_camera_1a5416dc30ec436707420db715ee56ce08) () const | Poll for 'std::vector<SettingOptions>' (blocking).
void | [set_setting_async](#classmavsdk_1_1_camera_1aace1d6ffd86a6fdf30b3466c8522feba) ([Setting](structmavsdk_1_1_camera_1_1_setting.md) setting, const [ResultCallback](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a8d6d59cd8d0a3584ef60b16255b6301f) callback) | Set a setting to some value.
[Result](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcf) | [set_setting](#classmavsdk_1_1_camera_1aa4b1293d8c6332293cccde87ec79f64a) ([Setting](structmavsdk_1_1_camera_1_1_setting.md) setting)const | Set a setting to some value.
void | [get_setting_async](#classmavsdk_1_1_camera_1a6b2e4e9b5b304aff313e4f988aa6ba86) ([Setting](structmavsdk_1_1_camera_1_1_setting.md) setting, const [GetSettingCallback](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1ac233f5688f0b7f1e712bb31dfaeadd85) callback) | Get a setting.
std::pair< [Result](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcf), [Camera::Setting](structmavsdk_1_1_camera_1_1_setting.md) > | [get_setting](#classmavsdk_1_1_camera_1ae88917857b666dc7cfd0d84b3ad29d9c) ([Setting](structmavsdk_1_1_camera_1_1_setting.md) setting)const | Get a setting.
void | [format_storage_async](#classmavsdk_1_1_camera_1a20455726797ece508d49fe05442fe0c1) (const [ResultCallback](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a8d6d59cd8d0a3584ef60b16255b6301f) callback) | Format storage (e.g. SD card) in camera.
[Result](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcf) | [format_storage](#classmavsdk_1_1_camera_1a1e2d39b44251f39a395527b0170e223a) () const | Format storage (e.g. SD card) in camera.
const [Camera](classmavsdk_1_1_camera.md) & | [operator=](#classmavsdk_1_1_camera_1aeff295155b6a665f5c942e473f1fe894) (const [Camera](classmavsdk_1_1_camera.md) &)=delete | Equality operator (object is not copyable).


## Constructor & Destructor Documentation


### Camera() {#classmavsdk_1_1_camera_1a186a2853440c879b99ed7e4a726969e9}
```cpp
mavsdk::Camera::Camera(System &system)
```


Constructor. Creates the plugin for a specific [System](classmavsdk_1_1_system.md).

The plugin is typically created as shown below: 

```cpp
auto camera = std::make_shared<Camera>(system);
```

**Parameters**

* [System](classmavsdk_1_1_system.md)& **system** - The specific system associated with this plugin.

### ~Camera() {#classmavsdk_1_1_camera_1abd845e6fb2adc386dba7c8860a67f761}
```cpp
mavsdk::Camera::~Camera()
```


Destructor (internal use only).


### Camera() {#classmavsdk_1_1_camera_1a3af73f81cf8cd051fe9d7af6f2df6945}
```cpp
mavsdk::Camera::Camera(const Camera &)=delete
```


Copy constructor (object is not copyable).


**Parameters**

* const [Camera](classmavsdk_1_1_camera.md)&  - 

## Member Typdef Documentation


### typedef ResultCallback {#classmavsdk_1_1_camera_1a8d6d59cd8d0a3584ef60b16255b6301f}

```cpp
using mavsdk::Camera::ResultCallback =  std::function<void(Result)>
```


Callback type for asynchronous [Camera](classmavsdk_1_1_camera.md) calls.


### typedef ModeCallback {#classmavsdk_1_1_camera_1a33a7257ab95d9277b786e6de86604931}

```cpp
using mavsdk::Camera::ModeCallback =  std::function<void(Mode)>
```


Callback type for subscribe_mode.


### typedef InformationCallback {#classmavsdk_1_1_camera_1af13455249eebaf152a71d59e32fcbf65}

```cpp
using mavsdk::Camera::InformationCallback =  std::function<void(Information)>
```


Callback type for subscribe_information.


### typedef VideoStreamInfoCallback {#classmavsdk_1_1_camera_1acd9baf073b816e46c22dbd6b599ece66}

```cpp
using mavsdk::Camera::VideoStreamInfoCallback =  std::function<void(VideoStreamInfo)>
```


Callback type for subscribe_video_stream_info.


### typedef CaptureInfoCallback {#classmavsdk_1_1_camera_1a9bf5c20ea0b03ab019057829d1a3441e}

```cpp
using mavsdk::Camera::CaptureInfoCallback =  std::function<void(CaptureInfo)>
```


Callback type for subscribe_capture_info.


### typedef StatusCallback {#classmavsdk_1_1_camera_1aea925914ce854b81b67e3213840c97ad}

```cpp
using mavsdk::Camera::StatusCallback =  std::function<void(Status)>
```


Callback type for subscribe_status.


### typedef CurrentSettingsCallback {#classmavsdk_1_1_camera_1a77484487381b2579460c36d97d367fe6}

```cpp
using mavsdk::Camera::CurrentSettingsCallback =  std::function<void(std::vector<Setting>)>
```


Callback type for subscribe_current_settings.


### typedef PossibleSettingOptionsCallback {#classmavsdk_1_1_camera_1a78e25614c29cd8bc1bbf26adcf417c2a}

```cpp
using mavsdk::Camera::PossibleSettingOptionsCallback =  std::function<void(std::vector<SettingOptions>)>
```


Callback type for subscribe_possible_setting_options.


### typedef GetSettingCallback {#classmavsdk_1_1_camera_1ac233f5688f0b7f1e712bb31dfaeadd85}

```cpp
using mavsdk::Camera::GetSettingCallback =  std::function<void(Result, Setting)>
```


Callback type for get_setting_async.


## Member Enumeration Documentation


### enum Mode {#classmavsdk_1_1_camera_1a02bb5ce37d125ba4c65d43f172cc2d65}


[Camera](classmavsdk_1_1_camera.md) mode type.


Value | Description
--- | ---
<span id="classmavsdk_1_1_camera_1a02bb5ce37d125ba4c65d43f172cc2d65a88183b946cc5f0e8c96b2e66e1c74a7e"></span> `Unknown` | Unknown. 
<span id="classmavsdk_1_1_camera_1a02bb5ce37d125ba4c65d43f172cc2d65ac03d53b70feba4ea842510abecd6c45e"></span> `Photo` | Photo mode. 
<span id="classmavsdk_1_1_camera_1a02bb5ce37d125ba4c65d43f172cc2d65a34e2d1989a1dbf75cd631596133ee5ee"></span> `Video` | Video mode. 

### enum Result {#classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcf}


Possible results returned for camera commands.


Value | Description
--- | ---
<span id="classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcfa88183b946cc5f0e8c96b2e66e1c74a7e"></span> `Unknown` | Unknown result. 
<span id="classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcfa505a83f220c02df2f85c3810cd9ceb38"></span> `Success` | Command executed successfully. 
<span id="classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcfa12d868c18cb29bf58f02b504be9033fd"></span> `InProgress` | Command in progress. 
<span id="classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcfad8a942ef2b04672adfafef0ad817a407"></span> `Busy` | [Camera](classmavsdk_1_1_camera.md) is busy and rejected command. 
<span id="classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcfa58d036b9b7f0e7eb38cfb90f1cc70a73"></span> `Denied` | [Camera](classmavsdk_1_1_camera.md) denied the command. 
<span id="classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcfa902b0d55fddef6f8d651fe1035b7d4bd"></span> `Error` | An error has occured while executing the command. 
<span id="classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcfac85a251cc457840f1e032f1b733e9398"></span> `Timeout` | Command timed out. 
<span id="classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcfa5a738160747f39c20e9f65416931c974"></span> `WrongArgument` | Command has wrong argument(s). 

## Member Function Documentation


### take_photo_async() {#classmavsdk_1_1_camera_1a343217bf38cc71cd258c7e81626dccb5}
```cpp
void mavsdk::Camera::take_photo_async(const ResultCallback callback)
```


Take one photo.

This function is non-blocking. See 'take_photo' for the blocking counterpart.

**Parameters**

* const [ResultCallback](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a8d6d59cd8d0a3584ef60b16255b6301f) **callback** - 

### take_photo() {#classmavsdk_1_1_camera_1a44b86cfda6262652a1796661e595003c}
```cpp
Result mavsdk::Camera::take_photo() const
```


Take one photo.

This function is blocking. See 'take_photo_async' for the non-blocking counterpart.

**Returns**

&emsp;[Result](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcf) - Result of request.

### start_photo_interval_async() {#classmavsdk_1_1_camera_1ae583f83e163e2b33a8dc4a6fcfebbac6}
```cpp
void mavsdk::Camera::start_photo_interval_async(float interval_s, const ResultCallback callback)
```


Start photo timelapse with a given interval.

This function is non-blocking. See 'start_photo_interval' for the blocking counterpart.

**Parameters**

* float **interval_s** - 
* const [ResultCallback](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a8d6d59cd8d0a3584ef60b16255b6301f) **callback** - 

### start_photo_interval() {#classmavsdk_1_1_camera_1adfa32eb338aabf19675a1218fc28d8bc}
```cpp
Result mavsdk::Camera::start_photo_interval(float interval_s) const
```


Start photo timelapse with a given interval.

This function is blocking. See 'start_photo_interval_async' for the non-blocking counterpart.

**Parameters**

* float **interval_s** - 

**Returns**

&emsp;[Result](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcf) - Result of request.

### stop_photo_interval_async() {#classmavsdk_1_1_camera_1a540d94eb58efe02fdd3659994c778203}
```cpp
void mavsdk::Camera::stop_photo_interval_async(const ResultCallback callback)
```


Stop a running photo timelapse.

This function is non-blocking. See 'stop_photo_interval' for the blocking counterpart.

**Parameters**

* const [ResultCallback](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a8d6d59cd8d0a3584ef60b16255b6301f) **callback** - 

### stop_photo_interval() {#classmavsdk_1_1_camera_1a287fa0fd3fcda1dee2cf40ad041d524a}
```cpp
Result mavsdk::Camera::stop_photo_interval() const
```


Stop a running photo timelapse.

This function is blocking. See 'stop_photo_interval_async' for the non-blocking counterpart.

**Returns**

&emsp;[Result](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcf) - Result of request.

### start_video_async() {#classmavsdk_1_1_camera_1a2d5dff782ea3f8346bc53560be368531}
```cpp
void mavsdk::Camera::start_video_async(const ResultCallback callback)
```


Start a video recording.

This function is non-blocking. See 'start_video' for the blocking counterpart.

**Parameters**

* const [ResultCallback](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a8d6d59cd8d0a3584ef60b16255b6301f) **callback** - 

### start_video() {#classmavsdk_1_1_camera_1ac64e77dee9f5ff9b5c84100d8f007670}
```cpp
Result mavsdk::Camera::start_video() const
```


Start a video recording.

This function is blocking. See 'start_video_async' for the non-blocking counterpart.

**Returns**

&emsp;[Result](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcf) - Result of request.

### stop_video_async() {#classmavsdk_1_1_camera_1a77d1b1a201164023c5eef3c91cdd4e54}
```cpp
void mavsdk::Camera::stop_video_async(const ResultCallback callback)
```


Stop a running video recording.

This function is non-blocking. See 'stop_video' for the blocking counterpart.

**Parameters**

* const [ResultCallback](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a8d6d59cd8d0a3584ef60b16255b6301f) **callback** - 

### stop_video() {#classmavsdk_1_1_camera_1a6062ac1907bd10944d2ddb9655943ddc}
```cpp
Result mavsdk::Camera::stop_video() const
```


Stop a running video recording.

This function is blocking. See 'stop_video_async' for the non-blocking counterpart.

**Returns**

&emsp;[Result](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcf) - Result of request.

### start_video_streaming() {#classmavsdk_1_1_camera_1a8714183c1b03ec4251287911db1492c3}
```cpp
Result mavsdk::Camera::start_video_streaming() const
```


Start video streaming.

This function is blocking.

**Returns**

&emsp;[Result](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcf) - Result of request.

### stop_video_streaming() {#classmavsdk_1_1_camera_1a9f6ec4e37cdd287f0cbeed40a2602416}
```cpp
Result mavsdk::Camera::stop_video_streaming() const
```


Stop current video streaming.

This function is blocking.

**Returns**

&emsp;[Result](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcf) - Result of request.

### set_mode_async() {#classmavsdk_1_1_camera_1a76d98d04885d38d0438da7c8696ef6ab}
```cpp
void mavsdk::Camera::set_mode_async(Mode mode, const ResultCallback callback)
```


Set camera mode.

This function is non-blocking. See 'set_mode' for the blocking counterpart.

**Parameters**

* [Mode](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a02bb5ce37d125ba4c65d43f172cc2d65) **mode** - 
* const [ResultCallback](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a8d6d59cd8d0a3584ef60b16255b6301f) **callback** - 

### set_mode() {#classmavsdk_1_1_camera_1a249755db2eaa8fd3d202ac01ca52448d}
```cpp
Result mavsdk::Camera::set_mode(Mode mode) const
```


Set camera mode.

This function is blocking. See 'set_mode_async' for the non-blocking counterpart.

**Parameters**

* [Mode](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a02bb5ce37d125ba4c65d43f172cc2d65) **mode** - 

**Returns**

&emsp;[Result](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcf) - Result of request.

### subscribe_mode() {#classmavsdk_1_1_camera_1a002b03af2331606752aba43da0216503}
```cpp
void mavsdk::Camera::subscribe_mode(ModeCallback callback)
```


Subscribe to camera mode updates.


**Parameters**

* [ModeCallback](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a33a7257ab95d9277b786e6de86604931) **callback** - 

### mode() {#classmavsdk_1_1_camera_1a222bce91e70d1ca53bcf5d885bacd418}
```cpp
Mode mavsdk::Camera::mode() const
```


Poll for 'Mode' (blocking).


**Returns**

&emsp;[Mode](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a02bb5ce37d125ba4c65d43f172cc2d65) - One Mode update.

### subscribe_information() {#classmavsdk_1_1_camera_1a64a8d8ac28784b0d304d5a7b1519657a}
```cpp
void mavsdk::Camera::subscribe_information(InformationCallback callback)
```


Subscribe to camera information updates.


**Parameters**

* [InformationCallback](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1af13455249eebaf152a71d59e32fcbf65) **callback** - 

### information() {#classmavsdk_1_1_camera_1a7feb16f3d913b91d05efc803ce4e396b}
```cpp
Information mavsdk::Camera::information() const
```


Poll for '[Information](structmavsdk_1_1_camera_1_1_information.md)' (blocking).


**Returns**

&emsp;[Information](structmavsdk_1_1_camera_1_1_information.md) - One [Information](structmavsdk_1_1_camera_1_1_information.md) update.

### subscribe_video_stream_info() {#classmavsdk_1_1_camera_1a23a43693897e77995d8be6d1b15fe62c}
```cpp
void mavsdk::Camera::subscribe_video_stream_info(VideoStreamInfoCallback callback)
```


Subscribe to video stream info updates.


**Parameters**

* [VideoStreamInfoCallback](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1acd9baf073b816e46c22dbd6b599ece66) **callback** - 

### video_stream_info() {#classmavsdk_1_1_camera_1ad466621feff2d4f0f11124a36dda656c}
```cpp
VideoStreamInfo mavsdk::Camera::video_stream_info() const
```


Poll for '[VideoStreamInfo](structmavsdk_1_1_camera_1_1_video_stream_info.md)' (blocking).


**Returns**

&emsp;[VideoStreamInfo](structmavsdk_1_1_camera_1_1_video_stream_info.md) - One [VideoStreamInfo](structmavsdk_1_1_camera_1_1_video_stream_info.md) update.

### subscribe_capture_info() {#classmavsdk_1_1_camera_1a26901f1812df6253a39457d7bc230895}
```cpp
void mavsdk::Camera::subscribe_capture_info(CaptureInfoCallback callback)
```


Subscribe to capture info updates.


**Parameters**

* [CaptureInfoCallback](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a9bf5c20ea0b03ab019057829d1a3441e) **callback** - 

### subscribe_status() {#classmavsdk_1_1_camera_1ab62186cc3fc79459bde0e4704eb1e768}
```cpp
void mavsdk::Camera::subscribe_status(StatusCallback callback)
```


Subscribe to camera status updates.


**Parameters**

* [StatusCallback](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1aea925914ce854b81b67e3213840c97ad) **callback** - 

### status() {#classmavsdk_1_1_camera_1a0bb78c2b665c28b314f00f11a0f676b1}
```cpp
Status mavsdk::Camera::status() const
```


Poll for '[Status](structmavsdk_1_1_camera_1_1_status.md)' (blocking).


**Returns**

&emsp;[Status](structmavsdk_1_1_camera_1_1_status.md) - One [Status](structmavsdk_1_1_camera_1_1_status.md) update.

### subscribe_current_settings() {#classmavsdk_1_1_camera_1a460cf8f9810417e63ce2643df9ed014a}
```cpp
void mavsdk::Camera::subscribe_current_settings(CurrentSettingsCallback callback)
```


Get the list of current camera settings.


**Parameters**

* [CurrentSettingsCallback](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a77484487381b2579460c36d97d367fe6) **callback** - 

### subscribe_possible_setting_options() {#classmavsdk_1_1_camera_1abd8c5e18e165b319aaae9815c735b683}
```cpp
void mavsdk::Camera::subscribe_possible_setting_options(PossibleSettingOptionsCallback callback)
```


Get the list of settings that can be changed.


**Parameters**

* [PossibleSettingOptionsCallback](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a78e25614c29cd8bc1bbf26adcf417c2a) **callback** - 

### possible_setting_options() {#classmavsdk_1_1_camera_1a5416dc30ec436707420db715ee56ce08}
```cpp
std::vector<SettingOptions> mavsdk::Camera::possible_setting_options() const
```


Poll for 'std::vector<SettingOptions>' (blocking).


**Returns**

&emsp;std::vector< [SettingOptions](structmavsdk_1_1_camera_1_1_setting_options.md) > - One std::vector<SettingOptions> update.

### set_setting_async() {#classmavsdk_1_1_camera_1aace1d6ffd86a6fdf30b3466c8522feba}
```cpp
void mavsdk::Camera::set_setting_async(Setting setting, const ResultCallback callback)
```


Set a setting to some value.

Only setting_id of setting and option_id of option needs to be set.


This function is non-blocking. See 'set_setting' for the blocking counterpart.

**Parameters**

* [Setting](structmavsdk_1_1_camera_1_1_setting.md) **setting** - 
* const [ResultCallback](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a8d6d59cd8d0a3584ef60b16255b6301f) **callback** - 

### set_setting() {#classmavsdk_1_1_camera_1aa4b1293d8c6332293cccde87ec79f64a}
```cpp
Result mavsdk::Camera::set_setting(Setting setting) const
```


Set a setting to some value.

Only setting_id of setting and option_id of option needs to be set.


This function is blocking. See 'set_setting_async' for the non-blocking counterpart.

**Parameters**

* [Setting](structmavsdk_1_1_camera_1_1_setting.md) **setting** - 

**Returns**

&emsp;[Result](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcf) - Result of request.

### get_setting_async() {#classmavsdk_1_1_camera_1a6b2e4e9b5b304aff313e4f988aa6ba86}
```cpp
void mavsdk::Camera::get_setting_async(Setting setting, const GetSettingCallback callback)
```


Get a setting.

Only setting_id of setting needs to be set.


This function is non-blocking. See 'get_setting' for the blocking counterpart.

**Parameters**

* [Setting](structmavsdk_1_1_camera_1_1_setting.md) **setting** - 
* const [GetSettingCallback](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1ac233f5688f0b7f1e712bb31dfaeadd85) **callback** - 

### get_setting() {#classmavsdk_1_1_camera_1ae88917857b666dc7cfd0d84b3ad29d9c}
```cpp
std::pair<Result, Camera::Setting> mavsdk::Camera::get_setting(Setting setting) const
```


Get a setting.

Only setting_id of setting needs to be set.


This function is blocking. See 'get_setting_async' for the non-blocking counterpart.

**Parameters**

* [Setting](structmavsdk_1_1_camera_1_1_setting.md) **setting** - 

**Returns**

&emsp;std::pair< [Result](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcf), [Camera::Setting](structmavsdk_1_1_camera_1_1_setting.md) > - Result of request.

### format_storage_async() {#classmavsdk_1_1_camera_1a20455726797ece508d49fe05442fe0c1}
```cpp
void mavsdk::Camera::format_storage_async(const ResultCallback callback)
```


Format storage (e.g. SD card) in camera.

This will delete all content of the camera storage!


This function is non-blocking. See 'format_storage' for the blocking counterpart.

**Parameters**

* const [ResultCallback](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a8d6d59cd8d0a3584ef60b16255b6301f) **callback** - 

### format_storage() {#classmavsdk_1_1_camera_1a1e2d39b44251f39a395527b0170e223a}
```cpp
Result mavsdk::Camera::format_storage() const
```


Format storage (e.g. SD card) in camera.

This will delete all content of the camera storage!


This function is blocking. See 'format_storage_async' for the non-blocking counterpart.

**Returns**

&emsp;[Result](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcf) - Result of request.

### operator=() {#classmavsdk_1_1_camera_1aeff295155b6a665f5c942e473f1fe894}
```cpp
const Camera& mavsdk::Camera::operator=(const Camera &)=delete
```


Equality operator (object is not copyable).


**Parameters**

* const [Camera](classmavsdk_1_1_camera.md)&  - 

**Returns**

&emsp;const [Camera](classmavsdk_1_1_camera.md) & - 