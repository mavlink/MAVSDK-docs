# mavsdk::Gimbal Class Reference
`#include: gimbal.h`

----


Provide control over a gimbal. 


## Public Types


Type | Description
--- | ---
enum [GimbalMode](#classmavsdk_1_1_gimbal_1afb92614c5d5915d3960bcea51bec2dca) | [Gimbal](classmavsdk_1_1_gimbal.md) mode type.
enum [Result](#classmavsdk_1_1_gimbal_1aa732ec0bd49ac03b7910199d635f76ac) | Possible results returned for gimbal commands.
std::function< void([Result](classmavsdk_1_1_gimbal.md#classmavsdk_1_1_gimbal_1aa732ec0bd49ac03b7910199d635f76ac))> [ResultCallback](#classmavsdk_1_1_gimbal_1a88ee7dd17821fb9b12c44b2a3630c197) | Callback type for asynchronous [Gimbal](classmavsdk_1_1_gimbal.md) calls.

## Public Member Functions


Type | Name | Description
---: | --- | ---
&nbsp; | [Gimbal](#classmavsdk_1_1_gimbal_1aa33f4df704c7f09698884083c379f787) ([System](classmavsdk_1_1_system.md) & system) | Constructor. Creates the plugin for a specific [System](classmavsdk_1_1_system.md).
&nbsp; | [~Gimbal](#classmavsdk_1_1_gimbal_1ae5047b7edcfc7086c8e80c758bdf98ee) () | Destructor (internal use only).
&nbsp; | [Gimbal](#classmavsdk_1_1_gimbal_1a1d1a20bd30dafe3adc7b326f3eeb3c68) (const [Gimbal](classmavsdk_1_1_gimbal.md) &)=delete | Copy constructor (object is not copyable).
void | [set_pitch_and_yaw_async](#classmavsdk_1_1_gimbal_1a325a49cc256359013cbc917b3576f292) (float pitch_deg, float yaw_deg, const [ResultCallback](classmavsdk_1_1_gimbal.md#classmavsdk_1_1_gimbal_1a88ee7dd17821fb9b12c44b2a3630c197) callback) | Set gimbal pitch and yaw angles.
[Result](classmavsdk_1_1_gimbal.md#classmavsdk_1_1_gimbal_1aa732ec0bd49ac03b7910199d635f76ac) | [set_pitch_and_yaw](#classmavsdk_1_1_gimbal_1ad65ba3258833fe78f2939b9b72dc3b88) (float pitch_deg, float yaw_deg)const | Set gimbal pitch and yaw angles.
void | [set_mode_async](#classmavsdk_1_1_gimbal_1ad69853994c134b0e88d0f94744254066) ([GimbalMode](classmavsdk_1_1_gimbal.md#classmavsdk_1_1_gimbal_1afb92614c5d5915d3960bcea51bec2dca) gimbal_mode, const [ResultCallback](classmavsdk_1_1_gimbal.md#classmavsdk_1_1_gimbal_1a88ee7dd17821fb9b12c44b2a3630c197) callback) | Set gimbal mode.
[Result](classmavsdk_1_1_gimbal.md#classmavsdk_1_1_gimbal_1aa732ec0bd49ac03b7910199d635f76ac) | [set_mode](#classmavsdk_1_1_gimbal_1a037285883ceba14e0df9c7f8c19f4423) ([GimbalMode](classmavsdk_1_1_gimbal.md#classmavsdk_1_1_gimbal_1afb92614c5d5915d3960bcea51bec2dca) gimbal_mode)const | Set gimbal mode.
void | [set_roi_location_async](#classmavsdk_1_1_gimbal_1ab3c42a7042231e48dfab881030fe30c0) (double latitude_deg, double longitude_deg, float altitude_m, const [ResultCallback](classmavsdk_1_1_gimbal.md#classmavsdk_1_1_gimbal_1a88ee7dd17821fb9b12c44b2a3630c197) callback) | Set gimbal region of interest (ROI).
[Result](classmavsdk_1_1_gimbal.md#classmavsdk_1_1_gimbal_1aa732ec0bd49ac03b7910199d635f76ac) | [set_roi_location](#classmavsdk_1_1_gimbal_1a035ddc270efce19a9be54b98add57919) (double latitude_deg, double longitude_deg, float altitude_m)const | Set gimbal region of interest (ROI).
const [Gimbal](classmavsdk_1_1_gimbal.md) & | [operator=](#classmavsdk_1_1_gimbal_1ac9a6e1936f58ce8f957be7c6bcc0d134) (const [Gimbal](classmavsdk_1_1_gimbal.md) &)=delete | Equality operator (object is not copyable).


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


### typedef ResultCallback {#classmavsdk_1_1_gimbal_1a88ee7dd17821fb9b12c44b2a3630c197}

```cpp
using mavsdk::Gimbal::ResultCallback =  std::function<void(Result)>
```


Callback type for asynchronous [Gimbal](classmavsdk_1_1_gimbal.md) calls.


## Member Enumeration Documentation


### enum GimbalMode {#classmavsdk_1_1_gimbal_1afb92614c5d5915d3960bcea51bec2dca}


[Gimbal](classmavsdk_1_1_gimbal.md) mode type.


Value | Description
--- | ---
<span id="classmavsdk_1_1_gimbal_1afb92614c5d5915d3960bcea51bec2dcaae370d3502f507d9c9ea57d6fd3c4ed7b"></span> `YawFollow` | Yaw follow will point the gimbal to the vehicle heading. 
<span id="classmavsdk_1_1_gimbal_1afb92614c5d5915d3960bcea51bec2dcaaf0a46b0b7151dca1ab120e02b6e6663e"></span> `YawLock` | Yaw lock will fix the gimbal poiting to an absolute direction. 

### enum Result {#classmavsdk_1_1_gimbal_1aa732ec0bd49ac03b7910199d635f76ac}


Possible results returned for gimbal commands.


Value | Description
--- | ---
<span id="classmavsdk_1_1_gimbal_1aa732ec0bd49ac03b7910199d635f76aca88183b946cc5f0e8c96b2e66e1c74a7e"></span> `Unknown` | Unknown result. 
<span id="classmavsdk_1_1_gimbal_1aa732ec0bd49ac03b7910199d635f76aca505a83f220c02df2f85c3810cd9ceb38"></span> `Success` | Command was accepted. 
<span id="classmavsdk_1_1_gimbal_1aa732ec0bd49ac03b7910199d635f76aca902b0d55fddef6f8d651fe1035b7d4bd"></span> `Error` | Error occurred sending the command. 
<span id="classmavsdk_1_1_gimbal_1aa732ec0bd49ac03b7910199d635f76acac85a251cc457840f1e032f1b733e9398"></span> `Timeout` | Command timed out. 

## Member Function Documentation


### set_pitch_and_yaw_async() {#classmavsdk_1_1_gimbal_1a325a49cc256359013cbc917b3576f292}
```cpp
void mavsdk::Gimbal::set_pitch_and_yaw_async(float pitch_deg, float yaw_deg, const ResultCallback callback)
```


Set gimbal pitch and yaw angles.

This sets the desired pitch and yaw angles of a gimbal. Will return when the command is accepted, however, it might take the gimbal longer to actually be set to the new angles.


This function is non-blocking. See 'set_pitch_and_yaw' for the blocking counterpart.

**Parameters**

* float **pitch_deg** - 
* float **yaw_deg** - 
* const [ResultCallback](classmavsdk_1_1_gimbal.md#classmavsdk_1_1_gimbal_1a88ee7dd17821fb9b12c44b2a3630c197) **callback** - 

### set_pitch_and_yaw() {#classmavsdk_1_1_gimbal_1ad65ba3258833fe78f2939b9b72dc3b88}
```cpp
Result mavsdk::Gimbal::set_pitch_and_yaw(float pitch_deg, float yaw_deg) const
```


Set gimbal pitch and yaw angles.

This sets the desired pitch and yaw angles of a gimbal. Will return when the command is accepted, however, it might take the gimbal longer to actually be set to the new angles.


This function is blocking. See 'set_pitch_and_yaw_async' for the non-blocking counterpart.

**Parameters**

* float **pitch_deg** - 
* float **yaw_deg** - 

**Returns**

&emsp;[Result](classmavsdk_1_1_gimbal.md#classmavsdk_1_1_gimbal_1aa732ec0bd49ac03b7910199d635f76ac) - Result of request.

### set_mode_async() {#classmavsdk_1_1_gimbal_1ad69853994c134b0e88d0f94744254066}
```cpp
void mavsdk::Gimbal::set_mode_async(GimbalMode gimbal_mode, const ResultCallback callback)
```


Set gimbal mode.

This sets the desired yaw mode of a gimbal. Will return when the command is accepted. However, it might take the gimbal longer to actually be set to the new angles.


This function is non-blocking. See 'set_mode' for the blocking counterpart.

**Parameters**

* [GimbalMode](classmavsdk_1_1_gimbal.md#classmavsdk_1_1_gimbal_1afb92614c5d5915d3960bcea51bec2dca) **gimbal_mode** - 
* const [ResultCallback](classmavsdk_1_1_gimbal.md#classmavsdk_1_1_gimbal_1a88ee7dd17821fb9b12c44b2a3630c197) **callback** - 

### set_mode() {#classmavsdk_1_1_gimbal_1a037285883ceba14e0df9c7f8c19f4423}
```cpp
Result mavsdk::Gimbal::set_mode(GimbalMode gimbal_mode) const
```


Set gimbal mode.

This sets the desired yaw mode of a gimbal. Will return when the command is accepted. However, it might take the gimbal longer to actually be set to the new angles.


This function is blocking. See 'set_mode_async' for the non-blocking counterpart.

**Parameters**

* [GimbalMode](classmavsdk_1_1_gimbal.md#classmavsdk_1_1_gimbal_1afb92614c5d5915d3960bcea51bec2dca) **gimbal_mode** - 

**Returns**

&emsp;[Result](classmavsdk_1_1_gimbal.md#classmavsdk_1_1_gimbal_1aa732ec0bd49ac03b7910199d635f76ac) - Result of request.

### set_roi_location_async() {#classmavsdk_1_1_gimbal_1ab3c42a7042231e48dfab881030fe30c0}
```cpp
void mavsdk::Gimbal::set_roi_location_async(double latitude_deg, double longitude_deg, float altitude_m, const ResultCallback callback)
```


Set gimbal region of interest (ROI).

This sets a region of interest that the gimbal will point to. The gimbal will continue to point to the specified region until it receives a new command. The function will return when the command is accepted, however, it might take the gimbal longer to actually rotate to the ROI.


This function is non-blocking. See 'set_roi_location' for the blocking counterpart.

**Parameters**

* double **latitude_deg** - 
* double **longitude_deg** - 
* float **altitude_m** - 
* const [ResultCallback](classmavsdk_1_1_gimbal.md#classmavsdk_1_1_gimbal_1a88ee7dd17821fb9b12c44b2a3630c197) **callback** - 

### set_roi_location() {#classmavsdk_1_1_gimbal_1a035ddc270efce19a9be54b98add57919}
```cpp
Result mavsdk::Gimbal::set_roi_location(double latitude_deg, double longitude_deg, float altitude_m) const
```


Set gimbal region of interest (ROI).

This sets a region of interest that the gimbal will point to. The gimbal will continue to point to the specified region until it receives a new command. The function will return when the command is accepted, however, it might take the gimbal longer to actually rotate to the ROI.


This function is blocking. See 'set_roi_location_async' for the non-blocking counterpart.

**Parameters**

* double **latitude_deg** - 
* double **longitude_deg** - 
* float **altitude_m** - 

**Returns**

&emsp;[Result](classmavsdk_1_1_gimbal.md#classmavsdk_1_1_gimbal_1aa732ec0bd49ac03b7910199d635f76ac) - Result of request.

### operator=() {#classmavsdk_1_1_gimbal_1ac9a6e1936f58ce8f957be7c6bcc0d134}
```cpp
const Gimbal& mavsdk::Gimbal::operator=(const Gimbal &)=delete
```


Equality operator (object is not copyable).


**Parameters**

* const [Gimbal](classmavsdk_1_1_gimbal.md)&  - 

**Returns**

&emsp;const [Gimbal](classmavsdk_1_1_gimbal.md) & - 