# dronecore::Camera Class Reference
`#include: camera.h`

----


The [Camera](classdronecore_1_1_camera.md) class can be used to manage cameras that implement the MAVLink [Camera](classdronecore_1_1_camera.md) Protocol: [https://mavlink.io/en/protocol/camera.html](https://mavlink.io/en/protocol/camera.html). 


Currently only a single camera is supported. When multiple cameras are supported the plugin will need to be instantiated separately for every camera.


Synchronous and asynchronous variants of the camera methods are supplied. 


## Data Structures


struct [CaptureInfo](structdronecore_1_1_camera_1_1_capture_info.md)

struct [Option](structdronecore_1_1_camera_1_1_option.md)

struct [Setting](structdronecore_1_1_camera_1_1_setting.md)

struct [SettingOptions](structdronecore_1_1_camera_1_1_setting_options.md)

struct [Status](structdronecore_1_1_camera_1_1_status.md)

struct [VideoStreamInfo](structdronecore_1_1_camera_1_1_video_stream_info.md)

struct [VideoStreamSettings](structdronecore_1_1_camera_1_1_video_stream_settings.md)

## Public Types


Type | Description
--- | ---
enum [Result](#classdronecore_1_1_camera_1ac4006505d99fc66a8c7516ecd3222a41) | Possible results returned for camera commands.
enum [Mode](#classdronecore_1_1_camera_1a06a76346c678cfe6789b3420951c8e53) | [Camera](classdronecore_1_1_camera.md) mode type.
std::function< void([Result](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1ac4006505d99fc66a8c7516ecd3222a41))> [result_callback_t](#classdronecore_1_1_camera_1a56dad71243eb163159eb240883497de7) | Callback type for asynchronous [Camera](classdronecore_1_1_camera.md) calls.
std::function< void([Result](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1ac4006505d99fc66a8c7516ecd3222a41), const [Mode](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1a06a76346c678cfe6789b3420951c8e53) &)> [mode_callback_t](#classdronecore_1_1_camera_1aad2a5b8de0e3d131ddcea57b0362559a) | Callback type for asynchronous camera mode calls.
std::function< void([Mode](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1a06a76346c678cfe6789b3420951c8e53))> [subscribe_mode_callback_t](#classdronecore_1_1_camera_1a4e3267a37cff292ee91e20630a4ef2b7) | Callback type for camera mode subscription.
std::function< void([Result](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1ac4006505d99fc66a8c7516ecd3222a41), [VideoStreamInfo](structdronecore_1_1_camera_1_1_video_stream_info.md))> [get_video_stream_info_callback_t](#classdronecore_1_1_camera_1ae43325964469d51a76ed7f4667e225c2) | Callback type for asynchronous video stream info call.
std::function< void([VideoStreamInfo](structdronecore_1_1_camera_1_1_video_stream_info.md))> [subscribe_video_stream_info_callback_t](#classdronecore_1_1_camera_1acdb19ae46316149cc91ad40794ccfae2) | Callback type for video stream info.
std::function< void([CaptureInfo](structdronecore_1_1_camera_1_1_capture_info.md))> [capture_info_callback_t](#classdronecore_1_1_camera_1a925fa5261c7b9805d17871392881584d) | Callback type for capture info updates.
std::function< void([Result](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1ac4006505d99fc66a8c7516ecd3222a41), [Status](structdronecore_1_1_camera_1_1_status.md))> [get_status_callback_t](#classdronecore_1_1_camera_1a376de495ea22cdc282509300974c55e7) | Callback type to get status.
std::function< void([Status](structdronecore_1_1_camera_1_1_status.md))> [subscribe_status_callback_t](#classdronecore_1_1_camera_1abcb91b4600000c94a259b278d5871341) | Callback type to subscribe to status updates.
std::function< void([Result](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1ac4006505d99fc66a8c7516ecd3222a41), const [Option](structdronecore_1_1_camera_1_1_option.md) &)> [get_option_callback_t](#classdronecore_1_1_camera_1a7d2886b627b173187353ff0cf85ab095) | Callback type to get an option.
std::function< void(const std::vector< [Setting](structdronecore_1_1_camera_1_1_setting.md) >)> [subscribe_current_settings_callback_t](#classdronecore_1_1_camera_1a52cdc16021ab2137c12e795e0c63d9be) | Callback type to get the currently selected settings.
std::function< void(const std::vector< [SettingOptions](structdronecore_1_1_camera_1_1_setting_options.md) >)> [subscribe_possible_setting_options_callback_t](#classdronecore_1_1_camera_1a8d06fffefc502b906315ac1b6b937537) | Callback type to get possible setting options.

## Public Member Functions


Type | Name | Description
---: | --- | ---
&nbsp; | [Camera](#classdronecore_1_1_camera_1a1ad8f6f09e5133a4e01330b0ef8f9183) ([System](classdronecore_1_1_system.md) & system) | Constructor. Creates the plugin for a specific [System](classdronecore_1_1_system.md).
&nbsp; | [~Camera](#classdronecore_1_1_camera_1a7105f66a1b0bbd6f674177a60bc21435) () | Destructor (internal use only).
&nbsp; | [Camera](#classdronecore_1_1_camera_1a45965cb1ff1c3be05a24db698325fe7d) (const [Camera](classdronecore_1_1_camera.md) &)=delete | Copy constructor (object is not copyable).
[Result](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1ac4006505d99fc66a8c7516ecd3222a41) | [take_photo](#classdronecore_1_1_camera_1a3ae5b3eff2075e70b1dc27d75426ee97) () | Take photo (synchronous).
[Result](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1ac4006505d99fc66a8c7516ecd3222a41) | [start_photo_interval](#classdronecore_1_1_camera_1ac803f96ffcfb936998fb40e3f18bff5f) (float interval_s) | Start photo interval (synchronous).
[Result](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1ac4006505d99fc66a8c7516ecd3222a41) | [stop_photo_interval](#classdronecore_1_1_camera_1aaa97336420cdc0eb92f0b6bea54c6034) () | Stop photo interval (synchronous).
[Result](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1ac4006505d99fc66a8c7516ecd3222a41) | [start_video](#classdronecore_1_1_camera_1a142603863f6ca0ad23393279d5bd8cda) () | Start video capture (synchronous).
[Result](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1ac4006505d99fc66a8c7516ecd3222a41) | [stop_video](#classdronecore_1_1_camera_1ae38edbf0281f860ea15ef6fce9e14bbc) () | Stop video capture (synchronous).
void | [take_photo_async](#classdronecore_1_1_camera_1a9ff78b51a7ebb89913ed38e6d49cf020) (const [result_callback_t](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1a56dad71243eb163159eb240883497de7) & callback) | Take photo (asynchronous).
void | [start_photo_interval_async](#classdronecore_1_1_camera_1a38520327452e28703f633f49fc5818dd) (float interval_s, const [result_callback_t](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1a56dad71243eb163159eb240883497de7) & callback) | Start photo interval (asynchronous).
void | [stop_photo_interval_async](#classdronecore_1_1_camera_1af3c2fa47f834872ca7c01e3161180eaa) (const [result_callback_t](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1a56dad71243eb163159eb240883497de7) & callback) | Stop photo interval (asynchronous).
void | [start_video_async](#classdronecore_1_1_camera_1a816aae9a3a513616cd84859a2c11090f) (const [result_callback_t](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1a56dad71243eb163159eb240883497de7) & callback) | Start video capture (asynchronous).
void | [stop_video_async](#classdronecore_1_1_camera_1a2d4cb350fb627ea4d441e47af8a5d1a2) (const [result_callback_t](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1a56dad71243eb163159eb240883497de7) & callback) | Stop video capture (asynchronous).
[Result](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1ac4006505d99fc66a8c7516ecd3222a41) | [set_mode](#classdronecore_1_1_camera_1a842458fb0b95b8bde1e3a487c6a06636) (const [Mode](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1a06a76346c678cfe6789b3420951c8e53) mode) | Setter for camera mode (synchronous).
void | [set_mode_async](#classdronecore_1_1_camera_1a7f01420faa7069fb524574f1e8b9b09b) (const [Mode](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1a06a76346c678cfe6789b3420951c8e53) mode, const [mode_callback_t](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1aad2a5b8de0e3d131ddcea57b0362559a) & callback) | Setter for camera mode (asynchronous).
void | [get_mode_async](#classdronecore_1_1_camera_1a530d68aafeac46c4d1c16fac4b115490) (const [mode_callback_t](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1aad2a5b8de0e3d131ddcea57b0362559a) & callback) | Getter for camera mode (asynchronous).
void | [subscribe_mode](#classdronecore_1_1_camera_1a92192adffcfa2836a2354a301d3b9564) (const [subscribe_mode_callback_t](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1a4e3267a37cff292ee91e20630a4ef2b7) callback) | Async subscription for camera mode updates (asynchronous).
void | [set_video_stream_settings](#classdronecore_1_1_camera_1a9a059a12960396051500fa7f4e2710f7) (const [VideoStreamSettings](structdronecore_1_1_camera_1_1_video_stream_settings.md) & settings) | Sets video stream settings.
[Result](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1ac4006505d99fc66a8c7516ecd3222a41) | [get_video_stream_info](#classdronecore_1_1_camera_1a1137d3b38b134e0e3ba7d88048448a1f) ([VideoStreamInfo](structdronecore_1_1_camera_1_1_video_stream_info.md) & info) | Get video stream information (synchronous).
void | [get_video_stream_info_async](#classdronecore_1_1_camera_1a040d6de1e162a82ceac6a29c6fc89d7b) (const [get_video_stream_info_callback_t](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1ae43325964469d51a76ed7f4667e225c2) callback) | Get video stream information (asynchronous).
void | [subscribe_video_stream_info](#classdronecore_1_1_camera_1a81e08ad87dd1fefdab5faec764580696) (const [subscribe_video_stream_info_callback_t](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1acdb19ae46316149cc91ad40794ccfae2) callback) | Async subscription for video stream info updates (asynchronous).
[Result](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1ac4006505d99fc66a8c7516ecd3222a41) | [start_video_streaming](#classdronecore_1_1_camera_1a1abbf7e3287e95c987a6d46b60f4e8fa) () | Starts video streaming (synchronous).
[Result](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1ac4006505d99fc66a8c7516ecd3222a41) | [stop_video_streaming](#classdronecore_1_1_camera_1a017f92a972bfbb96ff503d6ff83e841c) () | Stop the current video streaming (synchronous).
void | [subscribe_capture_info](#classdronecore_1_1_camera_1a1f63f8e6768346a983991a8fb1ee1a81) ([capture_info_callback_t](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1a925fa5261c7b9805d17871392881584d) callback) | Subscribe to capture info updates (asynchronous).
void | [get_status_async](#classdronecore_1_1_camera_1a9194c34754f227ecd0977fd703cd75c3) ([get_status_callback_t](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1a376de495ea22cdc282509300974c55e7) callback) | Get camera status (asynchronous).
void | [subscribe_status](#classdronecore_1_1_camera_1ac46241ea784b796e872f8f9b95131afa) (const [subscribe_status_callback_t](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1abcb91b4600000c94a259b278d5871341) callback) | Subscribe to status updates (asynchronous).
bool | [get_possible_setting_options](#classdronecore_1_1_camera_1a5bf6b71f90dea0bbbd8085aef12c4708) (std::vector< std::string > & settings) | Get settings that can be changed.
bool | [get_possible_options](#classdronecore_1_1_camera_1a362918b271c0aa64b5babb52fa3fb97e) (const std::string & setting_id, std::vector< [Camera::Option](structdronecore_1_1_camera_1_1_option.md) > & options) | Get possible options for a setting that can be selected.
[Camera::Result](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1ac4006505d99fc66a8c7516ecd3222a41) | [get_option](#classdronecore_1_1_camera_1a5cc192617ec521243d211148278995d6) (const std::string & setting_id, [Option](structdronecore_1_1_camera_1_1_option.md) & option) | Get an option of a setting (synchronous).
void | [get_option_async](#classdronecore_1_1_camera_1a1790674987daca13023ace4b88c9b771) (const std::string & setting_id, const [get_option_callback_t](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1a7d2886b627b173187353ff0cf85ab095) & callback) | Get an option of a setting (asynchronous).
void | [set_option_async](#classdronecore_1_1_camera_1ae3ec816ae7bc2ea4b69171f8c337630f) (const std::string & setting_id, const [Camera::Option](structdronecore_1_1_camera_1_1_option.md) & option, const [result_callback_t](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1a56dad71243eb163159eb240883497de7) & callback) | Set an option of a setting (asynchronous).
void | [subscribe_current_settings](#classdronecore_1_1_camera_1a00f75426185ebb44ced8fa161d0e7936) (const [subscribe_current_settings_callback_t](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1a52cdc16021ab2137c12e795e0c63d9be) & callback) | Subscribe to currently selected settings (asynchronous).
void | [subscribe_possible_setting_options](#classdronecore_1_1_camera_1aab77e07e0c13a992aa3fffde8678d540) (const [subscribe_possible_setting_options_callback_t](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1a8d06fffefc502b906315ac1b6b937537) & callback) | Subscribe to all possible setting options (asynchronous).
bool | [get_setting_str](#classdronecore_1_1_camera_1a7f0360e3bfea462e449adfcb35a67c0a) (const std::string & setting_id, std::string & description) | Get the human readable string of a setting.
bool | [get_option_str](#classdronecore_1_1_camera_1ab453950007c9d5c2976aefd752bd12a4) (const std::string & setting_id, const std::string & option_id, std::string & description) | Get the human readable string of an option.
const [Camera](classdronecore_1_1_camera.md) & | [operator=](#classdronecore_1_1_camera_1a909c0921d5920653a2b8a7a2e030ca29) (const [Camera](classdronecore_1_1_camera.md) &)=delete | Equality operator (object is not copyable).

## Static Public Member Functions


Type | Name | Description
---: | --- | ---
std::string | [result_str](#classdronecore_1_1_camera_1af319f7ae74920a72917a10fecf9ac4d0) ([Result](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1ac4006505d99fc66a8c7516ecd3222a41) result) | Returns a human-readable English string for [Camera::Result](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1ac4006505d99fc66a8c7516ecd3222a41).


## Constructor & Destructor Documentation


### Camera() {#classdronecore_1_1_camera_1a1ad8f6f09e5133a4e01330b0ef8f9183}
```cpp
dronecore::Camera::Camera(System &system)
```


Constructor. Creates the plugin for a specific [System](classdronecore_1_1_system.md).

The plugin is typically created as shown below: 

```cpp
auto camera = std::make_shared<Camera>(system);
```

**Parameters**

* [System](classdronecore_1_1_system.md)& **system** - The specific system associated with this plugin.

### ~Camera() {#classdronecore_1_1_camera_1a7105f66a1b0bbd6f674177a60bc21435}
```cpp
dronecore::Camera::~Camera()
```


Destructor (internal use only).


### Camera() {#classdronecore_1_1_camera_1a45965cb1ff1c3be05a24db698325fe7d}
```cpp
dronecore::Camera::Camera(const Camera &)=delete
```


Copy constructor (object is not copyable).


**Parameters**

* const [Camera](classdronecore_1_1_camera.md)&  - 

## Member Typdef Documentation


### typedef result_callback_t {#classdronecore_1_1_camera_1a56dad71243eb163159eb240883497de7}

```cpp
typedef std::function<void(Result)> dronecore::Camera::result_callback_t
```


Callback type for asynchronous [Camera](classdronecore_1_1_camera.md) calls.


### typedef mode_callback_t {#classdronecore_1_1_camera_1aad2a5b8de0e3d131ddcea57b0362559a}

```cpp
typedef std::function<void(Result, const Mode &)> dronecore::Camera::mode_callback_t
```


Callback type for asynchronous camera mode calls.


### typedef subscribe_mode_callback_t {#classdronecore_1_1_camera_1a4e3267a37cff292ee91e20630a4ef2b7}

```cpp
typedef std::function<void(Mode)> dronecore::Camera::subscribe_mode_callback_t
```


Callback type for camera mode subscription.


### typedef get_video_stream_info_callback_t {#classdronecore_1_1_camera_1ae43325964469d51a76ed7f4667e225c2}

```cpp
typedef std::function<void(Result, VideoStreamInfo)> dronecore::Camera::get_video_stream_info_callback_t
```


Callback type for asynchronous video stream info call.


### typedef subscribe_video_stream_info_callback_t {#classdronecore_1_1_camera_1acdb19ae46316149cc91ad40794ccfae2}

```cpp
typedef std::function<void(VideoStreamInfo)> dronecore::Camera::subscribe_video_stream_info_callback_t
```


Callback type for video stream info.


### typedef capture_info_callback_t {#classdronecore_1_1_camera_1a925fa5261c7b9805d17871392881584d}

```cpp
typedef std::function<void(CaptureInfo)> dronecore::Camera::capture_info_callback_t
```


Callback type for capture info updates.


### typedef get_status_callback_t {#classdronecore_1_1_camera_1a376de495ea22cdc282509300974c55e7}

```cpp
typedef std::function<void(Result, Status)> dronecore::Camera::get_status_callback_t
```


Callback type to get status.


### typedef subscribe_status_callback_t {#classdronecore_1_1_camera_1abcb91b4600000c94a259b278d5871341}

```cpp
typedef std::function<void(Status)> dronecore::Camera::subscribe_status_callback_t
```


Callback type to subscribe to status updates.


### typedef get_option_callback_t {#classdronecore_1_1_camera_1a7d2886b627b173187353ff0cf85ab095}

```cpp
typedef std::function<void(Result, const Option &)> dronecore::Camera::get_option_callback_t
```


Callback type to get an option.


### typedef subscribe_current_settings_callback_t {#classdronecore_1_1_camera_1a52cdc16021ab2137c12e795e0c63d9be}

```cpp
typedef std::function<void(const std::vector<Setting>)> dronecore::Camera::subscribe_current_settings_callback_t
```


Callback type to get the currently selected settings.


### typedef subscribe_possible_setting_options_callback_t {#classdronecore_1_1_camera_1a8d06fffefc502b906315ac1b6b937537}

```cpp
typedef std::function<void(const std::vector<SettingOptions>)> dronecore::Camera::subscribe_possible_setting_options_callback_t
```


Callback type to get possible setting options.


## Member Enumeration Documentation


### enum Result {#classdronecore_1_1_camera_1ac4006505d99fc66a8c7516ecd3222a41}


Possible results returned for camera commands.


Value | Description
--- | ---
<span id="classdronecore_1_1_camera_1ac4006505d99fc66a8c7516ecd3222a41a696b031073e74bf2cb98e5ef201d4aa3"></span> `UNKNOWN` | The result is unknown. 
<span id="classdronecore_1_1_camera_1ac4006505d99fc66a8c7516ecd3222a41ad0749aaba8b833466dfcbb0428e4f89c"></span> `SUCCESS` | [Camera](classdronecore_1_1_camera.md) command executed successfully. 
<span id="classdronecore_1_1_camera_1ac4006505d99fc66a8c7516ecd3222a41aca69f96c768067fbff6c911ca87bccc9"></span> `IN_PROGRESS` | [Camera](classdronecore_1_1_camera.md) command is in progress. 
<span id="classdronecore_1_1_camera_1ac4006505d99fc66a8c7516ecd3222a41a802706a9238e2928077f97736854bad4"></span> `BUSY` | [Camera](classdronecore_1_1_camera.md) is busy and rejected command. 
<span id="classdronecore_1_1_camera_1ac4006505d99fc66a8c7516ecd3222a41a66d5e0b0ce726b4aeb4ddf6c25b6c12b"></span> `DENIED` | [Camera](classdronecore_1_1_camera.md) has denied the command. 
<span id="classdronecore_1_1_camera_1ac4006505d99fc66a8c7516ecd3222a41abb1ca97ec761fc37101737ba0aa2e7c5"></span> `ERROR` | An error has occurred while executing the command. 
<span id="classdronecore_1_1_camera_1ac4006505d99fc66a8c7516ecd3222a41a070a0fb40f6c308ab544b227660aadff"></span> `TIMEOUT` | [Camera](classdronecore_1_1_camera.md) has not responded in time and the command has timed out. 
<span id="classdronecore_1_1_camera_1ac4006505d99fc66a8c7516ecd3222a41a817407ec3b637cb00de7413fd38429a1"></span> `WRONG_ARGUMENT` | The command has wrong arguments. 

### enum Mode {#classdronecore_1_1_camera_1a06a76346c678cfe6789b3420951c8e53}


[Camera](classdronecore_1_1_camera.md) mode type.


Value | Description
--- | ---
<span id="classdronecore_1_1_camera_1a06a76346c678cfe6789b3420951c8e53ac6c7e64f7c3b7e4c031d022f232298bf"></span> `PHOTO` | Photo mode. 
<span id="classdronecore_1_1_camera_1a06a76346c678cfe6789b3420951c8e53ae60ae31f67ab883c746bb71c7a145c18"></span> `VIDEO` | Video mode. 
<span id="classdronecore_1_1_camera_1a06a76346c678cfe6789b3420951c8e53a696b031073e74bf2cb98e5ef201d4aa3"></span> `UNKNOWN` | Unknown mode. 

## Member Function Documentation


### take_photo() {#classdronecore_1_1_camera_1a3ae5b3eff2075e70b1dc27d75426ee97}
```cpp
Result dronecore::Camera::take_photo()
```


Take photo (synchronous).

This takes one photo.

**Returns**

&emsp;[Result](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1ac4006505d99fc66a8c7516ecd3222a41) - Result of request.

### start_photo_interval() {#classdronecore_1_1_camera_1ac803f96ffcfb936998fb40e3f18bff5f}
```cpp
Result dronecore::Camera::start_photo_interval(float interval_s)
```


Start photo interval (synchronous).

Starts a photo timelapse with a given interval.

**Parameters**

* float **interval_s** - The interval between photos in seconds.

**Returns**

&emsp;[Result](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1ac4006505d99fc66a8c7516ecd3222a41) - Result of request.

**See Also:**
- [stop_photo_interval()](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1aaa97336420cdc0eb92f0b6bea54c6034)


### stop_photo_interval() {#classdronecore_1_1_camera_1aaa97336420cdc0eb92f0b6bea54c6034}
```cpp
Result dronecore::Camera::stop_photo_interval()
```


Stop photo interval (synchronous).

Stops a photo timelapse, previously started with [start_photo_interval()](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1ac803f96ffcfb936998fb40e3f18bff5f).

**Returns**

&emsp;[Result](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1ac4006505d99fc66a8c7516ecd3222a41) - Result of request.

### start_video() {#classdronecore_1_1_camera_1a142603863f6ca0ad23393279d5bd8cda}
```cpp
Result dronecore::Camera::start_video()
```


Start video capture (synchronous).

This starts a video recording.

**Returns**

&emsp;[Result](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1ac4006505d99fc66a8c7516ecd3222a41) - Result of request.

### stop_video() {#classdronecore_1_1_camera_1ae38edbf0281f860ea15ef6fce9e14bbc}
```cpp
Result dronecore::Camera::stop_video()
```


Stop video capture (synchronous).

This stops a video recording, previously started with [start_video()](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1a142603863f6ca0ad23393279d5bd8cda).

**Returns**

&emsp;[Result](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1ac4006505d99fc66a8c7516ecd3222a41) - Result of request.

### take_photo_async() {#classdronecore_1_1_camera_1a9ff78b51a7ebb89913ed38e6d49cf020}
```cpp
void dronecore::Camera::take_photo_async(const result_callback_t &callback)
```


Take photo (asynchronous).

This takes one photo.

**Parameters**

* const [result_callback_t](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1a56dad71243eb163159eb240883497de7)& **callback** - Function to call with result of request.

### start_photo_interval_async() {#classdronecore_1_1_camera_1a38520327452e28703f633f49fc5818dd}
```cpp
void dronecore::Camera::start_photo_interval_async(float interval_s, const result_callback_t &callback)
```


Start photo interval (asynchronous).

Starts a photo timelapse with a given interval.

**Parameters**

* float **interval_s** - The interval between photos in seconds.
* const [result_callback_t](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1a56dad71243eb163159eb240883497de7)& **callback** - Function to call with result of request.

**See Also:**
- [stop_photo_interval_async](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1af3c2fa47f834872ca7c01e3161180eaa)


### stop_photo_interval_async() {#classdronecore_1_1_camera_1af3c2fa47f834872ca7c01e3161180eaa}
```cpp
void dronecore::Camera::stop_photo_interval_async(const result_callback_t &callback)
```


Stop photo interval (asynchronous).

Stops a photo timelapse, previously started with [start_photo_interval_async()](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1a38520327452e28703f633f49fc5818dd).

**Parameters**

* const [result_callback_t](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1a56dad71243eb163159eb240883497de7)& **callback** - Function to call with result of request.

### start_video_async() {#classdronecore_1_1_camera_1a816aae9a3a513616cd84859a2c11090f}
```cpp
void dronecore::Camera::start_video_async(const result_callback_t &callback)
```


Start video capture (asynchronous).

This starts a video recording.

**Parameters**

* const [result_callback_t](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1a56dad71243eb163159eb240883497de7)& **callback** - Function to call with result of request.

### stop_video_async() {#classdronecore_1_1_camera_1a2d4cb350fb627ea4d441e47af8a5d1a2}
```cpp
void dronecore::Camera::stop_video_async(const result_callback_t &callback)
```


Stop video capture (asynchronous).

This stops a video recording, previously started with [start_video_async()](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1a816aae9a3a513616cd84859a2c11090f).

**Parameters**

* const [result_callback_t](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1a56dad71243eb163159eb240883497de7)& **callback** - Function to call with result of request.

### set_mode() {#classdronecore_1_1_camera_1a842458fb0b95b8bde1e3a487c6a06636}
```cpp
Result dronecore::Camera::set_mode(const Mode mode)
```


Setter for camera mode (synchronous).


**Parameters**

* const [Mode](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1a06a76346c678cfe6789b3420951c8e53) **mode** - [Camera](classdronecore_1_1_camera.md) mode to set

**Returns**

&emsp;[Result](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1ac4006505d99fc66a8c7516ecd3222a41) - SUCCESS if mode is set, error otherwise.

### set_mode_async() {#classdronecore_1_1_camera_1a7f01420faa7069fb524574f1e8b9b09b}
```cpp
void dronecore::Camera::set_mode_async(const Mode mode, const mode_callback_t &callback)
```


Setter for camera mode (asynchronous).


**Parameters**

* const [Mode](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1a06a76346c678cfe6789b3420951c8e53) **mode** - [Camera](classdronecore_1_1_camera.md) mode to set.
* const [mode_callback_t](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1aad2a5b8de0e3d131ddcea57b0362559a)& **callback** - Function to call with result of request.

### get_mode_async() {#classdronecore_1_1_camera_1a530d68aafeac46c4d1c16fac4b115490}
```cpp
void dronecore::Camera::get_mode_async(const mode_callback_t &callback)
```


Getter for camera mode (asynchronous).


**Parameters**

* const [mode_callback_t](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1aad2a5b8de0e3d131ddcea57b0362559a)& **callback** - Function to call with result of request.

### subscribe_mode() {#classdronecore_1_1_camera_1a92192adffcfa2836a2354a301d3b9564}
```cpp
void dronecore::Camera::subscribe_mode(const subscribe_mode_callback_t callback)
```


Async subscription for camera mode updates (asynchronous).


**Parameters**

* const [subscribe_mode_callback_t](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1a4e3267a37cff292ee91e20630a4ef2b7) **callback** - Function to call with camera mode updates.

### set_video_stream_settings() {#classdronecore_1_1_camera_1a9a059a12960396051500fa7f4e2710f7}
```cpp
void dronecore::Camera::set_video_stream_settings(const VideoStreamSettings &settings)
```


Sets video stream settings.


**Parameters**

* const [VideoStreamSettings](structdronecore_1_1_camera_1_1_video_stream_settings.md)& **settings** - Reference to custom video stream settings which include resolution, framerate, bitrate, etc.

### get_video_stream_info() {#classdronecore_1_1_camera_1a1137d3b38b134e0e3ba7d88048448a1f}
```cpp
Result dronecore::Camera::get_video_stream_info(VideoStreamInfo &info)
```


Get video stream information (synchronous).

Application may use media player like VLC and feed `uri` to play the ongoing video streaming.

**Parameters**

* [VideoStreamInfo](structdronecore_1_1_camera_1_1_video_stream_info.md)& **info** - Video stream information will be filled.

**Returns**

&emsp;[Result](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1ac4006505d99fc66a8c7516ecd3222a41) - SUCCESS if video stream info is received, error otherwise.

### get_video_stream_info_async() {#classdronecore_1_1_camera_1a040d6de1e162a82ceac6a29c6fc89d7b}
```cpp
void dronecore::Camera::get_video_stream_info_async(const get_video_stream_info_callback_t callback)
```


Get video stream information (asynchronous).


**Parameters**

* const [get_video_stream_info_callback_t](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1ae43325964469d51a76ed7f4667e225c2) **callback** - Function to call with video stream info.

### subscribe_video_stream_info() {#classdronecore_1_1_camera_1a81e08ad87dd1fefdab5faec764580696}
```cpp
void dronecore::Camera::subscribe_video_stream_info(const subscribe_video_stream_info_callback_t callback)
```


Async subscription for video stream info updates (asynchronous).


**Parameters**

* const [subscribe_video_stream_info_callback_t](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1acdb19ae46316149cc91ad40794ccfae2) **callback** - Function to call with video stream updates.

### start_video_streaming() {#classdronecore_1_1_camera_1a1abbf7e3287e95c987a6d46b60f4e8fa}
```cpp
Result dronecore::Camera::start_video_streaming()
```


Starts video streaming (synchronous).

Sends a request to start video streaming.

**Returns**

&emsp;[Result](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1ac4006505d99fc66a8c7516ecd3222a41) - SUCCESS if video streaming is started, error otherwise.

**See Also:**
- [stop_video_streaming()](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1a017f92a972bfbb96ff503d6ff83e841c)


### stop_video_streaming() {#classdronecore_1_1_camera_1a017f92a972bfbb96ff503d6ff83e841c}
```cpp
Result dronecore::Camera::stop_video_streaming()
```


Stop the current video streaming (synchronous).

Sends a request to stop ongoing video streaming.

**Returns**

&emsp;[Result](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1ac4006505d99fc66a8c7516ecd3222a41) - SUCCESS if video streaming is stopped, error otherwise.

**See Also:**
- [start_video_streaming()](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1a1abbf7e3287e95c987a6d46b60f4e8fa)


### subscribe_capture_info() {#classdronecore_1_1_camera_1a1f63f8e6768346a983991a8fb1ee1a81}
```cpp
void dronecore::Camera::subscribe_capture_info(capture_info_callback_t callback)
```


Subscribe to capture info updates (asynchronous).


**Parameters**

* [capture_info_callback_t](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1a925fa5261c7b9805d17871392881584d) **callback** - Function to call with updates.

### get_status_async() {#classdronecore_1_1_camera_1a9194c34754f227ecd0977fd703cd75c3}
```cpp
void dronecore::Camera::get_status_async(get_status_callback_t callback)
```


Get camera status (asynchronous).


**Parameters**

* [get_status_callback_t](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1a376de495ea22cdc282509300974c55e7) **callback** - Function to call with camera status.

### subscribe_status() {#classdronecore_1_1_camera_1ac46241ea784b796e872f8f9b95131afa}
```cpp
void dronecore::Camera::subscribe_status(const subscribe_status_callback_t callback)
```


Subscribe to status updates (asynchronous).


**Parameters**

* const [subscribe_status_callback_t](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1abcb91b4600000c94a259b278d5871341) **callback** - Function to call with status update.

### get_possible_setting_options() {#classdronecore_1_1_camera_1a5bf6b71f90dea0bbbd8085aef12c4708}
```cpp
bool dronecore::Camera::get_possible_setting_options(std::vector< std::string > &settings)
```


Get settings that can be changed.

The list of settings consists of machine readable parameters, for a human readable desription of the setting use [get_setting_str()](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1a7f0360e3bfea462e449adfcb35a67c0a).

**Parameters**

* std::vector< std::string >& **settings** - List of settings that can be changed.

**Returns**

&emsp;bool - true request was successful.

**See Also:**
- [get_setting_str](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1a7f0360e3bfea462e449adfcb35a67c0a)


### get_possible_options() {#classdronecore_1_1_camera_1a362918b271c0aa64b5babb52fa3fb97e}
```cpp
bool dronecore::Camera::get_possible_options(const std::string &setting_id, std::vector< Camera::Option > &options)
```


Get possible options for a setting that can be selected.

The list of options consists of machine readable option values, for a human readable description of the option use [get_option_str()](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1ab453950007c9d5c2976aefd752bd12a4).

**Parameters**

* const std::string& **setting_id** - Name of setting (machine readable).
* std::vector< [Camera::Option](structdronecore_1_1_camera_1_1_option.md) >& **options** - List of [Option](structdronecore_1_1_camera_1_1_option.md) objects to select from.

**Returns**

&emsp;bool - true if request was successful.

**See Also:**
- [get_option_str](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1ab453950007c9d5c2976aefd752bd12a4)


### get_option() {#classdronecore_1_1_camera_1a5cc192617ec521243d211148278995d6}
```cpp
Camera::Result dronecore::Camera::get_option(const std::string &setting_id, Option &option)
```


Get an option of a setting (synchronous).


**Parameters**

* const std::string& **setting_id** - The machine readable name of the setting.
* [Option](structdronecore_1_1_camera_1_1_option.md)& **option** - A reference to the option to set.

**Returns**

&emsp;[Camera::Result](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1ac4006505d99fc66a8c7516ecd3222a41) - Result of request.

### get_option_async() {#classdronecore_1_1_camera_1a1790674987daca13023ace4b88c9b771}
```cpp
void dronecore::Camera::get_option_async(const std::string &setting_id, const get_option_callback_t &callback)
```


Get an option of a setting (asynchronous).


**Parameters**

* const std::string& **setting_id** - The machine readable name of the setting.
* const [get_option_callback_t](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1a7d2886b627b173187353ff0cf85ab095)& **callback** - The callback to get the result and selected option.

### set_option_async() {#classdronecore_1_1_camera_1ae3ec816ae7bc2ea4b69171f8c337630f}
```cpp
void dronecore::Camera::set_option_async(const std::string &setting_id, const Camera::Option &option, const result_callback_t &callback)
```


Set an option of a setting (asynchronous).


**Parameters**

* const std::string& **setting_id** - The machine readable name of the setting.
* const [Camera::Option](structdronecore_1_1_camera_1_1_option.md)& **option** - The machine readable name of the option value.
* const [result_callback_t](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1a56dad71243eb163159eb240883497de7)& **callback** - The callback to get the result.

### subscribe_current_settings() {#classdronecore_1_1_camera_1a00f75426185ebb44ced8fa161d0e7936}
```cpp
void dronecore::Camera::subscribe_current_settings(const subscribe_current_settings_callback_t &callback)
```


Subscribe to currently selected settings (asynchronous).


**Parameters**

* const [subscribe_current_settings_callback_t](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1a52cdc16021ab2137c12e795e0c63d9be)& **callback** - Function to call when current options have been updated.

### subscribe_possible_setting_options() {#classdronecore_1_1_camera_1aab77e07e0c13a992aa3fffde8678d540}
```cpp
void dronecore::Camera::subscribe_possible_setting_options(const subscribe_possible_setting_options_callback_t &callback)
```


Subscribe to all possible setting options (asynchronous).


**Parameters**

* const [subscribe_possible_setting_options_callback_t](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1a8d06fffefc502b906315ac1b6b937537)& **callback** - Function to call when possible options have been updated.

### get_setting_str() {#classdronecore_1_1_camera_1a7f0360e3bfea462e449adfcb35a67c0a}
```cpp
bool dronecore::Camera::get_setting_str(const std::string &setting_id, std::string &description)
```


Get the human readable string of a setting.


**Parameters**

* const std::string& **setting_id** - The machine readable setting name.
* std::string& **description** - The human readable string of the setting to get.

**Returns**

&emsp;bool - true if call was successful and the description has been set.

### get_option_str() {#classdronecore_1_1_camera_1ab453950007c9d5c2976aefd752bd12a4}
```cpp
bool dronecore::Camera::get_option_str(const std::string &setting_id, const std::string &option_id, std::string &description)
```


Get the human readable string of an option.


**Parameters**

* const std::string& **setting_id** - The machine readable setting name.
* const std::string& **option_id** - The machine readable option value.
* std::string& **description** - The human readable string of the option to get.

**Returns**

&emsp;bool - true if call was successful and the description has been set.

### operator=() {#classdronecore_1_1_camera_1a909c0921d5920653a2b8a7a2e030ca29}
```cpp
const Camera& dronecore::Camera::operator=(const Camera &)=delete
```


Equality operator (object is not copyable).


**Parameters**

* const [Camera](classdronecore_1_1_camera.md)&  - 

**Returns**

&emsp;const [Camera](classdronecore_1_1_camera.md) & - 

### result_str() {#classdronecore_1_1_camera_1af319f7ae74920a72917a10fecf9ac4d0}
```cpp
static std::string dronecore::Camera::result_str(Result result)
```


Returns a human-readable English string for [Camera::Result](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1ac4006505d99fc66a8c7516ecd3222a41).


**Parameters**

* [Result](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1ac4006505d99fc66a8c7516ecd3222a41) **result** - The enum value for which a human readable string is required.

**Returns**

&emsp;std::string - Human readable string for the [Camera::Result](classdronecore_1_1_camera.md#classdronecore_1_1_camera_1ac4006505d99fc66a8c7516ecd3222a41).