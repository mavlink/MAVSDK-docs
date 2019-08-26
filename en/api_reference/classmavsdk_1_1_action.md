# mavsdk::Action Class Reference
`#include: action.h`

----


The [Action](classmavsdk_1_1_action.md) class enables simple actions for a drone such as arming, taking off, and landing. 


Synchronous and asynchronous variants of the action methods are supplied.


The action methods send their associated MAVLink commands to the vehicle and complete (return synchronously or callback asynchronously) with an [Action::Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) value indicating whether the vehicle has accepted or rejected the command, or that there has been some error. If the command is accepted, the vehicle will then start to perform the associated action. 


## Public Types


Type | Description
--- | ---
enum [Result](#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) | Possible results returned for commanded actions.
std::function< void([Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51))> [result_callback_t](#classmavsdk_1_1_action_1a11dc8f4beffb082ced5aa4da1f16a2a8) | Callback type for asynchronous [Action](classmavsdk_1_1_action.md) calls.

## Public Member Functions


Type | Name | Description
---: | --- | ---
&nbsp; | [Action](#classmavsdk_1_1_action_1a5e2a4d65f85d821be691a837453e56ee) ([System](classmavsdk_1_1_system.md) & system) | Constructor. Creates the plugin for a specific [System](classmavsdk_1_1_system.md).
&nbsp; | [~Action](#classmavsdk_1_1_action_1a20428abedfcd9fe413e16d2398ff99b4) () | Destructor (internal use only).
&nbsp; | [Action](#classmavsdk_1_1_action_1a890855f6b3350166a9b0d191e322526b) (const [Action](classmavsdk_1_1_action.md) &)=delete | Copy constructor (object is not copyable).
[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) | [arm](#classmavsdk_1_1_action_1ad1e15dd77bd359c05256e5a5ab83726f) () const | Send command to *arm* the drone (synchronous).
[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) | [disarm](#classmavsdk_1_1_action_1a6c759e461902d8c427026554e439774f) () const | Send command to *disarm* the drone (synchronous).
[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) | [kill](#classmavsdk_1_1_action_1a029f49ba496b23424095b47f73300d3a) () const | Send command to *kill* the drone (synchronous).
[Action::Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) | [reboot](#classmavsdk_1_1_action_1a8399ec8cfce871acb7617d35a683dec2) () const | Send command to *reboot* the drone components.
[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) | [takeoff](#classmavsdk_1_1_action_1a9c1df1ac24144286d8b0d05b119787d1) () const | Send command to *take off and hover* (synchronous).
[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) | [land](#classmavsdk_1_1_action_1a0383185c4f9a1afecd3da58b8158b079) () const | Send command to *land* at the current position (synchronous).
[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) | [return_to_launch](#classmavsdk_1_1_action_1a699c3488106efc02d0f912f7b58db98a) () const | Send command to *return to the launch* (takeoff) position and *land* (asynchronous).
[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) | [goto_location](#classmavsdk_1_1_action_1ac6a2496c569f02c1475a375e90a50550) (double latitude_deg, double longitude_deg, float altitude_amsl_m, float yaw_deg) | Send command to move the vehicle to a specific global position.
[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) | [transition_to_fixedwing](#classmavsdk_1_1_action_1af69cb37e52db442532fe82edcf479871) () const | Send command to transition the drone to fixedwing.
[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) | [transition_to_multicopter](#classmavsdk_1_1_action_1a9be72a826ce1d0fbce501b07023ea6ce) () const | Send command to transition the drone to multicopter.
void | [arm_async](#classmavsdk_1_1_action_1a64ac2dec2c36107f78df8b3dffa2bece) ([result_callback_t](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a11dc8f4beffb082ced5aa4da1f16a2a8) callback) | Send command to *arm* the drone (asynchronous).
void | [disarm_async](#classmavsdk_1_1_action_1a63576bca2b437db3951c3fa1c0b2e534) ([result_callback_t](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a11dc8f4beffb082ced5aa4da1f16a2a8) callback) | Send command to *disarm* the drone (asynchronous).
void | [kill_async](#classmavsdk_1_1_action_1a3527b7ff2de7bbc4cf2fce6836dd54b6) ([result_callback_t](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a11dc8f4beffb082ced5aa4da1f16a2a8) callback) | Send command to *kill* the drone (asynchronous).
void | [takeoff_async](#classmavsdk_1_1_action_1ae11d1410938a7083a8f765ca9196a1ef) ([result_callback_t](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a11dc8f4beffb082ced5aa4da1f16a2a8) callback) | Send command to *take off and hover* (asynchronous).
void | [land_async](#classmavsdk_1_1_action_1a504b80b6b482c717b7f9ec88f7fced13) ([result_callback_t](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a11dc8f4beffb082ced5aa4da1f16a2a8) callback) | Send command to *land* at the current position (asynchronous).
void | [return_to_launch_async](#classmavsdk_1_1_action_1a2c840742bcfbc0d977e2897d068cda04) ([result_callback_t](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a11dc8f4beffb082ced5aa4da1f16a2a8) callback) | Send command to *return to the launch* (takeoff) position and *land* (asynchronous).
void | [transition_to_fixedwing_async](#classmavsdk_1_1_action_1a862865ff6acfcfeed6f5a0d0936d0667) ([result_callback_t](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a11dc8f4beffb082ced5aa4da1f16a2a8) callback) | Send command to transition the drone to fixedwing (asynchronous).
void | [transition_to_multicopter_async](#classmavsdk_1_1_action_1afb60f1d37112f88140d359a9e5e87043) ([result_callback_t](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a11dc8f4beffb082ced5aa4da1f16a2a8) callback) | Send command to transition the drone to multicopter (asynchronous).
[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) | [set_takeoff_altitude](#classmavsdk_1_1_action_1a784da0b31be4515636fb93302a8f58c2) (float relative_altitude_m) | Set takeoff altitude above ground.
std::pair< [Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51), float > | [get_takeoff_altitude](#classmavsdk_1_1_action_1ae35fc7237cb28597471bb40479fa3fba) () const | Get the takeoff altitude.
[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) | [set_max_speed](#classmavsdk_1_1_action_1aa2ea0a257043f75b7332606162aa20c2) (float speed_m_s) | Set vehicle maximum speed.
std::pair< [Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51), float > | [get_max_speed](#classmavsdk_1_1_action_1a8f4b8b486492b87bd4fa61b747ba674f) () const | Get the vehicle maximum speed.
[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) | [set_return_to_launch_return_altitude](#classmavsdk_1_1_action_1ad992f1d8eb4184d22289560c031a6ed4) (float relative_altitude_m) | Set the return to launch minimum return altitude.
std::pair< [Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51), float > | [get_return_to_launch_return_altitude](#classmavsdk_1_1_action_1aa6d5f759f9d966fab465ce979e70f78d) () const | Get the return to launch minimum return altitude.
const [Action](classmavsdk_1_1_action.md) & | [operator=](#classmavsdk_1_1_action_1a1ff7e178b7ededc41bd9ccab0ca07457) (const [Action](classmavsdk_1_1_action.md) &)=delete | Equality operator (object is not copyable).

## Static Public Member Functions


Type | Name | Description
---: | --- | ---
const char * | [result_str](#classmavsdk_1_1_action_1a0c6e1120f26f1921ee14caab9099d07b) ([Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) result) | Returns a human-readable English string for an Result.


## Constructor & Destructor Documentation


### Action() {#classmavsdk_1_1_action_1a5e2a4d65f85d821be691a837453e56ee}
```cpp
mavsdk::Action::Action(System &system)
```


Constructor. Creates the plugin for a specific [System](classmavsdk_1_1_system.md).

The plugin is typically created as shown below: 

```cpp
auto action = std::make_shared<Action>(system);
```

**Parameters**

* [System](classmavsdk_1_1_system.md)& **system** - The specific system associated with this plugin.

### ~Action() {#classmavsdk_1_1_action_1a20428abedfcd9fe413e16d2398ff99b4}
```cpp
mavsdk::Action::~Action()
```


Destructor (internal use only).


### Action() {#classmavsdk_1_1_action_1a890855f6b3350166a9b0d191e322526b}
```cpp
mavsdk::Action::Action(const Action &)=delete
```


Copy constructor (object is not copyable).


**Parameters**

* const [Action](classmavsdk_1_1_action.md)&  - 

## Member Typdef Documentation


### typedef result_callback_t {#classmavsdk_1_1_action_1a11dc8f4beffb082ced5aa4da1f16a2a8}

```cpp
typedef std::function<void(Result)> mavsdk::Action::result_callback_t
```


Callback type for asynchronous [Action](classmavsdk_1_1_action.md) calls.


## Member Enumeration Documentation


### enum Result {#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51}


Possible results returned for commanded actions.

> **Note** [Mavsdk](classmavsdk_1_1_mavsdk.md) does not throw exceptions. Instead a result of this type will be returned when you execute actions.

Value | Description
--- | ---
<span id="classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51a696b031073e74bf2cb98e5ef201d4aa3"></span> `UNKNOWN` | Unspecified error. 
<span id="classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51ad0749aaba8b833466dfcbb0428e4f89c"></span> `SUCCESS` | Success. The action command was accepted by the vehicle. 
<span id="classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51afeae72a3a2feec3c92c2a79a30d31186"></span> `NO_SYSTEM` | No system is connected error. 
<span id="classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51ac77f1f09dab2c0c9980fca7cfae02518"></span> `CONNECTION_ERROR` | Connection error. 
<span id="classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51a802706a9238e2928077f97736854bad4"></span> `BUSY` | Vehicle busy error. 
<span id="classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51a6fa4dbf368cea972db8d9156799d5dbe"></span> `COMMAND_DENIED` | Command refused by vehicle. 
<span id="classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51a939d986bd1af6a2e1db07a61a60f7ae2"></span> `COMMAND_DENIED_LANDED_STATE_UNKNOWN` | Command refused because landed state is unknown. 
<span id="classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51ad7e95e2842caf0baff502fbd1290fd69"></span> `COMMAND_DENIED_NOT_LANDED` | Command refused because vehicle not landed. 
<span id="classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51a070a0fb40f6c308ab544b227660aadff"></span> `TIMEOUT` | Timeout waiting for command acknowledgement from vehicle. 
<span id="classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51a59e19d623bfb3a7a60195410afcbe31f"></span> `VTOL_TRANSITION_SUPPORT_UNKNOWN` | hybrid/VTOL transition refused because VTOL support is unknown. 
<span id="classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51af3712e88cb2a09f0d5b72e8e493b53be"></span> `NO_VTOL_TRANSITION_SUPPORT` | Vehicle does not support hybrid/VTOL transitions. 
<span id="classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51a637905cbbdef76bf168f9a036968526a"></span> `PARAMETER_ERROR` | Error getting or setting parameter. 

## Member Function Documentation


### arm() {#classmavsdk_1_1_action_1ad1e15dd77bd359c05256e5a5ab83726f}
```cpp
Result mavsdk::Action::arm() const
```


Send command to *arm* the drone (synchronous).

> **Note** Arming a drone normally causes motors to spin at idle. Before arming take all safety precautions and stand clear of the drone!

**Returns**

&emsp;[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) - Result of request.

### disarm() {#classmavsdk_1_1_action_1a6c759e461902d8c427026554e439774f}
```cpp
Result mavsdk::Action::disarm() const
```


Send command to *disarm* the drone (synchronous).

This will disarm a drone that considers itself landed. If flying, the drone should reject the disarm command. Disarming means that all motors will stop.

**Returns**

&emsp;[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) - Result of request.

### kill() {#classmavsdk_1_1_action_1a029f49ba496b23424095b47f73300d3a}
```cpp
Result mavsdk::Action::kill() const
```


Send command to *kill* the drone (synchronous).

This will disarm a drone irrespective of whether it is landed or flying. Note that the drone will fall out of the sky if this command is used while flying.

**Returns**

&emsp;[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) - Result of request.

### reboot() {#classmavsdk_1_1_action_1a8399ec8cfce871acb7617d35a683dec2}
```cpp
Action::Result mavsdk::Action::reboot() const
```


Send command to *reboot* the drone components.

This will reboot the autopilot, onboard computer, camera and gimbal.

**Returns**

&emsp;[Action::Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) - [Action::Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) of request.

### takeoff() {#classmavsdk_1_1_action_1a9c1df1ac24144286d8b0d05b119787d1}
```cpp
Result mavsdk::Action::takeoff() const
```


Send command to *take off and hover* (synchronous).

This switches the drone into position control mode and commands it to take off and hover at the takeoff altitude (set using [set_takeoff_altitude()](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a784da0b31be4515636fb93302a8f58c2)).


Note that the vehicle must be armed before it can take off.

**Returns**

&emsp;[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) - Result of request.

### land() {#classmavsdk_1_1_action_1a0383185c4f9a1afecd3da58b8158b079}
```cpp
Result mavsdk::Action::land() const
```


Send command to *land* at the current position (synchronous).

This switches the drone to [Land mode](https://docs.px4.io/en/flight_modes/land.html).

**Returns**

&emsp;[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) - Result of request.

### return_to_launch() {#classmavsdk_1_1_action_1a699c3488106efc02d0f912f7b58db98a}
```cpp
Result mavsdk::Action::return_to_launch() const
```


Send command to *return to the launch* (takeoff) position and *land* (asynchronous).

This switches the drone into [RTL mode](https://docs.px4.io/en/flight_modes/rtl.html) which generally means it will rise up to a certain altitude to clear any obstacles before heading back to the launch (takeoff) position and land there.

**Returns**

&emsp;[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) - Result of request.

### goto_location() {#classmavsdk_1_1_action_1ac6a2496c569f02c1475a375e90a50550}
```cpp
Result mavsdk::Action::goto_location(double latitude_deg, double longitude_deg, float altitude_amsl_m, float yaw_deg)
```


Send command to move the vehicle to a specific global position.

The latitude and longitude are given in degrees (WGS84 frame) and the altitude in meters AMSL (above mean sea level).

**Parameters**

* double **latitude_deg** - Latitude in degrees.
* double **longitude_deg** - Longitude in degrees.
* float **altitude_amsl_m** - Altitude AMSL in meters.
* float **yaw_deg** - Yaw angle in degrees (Frame is NED, 0 is North, positive is clockwise).

**Returns**

&emsp;[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) - Result of request.

### transition_to_fixedwing() {#classmavsdk_1_1_action_1af69cb37e52db442532fe82edcf479871}
```cpp
Result mavsdk::Action::transition_to_fixedwing() const
```


Send command to transition the drone to fixedwing.

The associated action will only be executed for VTOL vehicles (on other vehicle types the command will fail with an Result). The command will succeed if called when the vehicle is already in fixedwing mode.

**Returns**

&emsp;[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) - Result of request.

### transition_to_multicopter() {#classmavsdk_1_1_action_1a9be72a826ce1d0fbce501b07023ea6ce}
```cpp
Result mavsdk::Action::transition_to_multicopter() const
```


Send command to transition the drone to multicopter.

The associated action will only be executed for VTOL vehicles (on other vehicle types the command will fail with an Result). The command will succeed if called when the vehicle is already in multicopter mode.

**Returns**

&emsp;[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) - Result of request.

### arm_async() {#classmavsdk_1_1_action_1a64ac2dec2c36107f78df8b3dffa2bece}
```cpp
void mavsdk::Action::arm_async(result_callback_t callback)
```


Send command to *arm* the drone (asynchronous).

Note that arming a drone normally means that the motors will spin at idle. Therefore, before arming take all safety precautions and stand clear of the drone.

**Parameters**

* [result_callback_t](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a11dc8f4beffb082ced5aa4da1f16a2a8) **callback** - Function to call with result of request.

### disarm_async() {#classmavsdk_1_1_action_1a63576bca2b437db3951c3fa1c0b2e534}
```cpp
void mavsdk::Action::disarm_async(result_callback_t callback)
```


Send command to *disarm* the drone (asynchronous).

This will disarm a drone that considers itself landed. If flying, the drone should reject the disarm command. Disarming means that all motors will stop.

**Parameters**

* [result_callback_t](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a11dc8f4beffb082ced5aa4da1f16a2a8) **callback** - Function to call with result of request.

### kill_async() {#classmavsdk_1_1_action_1a3527b7ff2de7bbc4cf2fce6836dd54b6}
```cpp
void mavsdk::Action::kill_async(result_callback_t callback)
```


Send command to *kill* the drone (asynchronous).

This will disarm a drone irrespective of whether it is landed or flying. Note that the drone will fall out of the sky if you use this command while flying.

**Parameters**

* [result_callback_t](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a11dc8f4beffb082ced5aa4da1f16a2a8) **callback** - Function to call with result of request.

### takeoff_async() {#classmavsdk_1_1_action_1ae11d1410938a7083a8f765ca9196a1ef}
```cpp
void mavsdk::Action::takeoff_async(result_callback_t callback)
```


Send command to *take off and hover* (asynchronous).

This switches the drone into position control mode and commands it to take off and hover at the takeoff altitude set using [set_takeoff_altitude()](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a784da0b31be4515636fb93302a8f58c2).


Note that the vehicle must be armed before it can take off.

**Parameters**

* [result_callback_t](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a11dc8f4beffb082ced5aa4da1f16a2a8) **callback** - Function to call with result of request

### land_async() {#classmavsdk_1_1_action_1a504b80b6b482c717b7f9ec88f7fced13}
```cpp
void mavsdk::Action::land_async(result_callback_t callback)
```


Send command to *land* at the current position (asynchronous).

This switches the drone to [Land mode](https://docs.px4.io/en/flight_modes/land.html).

**Parameters**

* [result_callback_t](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a11dc8f4beffb082ced5aa4da1f16a2a8) **callback** - Function to call with result of request.

### return_to_launch_async() {#classmavsdk_1_1_action_1a2c840742bcfbc0d977e2897d068cda04}
```cpp
void mavsdk::Action::return_to_launch_async(result_callback_t callback)
```


Send command to *return to the launch* (takeoff) position and *land* (asynchronous).

This switches the drone into [RTL mode](https://docs.px4.io/en/flight_modes/rtl.html) which generally means it will rise up to a certain altitude to clear any obstacles before heading back to the launch (takeoff) position and land there.

**Parameters**

* [result_callback_t](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a11dc8f4beffb082ced5aa4da1f16a2a8) **callback** - Function to call with result of request.

### transition_to_fixedwing_async() {#classmavsdk_1_1_action_1a862865ff6acfcfeed6f5a0d0936d0667}
```cpp
void mavsdk::Action::transition_to_fixedwing_async(result_callback_t callback)
```


Send command to transition the drone to fixedwing (asynchronous).

The associated action will only be executed for VTOL vehicles (on other vehicle types the command will fail with an Result). The command will succeed if called when the vehicle is already in fixedwing mode.

**Parameters**

* [result_callback_t](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a11dc8f4beffb082ced5aa4da1f16a2a8) **callback** - Function to call with result of request.

### transition_to_multicopter_async() {#classmavsdk_1_1_action_1afb60f1d37112f88140d359a9e5e87043}
```cpp
void mavsdk::Action::transition_to_multicopter_async(result_callback_t callback)
```


Send command to transition the drone to multicopter (asynchronous).

The associated action will only be executed for VTOL vehicles (on other vehicle types the command will fail with an Result). The command will succeed if called when the vehicle is already in multicopter mode.

**Parameters**

* [result_callback_t](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a11dc8f4beffb082ced5aa4da1f16a2a8) **callback** - Function to call with result of request.

### set_takeoff_altitude() {#classmavsdk_1_1_action_1a784da0b31be4515636fb93302a8f58c2}
```cpp
Result mavsdk::Action::set_takeoff_altitude(float relative_altitude_m)
```


Set takeoff altitude above ground.


**Parameters**

* float **relative_altitude_m** - Takeoff altitude relative to takeoff location, in meters.

**Returns**

&emsp;[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) - Result of request.

### get_takeoff_altitude() {#classmavsdk_1_1_action_1ae35fc7237cb28597471bb40479fa3fba}
```cpp
std::pair<Result, float> mavsdk::Action::get_takeoff_altitude() const
```


Get the takeoff altitude.


**Returns**

&emsp;std::pair< [Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51), float > - A pair containing the result of request and if successful, the takeoff altitude relative to ground/takeoff location, in meters.

### set_max_speed() {#classmavsdk_1_1_action_1aa2ea0a257043f75b7332606162aa20c2}
```cpp
Result mavsdk::Action::set_max_speed(float speed_m_s)
```


Set vehicle maximum speed.


**Parameters**

* float **speed_m_s** - Maximum speed in metres/second.

**Returns**

&emsp;[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) - Result of request.

### get_max_speed() {#classmavsdk_1_1_action_1a8f4b8b486492b87bd4fa61b747ba674f}
```cpp
std::pair<Result, float> mavsdk::Action::get_max_speed() const
```


Get the vehicle maximum speed.


**Returns**

&emsp;std::pair< [Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51), float > - A pair containing the result of the request and if successful, the maximum speed in metres/second.

### set_return_to_launch_return_altitude() {#classmavsdk_1_1_action_1ad992f1d8eb4184d22289560c031a6ed4}
```cpp
Result mavsdk::Action::set_return_to_launch_return_altitude(float relative_altitude_m)
```


Set the return to launch minimum return altitude.

When return to launch is initiated, the vehicle climbs to the return altitude if it is lower and stays at the current altitude if higher than the return altitude. Then it returns to the home location and lands there.

**Parameters**

* float **relative_altitude_m** - Return altitude relative to takeoff location, in meters.

**Returns**

&emsp;[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) - Result of request.

### get_return_to_launch_return_altitude() {#classmavsdk_1_1_action_1aa6d5f759f9d966fab465ce979e70f78d}
```cpp
std::pair<Result, float> mavsdk::Action::get_return_to_launch_return_altitude() const
```


Get the return to launch minimum return altitude.


**Returns**

&emsp;std::pair< [Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51), float > - A pair containing the result of the request and if successful, the return altitude relative to takeoff location, in meters.

**See Also:**
- [set_return_to_launch_return_altitude](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1ad992f1d8eb4184d22289560c031a6ed4).


### operator=() {#classmavsdk_1_1_action_1a1ff7e178b7ededc41bd9ccab0ca07457}
```cpp
const Action& mavsdk::Action::operator=(const Action &)=delete
```


Equality operator (object is not copyable).


**Parameters**

* const [Action](classmavsdk_1_1_action.md)&  - 

**Returns**

&emsp;const [Action](classmavsdk_1_1_action.md) & - 

### result_str() {#classmavsdk_1_1_action_1a0c6e1120f26f1921ee14caab9099d07b}
```cpp
static const char* mavsdk::Action::result_str(Result result)
```


Returns a human-readable English string for an Result.


**Parameters**

* [Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) **result** - The enum value for which a human readable string is required.

**Returns**

&emsp;const char * - Human readable string for the Result.