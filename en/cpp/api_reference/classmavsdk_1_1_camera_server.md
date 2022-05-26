# mavsdk::CameraServer Class Reference
`#include: camera_server.h`

----


Provides handling of camera trigger commands. 


## Data Structures


struct [CaptureInfo](structmavsdk_1_1_camera_server_1_1_capture_info.md)

struct [Information](structmavsdk_1_1_camera_server_1_1_information.md)

struct [Position](structmavsdk_1_1_camera_server_1_1_position.md)

struct [Quaternion](structmavsdk_1_1_camera_server_1_1_quaternion.md)

## Public Types


Type | Description
--- | ---
enum [TakePhotoFeedback](#classmavsdk_1_1_camera_server_1a020b32577d70af1c042fb0617eaf638f) | Possible results when taking a photo.
enum [Result](#classmavsdk_1_1_camera_server_1aa625af622ca91165c737cffebfe57f8d) | Possible results returned for action requests.
std::function< void([Result](classmavsdk_1_1_camera_server.md#classmavsdk_1_1_camera_server_1aa625af622ca91165c737cffebfe57f8d))> [ResultCallback](#classmavsdk_1_1_camera_server_1a06aae7383f055f54a659cfce45432207) | Callback type for asynchronous [CameraServer](classmavsdk_1_1_camera_server.md) calls.
std::function< void(int32_t)> [TakePhotoCallback](#classmavsdk_1_1_camera_server_1a947529ac03c8dfac60c7c798db60a2d0) | Callback type for subscribe_take_photo.

## Public Member Functions


Type | Name | Description
---: | --- | ---
&nbsp; | [CameraServer](#classmavsdk_1_1_camera_server_1ac8575ed408d1c5f317aeec458402ccc3) (std::shared_ptr< ServerComponent > server_component) | Constructor. Creates the plugin for a ServerComponent instance.
&nbsp; | [~CameraServer](#classmavsdk_1_1_camera_server_1a6e387b798274d5e4dadb01499d91daff) () override | Destructor (internal use only).
&nbsp; | [CameraServer](#classmavsdk_1_1_camera_server_1acf1f1fcd248cf4942cd061a2345c89b9) (const [CameraServer](classmavsdk_1_1_camera_server.md) & other) | Copy constructor.
[Result](classmavsdk_1_1_camera_server.md#classmavsdk_1_1_camera_server_1aa625af622ca91165c737cffebfe57f8d) | [set_information](#classmavsdk_1_1_camera_server_1a81b6b957f11cc8764ea5bddfae88fc64) ([Information](structmavsdk_1_1_camera_server_1_1_information.md) information)const | Sets the camera information. This must be called as soon as the camera server is created.
[Result](classmavsdk_1_1_camera_server.md#classmavsdk_1_1_camera_server_1aa625af622ca91165c737cffebfe57f8d) | [set_in_progress](#classmavsdk_1_1_camera_server_1a9f4c5012412b889017c9f47d01044651) (bool in_progress)const | Sets image capture in progress status flags. This should be set to true when the camera is busy taking a photo and false when it is done.
void | [subscribe_take_photo](#classmavsdk_1_1_camera_server_1a30e1bae8e7ddaea57ab77e849a9f3d64) ([TakePhotoCallback](classmavsdk_1_1_camera_server.md#classmavsdk_1_1_camera_server_1a947529ac03c8dfac60c7c798db60a2d0) callback) | Subscribe to image capture requests. Each request received should respond to using RespondTakePhoto.
[Result](classmavsdk_1_1_camera_server.md#classmavsdk_1_1_camera_server_1aa625af622ca91165c737cffebfe57f8d) | [respond_take_photo](#classmavsdk_1_1_camera_server_1affa2204107777b389afe8e36e8628787) ([TakePhotoFeedback](classmavsdk_1_1_camera_server.md#classmavsdk_1_1_camera_server_1a020b32577d70af1c042fb0617eaf638f) take_photo_feedback, [CaptureInfo](structmavsdk_1_1_camera_server_1_1_capture_info.md) capture_info)const | Respond to an image capture request from SubscribeTakePhoto.
const [CameraServer](classmavsdk_1_1_camera_server.md) & | [operator=](#classmavsdk_1_1_camera_server_1a08a928060071a9a9e4d321403f7d446a) (const [CameraServer](classmavsdk_1_1_camera_server.md) &)=delete | Equality operator (object is not copyable).


## Constructor & Destructor Documentation


### CameraServer() {#classmavsdk_1_1_camera_server_1ac8575ed408d1c5f317aeec458402ccc3}
```cpp
mavsdk::CameraServer::CameraServer(std::shared_ptr< ServerComponent > server_component)
```


Constructor. Creates the plugin for a ServerComponent instance.

The plugin is typically created as shown below: 

```cpp
auto camera_server = CameraServer(server_component);
```

**Parameters**

* std::shared_ptr< ServerComponent > **server_component** - The ServerComponent instance associated with this server plugin.

### ~CameraServer() {#classmavsdk_1_1_camera_server_1a6e387b798274d5e4dadb01499d91daff}
```cpp
mavsdk::CameraServer::~CameraServer() override
```


Destructor (internal use only).


### CameraServer() {#classmavsdk_1_1_camera_server_1acf1f1fcd248cf4942cd061a2345c89b9}
```cpp
mavsdk::CameraServer::CameraServer(const CameraServer &other)
```


Copy constructor.


**Parameters**

* const [CameraServer](classmavsdk_1_1_camera_server.md)& **other** - 

## Member Typdef Documentation


### typedef ResultCallback {#classmavsdk_1_1_camera_server_1a06aae7383f055f54a659cfce45432207}

```cpp
using mavsdk::CameraServer::ResultCallback =  std::function<void(Result)>
```


Callback type for asynchronous [CameraServer](classmavsdk_1_1_camera_server.md) calls.


### typedef TakePhotoCallback {#classmavsdk_1_1_camera_server_1a947529ac03c8dfac60c7c798db60a2d0}

```cpp
using mavsdk::CameraServer::TakePhotoCallback =  std::function<void(int32_t)>
```


Callback type for subscribe_take_photo.


## Member Enumeration Documentation


### enum TakePhotoFeedback {#classmavsdk_1_1_camera_server_1a020b32577d70af1c042fb0617eaf638f}


Possible results when taking a photo.


Value | Description
--- | ---
<span id="classmavsdk_1_1_camera_server_1a020b32577d70af1c042fb0617eaf638fa88183b946cc5f0e8c96b2e66e1c74a7e"></span> `Unknown` | Unknown. 
<span id="classmavsdk_1_1_camera_server_1a020b32577d70af1c042fb0617eaf638faa60852f204ed8028c1c58808b746d115"></span> `Ok` | Ok. 
<span id="classmavsdk_1_1_camera_server_1a020b32577d70af1c042fb0617eaf638fad8a942ef2b04672adfafef0ad817a407"></span> `Busy` | Busy. 
<span id="classmavsdk_1_1_camera_server_1a020b32577d70af1c042fb0617eaf638fad7c8c85bf79bbe1b7188497c32c3b0ca"></span> `Failed` | Failed. 

### enum Result {#classmavsdk_1_1_camera_server_1aa625af622ca91165c737cffebfe57f8d}


Possible results returned for action requests.


Value | Description
--- | ---
<span id="classmavsdk_1_1_camera_server_1aa625af622ca91165c737cffebfe57f8da88183b946cc5f0e8c96b2e66e1c74a7e"></span> `Unknown` | Unknown result. 
<span id="classmavsdk_1_1_camera_server_1aa625af622ca91165c737cffebfe57f8da505a83f220c02df2f85c3810cd9ceb38"></span> `Success` | Command executed successfully. 
<span id="classmavsdk_1_1_camera_server_1aa625af622ca91165c737cffebfe57f8da12d868c18cb29bf58f02b504be9033fd"></span> `InProgress` | Command in progress. 
<span id="classmavsdk_1_1_camera_server_1aa625af622ca91165c737cffebfe57f8dad8a942ef2b04672adfafef0ad817a407"></span> `Busy` | [Camera](classmavsdk_1_1_camera.md) is busy and rejected command. 
<span id="classmavsdk_1_1_camera_server_1aa625af622ca91165c737cffebfe57f8da58d036b9b7f0e7eb38cfb90f1cc70a73"></span> `Denied` | [Camera](classmavsdk_1_1_camera.md) denied the command. 
<span id="classmavsdk_1_1_camera_server_1aa625af622ca91165c737cffebfe57f8da902b0d55fddef6f8d651fe1035b7d4bd"></span> `Error` | An error has occurred while executing the command. 
<span id="classmavsdk_1_1_camera_server_1aa625af622ca91165c737cffebfe57f8dac85a251cc457840f1e032f1b733e9398"></span> `Timeout` | Command timed out. 
<span id="classmavsdk_1_1_camera_server_1aa625af622ca91165c737cffebfe57f8da5a738160747f39c20e9f65416931c974"></span> `WrongArgument` | Command has wrong argument(s). 
<span id="classmavsdk_1_1_camera_server_1aa625af622ca91165c737cffebfe57f8da1119faf72ba0dfb23aeea644fed960ad"></span> `NoSystem` | No system connected. 

## Member Function Documentation


### set_information() {#classmavsdk_1_1_camera_server_1a81b6b957f11cc8764ea5bddfae88fc64}
```cpp
Result mavsdk::CameraServer::set_information(Information information) const
```


Sets the camera information. This must be called as soon as the camera server is created.

This function is blocking.

**Parameters**

* [Information](structmavsdk_1_1_camera_server_1_1_information.md) **information** - 

**Returns**

&emsp;[Result](classmavsdk_1_1_camera_server.md#classmavsdk_1_1_camera_server_1aa625af622ca91165c737cffebfe57f8d) - Result of request.

### set_in_progress() {#classmavsdk_1_1_camera_server_1a9f4c5012412b889017c9f47d01044651}
```cpp
Result mavsdk::CameraServer::set_in_progress(bool in_progress) const
```


Sets image capture in progress status flags. This should be set to true when the camera is busy taking a photo and false when it is done.

This function is blocking.

**Parameters**

* bool **in_progress** - 

**Returns**

&emsp;[Result](classmavsdk_1_1_camera_server.md#classmavsdk_1_1_camera_server_1aa625af622ca91165c737cffebfe57f8d) - Result of request.

### subscribe_take_photo() {#classmavsdk_1_1_camera_server_1a30e1bae8e7ddaea57ab77e849a9f3d64}
```cpp
void mavsdk::CameraServer::subscribe_take_photo(TakePhotoCallback callback)
```


Subscribe to image capture requests. Each request received should respond to using RespondTakePhoto.


**Parameters**

* [TakePhotoCallback](classmavsdk_1_1_camera_server.md#classmavsdk_1_1_camera_server_1a947529ac03c8dfac60c7c798db60a2d0) **callback** - 

### respond_take_photo() {#classmavsdk_1_1_camera_server_1affa2204107777b389afe8e36e8628787}
```cpp
Result mavsdk::CameraServer::respond_take_photo(TakePhotoFeedback take_photo_feedback, CaptureInfo capture_info) const
```


Respond to an image capture request from SubscribeTakePhoto.

This function is blocking.

**Parameters**

* [TakePhotoFeedback](classmavsdk_1_1_camera_server.md#classmavsdk_1_1_camera_server_1a020b32577d70af1c042fb0617eaf638f) **take_photo_feedback** - 
* [CaptureInfo](structmavsdk_1_1_camera_server_1_1_capture_info.md) **capture_info** - 

**Returns**

&emsp;[Result](classmavsdk_1_1_camera_server.md#classmavsdk_1_1_camera_server_1aa625af622ca91165c737cffebfe57f8d) - Result of request.

### operator=() {#classmavsdk_1_1_camera_server_1a08a928060071a9a9e4d321403f7d446a}
```cpp
const CameraServer& mavsdk::CameraServer::operator=(const CameraServer &)=delete
```


Equality operator (object is not copyable).


**Parameters**

* const [CameraServer](classmavsdk_1_1_camera_server.md)&  - 

**Returns**

&emsp;const [CameraServer](classmavsdk_1_1_camera_server.md) & - 