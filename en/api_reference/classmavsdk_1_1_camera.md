# mavsdk::Camera Class Reference
`#include: camera.h`

----


The [Camera](classmavsdk_1_1_camera.md) class can be used to manage cameras that implement the MAVLink [Camera](classmavsdk_1_1_camera.md) Protocol: [https://mavlink.io/en/protocol/camera.html](https://mavlink.io/en/protocol/camera.html). 


Currently only a single camera is supported. When multiple cameras are supported the plugin will need to be instantiated separately for every camera and the camera selected using `select_camera`.


Synchronous and asynchronous variants of the camera methods are supplied. 


## Data Structures


struct [CaptureInfo](structmavsdk_1_1_camera_1_1_capture_info.md)

struct [Information](structmavsdk_1_1_camera_1_1_information.md)

struct [Option](structmavsdk_1_1_camera_1_1_option.md)

struct [Setting](structmavsdk_1_1_camera_1_1_setting.md)

struct [SettingOptions](structmavsdk_1_1_camera_1_1_setting_options.md)

struct [Status](structmavsdk_1_1_camera_1_1_status.md)

struct [VideoStreamInfo](structmavsdk_1_1_camera_1_1_video_stream_info.md)

struct [VideoStreamSettings](structmavsdk_1_1_camera_1_1_video_stream_settings.md)

## Public Types


Type | Description
--- | ---
enum [Result](#classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcf) | Possible results returned for camera commands.
enum [Mode](#classmavsdk_1_1_camera_1a02bb5ce37d125ba4c65d43f172cc2d65) | [Camera](classmavsdk_1_1_camera.md) mode type.
std::function< void([Result](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcf))> [result_callback_t](#classmavsdk_1_1_camera_1af685f3246e2c9e909acd34eede604a78) | Callback type for asynchronous [Camera](classmavsdk_1_1_camera.md) calls.
std::function< void([Result](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcf), const [Mode](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a02bb5ce37d125ba4c65d43f172cc2d65) &)> [mode_callback_t](#classmavsdk_1_1_camera_1a80ac6809a31a1fef9e398396f48c230b) | Callback type for asynchronous camera mode calls.
std::function< void([Mode](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a02bb5ce37d125ba4c65d43f172cc2d65))> [subscribe_mode_callback_t](#classmavsdk_1_1_camera_1a2e192f7058babf50350ca67b4e182311) | Callback type for camera mode subscription.
std::function< void([Result](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcf), [VideoStreamInfo](structmavsdk_1_1_camera_1_1_video_stream_info.md))> [get_video_stream_info_callback_t](#classmavsdk_1_1_camera_1aee360f2b81c01de025e09822c9f4fefb) | Callback type for asynchronous video stream info call.
std::function< void([VideoStreamInfo](structmavsdk_1_1_camera_1_1_video_stream_info.md))> [subscribe_video_stream_info_callback_t](#classmavsdk_1_1_camera_1acf186b5a738ceae773680300c25b8963) | Callback type for video stream info.
std::function< void([CaptureInfo](structmavsdk_1_1_camera_1_1_capture_info.md))> [capture_info_callback_t](#classmavsdk_1_1_camera_1aa3e2d58e59d03e02d9ddcdb8979a9d9f) | Callback type for capture info updates.
std::function< void([Result](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcf), [Status](structmavsdk_1_1_camera_1_1_status.md))> [get_status_callback_t](#classmavsdk_1_1_camera_1a032cddeed41b596da72cadd488967f81) | Callback type to get status.
std::function< void([Status](structmavsdk_1_1_camera_1_1_status.md))> [subscribe_status_callback_t](#classmavsdk_1_1_camera_1a46daf718ef0b20ef7d3dcdb92edd9107) | Callback type to subscribe to status updates.
std::function< void([Result](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcf), const [Option](structmavsdk_1_1_camera_1_1_option.md) &)> [get_option_callback_t](#classmavsdk_1_1_camera_1a30144e05163adff09295188dcf854a8c) | Callback type to get an option.
std::function< void(const std::vector< [Setting](structmavsdk_1_1_camera_1_1_setting.md) >)> [subscribe_current_settings_callback_t](#classmavsdk_1_1_camera_1aec89b50d9d7aacd3999025e6af9a4537) | Callback type to get the currently selected settings.
std::function< void(const std::vector< [SettingOptions](structmavsdk_1_1_camera_1_1_setting_options.md) >)> [subscribe_possible_setting_options_callback_t](#classmavsdk_1_1_camera_1a8e6d20f6aead2fdd7ef4f5eea87afc0b) | Callback type to get possible setting options.

## Public Member Functions


Type | Name | Description
---: | --- | ---
&nbsp; | [Camera](#classmavsdk_1_1_camera_1a186a2853440c879b99ed7e4a726969e9) ([System](classmavsdk_1_1_system.md) & system) | Constructor. Creates the plugin for a specific [System](classmavsdk_1_1_system.md).
&nbsp; | [~Camera](#classmavsdk_1_1_camera_1abd845e6fb2adc386dba7c8860a67f761) () | Destructor (internal use only).
&nbsp; | [Camera](#classmavsdk_1_1_camera_1a3af73f81cf8cd051fe9d7af6f2df6945) (const [Camera](classmavsdk_1_1_camera.md) &)=delete | Copy constructor (object is not copyable).
[Result](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcf) | [select_camera](#classmavsdk_1_1_camera_1a0727be2c56a75d8eabc77c0e72bf6ab4) (unsigned id) | Select camera to interact with.
[Result](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcf) | [take_photo](#classmavsdk_1_1_camera_1a138180f7193a3f49722511b45a81b434) () | Take photo (synchronous).
[Result](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcf) | [start_photo_interval](#classmavsdk_1_1_camera_1a4a4e2724bb7dcff499173b97f99df14b) (float interval_s) | Start photo interval (synchronous).
[Result](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcf) | [stop_photo_interval](#classmavsdk_1_1_camera_1a4d1a2e4794e01c95b77b2bf13912a62b) () | Stop photo interval (synchronous).
[Result](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcf) | [start_video](#classmavsdk_1_1_camera_1ab3de7ff32dd8b87c081d6b35f5960d08) () | Start video capture (synchronous).
[Result](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcf) | [stop_video](#classmavsdk_1_1_camera_1afaac17787c6c4b32368f0e928fa1bc26) () | Stop video capture (synchronous).
void | [take_photo_async](#classmavsdk_1_1_camera_1ae959fc926fc5ce4f21ee81e1b9ae7e81) (const [result_callback_t](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1af685f3246e2c9e909acd34eede604a78) & callback) | Take photo (asynchronous).
void | [start_photo_interval_async](#classmavsdk_1_1_camera_1a732ceb505de508eb091f0b2c57e364c4) (float interval_s, const [result_callback_t](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1af685f3246e2c9e909acd34eede604a78) & callback) | Start photo interval (asynchronous).
void | [stop_photo_interval_async](#classmavsdk_1_1_camera_1ac421c8b59b2da667436ee735d31b5c8e) (const [result_callback_t](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1af685f3246e2c9e909acd34eede604a78) & callback) | Stop photo interval (asynchronous).
void | [start_video_async](#classmavsdk_1_1_camera_1a59500409cb9b6b375e2fb95c4e65981e) (const [result_callback_t](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1af685f3246e2c9e909acd34eede604a78) & callback) | Start video capture (asynchronous).
void | [stop_video_async](#classmavsdk_1_1_camera_1a2af00a4739fda46a97699a5445244934) (const [result_callback_t](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1af685f3246e2c9e909acd34eede604a78) & callback) | Stop video capture (asynchronous).
[Information](structmavsdk_1_1_camera_1_1_information.md) | [get_information](#classmavsdk_1_1_camera_1a4f53cc13faad6d1e7232881f0cdd4e8f) () | Get general camera information.
[Result](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcf) | [set_mode](#classmavsdk_1_1_camera_1a557241d62d86433781fe86c0c039ada3) (const [Mode](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a02bb5ce37d125ba4c65d43f172cc2d65) mode) | Setter for camera mode (synchronous).
void | [set_mode_async](#classmavsdk_1_1_camera_1ab8baf90189d997be33689444af28d299) (const [Mode](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a02bb5ce37d125ba4c65d43f172cc2d65) mode, const [mode_callback_t](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a80ac6809a31a1fef9e398396f48c230b) & callback) | Setter for camera mode (asynchronous).
void | [get_mode_async](#classmavsdk_1_1_camera_1a8c6ea001c393a0d49d19be54d5195a44) (const [mode_callback_t](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a80ac6809a31a1fef9e398396f48c230b) & callback) | Getter for camera mode (asynchronous).
void | [subscribe_mode](#classmavsdk_1_1_camera_1aa366c1ac76c8083996a97d86cb1769e7) (const [subscribe_mode_callback_t](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a2e192f7058babf50350ca67b4e182311) callback) | Async subscription for camera mode updates (asynchronous).
[Result](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcf) | [get_video_stream_info](#classmavsdk_1_1_camera_1a6e099070d34896daffae871b5def94e3) ([VideoStreamInfo](structmavsdk_1_1_camera_1_1_video_stream_info.md) & info) | Get video stream information (synchronous).
void | [get_video_stream_info_async](#classmavsdk_1_1_camera_1ad98bdefee6ea01c7e251fcd33dbb19bf) (const [get_video_stream_info_callback_t](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1aee360f2b81c01de025e09822c9f4fefb) callback) | Get video stream information (asynchronous).
void | [subscribe_video_stream_info](#classmavsdk_1_1_camera_1aedb09a2fd502ff7f5cea812d025766b7) (const [subscribe_video_stream_info_callback_t](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1acf186b5a738ceae773680300c25b8963) callback) | Async subscription for video stream info updates (asynchronous).
[Result](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcf) | [start_video_streaming](#classmavsdk_1_1_camera_1a6a65321f94db6dd31b91acd399dbbf32) () | Starts video streaming (synchronous).
[Result](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcf) | [stop_video_streaming](#classmavsdk_1_1_camera_1a0464441361a1930495857c21812e70df) () | Stop the current video streaming (synchronous).
void | [subscribe_capture_info](#classmavsdk_1_1_camera_1a63762d5a5fc0f3cdb4c51d75080bb9cd) ([capture_info_callback_t](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1aa3e2d58e59d03e02d9ddcdb8979a9d9f) callback) | Subscribe to capture info updates (asynchronous).
void | [get_status_async](#classmavsdk_1_1_camera_1a12c606c914924700ec3290dfbb375f35) ([get_status_callback_t](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a032cddeed41b596da72cadd488967f81) callback) | Get camera status (asynchronous).
void | [subscribe_status](#classmavsdk_1_1_camera_1a3823140cea0f7e145f99cb18a34b48ad) (const [subscribe_status_callback_t](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a46daf718ef0b20ef7d3dcdb92edd9107) callback) | Subscribe to status updates (asynchronous).
bool | [get_possible_setting_options](#classmavsdk_1_1_camera_1a4d9ef3283a3fde980b7a0d864f4a3d02) (std::vector< std::string > & settings) | Get settings that can be changed.
bool | [get_possible_options](#classmavsdk_1_1_camera_1a62e79ba028ca57540c10e544737bfc34) (const std::string & setting_id, std::vector< [Camera::Option](structmavsdk_1_1_camera_1_1_option.md) > & options) | Get possible options for a setting that can be selected.
bool | [is_setting_range](#classmavsdk_1_1_camera_1ad1337a07240b1c9192170b4a265bad7b) (const std::string & setting_id) | Query if setting is a range setting.
[Camera::Result](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcf) | [get_option](#classmavsdk_1_1_camera_1a32787e97209786b50811ef2a04954560) (const std::string & setting_id, [Option](structmavsdk_1_1_camera_1_1_option.md) & option) | Get an option of a setting (synchronous).
void | [get_option_async](#classmavsdk_1_1_camera_1a766d2406904f1a06e7668bb0c2d8dd38) (const std::string & setting_id, const [get_option_callback_t](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a30144e05163adff09295188dcf854a8c) & callback) | Get an option of a setting (asynchronous).
void | [set_option_async](#classmavsdk_1_1_camera_1ad36497ef20292f8b719cd3f66844abf1) (const [result_callback_t](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1af685f3246e2c9e909acd34eede604a78) & callback, const std::string & setting_id, const [Camera::Option](structmavsdk_1_1_camera_1_1_option.md) & option) | Set an option of a setting (asynchronous).
void | [subscribe_current_settings](#classmavsdk_1_1_camera_1a86c3b93eff94958893f2a2eaf7b0af02) (const [subscribe_current_settings_callback_t](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1aec89b50d9d7aacd3999025e6af9a4537) & callback) | Subscribe to currently selected settings (asynchronous).
void | [subscribe_possible_setting_options](#classmavsdk_1_1_camera_1a1f36ef38920baf86bd2943f09cbb0f00) (const [subscribe_possible_setting_options_callback_t](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a8e6d20f6aead2fdd7ef4f5eea87afc0b) & callback) | Subscribe to all possible setting options (asynchronous).
void | [format_storage_async](#classmavsdk_1_1_camera_1a00390c325bdbf78461a5e59b786903f2) ([result_callback_t](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1af685f3246e2c9e909acd34eede604a78) callback) | Format storage (e.g. SD card) in camera (asynchronous).
[Result](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcf) | [format_storage](#classmavsdk_1_1_camera_1a347509c9f099f79b562786b6aac56f34) () | Format storage (e.g. SD card) in camera (synchronous).
const [Camera](classmavsdk_1_1_camera.md) & | [operator=](#classmavsdk_1_1_camera_1aeff295155b6a665f5c942e473f1fe894) (const [Camera](classmavsdk_1_1_camera.md) &)=delete | Equality operator (object is not copyable).

## Static Public Member Functions


Type | Name | Description
---: | --- | ---
std::string | [result_str](#classmavsdk_1_1_camera_1a1b768bb0af672b634a902a9e481c1327) ([Result](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcf) result) | Returns a human-readable English string for [Camera::Result](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcf).


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


### typedef result_callback_t {#classmavsdk_1_1_camera_1af685f3246e2c9e909acd34eede604a78}

```cpp
typedef std::function<void(Result)> mavsdk::Camera::result_callback_t
```


Callback type for asynchronous [Camera](classmavsdk_1_1_camera.md) calls.


### typedef mode_callback_t {#classmavsdk_1_1_camera_1a80ac6809a31a1fef9e398396f48c230b}

```cpp
typedef std::function<void(Result, const Mode&)> mavsdk::Camera::mode_callback_t
```


Callback type for asynchronous camera mode calls.


### typedef subscribe_mode_callback_t {#classmavsdk_1_1_camera_1a2e192f7058babf50350ca67b4e182311}

```cpp
typedef std::function<void(Mode)> mavsdk::Camera::subscribe_mode_callback_t
```


Callback type for camera mode subscription.


### typedef get_video_stream_info_callback_t {#classmavsdk_1_1_camera_1aee360f2b81c01de025e09822c9f4fefb}

```cpp
typedef std::function<void(Result, VideoStreamInfo)> mavsdk::Camera::get_video_stream_info_callback_t
```


Callback type for asynchronous video stream info call.


### typedef subscribe_video_stream_info_callback_t {#classmavsdk_1_1_camera_1acf186b5a738ceae773680300c25b8963}

```cpp
typedef std::function<void(VideoStreamInfo)> mavsdk::Camera::subscribe_video_stream_info_callback_t
```


Callback type for video stream info.


### typedef capture_info_callback_t {#classmavsdk_1_1_camera_1aa3e2d58e59d03e02d9ddcdb8979a9d9f}

```cpp
typedef std::function<void(CaptureInfo)> mavsdk::Camera::capture_info_callback_t
```


Callback type for capture info updates.


### typedef get_status_callback_t {#classmavsdk_1_1_camera_1a032cddeed41b596da72cadd488967f81}

```cpp
typedef std::function<void(Result, Status)> mavsdk::Camera::get_status_callback_t
```


Callback type to get status.


### typedef subscribe_status_callback_t {#classmavsdk_1_1_camera_1a46daf718ef0b20ef7d3dcdb92edd9107}

```cpp
typedef std::function<void(Status)> mavsdk::Camera::subscribe_status_callback_t
```


Callback type to subscribe to status updates.


### typedef get_option_callback_t {#classmavsdk_1_1_camera_1a30144e05163adff09295188dcf854a8c}

```cpp
typedef std::function<void(Result, const Option&)> mavsdk::Camera::get_option_callback_t
```


Callback type to get an option.


### typedef subscribe_current_settings_callback_t {#classmavsdk_1_1_camera_1aec89b50d9d7aacd3999025e6af9a4537}

```cpp
typedef std::function<void(const std::vector<Setting>)> mavsdk::Camera::subscribe_current_settings_callback_t
```


Callback type to get the currently selected settings.


### typedef subscribe_possible_setting_options_callback_t {#classmavsdk_1_1_camera_1a8e6d20f6aead2fdd7ef4f5eea87afc0b}

```cpp
typedef std::function<void(const std::vector<SettingOptions>)> mavsdk::Camera::subscribe_possible_setting_options_callback_t
```


Callback type to get possible setting options.


## Member Enumeration Documentation


### enum Result {#classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcf}


Possible results returned for camera commands.


Value | Description
--- | ---
<span id="classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcfa696b031073e74bf2cb98e5ef201d4aa3"></span> `UNKNOWN` | The result is unknown. 
<span id="classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcfad0749aaba8b833466dfcbb0428e4f89c"></span> `SUCCESS` | [Camera](classmavsdk_1_1_camera.md) command executed successfully. 
<span id="classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcfaca69f96c768067fbff6c911ca87bccc9"></span> `IN_PROGRESS` | [Camera](classmavsdk_1_1_camera.md) command is in progress. 
<span id="classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcfa802706a9238e2928077f97736854bad4"></span> `BUSY` | [Camera](classmavsdk_1_1_camera.md) is busy and rejected command. 
<span id="classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcfa66d5e0b0ce726b4aeb4ddf6c25b6c12b"></span> `DENIED` | [Camera](classmavsdk_1_1_camera.md) has denied the command. 
<span id="classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcfabb1ca97ec761fc37101737ba0aa2e7c5"></span> `ERROR` | An error has occurred while executing the command. 
<span id="classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcfa070a0fb40f6c308ab544b227660aadff"></span> `TIMEOUT` | [Camera](classmavsdk_1_1_camera.md) has not responded in time and the command has timed out. 
<span id="classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcfa817407ec3b637cb00de7413fd38429a1"></span> `WRONG_ARGUMENT` | The command has wrong arguments. 

### enum Mode {#classmavsdk_1_1_camera_1a02bb5ce37d125ba4c65d43f172cc2d65}


[Camera](classmavsdk_1_1_camera.md) mode type.


Value | Description
--- | ---
<span id="classmavsdk_1_1_camera_1a02bb5ce37d125ba4c65d43f172cc2d65ac6c7e64f7c3b7e4c031d022f232298bf"></span> `PHOTO` | Photo mode. 
<span id="classmavsdk_1_1_camera_1a02bb5ce37d125ba4c65d43f172cc2d65ae60ae31f67ab883c746bb71c7a145c18"></span> `VIDEO` | Video mode. 
<span id="classmavsdk_1_1_camera_1a02bb5ce37d125ba4c65d43f172cc2d65a696b031073e74bf2cb98e5ef201d4aa3"></span> `UNKNOWN` | Unknown mode. 

## Member Function Documentation


### select_camera() {#classmavsdk_1_1_camera_1a0727be2c56a75d8eabc77c0e72bf6ab4}
```cpp
Result mavsdk::Camera::select_camera(unsigned id)
```


Select camera to interact with.

It is recommended to instantiate multiple camera plugins to deal with multiple cameras and to select the camera once right after creating the plugin.

**Parameters**

* unsigned **id** - The camera ID from 0 to 5.

**Returns**

&emsp;[Result](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcf) - Result of request.

### take_photo() {#classmavsdk_1_1_camera_1a138180f7193a3f49722511b45a81b434}
```cpp
Result mavsdk::Camera::take_photo()
```


Take photo (synchronous).

This takes one photo.

**Returns**

&emsp;[Result](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcf) - Result of request.

### start_photo_interval() {#classmavsdk_1_1_camera_1a4a4e2724bb7dcff499173b97f99df14b}
```cpp
Result mavsdk::Camera::start_photo_interval(float interval_s)
```


Start photo interval (synchronous).

Starts a photo timelapse with a given interval.

**Parameters**

* float **interval_s** - The interval between photos in seconds.

**Returns**

&emsp;[Result](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcf) - Result of request.

**See Also:**
- [stop_photo_interval()](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a4d1a2e4794e01c95b77b2bf13912a62b)


### stop_photo_interval() {#classmavsdk_1_1_camera_1a4d1a2e4794e01c95b77b2bf13912a62b}
```cpp
Result mavsdk::Camera::stop_photo_interval()
```


Stop photo interval (synchronous).

Stops a photo timelapse, previously started with [start_photo_interval()](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a4a4e2724bb7dcff499173b97f99df14b).

**Returns**

&emsp;[Result](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcf) - Result of request.

### start_video() {#classmavsdk_1_1_camera_1ab3de7ff32dd8b87c081d6b35f5960d08}
```cpp
Result mavsdk::Camera::start_video()
```


Start video capture (synchronous).

This starts a video recording.

**Returns**

&emsp;[Result](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcf) - Result of request.

### stop_video() {#classmavsdk_1_1_camera_1afaac17787c6c4b32368f0e928fa1bc26}
```cpp
Result mavsdk::Camera::stop_video()
```


Stop video capture (synchronous).

This stops a video recording, previously started with [start_video()](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1ab3de7ff32dd8b87c081d6b35f5960d08).

**Returns**

&emsp;[Result](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcf) - Result of request.

### take_photo_async() {#classmavsdk_1_1_camera_1ae959fc926fc5ce4f21ee81e1b9ae7e81}
```cpp
void mavsdk::Camera::take_photo_async(const result_callback_t &callback)
```


Take photo (asynchronous).

This takes one photo.

**Parameters**

* const [result_callback_t](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1af685f3246e2c9e909acd34eede604a78)& **callback** - Function to call with result of request.

### start_photo_interval_async() {#classmavsdk_1_1_camera_1a732ceb505de508eb091f0b2c57e364c4}
```cpp
void mavsdk::Camera::start_photo_interval_async(float interval_s, const result_callback_t &callback)
```


Start photo interval (asynchronous).

Starts a photo timelapse with a given interval.

**Parameters**

* float **interval_s** - The interval between photos in seconds.
* const [result_callback_t](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1af685f3246e2c9e909acd34eede604a78)& **callback** - Function to call with result of request.

**See Also:**
- [stop_photo_interval_async](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1ac421c8b59b2da667436ee735d31b5c8e)


### stop_photo_interval_async() {#classmavsdk_1_1_camera_1ac421c8b59b2da667436ee735d31b5c8e}
```cpp
void mavsdk::Camera::stop_photo_interval_async(const result_callback_t &callback)
```


Stop photo interval (asynchronous).

Stops a photo timelapse, previously started with [start_photo_interval_async()](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a732ceb505de508eb091f0b2c57e364c4).

**Parameters**

* const [result_callback_t](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1af685f3246e2c9e909acd34eede604a78)& **callback** - Function to call with result of request.

### start_video_async() {#classmavsdk_1_1_camera_1a59500409cb9b6b375e2fb95c4e65981e}
```cpp
void mavsdk::Camera::start_video_async(const result_callback_t &callback)
```


Start video capture (asynchronous).

This starts a video recording.

**Parameters**

* const [result_callback_t](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1af685f3246e2c9e909acd34eede604a78)& **callback** - Function to call with result of request.

### stop_video_async() {#classmavsdk_1_1_camera_1a2af00a4739fda46a97699a5445244934}
```cpp
void mavsdk::Camera::stop_video_async(const result_callback_t &callback)
```


Stop video capture (asynchronous).

This stops a video recording, previously started with [start_video_async()](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a59500409cb9b6b375e2fb95c4e65981e).

**Parameters**

* const [result_callback_t](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1af685f3246e2c9e909acd34eede604a78)& **callback** - Function to call with result of request.

### get_information() {#classmavsdk_1_1_camera_1a4f53cc13faad6d1e7232881f0cdd4e8f}
```cpp
Information mavsdk::Camera::get_information()
```


Get general camera information.


**Returns**

&emsp;[Information](structmavsdk_1_1_camera_1_1_information.md) - The camera information struct.

### set_mode() {#classmavsdk_1_1_camera_1a557241d62d86433781fe86c0c039ada3}
```cpp
Result mavsdk::Camera::set_mode(const Mode mode)
```


Setter for camera mode (synchronous).


**Parameters**

* const [Mode](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a02bb5ce37d125ba4c65d43f172cc2d65) **mode** - [Camera](classmavsdk_1_1_camera.md) mode to set

**Returns**

&emsp;[Result](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcf) - SUCCESS if mode is set, error otherwise.

### set_mode_async() {#classmavsdk_1_1_camera_1ab8baf90189d997be33689444af28d299}
```cpp
void mavsdk::Camera::set_mode_async(const Mode mode, const mode_callback_t &callback)
```


Setter for camera mode (asynchronous).


**Parameters**

* const [Mode](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a02bb5ce37d125ba4c65d43f172cc2d65) **mode** - [Camera](classmavsdk_1_1_camera.md) mode to set.
* const [mode_callback_t](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a80ac6809a31a1fef9e398396f48c230b)& **callback** - Function to call with result of request.

### get_mode_async() {#classmavsdk_1_1_camera_1a8c6ea001c393a0d49d19be54d5195a44}
```cpp
void mavsdk::Camera::get_mode_async(const mode_callback_t &callback)
```


Getter for camera mode (asynchronous).


**Parameters**

* const [mode_callback_t](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a80ac6809a31a1fef9e398396f48c230b)& **callback** - Function to call with result of request.

### subscribe_mode() {#classmavsdk_1_1_camera_1aa366c1ac76c8083996a97d86cb1769e7}
```cpp
void mavsdk::Camera::subscribe_mode(const subscribe_mode_callback_t callback)
```


Async subscription for camera mode updates (asynchronous).


**Parameters**

* const [subscribe_mode_callback_t](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a2e192f7058babf50350ca67b4e182311) **callback** - Function to call with camera mode updates.

### get_video_stream_info() {#classmavsdk_1_1_camera_1a6e099070d34896daffae871b5def94e3}
```cpp
Result mavsdk::Camera::get_video_stream_info(VideoStreamInfo &info)
```


Get video stream information (synchronous).

Application may use media player like VLC and feed `uri` to play the ongoing video streaming.

**Parameters**

* [VideoStreamInfo](structmavsdk_1_1_camera_1_1_video_stream_info.md)& **info** - Video stream information will be filled.

**Returns**

&emsp;[Result](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcf) - SUCCESS if video stream info is received, error otherwise.

### get_video_stream_info_async() {#classmavsdk_1_1_camera_1ad98bdefee6ea01c7e251fcd33dbb19bf}
```cpp
void mavsdk::Camera::get_video_stream_info_async(const get_video_stream_info_callback_t callback)
```


Get video stream information (asynchronous).


**Parameters**

* const [get_video_stream_info_callback_t](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1aee360f2b81c01de025e09822c9f4fefb) **callback** - Function to call with video stream info.

### subscribe_video_stream_info() {#classmavsdk_1_1_camera_1aedb09a2fd502ff7f5cea812d025766b7}
```cpp
void mavsdk::Camera::subscribe_video_stream_info(const subscribe_video_stream_info_callback_t callback)
```


Async subscription for video stream info updates (asynchronous).


**Parameters**

* const [subscribe_video_stream_info_callback_t](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1acf186b5a738ceae773680300c25b8963) **callback** - Function to call with video stream updates.

### start_video_streaming() {#classmavsdk_1_1_camera_1a6a65321f94db6dd31b91acd399dbbf32}
```cpp
Result mavsdk::Camera::start_video_streaming()
```


Starts video streaming (synchronous).

Sends a request to start video streaming.

**Returns**

&emsp;[Result](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcf) - SUCCESS if video streaming is started, error otherwise.

**See Also:**
- [stop_video_streaming()](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a0464441361a1930495857c21812e70df)


### stop_video_streaming() {#classmavsdk_1_1_camera_1a0464441361a1930495857c21812e70df}
```cpp
Result mavsdk::Camera::stop_video_streaming()
```


Stop the current video streaming (synchronous).

Sends a request to stop ongoing video streaming.

**Returns**

&emsp;[Result](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcf) - SUCCESS if video streaming is stopped, error otherwise.

**See Also:**
- [start_video_streaming()](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a6a65321f94db6dd31b91acd399dbbf32)


### subscribe_capture_info() {#classmavsdk_1_1_camera_1a63762d5a5fc0f3cdb4c51d75080bb9cd}
```cpp
void mavsdk::Camera::subscribe_capture_info(capture_info_callback_t callback)
```


Subscribe to capture info updates (asynchronous).


**Parameters**

* [capture_info_callback_t](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1aa3e2d58e59d03e02d9ddcdb8979a9d9f) **callback** - Function to call with updates.

### get_status_async() {#classmavsdk_1_1_camera_1a12c606c914924700ec3290dfbb375f35}
```cpp
void mavsdk::Camera::get_status_async(get_status_callback_t callback)
```


Get camera status (asynchronous).


**Parameters**

* [get_status_callback_t](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a032cddeed41b596da72cadd488967f81) **callback** - Function to call with camera status.

### subscribe_status() {#classmavsdk_1_1_camera_1a3823140cea0f7e145f99cb18a34b48ad}
```cpp
void mavsdk::Camera::subscribe_status(const subscribe_status_callback_t callback)
```


Subscribe to status updates (asynchronous).


**Parameters**

* const [subscribe_status_callback_t](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a46daf718ef0b20ef7d3dcdb92edd9107) **callback** - Function to call with status update.

### get_possible_setting_options() {#classmavsdk_1_1_camera_1a4d9ef3283a3fde980b7a0d864f4a3d02}
```cpp
bool mavsdk::Camera::get_possible_setting_options(std::vector< std::string > &settings)
```


Get settings that can be changed.


**Parameters**

* std::vector< std::string >& **settings** - List of settings that can be changed.

**Returns**

&emsp;bool - true request was successful.

### get_possible_options() {#classmavsdk_1_1_camera_1a62e79ba028ca57540c10e544737bfc34}
```cpp
bool mavsdk::Camera::get_possible_options(const std::string &setting_id, std::vector< Camera::Option > &options)
```


Get possible options for a setting that can be selected.


**Parameters**

* const std::string& **setting_id** - Name of setting (machine readable).
* std::vector< [Camera::Option](structmavsdk_1_1_camera_1_1_option.md) >& **options** - List of [Option](structmavsdk_1_1_camera_1_1_option.md) objects to select from.

**Returns**

&emsp;bool - true if request was successful.

### is_setting_range() {#classmavsdk_1_1_camera_1ad1337a07240b1c9192170b4a265bad7b}
```cpp
bool mavsdk::Camera::is_setting_range(const std::string &setting_id)
```


Query if setting is a range setting.

A range setting is not given by possible options but rather by [min, max] or [min, max, interval].

**Parameters**

* const std::string& **setting_id** - Name of setting (machine readable).

**Returns**

&emsp;bool - true if it is a range setting.

### get_option() {#classmavsdk_1_1_camera_1a32787e97209786b50811ef2a04954560}
```cpp
Camera::Result mavsdk::Camera::get_option(const std::string &setting_id, Option &option)
```


Get an option of a setting (synchronous).


**Parameters**

* const std::string& **setting_id** - The machine readable name of the setting.
* [Option](structmavsdk_1_1_camera_1_1_option.md)& **option** - A reference to the option to set.

**Returns**

&emsp;[Camera::Result](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcf) - Result of request.

### get_option_async() {#classmavsdk_1_1_camera_1a766d2406904f1a06e7668bb0c2d8dd38}
```cpp
void mavsdk::Camera::get_option_async(const std::string &setting_id, const get_option_callback_t &callback)
```


Get an option of a setting (asynchronous).


**Parameters**

* const std::string& **setting_id** - The machine readable name of the setting.
* const [get_option_callback_t](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a30144e05163adff09295188dcf854a8c)& **callback** - The callback to get the result and selected option.

### set_option_async() {#classmavsdk_1_1_camera_1ad36497ef20292f8b719cd3f66844abf1}
```cpp
void mavsdk::Camera::set_option_async(const result_callback_t &callback, const std::string &setting_id, const Camera::Option &option)
```


Set an option of a setting (asynchronous).


**Parameters**

* const [result_callback_t](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1af685f3246e2c9e909acd34eede604a78)& **callback** - The callback to get the result.
* const std::string& **setting_id** - The machine readable name of the setting.
* const [Camera::Option](structmavsdk_1_1_camera_1_1_option.md)& **option** - The machine readable name of the option value.

### subscribe_current_settings() {#classmavsdk_1_1_camera_1a86c3b93eff94958893f2a2eaf7b0af02}
```cpp
void mavsdk::Camera::subscribe_current_settings(const subscribe_current_settings_callback_t &callback)
```


Subscribe to currently selected settings (asynchronous).


**Parameters**

* const [subscribe_current_settings_callback_t](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1aec89b50d9d7aacd3999025e6af9a4537)& **callback** - Function to call when current options have been updated.

### subscribe_possible_setting_options() {#classmavsdk_1_1_camera_1a1f36ef38920baf86bd2943f09cbb0f00}
```cpp
void mavsdk::Camera::subscribe_possible_setting_options(const subscribe_possible_setting_options_callback_t &callback)
```


Subscribe to all possible setting options (asynchronous).


**Parameters**

* const [subscribe_possible_setting_options_callback_t](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a8e6d20f6aead2fdd7ef4f5eea87afc0b)& **callback** - Function to call when possible options have been updated.

### format_storage_async() {#classmavsdk_1_1_camera_1a00390c325bdbf78461a5e59b786903f2}
```cpp
void mavsdk::Camera::format_storage_async(result_callback_t callback)
```


Format storage (e.g. SD card) in camera (asynchronous).

> **Note** This will delete all content of the camera storage (e.g. SD card).

**Parameters**

* [result_callback_t](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1af685f3246e2c9e909acd34eede604a78) **callback** - Callback to get result.

### format_storage() {#classmavsdk_1_1_camera_1a347509c9f099f79b562786b6aac56f34}
```cpp
Result mavsdk::Camera::format_storage()
```


Format storage (e.g. SD card) in camera (synchronous).

> **Note** This will delete all content of the camera storage (e.g. SD card).

**Returns**

&emsp;[Result](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcf) - result of request.

### operator=() {#classmavsdk_1_1_camera_1aeff295155b6a665f5c942e473f1fe894}
```cpp
const Camera& mavsdk::Camera::operator=(const Camera &)=delete
```


Equality operator (object is not copyable).


**Parameters**

* const [Camera](classmavsdk_1_1_camera.md)&  - 

**Returns**

&emsp;const [Camera](classmavsdk_1_1_camera.md) & - 

### result_str() {#classmavsdk_1_1_camera_1a1b768bb0af672b634a902a9e481c1327}
```cpp
static std::string mavsdk::Camera::result_str(Result result)
```


Returns a human-readable English string for [Camera::Result](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcf).


**Parameters**

* [Result](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcf) **result** - The enum value for which a human readable string is required.

**Returns**

&emsp;std::string - Human readable string for the [Camera::Result](classmavsdk_1_1_camera.md#classmavsdk_1_1_camera_1a2a84df3938372f4f302576227b308bcf).