# mavsdk::Gimbal Class Reference
`#include: gimbal.h`

----


The [Gimbal](classmavsdk_1_1_gimbal.md) class provides control over a gimbal. 


Synchronous and asynchronous variants of the gimbal methods are supplied. 


## Public Types


Type | Description
--- | ---
enum [Result](#classmavsdk_1_1_gimbal_1aa732ec0bd49ac03b7910199d635f76ac) | Possible results returned for gimbal commands.
enum [GimbalMode](#classmavsdk_1_1_gimbal_1afb92614c5d5915d3960bcea51bec2dca) | [Gimbal](classmavsdk_1_1_gimbal.md) mode type.
std::function< void([Result](classmavsdk_1_1_gimbal.md#classmavsdk_1_1_gimbal_1aa732ec0bd49ac03b7910199d635f76ac))> [result_callback_t](#classmavsdk_1_1_gimbal_1a477da8c10a4598415f26270ad0cc1a81) | Callback type for asynchronous [Gimbal](classmavsdk_1_1_gimbal.md) calls.

## Public Member Functions


Type | Name | Description
---: | --- | ---
&nbsp; | [Gimbal](#classmavsdk_1_1_gimbal_1aa33f4df704c7f09698884083c379f787) ([System](classmavsdk_1_1_system.md) & system) | Constructor. Creates the plugin for a specific [System](classmavsdk_1_1_system.md).
&nbsp; | [~Gimbal](#classmavsdk_1_1_gimbal_1ae5047b7edcfc7086c8e80c758bdf98ee) () | Destructor (internal use only).
&nbsp; | [Gimbal](#classmavsdk_1_1_gimbal_1a1d1a20bd30dafe3adc7b326f3eeb3c68) (const [Gimbal](classmavsdk_1_1_gimbal.md) &)=delete | Copy constructor (object is not copyable).
[Result](classmavsdk_1_1_gimbal.md#classmavsdk_1_1_gimbal_1aa732ec0bd49ac03b7910199d635f76ac) | [set_pitch_and_yaw](#classmavsdk_1_1_gimbal_1a1a0c7a510f7246e60d35f57c9636c7e3) (float pitch_deg, float yaw_deg) | Set gimbal pitch and yaw angles (synchronous).
void | [set_pitch_and_yaw_async](#classmavsdk_1_1_gimbal_1a46aa5276963e1a2afecd3e0b29569e50) (float pitch_deg, float yaw_deg, [result_callback_t](classmavsdk_1_1_gimbal.md#classmavsdk_1_1_gimbal_1a477da8c10a4598415f26270ad0cc1a81) callback) | Set gimbal pitch and yaw angles (asynchronous).
[Result](classmavsdk_1_1_gimbal.md#classmavsdk_1_1_gimbal_1aa732ec0bd49ac03b7910199d635f76ac) | [set_gimbal_mode](#classmavsdk_1_1_gimbal_1aae13a825ba0ba8691f016c65159d9233) (const [Gimbal::GimbalMode](classmavsdk_1_1_gimbal.md#classmavsdk_1_1_gimbal_1afb92614c5d5915d3960bcea51bec2dca) gimbal_mode) | Set gimbal mode (synchronous).
void | [set_gimbal_mode_async](#classmavsdk_1_1_gimbal_1ab365a81bfb4a880a5389b29a80ad1458) (const [Gimbal::GimbalMode](classmavsdk_1_1_gimbal.md#classmavsdk_1_1_gimbal_1afb92614c5d5915d3960bcea51bec2dca) gimbal_mode, [result_callback_t](classmavsdk_1_1_gimbal.md#classmavsdk_1_1_gimbal_1a477da8c10a4598415f26270ad0cc1a81) callback) | Set gimbal mode (asynchronous).
[Result](classmavsdk_1_1_gimbal.md#classmavsdk_1_1_gimbal_1aa732ec0bd49ac03b7910199d635f76ac) | [set_roi_location](#classmavsdk_1_1_gimbal_1a903b755a37238f3f042c6cd19bc5ad0a) (double latitude_deg, double longitude_deg, float altitude_m) | Set gimbal region of interest (ROI).
void | [set_roi_location_async](#classmavsdk_1_1_gimbal_1ad76f24fc98adbe32caaf86bb5d1a2f4f) (double latitude_deg, double longitude_deg, float altitude_m, [result_callback_t](classmavsdk_1_1_gimbal.md#classmavsdk_1_1_gimbal_1a477da8c10a4598415f26270ad0cc1a81) callback) | Set gimbal region of interest (ROI) (asynchronous).
const [Gimbal](classmavsdk_1_1_gimbal.md) & | [operator=](#classmavsdk_1_1_gimbal_1ac9a6e1936f58ce8f957be7c6bcc0d134) (const [Gimbal](classmavsdk_1_1_gimbal.md) &)=delete | Equality operator (object is not copyable).

## Static Public Member Functions


Type | Name | Description
---: | --- | ---
const char * | [result_str](#classmavsdk_1_1_gimbal_1a0ba5f2b1d1570a1bc322e1bb0bdbf9cb) ([Result](classmavsdk_1_1_gimbal.md#classmavsdk_1_1_gimbal_1aa732ec0bd49ac03b7910199d635f76ac) result) | Returns a human-readable English string for [Gimbal::Result](classmavsdk_1_1_gimbal.md#classmavsdk_1_1_gimbal_1aa732ec0bd49ac03b7910199d635f76ac).


## Constructor & Destructor Documentation


### Gimbal() {#classmavsdk_1_1_gimbal_1aa33f4df704c7f09698884083c379f787}
```cpp
mavsdk::Gimbal::Gimbal(System &system)
```


Constructor. Creates the plugin for a specific [System](classmavsdk_1_1_system.md).

The plugin is typically created as shown below: 

```cpp
auto gimbal = std::make_shared<Gimbal>(system);
```

**Parameters**

* [System](classmavsdk_1_1_system.md)& **system** - The specific system associated with this plugin.

### ~Gimbal() {#classmavsdk_1_1_gimbal_1ae5047b7edcfc7086c8e80c758bdf98ee}
```cpp
mavsdk::Gimbal::~Gimbal()
```


Destructor (internal use only).


### Gimbal() {#classmavsdk_1_1_gimbal_1a1d1a20bd30dafe3adc7b326f3eeb3c68}
```cpp
mavsdk::Gimbal::Gimbal(const Gimbal &)=delete
```


Copy constructor (object is not copyable).


**Parameters**

* const [Gimbal](classmavsdk_1_1_gimbal.md)&  - 

## Member Typdef Documentation


### typedef result_callback_t {#classmavsdk_1_1_gimbal_1a477da8c10a4598415f26270ad0cc1a81}

```cpp
typedef std::function<void(Result)> mavsdk::Gimbal::result_callback_t
```


Callback type for asynchronous [Gimbal](classmavsdk_1_1_gimbal.md) calls.


## Member Enumeration Documentation


### enum Result {#classmavsdk_1_1_gimbal_1aa732ec0bd49ac03b7910199d635f76ac}


Possible results returned for gimbal commands.


Value | Description
--- | ---
<span id="classmavsdk_1_1_gimbal_1aa732ec0bd49ac03b7910199d635f76acad0749aaba8b833466dfcbb0428e4f89c"></span> `SUCCESS` | Success. The gimbal command was accepted. 
<span id="classmavsdk_1_1_gimbal_1aa732ec0bd49ac03b7910199d635f76acabb1ca97ec761fc37101737ba0aa2e7c5"></span> `ERROR` | Error. An error occured sending the command. 
<span id="classmavsdk_1_1_gimbal_1aa732ec0bd49ac03b7910199d635f76aca070a0fb40f6c308ab544b227660aadff"></span> `TIMEOUT` | Timeout. A timeout occured sending the command. 
<span id="classmavsdk_1_1_gimbal_1aa732ec0bd49ac03b7910199d635f76aca696b031073e74bf2cb98e5ef201d4aa3"></span> `UNKNOWN` | Unspecified error. 

### enum GimbalMode {#classmavsdk_1_1_gimbal_1afb92614c5d5915d3960bcea51bec2dca}


[Gimbal](classmavsdk_1_1_gimbal.md) mode type.


Value | Description
--- | ---
<span id="classmavsdk_1_1_gimbal_1afb92614c5d5915d3960bcea51bec2dcaa1aa9914a1c1c677bc17d35b26ee85533"></span> `YAW_FOLLOW` | Yaw follow mode. 
<span id="classmavsdk_1_1_gimbal_1afb92614c5d5915d3960bcea51bec2dcaa8790c7f1484d0e41ece170a55490901c"></span> `YAW_LOCK` | Yaw lock mode. 

## Member Function Documentation


### set_pitch_and_yaw() {#classmavsdk_1_1_gimbal_1a1a0c7a510f7246e60d35f57c9636c7e3}
```cpp
Result mavsdk::Gimbal::set_pitch_and_yaw(float pitch_deg, float yaw_deg)
```


Set gimbal pitch and yaw angles (synchronous).

This sets the desired pitch and yaw angles of a gimbal. The function will return when the command is accepted, however, it might take the gimbal longer to actually be set to the new angles.

**Parameters**

* float **pitch_deg** - The pitch angle in degrees. Negative to point down.
* float **yaw_deg** - The yaw angle in degrees. Positive for clock-wise, range -180..180 or 0..360. The yaw angle is relative to vehicle heading if the `GimbalMode` is `YAW_FOLLOW` and relative to absolute North if the `GimbalMode` is `YAW_LOCK`.

**Returns**

&emsp;[Result](classmavsdk_1_1_gimbal.md#classmavsdk_1_1_gimbal_1aa732ec0bd49ac03b7910199d635f76ac) - Result of request.

### set_pitch_and_yaw_async() {#classmavsdk_1_1_gimbal_1a46aa5276963e1a2afecd3e0b29569e50}
```cpp
void mavsdk::Gimbal::set_pitch_and_yaw_async(float pitch_deg, float yaw_deg, result_callback_t callback)
```


Set gimbal pitch and yaw angles (asynchronous).

This sets the desired pitch and yaw angles of a gimbal. The callback will be called when the command is accepted, however, it might take the gimbal longer to actually be set to the new angles.

**Parameters**

* float **pitch_deg** - The pitch angle in degrees. Negative to point down.
* float **yaw_deg** - The yaw angle in degrees. Positive for clock-wise, range -180..180 or 0..360. The yaw angle is relative to vehicle heading if the `GimbalMode` is `YAW_FOLLOW` and relative to absolute North if the `GimbalMode` is `YAW_LOCK`.
* [result_callback_t](classmavsdk_1_1_gimbal.md#classmavsdk_1_1_gimbal_1a477da8c10a4598415f26270ad0cc1a81) **callback** - Function to call with result of request.

### set_gimbal_mode() {#classmavsdk_1_1_gimbal_1aae13a825ba0ba8691f016c65159d9233}
```cpp
Result mavsdk::Gimbal::set_gimbal_mode(const Gimbal::GimbalMode gimbal_mode)
```


Set gimbal mode (synchronous).

This sets the desired yaw mode of a gimbal. The function will return when the command is accepted, however, it might take the gimbal longer to actually be set to the new angles.

**Parameters**

* const [Gimbal::GimbalMode](classmavsdk_1_1_gimbal.md#classmavsdk_1_1_gimbal_1afb92614c5d5915d3960bcea51bec2dca) **gimbal_mode** - The mode to be set. Either yaw lock or yaw follow. Yaw lock will fix the gimbal poiting to an absolute direction. Yaw follow will point the gimbal to the vehicle heading.

**Returns**

&emsp;[Result](classmavsdk_1_1_gimbal.md#classmavsdk_1_1_gimbal_1aa732ec0bd49ac03b7910199d635f76ac) - Result of request.

### set_gimbal_mode_async() {#classmavsdk_1_1_gimbal_1ab365a81bfb4a880a5389b29a80ad1458}
```cpp
void mavsdk::Gimbal::set_gimbal_mode_async(const Gimbal::GimbalMode gimbal_mode, result_callback_t callback)
```


Set gimbal mode (asynchronous).

This sets the desired yaw mode of a gimbal. The function will return when the command is accepted, however, it might take the gimbal longer to actually be set to the new angles.

**Parameters**

* const [Gimbal::GimbalMode](classmavsdk_1_1_gimbal.md#classmavsdk_1_1_gimbal_1afb92614c5d5915d3960bcea51bec2dca) **gimbal_mode** - The mode to be set. Either yaw lock or yaw follow. Yaw lock will fix the gimbal poiting to an absolute direction. Yaw follow will point the gimbal to the vehicle heading.
* [result_callback_t](classmavsdk_1_1_gimbal.md#classmavsdk_1_1_gimbal_1a477da8c10a4598415f26270ad0cc1a81) **callback** - Function to call with result of request.

### set_roi_location() {#classmavsdk_1_1_gimbal_1a903b755a37238f3f042c6cd19bc5ad0a}
```cpp
Result mavsdk::Gimbal::set_roi_location(double latitude_deg, double longitude_deg, float altitude_m)
```


Set gimbal region of interest (ROI).

This sets a region of interest that the gimbal will point to. The gimbal will continue to point to the specified region until it receives a new command. The function will return when the command is accepted, however, it might take the gimbal longer to actually rotate to the ROI.

**Parameters**

* double **latitude_deg** - Latitude in degrees.
* double **longitude_deg** - Longitude in degrees.
* float **altitude_m** - Altitude in meters (ASML).

**Returns**

&emsp;[Result](classmavsdk_1_1_gimbal.md#classmavsdk_1_1_gimbal_1aa732ec0bd49ac03b7910199d635f76ac) - Result of request.

### set_roi_location_async() {#classmavsdk_1_1_gimbal_1ad76f24fc98adbe32caaf86bb5d1a2f4f}
```cpp
void mavsdk::Gimbal::set_roi_location_async(double latitude_deg, double longitude_deg, float altitude_m, result_callback_t callback)
```


Set gimbal region of interest (ROI) (asynchronous).

This sets a region of interest that the gimbal will point to. The gimbal will continue to point to the specified region until it receives a new command. The callback will be called when the command is accepted, however, it might take the gimbal longer to actually be set to the new angles.

**Parameters**

* double **latitude_deg** - Latitude in degrees.
* double **longitude_deg** - Longitude in degrees.
* float **altitude_m** - Altitude in meters (ASML).
* [result_callback_t](classmavsdk_1_1_gimbal.md#classmavsdk_1_1_gimbal_1a477da8c10a4598415f26270ad0cc1a81) **callback** - Function to call with result of request.

### operator=() {#classmavsdk_1_1_gimbal_1ac9a6e1936f58ce8f957be7c6bcc0d134}
```cpp
const Gimbal& mavsdk::Gimbal::operator=(const Gimbal &)=delete
```


Equality operator (object is not copyable).


**Parameters**

* const [Gimbal](classmavsdk_1_1_gimbal.md)&  - 

**Returns**

&emsp;const [Gimbal](classmavsdk_1_1_gimbal.md) & - 

### result_str() {#classmavsdk_1_1_gimbal_1a0ba5f2b1d1570a1bc322e1bb0bdbf9cb}
```cpp
static const char* mavsdk::Gimbal::result_str(Result result)
```


Returns a human-readable English string for [Gimbal::Result](classmavsdk_1_1_gimbal.md#classmavsdk_1_1_gimbal_1aa732ec0bd49ac03b7910199d635f76ac).


**Parameters**

* [Result](classmavsdk_1_1_gimbal.md#classmavsdk_1_1_gimbal_1aa732ec0bd49ac03b7910199d635f76ac) **result** - The enum value for which a human readable string is required.

**Returns**

&emsp;const char * - Human readable string for the [Gimbal::Result](classmavsdk_1_1_gimbal.md#classmavsdk_1_1_gimbal_1aa732ec0bd49ac03b7910199d635f76ac).