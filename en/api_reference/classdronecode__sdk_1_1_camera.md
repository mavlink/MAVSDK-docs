# dronecode_sdk::Camera Class Reference
`#include: camera.h`

----


The [Camera](classdronecode__sdk_1_1_camera.md) class can be used to manage cameras that implement the MAVLink [Camera](classdronecode__sdk_1_1_camera.md) Protocol: [https://mavlink.io/en/protocol/camera.html](https://mavlink.io/en/protocol/camera.html). 


Currently only a single camera is supported. When multiple cameras are supported the plugin will need to be instantiated separately for every camera.


Synchronous and asynchronous variants of the camera methods are supplied. 


## Data Structures


struct [CaptureInfo](structdronecode__sdk_1_1_camera_1_1_capture_info.md)

struct [Option](structdronecode__sdk_1_1_camera_1_1_option.md)

struct [Setting](structdronecode__sdk_1_1_camera_1_1_setting.md)

struct [SettingOptions](structdronecode__sdk_1_1_camera_1_1_setting_options.md)

struct [Status](structdronecode__sdk_1_1_camera_1_1_status.md)

struct [VideoStreamInfo](structdronecode__sdk_1_1_camera_1_1_video_stream_info.md)

struct [VideoStreamSettings](structdronecode__sdk_1_1_camera_1_1_video_stream_settings.md)

## Public Types


Type | Description
--- | ---
enum [Result](#classdronecode__sdk_1_1_camera_1af195d32b1a669d8dbb28220b45f7c069) | Possible results returned for camera commands.
enum [Mode](#classdronecode__sdk_1_1_camera_1abfab7c03f8ed13db0fe856c4e392f99c) | [Camera](classdronecode__sdk_1_1_camera.md) mode type.
std::function< void([Result](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1af195d32b1a669d8dbb28220b45f7c069))> [result_callback_t](#classdronecode__sdk_1_1_camera_1ac5397f374d932c39d2ea91a882c65350) | Callback type for asynchronous [Camera](classdronecode__sdk_1_1_camera.md) calls.
std::function< void([Result](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1af195d32b1a669d8dbb28220b45f7c069), const [Mode](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1abfab7c03f8ed13db0fe856c4e392f99c) &)> [mode_callback_t](#classdronecode__sdk_1_1_camera_1a13c53bd44c1f67c837ba81a532fb6f32) | Callback type for asynchronous camera mode calls.
std::function< void([Mode](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1abfab7c03f8ed13db0fe856c4e392f99c))> [subscribe_mode_callback_t](#classdronecode__sdk_1_1_camera_1a31df879f6cde86c5df70f71e93aa87e0) | Callback type for camera mode subscription.
std::function< void([Result](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1af195d32b1a669d8dbb28220b45f7c069), [VideoStreamInfo](structdronecode__sdk_1_1_camera_1_1_video_stream_info.md))> [get_video_stream_info_callback_t](#classdronecode__sdk_1_1_camera_1a24ad01b78c1650ee1aa3203009b94535) | Callback type for asynchronous video stream info call.
std::function< void([VideoStreamInfo](structdronecode__sdk_1_1_camera_1_1_video_stream_info.md))> [subscribe_video_stream_info_callback_t](#classdronecode__sdk_1_1_camera_1a73f812431af1dd50b557034ceaace539) | Callback type for video stream info.
std::function< void([CaptureInfo](structdronecode__sdk_1_1_camera_1_1_capture_info.md))> [capture_info_callback_t](#classdronecode__sdk_1_1_camera_1aa9233aee79ba22838c08a5fdd56b234a) | Callback type for capture info updates.
std::function< void([Result](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1af195d32b1a669d8dbb28220b45f7c069), [Status](structdronecode__sdk_1_1_camera_1_1_status.md))> [get_status_callback_t](#classdronecode__sdk_1_1_camera_1a9dd22288151e16ea6df8ada5514b7f84) | Callback type to get status.
std::function< void([Status](structdronecode__sdk_1_1_camera_1_1_status.md))> [subscribe_status_callback_t](#classdronecode__sdk_1_1_camera_1aa899e84ebac5575cb3ace38faa7bebfe) | Callback type to subscribe to status updates.
std::function< void([Result](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1af195d32b1a669d8dbb28220b45f7c069), const [Option](structdronecode__sdk_1_1_camera_1_1_option.md) &)> [get_option_callback_t](#classdronecode__sdk_1_1_camera_1a35680fbbfbd46601c772a7b0ed434fb7) | Callback type to get an option.
std::function< void(const std::vector< [Setting](structdronecode__sdk_1_1_camera_1_1_setting.md) >)> [subscribe_current_settings_callback_t](#classdronecode__sdk_1_1_camera_1a69ac5b28b392c02bc6d24e917f0323d3) | Callback type to get the currently selected settings.
std::function< void(const std::vector< [SettingOptions](structdronecode__sdk_1_1_camera_1_1_setting_options.md) >)> [subscribe_possible_setting_options_callback_t](#classdronecode__sdk_1_1_camera_1a6873ea9adf206a006a234fabb48b06c2) | Callback type to get possible setting options.

## Public Member Functions


Type | Name | Description
---: | --- | ---
&nbsp; | [Camera](#classdronecode__sdk_1_1_camera_1ab578fe3d602cd2c9f916c454f00208db) ([System](classdronecode__sdk_1_1_system.md) & system) | Constructor. Creates the plugin for a specific [System](classdronecode__sdk_1_1_system.md).
&nbsp; | [~Camera](#classdronecode__sdk_1_1_camera_1a858b876e442b38f4b9953de0f5fcbfd5) () | Destructor (internal use only).
&nbsp; | [Camera](#classdronecode__sdk_1_1_camera_1a944afb176f249e97183edf97f9a3313e) (const [Camera](classdronecode__sdk_1_1_camera.md) &)=delete | Copy constructor (object is not copyable).
[Result](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1af195d32b1a669d8dbb28220b45f7c069) | [take_photo](#classdronecode__sdk_1_1_camera_1ae62b17fc618d9734aad479737a2af775) () | Take photo (synchronous).
[Result](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1af195d32b1a669d8dbb28220b45f7c069) | [start_photo_interval](#classdronecode__sdk_1_1_camera_1a8c958ad6a09ead28b6ed9cdd5be2f411) (float interval_s) | Start photo interval (synchronous).
[Result](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1af195d32b1a669d8dbb28220b45f7c069) | [stop_photo_interval](#classdronecode__sdk_1_1_camera_1adebc3692071d0309e9c3015789a5a253) () | Stop photo interval (synchronous).
[Result](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1af195d32b1a669d8dbb28220b45f7c069) | [start_video](#classdronecode__sdk_1_1_camera_1afdc040520cb1756c663bbf9d56ab872d) () | Start video capture (synchronous).
[Result](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1af195d32b1a669d8dbb28220b45f7c069) | [stop_video](#classdronecode__sdk_1_1_camera_1a02d735e03e782f21506d95ced5359f8f) () | Stop video capture (synchronous).
void | [take_photo_async](#classdronecode__sdk_1_1_camera_1a34fcaee0f41c099a82e0899d1e5f18ad) (const [result_callback_t](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1ac5397f374d932c39d2ea91a882c65350) & callback) | Take photo (asynchronous).
void | [start_photo_interval_async](#classdronecode__sdk_1_1_camera_1a912717b1180fef33285aebc5cfc7c14b) (float interval_s, const [result_callback_t](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1ac5397f374d932c39d2ea91a882c65350) & callback) | Start photo interval (asynchronous).
void | [stop_photo_interval_async](#classdronecode__sdk_1_1_camera_1a05ed862e0ab91f9ec96a1f95454d7c4b) (const [result_callback_t](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1ac5397f374d932c39d2ea91a882c65350) & callback) | Stop photo interval (asynchronous).
void | [start_video_async](#classdronecode__sdk_1_1_camera_1a2296942890cbdc7286fc17bed6a469e8) (const [result_callback_t](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1ac5397f374d932c39d2ea91a882c65350) & callback) | Start video capture (asynchronous).
void | [stop_video_async](#classdronecode__sdk_1_1_camera_1a19600848ad65b548c3aca3cd0723dd9e) (const [result_callback_t](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1ac5397f374d932c39d2ea91a882c65350) & callback) | Stop video capture (asynchronous).
[Result](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1af195d32b1a669d8dbb28220b45f7c069) | [set_mode](#classdronecode__sdk_1_1_camera_1affe639d8bf6a68872465b97420123e67) (const [Mode](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1abfab7c03f8ed13db0fe856c4e392f99c) mode) | Setter for camera mode (synchronous).
void | [set_mode_async](#classdronecode__sdk_1_1_camera_1acd5ead4f51a996a0fdc4565143fae43f) (const [Mode](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1abfab7c03f8ed13db0fe856c4e392f99c) mode, const [mode_callback_t](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1a13c53bd44c1f67c837ba81a532fb6f32) & callback) | Setter for camera mode (asynchronous).
void | [get_mode_async](#classdronecode__sdk_1_1_camera_1adf841eb57aee5face71f2cdfb1feec3e) (const [mode_callback_t](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1a13c53bd44c1f67c837ba81a532fb6f32) & callback) | Getter for camera mode (asynchronous).
void | [subscribe_mode](#classdronecode__sdk_1_1_camera_1ad2963aa513b1e9226d230af32c6237b3) (const [subscribe_mode_callback_t](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1a31df879f6cde86c5df70f71e93aa87e0) callback) | Async subscription for camera mode updates (asynchronous).
void | [set_video_stream_settings](#classdronecode__sdk_1_1_camera_1a3fb0697f85f6b5c92dff59d7c8bc24ad) (const [VideoStreamSettings](structdronecode__sdk_1_1_camera_1_1_video_stream_settings.md) & settings) | Sets video stream settings.
[Result](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1af195d32b1a669d8dbb28220b45f7c069) | [get_video_stream_info](#classdronecode__sdk_1_1_camera_1a8a617875ae274b4137ef05e12308ee1f) ([VideoStreamInfo](structdronecode__sdk_1_1_camera_1_1_video_stream_info.md) & info) | Get video stream information (synchronous).
void | [get_video_stream_info_async](#classdronecode__sdk_1_1_camera_1a11fdef92c6c9a713be6289c0ac9e0b1a) (const [get_video_stream_info_callback_t](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1a24ad01b78c1650ee1aa3203009b94535) callback) | Get video stream information (asynchronous).
void | [subscribe_video_stream_info](#classdronecode__sdk_1_1_camera_1ac47e74e5a267db40918b0c1ce00999b7) (const [subscribe_video_stream_info_callback_t](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1a73f812431af1dd50b557034ceaace539) callback) | Async subscription for video stream info updates (asynchronous).
[Result](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1af195d32b1a669d8dbb28220b45f7c069) | [start_video_streaming](#classdronecode__sdk_1_1_camera_1a62d02486c4a7de09a41384bb5a9c6a23) () | Starts video streaming (synchronous).
[Result](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1af195d32b1a669d8dbb28220b45f7c069) | [stop_video_streaming](#classdronecode__sdk_1_1_camera_1a56f2c88cca9e32b42a0e69c6e5493410) () | Stop the current video streaming (synchronous).
void | [subscribe_capture_info](#classdronecode__sdk_1_1_camera_1a906264e8e1c2c7cf402289b9f06f4d32) ([capture_info_callback_t](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1aa9233aee79ba22838c08a5fdd56b234a) callback) | Subscribe to capture info updates (asynchronous).
void | [get_status_async](#classdronecode__sdk_1_1_camera_1a2b652c1523e1ba36890282c8213d45c8) ([get_status_callback_t](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1a9dd22288151e16ea6df8ada5514b7f84) callback) | Get camera status (asynchronous).
void | [subscribe_status](#classdronecode__sdk_1_1_camera_1ad0f331e5fc979f2ecdc319a8c74acd15) (const [subscribe_status_callback_t](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1aa899e84ebac5575cb3ace38faa7bebfe) callback) | Subscribe to status updates (asynchronous).
bool | [get_possible_setting_options](#classdronecode__sdk_1_1_camera_1a1addc544585f7887fc139128c4347538) (std::vector< std::string > & settings) | Get settings that can be changed.
bool | [get_possible_options](#classdronecode__sdk_1_1_camera_1a2f15420107cf5efd0c1fe41ff2a007e2) (const std::string & setting_id, std::vector< [Camera::Option](structdronecode__sdk_1_1_camera_1_1_option.md) > & options) | Get possible options for a setting that can be selected.
[Camera::Result](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1af195d32b1a669d8dbb28220b45f7c069) | [get_option](#classdronecode__sdk_1_1_camera_1a339bd5252a991d761d61d92e5a5ff337) (const std::string & setting_id, [Option](structdronecode__sdk_1_1_camera_1_1_option.md) & option) | Get an option of a setting (synchronous).
void | [get_option_async](#classdronecode__sdk_1_1_camera_1a491f0ae27e7c20efcad23a06250d9e7a) (const std::string & setting_id, const [get_option_callback_t](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1a35680fbbfbd46601c772a7b0ed434fb7) & callback) | Get an option of a setting (asynchronous).
void | [set_option_async](#classdronecode__sdk_1_1_camera_1aadffb7c8d7c6b10181cda0a4b3ab66a0) (const std::string & setting_id, const [Camera::Option](structdronecode__sdk_1_1_camera_1_1_option.md) & option, const [result_callback_t](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1ac5397f374d932c39d2ea91a882c65350) & callback) | Set an option of a setting (asynchronous).
void | [subscribe_current_settings](#classdronecode__sdk_1_1_camera_1a3118ea942d89d33e66e7ae937fe3a8fc) (const [subscribe_current_settings_callback_t](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1a69ac5b28b392c02bc6d24e917f0323d3) & callback) | Subscribe to currently selected settings (asynchronous).
void | [subscribe_possible_setting_options](#classdronecode__sdk_1_1_camera_1a374904d4bde4804084c77112310eb514) (const [subscribe_possible_setting_options_callback_t](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1a6873ea9adf206a006a234fabb48b06c2) & callback) | Subscribe to all possible setting options (asynchronous).
bool | [get_setting_str](#classdronecode__sdk_1_1_camera_1a037a62e1d42815cb3bbfeecd5602197f) (const std::string & setting_id, std::string & description) | Get the human readable string of a setting.
bool | [get_option_str](#classdronecode__sdk_1_1_camera_1a3899b2a7e46c75dc8bc50c3994f269f1) (const std::string & setting_id, const std::string & option_id, std::string & description) | Get the human readable string of an option.
const [Camera](classdronecode__sdk_1_1_camera.md) & | [operator=](#classdronecode__sdk_1_1_camera_1a313b91c05716c94f8097605641968576) (const [Camera](classdronecode__sdk_1_1_camera.md) &)=delete | Equality operator (object is not copyable).

## Static Public Member Functions


Type | Name | Description
---: | --- | ---
std::string | [result_str](#classdronecode__sdk_1_1_camera_1a18f123070520ffded5397d00eebcbac2) ([Result](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1af195d32b1a669d8dbb28220b45f7c069) result) | Returns a human-readable English string for [Camera::Result](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1af195d32b1a669d8dbb28220b45f7c069).


## Constructor & Destructor Documentation


### Camera() {#classdronecode__sdk_1_1_camera_1ab578fe3d602cd2c9f916c454f00208db}
```cpp
dronecode_sdk::Camera::Camera(System &system)
```


Constructor. Creates the plugin for a specific [System](classdronecode__sdk_1_1_system.md).

The plugin is typically created as shown below: 

```cpp
auto camera = std::make_shared<Camera>(system);
```

**Parameters**

* [System](classdronecode__sdk_1_1_system.md)& **system** - The specific system associated with this plugin.

### ~Camera() {#classdronecode__sdk_1_1_camera_1a858b876e442b38f4b9953de0f5fcbfd5}
```cpp
dronecode_sdk::Camera::~Camera()
```


Destructor (internal use only).


### Camera() {#classdronecode__sdk_1_1_camera_1a944afb176f249e97183edf97f9a3313e}
```cpp
dronecode_sdk::Camera::Camera(const Camera &)=delete
```


Copy constructor (object is not copyable).


**Parameters**

* const [Camera](classdronecode__sdk_1_1_camera.md)&  - 

## Member Typdef Documentation


### typedef result_callback_t {#classdronecode__sdk_1_1_camera_1ac5397f374d932c39d2ea91a882c65350}

```cpp
typedef std::function<void(Result)> dronecode_sdk::Camera::result_callback_t
```


Callback type for asynchronous [Camera](classdronecode__sdk_1_1_camera.md) calls.


### typedef mode_callback_t {#classdronecode__sdk_1_1_camera_1a13c53bd44c1f67c837ba81a532fb6f32}

```cpp
typedef std::function<void(Result, const Mode &)> dronecode_sdk::Camera::mode_callback_t
```


Callback type for asynchronous camera mode calls.


### typedef subscribe_mode_callback_t {#classdronecode__sdk_1_1_camera_1a31df879f6cde86c5df70f71e93aa87e0}

```cpp
typedef std::function<void(Mode)> dronecode_sdk::Camera::subscribe_mode_callback_t
```


Callback type for camera mode subscription.


### typedef get_video_stream_info_callback_t {#classdronecode__sdk_1_1_camera_1a24ad01b78c1650ee1aa3203009b94535}

```cpp
typedef std::function<void(Result, VideoStreamInfo)> dronecode_sdk::Camera::get_video_stream_info_callback_t
```


Callback type for asynchronous video stream info call.


### typedef subscribe_video_stream_info_callback_t {#classdronecode__sdk_1_1_camera_1a73f812431af1dd50b557034ceaace539}

```cpp
typedef std::function<void(VideoStreamInfo)> dronecode_sdk::Camera::subscribe_video_stream_info_callback_t
```


Callback type for video stream info.


### typedef capture_info_callback_t {#classdronecode__sdk_1_1_camera_1aa9233aee79ba22838c08a5fdd56b234a}

```cpp
typedef std::function<void(CaptureInfo)> dronecode_sdk::Camera::capture_info_callback_t
```


Callback type for capture info updates.


### typedef get_status_callback_t {#classdronecode__sdk_1_1_camera_1a9dd22288151e16ea6df8ada5514b7f84}

```cpp
typedef std::function<void(Result, Status)> dronecode_sdk::Camera::get_status_callback_t
```


Callback type to get status.


### typedef subscribe_status_callback_t {#classdronecode__sdk_1_1_camera_1aa899e84ebac5575cb3ace38faa7bebfe}

```cpp
typedef std::function<void(Status)> dronecode_sdk::Camera::subscribe_status_callback_t
```


Callback type to subscribe to status updates.


### typedef get_option_callback_t {#classdronecode__sdk_1_1_camera_1a35680fbbfbd46601c772a7b0ed434fb7}

```cpp
typedef std::function<void(Result, const Option &)> dronecode_sdk::Camera::get_option_callback_t
```


Callback type to get an option.


### typedef subscribe_current_settings_callback_t {#classdronecode__sdk_1_1_camera_1a69ac5b28b392c02bc6d24e917f0323d3}

```cpp
typedef std::function<void(const std::vector<Setting>)> dronecode_sdk::Camera::subscribe_current_settings_callback_t
```


Callback type to get the currently selected settings.


### typedef subscribe_possible_setting_options_callback_t {#classdronecode__sdk_1_1_camera_1a6873ea9adf206a006a234fabb48b06c2}

```cpp
typedef std::function<void(const std::vector<SettingOptions>)> dronecode_sdk::Camera::subscribe_possible_setting_options_callback_t
```


Callback type to get possible setting options.


## Member Enumeration Documentation


### enum Result {#classdronecode__sdk_1_1_camera_1af195d32b1a669d8dbb28220b45f7c069}


Possible results returned for camera commands.


Value | Description
--- | ---
<span id="classdronecode__sdk_1_1_camera_1af195d32b1a669d8dbb28220b45f7c069a696b031073e74bf2cb98e5ef201d4aa3"></span> `UNKNOWN` | The result is unknown. 
<span id="classdronecode__sdk_1_1_camera_1af195d32b1a669d8dbb28220b45f7c069ad0749aaba8b833466dfcbb0428e4f89c"></span> `SUCCESS` | [Camera](classdronecode__sdk_1_1_camera.md) command executed successfully. 
<span id="classdronecode__sdk_1_1_camera_1af195d32b1a669d8dbb28220b45f7c069aca69f96c768067fbff6c911ca87bccc9"></span> `IN_PROGRESS` | [Camera](classdronecode__sdk_1_1_camera.md) command is in progress. 
<span id="classdronecode__sdk_1_1_camera_1af195d32b1a669d8dbb28220b45f7c069a802706a9238e2928077f97736854bad4"></span> `BUSY` | [Camera](classdronecode__sdk_1_1_camera.md) is busy and rejected command. 
<span id="classdronecode__sdk_1_1_camera_1af195d32b1a669d8dbb28220b45f7c069a66d5e0b0ce726b4aeb4ddf6c25b6c12b"></span> `DENIED` | [Camera](classdronecode__sdk_1_1_camera.md) has denied the command. 
<span id="classdronecode__sdk_1_1_camera_1af195d32b1a669d8dbb28220b45f7c069abb1ca97ec761fc37101737ba0aa2e7c5"></span> `ERROR` | An error has occurred while executing the command. 
<span id="classdronecode__sdk_1_1_camera_1af195d32b1a669d8dbb28220b45f7c069a070a0fb40f6c308ab544b227660aadff"></span> `TIMEOUT` | [Camera](classdronecode__sdk_1_1_camera.md) has not responded in time and the command has timed out. 
<span id="classdronecode__sdk_1_1_camera_1af195d32b1a669d8dbb28220b45f7c069a817407ec3b637cb00de7413fd38429a1"></span> `WRONG_ARGUMENT` | The command has wrong arguments. 

### enum Mode {#classdronecode__sdk_1_1_camera_1abfab7c03f8ed13db0fe856c4e392f99c}


[Camera](classdronecode__sdk_1_1_camera.md) mode type.


Value | Description
--- | ---
<span id="classdronecode__sdk_1_1_camera_1abfab7c03f8ed13db0fe856c4e392f99cac6c7e64f7c3b7e4c031d022f232298bf"></span> `PHOTO` | Photo mode. 
<span id="classdronecode__sdk_1_1_camera_1abfab7c03f8ed13db0fe856c4e392f99cae60ae31f67ab883c746bb71c7a145c18"></span> `VIDEO` | Video mode. 
<span id="classdronecode__sdk_1_1_camera_1abfab7c03f8ed13db0fe856c4e392f99ca696b031073e74bf2cb98e5ef201d4aa3"></span> `UNKNOWN` | Unknown mode. 

## Member Function Documentation


### take_photo() {#classdronecode__sdk_1_1_camera_1ae62b17fc618d9734aad479737a2af775}
```cpp
Result dronecode_sdk::Camera::take_photo()
```


Take photo (synchronous).

This takes one photo.

**Returns**

&emsp;[Result](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1af195d32b1a669d8dbb28220b45f7c069) - Result of request.

### start_photo_interval() {#classdronecode__sdk_1_1_camera_1a8c958ad6a09ead28b6ed9cdd5be2f411}
```cpp
Result dronecode_sdk::Camera::start_photo_interval(float interval_s)
```


Start photo interval (synchronous).

Starts a photo timelapse with a given interval.

**Parameters**

* float **interval_s** - The interval between photos in seconds.

**Returns**

&emsp;[Result](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1af195d32b1a669d8dbb28220b45f7c069) - Result of request.

**See Also:**
- [stop_photo_interval()](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1adebc3692071d0309e9c3015789a5a253)


### stop_photo_interval() {#classdronecode__sdk_1_1_camera_1adebc3692071d0309e9c3015789a5a253}
```cpp
Result dronecode_sdk::Camera::stop_photo_interval()
```


Stop photo interval (synchronous).

Stops a photo timelapse, previously started with [start_photo_interval()](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1a8c958ad6a09ead28b6ed9cdd5be2f411).

**Returns**

&emsp;[Result](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1af195d32b1a669d8dbb28220b45f7c069) - Result of request.

### start_video() {#classdronecode__sdk_1_1_camera_1afdc040520cb1756c663bbf9d56ab872d}
```cpp
Result dronecode_sdk::Camera::start_video()
```


Start video capture (synchronous).

This starts a video recording.

**Returns**

&emsp;[Result](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1af195d32b1a669d8dbb28220b45f7c069) - Result of request.

### stop_video() {#classdronecode__sdk_1_1_camera_1a02d735e03e782f21506d95ced5359f8f}
```cpp
Result dronecode_sdk::Camera::stop_video()
```


Stop video capture (synchronous).

This stops a video recording, previously started with [start_video()](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1afdc040520cb1756c663bbf9d56ab872d).

**Returns**

&emsp;[Result](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1af195d32b1a669d8dbb28220b45f7c069) - Result of request.

### take_photo_async() {#classdronecode__sdk_1_1_camera_1a34fcaee0f41c099a82e0899d1e5f18ad}
```cpp
void dronecode_sdk::Camera::take_photo_async(const result_callback_t &callback)
```


Take photo (asynchronous).

This takes one photo.

**Parameters**

* const [result_callback_t](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1ac5397f374d932c39d2ea91a882c65350)& **callback** - Function to call with result of request.

### start_photo_interval_async() {#classdronecode__sdk_1_1_camera_1a912717b1180fef33285aebc5cfc7c14b}
```cpp
void dronecode_sdk::Camera::start_photo_interval_async(float interval_s, const result_callback_t &callback)
```


Start photo interval (asynchronous).

Starts a photo timelapse with a given interval.

**Parameters**

* float **interval_s** - The interval between photos in seconds.
* const [result_callback_t](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1ac5397f374d932c39d2ea91a882c65350)& **callback** - Function to call with result of request.

**See Also:**
- [stop_photo_interval_async](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1a05ed862e0ab91f9ec96a1f95454d7c4b)


### stop_photo_interval_async() {#classdronecode__sdk_1_1_camera_1a05ed862e0ab91f9ec96a1f95454d7c4b}
```cpp
void dronecode_sdk::Camera::stop_photo_interval_async(const result_callback_t &callback)
```


Stop photo interval (asynchronous).

Stops a photo timelapse, previously started with [start_photo_interval_async()](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1a912717b1180fef33285aebc5cfc7c14b).

**Parameters**

* const [result_callback_t](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1ac5397f374d932c39d2ea91a882c65350)& **callback** - Function to call with result of request.

### start_video_async() {#classdronecode__sdk_1_1_camera_1a2296942890cbdc7286fc17bed6a469e8}
```cpp
void dronecode_sdk::Camera::start_video_async(const result_callback_t &callback)
```


Start video capture (asynchronous).

This starts a video recording.

**Parameters**

* const [result_callback_t](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1ac5397f374d932c39d2ea91a882c65350)& **callback** - Function to call with result of request.

### stop_video_async() {#classdronecode__sdk_1_1_camera_1a19600848ad65b548c3aca3cd0723dd9e}
```cpp
void dronecode_sdk::Camera::stop_video_async(const result_callback_t &callback)
```


Stop video capture (asynchronous).

This stops a video recording, previously started with [start_video_async()](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1a2296942890cbdc7286fc17bed6a469e8).

**Parameters**

* const [result_callback_t](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1ac5397f374d932c39d2ea91a882c65350)& **callback** - Function to call with result of request.

### set_mode() {#classdronecode__sdk_1_1_camera_1affe639d8bf6a68872465b97420123e67}
```cpp
Result dronecode_sdk::Camera::set_mode(const Mode mode)
```


Setter for camera mode (synchronous).


**Parameters**

* const [Mode](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1abfab7c03f8ed13db0fe856c4e392f99c) **mode** - [Camera](classdronecode__sdk_1_1_camera.md) mode to set

**Returns**

&emsp;[Result](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1af195d32b1a669d8dbb28220b45f7c069) - SUCCESS if mode is set, error otherwise.

### set_mode_async() {#classdronecode__sdk_1_1_camera_1acd5ead4f51a996a0fdc4565143fae43f}
```cpp
void dronecode_sdk::Camera::set_mode_async(const Mode mode, const mode_callback_t &callback)
```


Setter for camera mode (asynchronous).


**Parameters**

* const [Mode](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1abfab7c03f8ed13db0fe856c4e392f99c) **mode** - [Camera](classdronecode__sdk_1_1_camera.md) mode to set.
* const [mode_callback_t](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1a13c53bd44c1f67c837ba81a532fb6f32)& **callback** - Function to call with result of request.

### get_mode_async() {#classdronecode__sdk_1_1_camera_1adf841eb57aee5face71f2cdfb1feec3e}
```cpp
void dronecode_sdk::Camera::get_mode_async(const mode_callback_t &callback)
```


Getter for camera mode (asynchronous).


**Parameters**

* const [mode_callback_t](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1a13c53bd44c1f67c837ba81a532fb6f32)& **callback** - Function to call with result of request.

### subscribe_mode() {#classdronecode__sdk_1_1_camera_1ad2963aa513b1e9226d230af32c6237b3}
```cpp
void dronecode_sdk::Camera::subscribe_mode(const subscribe_mode_callback_t callback)
```


Async subscription for camera mode updates (asynchronous).


**Parameters**

* const [subscribe_mode_callback_t](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1a31df879f6cde86c5df70f71e93aa87e0) **callback** - Function to call with camera mode updates.

### set_video_stream_settings() {#classdronecode__sdk_1_1_camera_1a3fb0697f85f6b5c92dff59d7c8bc24ad}
```cpp
void dronecode_sdk::Camera::set_video_stream_settings(const VideoStreamSettings &settings)
```


Sets video stream settings.


**Parameters**

* const [VideoStreamSettings](structdronecode__sdk_1_1_camera_1_1_video_stream_settings.md)& **settings** - Reference to custom video stream settings which include resolution, framerate, bitrate, etc.

### get_video_stream_info() {#classdronecode__sdk_1_1_camera_1a8a617875ae274b4137ef05e12308ee1f}
```cpp
Result dronecode_sdk::Camera::get_video_stream_info(VideoStreamInfo &info)
```


Get video stream information (synchronous).

Application may use media player like VLC and feed `uri` to play the ongoing video streaming.

**Parameters**

* [VideoStreamInfo](structdronecode__sdk_1_1_camera_1_1_video_stream_info.md)& **info** - Video stream information will be filled.

**Returns**

&emsp;[Result](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1af195d32b1a669d8dbb28220b45f7c069) - SUCCESS if video stream info is received, error otherwise.

### get_video_stream_info_async() {#classdronecode__sdk_1_1_camera_1a11fdef92c6c9a713be6289c0ac9e0b1a}
```cpp
void dronecode_sdk::Camera::get_video_stream_info_async(const get_video_stream_info_callback_t callback)
```


Get video stream information (asynchronous).


**Parameters**

* const [get_video_stream_info_callback_t](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1a24ad01b78c1650ee1aa3203009b94535) **callback** - Function to call with video stream info.

### subscribe_video_stream_info() {#classdronecode__sdk_1_1_camera_1ac47e74e5a267db40918b0c1ce00999b7}
```cpp
void dronecode_sdk::Camera::subscribe_video_stream_info(const subscribe_video_stream_info_callback_t callback)
```


Async subscription for video stream info updates (asynchronous).


**Parameters**

* const [subscribe_video_stream_info_callback_t](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1a73f812431af1dd50b557034ceaace539) **callback** - Function to call with video stream updates.

### start_video_streaming() {#classdronecode__sdk_1_1_camera_1a62d02486c4a7de09a41384bb5a9c6a23}
```cpp
Result dronecode_sdk::Camera::start_video_streaming()
```


Starts video streaming (synchronous).

Sends a request to start video streaming.

**Returns**

&emsp;[Result](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1af195d32b1a669d8dbb28220b45f7c069) - SUCCESS if video streaming is started, error otherwise.

**See Also:**
- [stop_video_streaming()](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1a56f2c88cca9e32b42a0e69c6e5493410)


### stop_video_streaming() {#classdronecode__sdk_1_1_camera_1a56f2c88cca9e32b42a0e69c6e5493410}
```cpp
Result dronecode_sdk::Camera::stop_video_streaming()
```


Stop the current video streaming (synchronous).

Sends a request to stop ongoing video streaming.

**Returns**

&emsp;[Result](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1af195d32b1a669d8dbb28220b45f7c069) - SUCCESS if video streaming is stopped, error otherwise.

**See Also:**
- [start_video_streaming()](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1a62d02486c4a7de09a41384bb5a9c6a23)


### subscribe_capture_info() {#classdronecode__sdk_1_1_camera_1a906264e8e1c2c7cf402289b9f06f4d32}
```cpp
void dronecode_sdk::Camera::subscribe_capture_info(capture_info_callback_t callback)
```


Subscribe to capture info updates (asynchronous).


**Parameters**

* [capture_info_callback_t](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1aa9233aee79ba22838c08a5fdd56b234a) **callback** - Function to call with updates.

### get_status_async() {#classdronecode__sdk_1_1_camera_1a2b652c1523e1ba36890282c8213d45c8}
```cpp
void dronecode_sdk::Camera::get_status_async(get_status_callback_t callback)
```


Get camera status (asynchronous).


**Parameters**

* [get_status_callback_t](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1a9dd22288151e16ea6df8ada5514b7f84) **callback** - Function to call with camera status.

### subscribe_status() {#classdronecode__sdk_1_1_camera_1ad0f331e5fc979f2ecdc319a8c74acd15}
```cpp
void dronecode_sdk::Camera::subscribe_status(const subscribe_status_callback_t callback)
```


Subscribe to status updates (asynchronous).


**Parameters**

* const [subscribe_status_callback_t](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1aa899e84ebac5575cb3ace38faa7bebfe) **callback** - Function to call with status update.

### get_possible_setting_options() {#classdronecode__sdk_1_1_camera_1a1addc544585f7887fc139128c4347538}
```cpp
bool dronecode_sdk::Camera::get_possible_setting_options(std::vector< std::string > &settings)
```


Get settings that can be changed.

The list of settings consists of machine readable parameters, for a human readable desription of the setting use [get_setting_str()](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1a037a62e1d42815cb3bbfeecd5602197f).

**Parameters**

* std::vector< std::string >& **settings** - List of settings that can be changed.

**Returns**

&emsp;bool - true request was successful.

**See Also:**
- [get_setting_str](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1a037a62e1d42815cb3bbfeecd5602197f)


### get_possible_options() {#classdronecode__sdk_1_1_camera_1a2f15420107cf5efd0c1fe41ff2a007e2}
```cpp
bool dronecode_sdk::Camera::get_possible_options(const std::string &setting_id, std::vector< Camera::Option > &options)
```


Get possible options for a setting that can be selected.

The list of options consists of machine readable option values, for a human readable description of the option use [get_option_str()](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1a3899b2a7e46c75dc8bc50c3994f269f1).

**Parameters**

* const std::string& **setting_id** - Name of setting (machine readable).
* std::vector< [Camera::Option](structdronecode__sdk_1_1_camera_1_1_option.md) >& **options** - List of [Option](structdronecode__sdk_1_1_camera_1_1_option.md) objects to select from.

**Returns**

&emsp;bool - true if request was successful.

**See Also:**
- [get_option_str](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1a3899b2a7e46c75dc8bc50c3994f269f1)


### get_option() {#classdronecode__sdk_1_1_camera_1a339bd5252a991d761d61d92e5a5ff337}
```cpp
Camera::Result dronecode_sdk::Camera::get_option(const std::string &setting_id, Option &option)
```


Get an option of a setting (synchronous).


**Parameters**

* const std::string& **setting_id** - The machine readable name of the setting.
* [Option](structdronecode__sdk_1_1_camera_1_1_option.md)& **option** - A reference to the option to set.

**Returns**

&emsp;[Camera::Result](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1af195d32b1a669d8dbb28220b45f7c069) - Result of request.

### get_option_async() {#classdronecode__sdk_1_1_camera_1a491f0ae27e7c20efcad23a06250d9e7a}
```cpp
void dronecode_sdk::Camera::get_option_async(const std::string &setting_id, const get_option_callback_t &callback)
```


Get an option of a setting (asynchronous).


**Parameters**

* const std::string& **setting_id** - The machine readable name of the setting.
* const [get_option_callback_t](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1a35680fbbfbd46601c772a7b0ed434fb7)& **callback** - The callback to get the result and selected option.

### set_option_async() {#classdronecode__sdk_1_1_camera_1aadffb7c8d7c6b10181cda0a4b3ab66a0}
```cpp
void dronecode_sdk::Camera::set_option_async(const std::string &setting_id, const Camera::Option &option, const result_callback_t &callback)
```


Set an option of a setting (asynchronous).


**Parameters**

* const std::string& **setting_id** - The machine readable name of the setting.
* const [Camera::Option](structdronecode__sdk_1_1_camera_1_1_option.md)& **option** - The machine readable name of the option value.
* const [result_callback_t](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1ac5397f374d932c39d2ea91a882c65350)& **callback** - The callback to get the result.

### subscribe_current_settings() {#classdronecode__sdk_1_1_camera_1a3118ea942d89d33e66e7ae937fe3a8fc}
```cpp
void dronecode_sdk::Camera::subscribe_current_settings(const subscribe_current_settings_callback_t &callback)
```


Subscribe to currently selected settings (asynchronous).


**Parameters**

* const [subscribe_current_settings_callback_t](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1a69ac5b28b392c02bc6d24e917f0323d3)& **callback** - Function to call when current options have been updated.

### subscribe_possible_setting_options() {#classdronecode__sdk_1_1_camera_1a374904d4bde4804084c77112310eb514}
```cpp
void dronecode_sdk::Camera::subscribe_possible_setting_options(const subscribe_possible_setting_options_callback_t &callback)
```


Subscribe to all possible setting options (asynchronous).


**Parameters**

* const [subscribe_possible_setting_options_callback_t](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1a6873ea9adf206a006a234fabb48b06c2)& **callback** - Function to call when possible options have been updated.

### get_setting_str() {#classdronecode__sdk_1_1_camera_1a037a62e1d42815cb3bbfeecd5602197f}
```cpp
bool dronecode_sdk::Camera::get_setting_str(const std::string &setting_id, std::string &description)
```


Get the human readable string of a setting.


**Parameters**

* const std::string& **setting_id** - The machine readable setting name.
* std::string& **description** - The human readable string of the setting to get.

**Returns**

&emsp;bool - true if call was successful and the description has been set.

### get_option_str() {#classdronecode__sdk_1_1_camera_1a3899b2a7e46c75dc8bc50c3994f269f1}
```cpp
bool dronecode_sdk::Camera::get_option_str(const std::string &setting_id, const std::string &option_id, std::string &description)
```


Get the human readable string of an option.


**Parameters**

* const std::string& **setting_id** - The machine readable setting name.
* const std::string& **option_id** - The machine readable option value.
* std::string& **description** - The human readable string of the option to get.

**Returns**

&emsp;bool - true if call was successful and the description has been set.

### operator=() {#classdronecode__sdk_1_1_camera_1a313b91c05716c94f8097605641968576}
```cpp
const Camera& dronecode_sdk::Camera::operator=(const Camera &)=delete
```


Equality operator (object is not copyable).


**Parameters**

* const [Camera](classdronecode__sdk_1_1_camera.md)&  - 

**Returns**

&emsp;const [Camera](classdronecode__sdk_1_1_camera.md) & - 

### result_str() {#classdronecode__sdk_1_1_camera_1a18f123070520ffded5397d00eebcbac2}
```cpp
static std::string dronecode_sdk::Camera::result_str(Result result)
```


Returns a human-readable English string for [Camera::Result](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1af195d32b1a669d8dbb28220b45f7c069).


**Parameters**

* [Result](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1af195d32b1a669d8dbb28220b45f7c069) **result** - The enum value for which a human readable string is required.

**Returns**

&emsp;std::string - Human readable string for the [Camera::Result](classdronecode__sdk_1_1_camera.md#classdronecode__sdk_1_1_camera_1af195d32b1a669d8dbb28220b45f7c069).