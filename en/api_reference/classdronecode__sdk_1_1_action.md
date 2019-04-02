# dronecode_sdk::Action Class Reference
`#include: action.h`

----


The [Action](classdronecode__sdk_1_1_action.md) class enables simple actions for a drone such as arming, taking off, and landing. 


Synchronous and asynchronous variants of the action methods are supplied.


The action methods send their associated MAVLink commands to the vehicle and complete (return synchronously or callback asynchronously) with an [Action::Result](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1a7075ba49da42a7e5122b3c9a1979df6d) value indicating whether the vehicle has accepted or rejected the command, or that there has been some error. If the command is accepted, the vehicle will then start to perform the associated action. 


## Public Types


Type | Description
--- | ---
enum [Result](#classdronecode__sdk_1_1_action_1a7075ba49da42a7e5122b3c9a1979df6d) | Possible results returned for commanded actions.
std::function< void([Result](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1a7075ba49da42a7e5122b3c9a1979df6d))> [result_callback_t](#classdronecode__sdk_1_1_action_1ac20e209e6ad3fce8e1b755f025a6581b) | Callback type for asynchronous [Action](classdronecode__sdk_1_1_action.md) calls.

## Public Member Functions


Type | Name | Description
---: | --- | ---
&nbsp; | [Action](#classdronecode__sdk_1_1_action_1a45dbd7f3b0517a9b6e8caa0adc78ce62) ([System](classdronecode__sdk_1_1_system.md) & system) | Constructor. Creates the plugin for a specific [System](classdronecode__sdk_1_1_system.md).
&nbsp; | [~Action](#classdronecode__sdk_1_1_action_1a741bc86dbdb6069afb2b5877af67479b) () | Destructor (internal use only).
&nbsp; | [Action](#classdronecode__sdk_1_1_action_1a9610491e1c478f35b7c20c5a195ebe64) (const [Action](classdronecode__sdk_1_1_action.md) &)=delete | Copy constructor (object is not copyable).
[Result](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1a7075ba49da42a7e5122b3c9a1979df6d) | [arm](#classdronecode__sdk_1_1_action_1a85a98a013deead8a9ed8a55af2bab3d1) () const | Send command to *arm* the drone (synchronous).
[Result](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1a7075ba49da42a7e5122b3c9a1979df6d) | [disarm](#classdronecode__sdk_1_1_action_1a83beeef0bf1ad22fc1d26c7ce97e3a35) () const | Send command to *disarm* the drone (synchronous).
[Result](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1a7075ba49da42a7e5122b3c9a1979df6d) | [kill](#classdronecode__sdk_1_1_action_1a7c12e59ccef183bf250d74c6f630028c) () const | Send command to *kill* the drone (synchronous).
[Action::Result](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1a7075ba49da42a7e5122b3c9a1979df6d) | [reboot](#classdronecode__sdk_1_1_action_1a01caea533ada91a7467530531f1ee5f1) () const | Send command to *reboot* the drone components.
[Result](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1a7075ba49da42a7e5122b3c9a1979df6d) | [takeoff](#classdronecode__sdk_1_1_action_1abbcce1c335e6aec78917af9e705e235e) () const | Send command to *take off and hover* (synchronous).
[Result](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1a7075ba49da42a7e5122b3c9a1979df6d) | [land](#classdronecode__sdk_1_1_action_1af50fb3a17784557281ac37e83022575f) () const | Send command to *land* at the current position (synchronous).
[Result](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1a7075ba49da42a7e5122b3c9a1979df6d) | [return_to_launch](#classdronecode__sdk_1_1_action_1aae04fe166fac96b2efadee26f91de3d1) () const | Send command to *return to the launch* (takeoff) position and *land* (asynchronous).
[Result](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1a7075ba49da42a7e5122b3c9a1979df6d) | [goto_location](#classdronecode__sdk_1_1_action_1ab6bcb58fdac1aa7e699f89ed605c7666) (double latitude_deg, double longitude_deg, float altitude_amsl_m, float yaw_deg) | Send command to move the vehicle to a specific global position.
[Result](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1a7075ba49da42a7e5122b3c9a1979df6d) | [transition_to_fixedwing](#classdronecode__sdk_1_1_action_1a80c1336efa7b165df4beadb64435f31a) () const | Send command to transition the drone to fixedwing.
[Result](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1a7075ba49da42a7e5122b3c9a1979df6d) | [transition_to_multicopter](#classdronecode__sdk_1_1_action_1ab18e5b60e262e5dc9e6cb9479a285b2a) () const | Send command to transition the drone to multicopter.
void | [arm_async](#classdronecode__sdk_1_1_action_1ad295c4f5fb38636d1603dd1c401ca4a1) ([result_callback_t](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1ac20e209e6ad3fce8e1b755f025a6581b) callback) | Send command to *arm* the drone (asynchronous).
void | [disarm_async](#classdronecode__sdk_1_1_action_1a0bbbc62bb4562d9ed6b9870b530ba297) ([result_callback_t](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1ac20e209e6ad3fce8e1b755f025a6581b) callback) | Send command to *disarm* the drone (asynchronous).
void | [kill_async](#classdronecode__sdk_1_1_action_1ae4fd776f8b26fe79410925713c621e11) ([result_callback_t](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1ac20e209e6ad3fce8e1b755f025a6581b) callback) | Send command to *kill* the drone (asynchronous).
void | [takeoff_async](#classdronecode__sdk_1_1_action_1a602ed5e630a57edd01667f17f7843a80) ([result_callback_t](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1ac20e209e6ad3fce8e1b755f025a6581b) callback) | Send command to *take off and hover* (asynchronous).
void | [land_async](#classdronecode__sdk_1_1_action_1a69b781f22f5d624fe36d3af99c3aa5f3) ([result_callback_t](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1ac20e209e6ad3fce8e1b755f025a6581b) callback) | Send command to *land* at the current position (asynchronous).
void | [return_to_launch_async](#classdronecode__sdk_1_1_action_1a722a90a796c69ece78742fda4a90fc82) ([result_callback_t](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1ac20e209e6ad3fce8e1b755f025a6581b) callback) | Send command to *return to the launch* (takeoff) position and *land* (asynchronous).
void | [transition_to_fixedwing_async](#classdronecode__sdk_1_1_action_1a6d544dca4db484867fbe702fcfaddf84) ([result_callback_t](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1ac20e209e6ad3fce8e1b755f025a6581b) callback) | Send command to transition the drone to fixedwing (asynchronous).
void | [transition_to_multicopter_async](#classdronecode__sdk_1_1_action_1abecc30198261ac816519a4f33ebfbc4d) ([result_callback_t](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1ac20e209e6ad3fce8e1b755f025a6581b) callback) | Send command to transition the drone to multicopter (asynchronous).
[Result](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1a7075ba49da42a7e5122b3c9a1979df6d) | [set_takeoff_altitude](#classdronecode__sdk_1_1_action_1a4ff70ee80d704e913f71d8cca7a85a77) (float relative_altitude_m) | Set takeoff altitude above ground.
std::pair< [Result](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1a7075ba49da42a7e5122b3c9a1979df6d), float > | [get_takeoff_altitude](#classdronecode__sdk_1_1_action_1a1caf91de10314878863dc11a0b156ff3) () const | Get the takeoff altitude.
[Result](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1a7075ba49da42a7e5122b3c9a1979df6d) | [set_max_speed](#classdronecode__sdk_1_1_action_1ab16f13152fdee5819777b3bafbdc602d) (float speed_m_s) | Set vehicle maximum speed.
std::pair< [Result](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1a7075ba49da42a7e5122b3c9a1979df6d), float > | [get_max_speed](#classdronecode__sdk_1_1_action_1a2dfd2990216533a1c085c13fef0d97fc) () const | Get the vehicle maximum speed.
[Result](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1a7075ba49da42a7e5122b3c9a1979df6d) | [set_return_to_launch_return_altitude](#classdronecode__sdk_1_1_action_1a9c05835f0fbd616f8f96617a32d0c440) (float relative_altitude_m) | Set the return to launch minimum return altitude.
std::pair< [Result](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1a7075ba49da42a7e5122b3c9a1979df6d), float > | [get_return_to_launch_return_altitude](#classdronecode__sdk_1_1_action_1a2f6e890fb8f0bbcdd90c85f9ba4eb9f1) () const | Get the return to launch minimum return altitude.
const [Action](classdronecode__sdk_1_1_action.md) & | [operator=](#classdronecode__sdk_1_1_action_1a823b493fd0bc5219fb13ca5ca05e4cff) (const [Action](classdronecode__sdk_1_1_action.md) &)=delete | Equality operator (object is not copyable).

## Static Public Member Functions


Type | Name | Description
---: | --- | ---
const char * | [result_str](#classdronecode__sdk_1_1_action_1a1826cfa3b217437d6fccf861c4249a10) ([Result](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1a7075ba49da42a7e5122b3c9a1979df6d) result) | Returns a human-readable English string for an Result.


## Constructor & Destructor Documentation


### Action() {#classdronecode__sdk_1_1_action_1a45dbd7f3b0517a9b6e8caa0adc78ce62}
```cpp
dronecode_sdk::Action::Action(System &system)
```


Constructor. Creates the plugin for a specific [System](classdronecode__sdk_1_1_system.md).

The plugin is typically created as shown below: 

```cpp
auto action = std::make_shared<Action>(system);
```

**Parameters**

* [System](classdronecode__sdk_1_1_system.md)& **system** - The specific system associated with this plugin.

### ~Action() {#classdronecode__sdk_1_1_action_1a741bc86dbdb6069afb2b5877af67479b}
```cpp
dronecode_sdk::Action::~Action()
```


Destructor (internal use only).


### Action() {#classdronecode__sdk_1_1_action_1a9610491e1c478f35b7c20c5a195ebe64}
```cpp
dronecode_sdk::Action::Action(const Action &)=delete
```


Copy constructor (object is not copyable).


**Parameters**

* const [Action](classdronecode__sdk_1_1_action.md)&  - 

## Member Typdef Documentation


### typedef result_callback_t {#classdronecode__sdk_1_1_action_1ac20e209e6ad3fce8e1b755f025a6581b}

```cpp
typedef std::function<void(Result)> dronecode_sdk::Action::result_callback_t
```


Callback type for asynchronous [Action](classdronecode__sdk_1_1_action.md) calls.


## Member Enumeration Documentation


### enum Result {#classdronecode__sdk_1_1_action_1a7075ba49da42a7e5122b3c9a1979df6d}


Possible results returned for commanded actions.

> **Note** [DronecodeSDK](classdronecode__sdk_1_1_dronecode_s_d_k.md) does not throw exceptions. Instead a result of this type will be returned when you execute actions.

Value | Description
--- | ---
<span id="classdronecode__sdk_1_1_action_1a7075ba49da42a7e5122b3c9a1979df6da696b031073e74bf2cb98e5ef201d4aa3"></span> `UNKNOWN` | Unspecified error. 
<span id="classdronecode__sdk_1_1_action_1a7075ba49da42a7e5122b3c9a1979df6dad0749aaba8b833466dfcbb0428e4f89c"></span> `SUCCESS` | Success. The action command was accepted by the vehicle. 
<span id="classdronecode__sdk_1_1_action_1a7075ba49da42a7e5122b3c9a1979df6dafeae72a3a2feec3c92c2a79a30d31186"></span> `NO_SYSTEM` | No system is connected error. 
<span id="classdronecode__sdk_1_1_action_1a7075ba49da42a7e5122b3c9a1979df6dac77f1f09dab2c0c9980fca7cfae02518"></span> `CONNECTION_ERROR` | Connection error. 
<span id="classdronecode__sdk_1_1_action_1a7075ba49da42a7e5122b3c9a1979df6da802706a9238e2928077f97736854bad4"></span> `BUSY` | Vehicle busy error. 
<span id="classdronecode__sdk_1_1_action_1a7075ba49da42a7e5122b3c9a1979df6da6fa4dbf368cea972db8d9156799d5dbe"></span> `COMMAND_DENIED` | Command refused by vehicle. 
<span id="classdronecode__sdk_1_1_action_1a7075ba49da42a7e5122b3c9a1979df6da939d986bd1af6a2e1db07a61a60f7ae2"></span> `COMMAND_DENIED_LANDED_STATE_UNKNOWN` | Command refused because landed state is unknown. 
<span id="classdronecode__sdk_1_1_action_1a7075ba49da42a7e5122b3c9a1979df6dad7e95e2842caf0baff502fbd1290fd69"></span> `COMMAND_DENIED_NOT_LANDED` | Command refused because vehicle not landed. 
<span id="classdronecode__sdk_1_1_action_1a7075ba49da42a7e5122b3c9a1979df6da070a0fb40f6c308ab544b227660aadff"></span> `TIMEOUT` | Timeout waiting for command acknowledgement from vehicle. 
<span id="classdronecode__sdk_1_1_action_1a7075ba49da42a7e5122b3c9a1979df6da59e19d623bfb3a7a60195410afcbe31f"></span> `VTOL_TRANSITION_SUPPORT_UNKNOWN` | hybrid/VTOL transition refused because VTOL support is unknown. 
<span id="classdronecode__sdk_1_1_action_1a7075ba49da42a7e5122b3c9a1979df6daf3712e88cb2a09f0d5b72e8e493b53be"></span> `NO_VTOL_TRANSITION_SUPPORT` | Vehicle does not support hybrid/VTOL transitions. 
<span id="classdronecode__sdk_1_1_action_1a7075ba49da42a7e5122b3c9a1979df6da637905cbbdef76bf168f9a036968526a"></span> `PARAMETER_ERROR` | Error getting or setting parameter. 

## Member Function Documentation


### arm() {#classdronecode__sdk_1_1_action_1a85a98a013deead8a9ed8a55af2bab3d1}
```cpp
Result dronecode_sdk::Action::arm() const
```


Send command to *arm* the drone (synchronous).

> **Note** Arming a drone normally causes motors to spin at idle. Before arming take all safety precautions and stand clear of the drone!

**Returns**

&emsp;[Result](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1a7075ba49da42a7e5122b3c9a1979df6d) - Result of request.

### disarm() {#classdronecode__sdk_1_1_action_1a83beeef0bf1ad22fc1d26c7ce97e3a35}
```cpp
Result dronecode_sdk::Action::disarm() const
```


Send command to *disarm* the drone (synchronous).

This will disarm a drone that considers itself landed. If flying, the drone should reject the disarm command. Disarming means that all motors will stop.

**Returns**

&emsp;[Result](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1a7075ba49da42a7e5122b3c9a1979df6d) - Result of request.

### kill() {#classdronecode__sdk_1_1_action_1a7c12e59ccef183bf250d74c6f630028c}
```cpp
Result dronecode_sdk::Action::kill() const
```


Send command to *kill* the drone (synchronous).

This will disarm a drone irrespective of whether it is landed or flying. Note that the drone will fall out of the sky if this command is used while flying.

**Returns**

&emsp;[Result](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1a7075ba49da42a7e5122b3c9a1979df6d) - Result of request.

### reboot() {#classdronecode__sdk_1_1_action_1a01caea533ada91a7467530531f1ee5f1}
```cpp
Action::Result dronecode_sdk::Action::reboot() const
```


Send command to *reboot* the drone components.

This will reboot the autopilot, onboard computer, camera and gimbal.

**Returns**

&emsp;[Action::Result](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1a7075ba49da42a7e5122b3c9a1979df6d) - [Action::Result](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1a7075ba49da42a7e5122b3c9a1979df6d) of request.

### takeoff() {#classdronecode__sdk_1_1_action_1abbcce1c335e6aec78917af9e705e235e}
```cpp
Result dronecode_sdk::Action::takeoff() const
```


Send command to *take off and hover* (synchronous).

This switches the drone into position control mode and commands it to take off and hover at the takeoff altitude (set using [set_takeoff_altitude()](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1a4ff70ee80d704e913f71d8cca7a85a77)).


Note that the vehicle must be armed before it can take off.

**Returns**

&emsp;[Result](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1a7075ba49da42a7e5122b3c9a1979df6d) - Result of request.

### land() {#classdronecode__sdk_1_1_action_1af50fb3a17784557281ac37e83022575f}
```cpp
Result dronecode_sdk::Action::land() const
```


Send command to *land* at the current position (synchronous).

This switches the drone to [Land mode](https://docs.px4.io/en/flight_modes/land.html).

**Returns**

&emsp;[Result](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1a7075ba49da42a7e5122b3c9a1979df6d) - Result of request.

### return_to_launch() {#classdronecode__sdk_1_1_action_1aae04fe166fac96b2efadee26f91de3d1}
```cpp
Result dronecode_sdk::Action::return_to_launch() const
```


Send command to *return to the launch* (takeoff) position and *land* (asynchronous).

This switches the drone into [RTL mode](https://docs.px4.io/en/flight_modes/rtl.html) which generally means it will rise up to a certain altitude to clear any obstacles before heading back to the launch (takeoff) position and land there.

**Returns**

&emsp;[Result](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1a7075ba49da42a7e5122b3c9a1979df6d) - Result of request.

### goto_location() {#classdronecode__sdk_1_1_action_1ab6bcb58fdac1aa7e699f89ed605c7666}
```cpp
Result dronecode_sdk::Action::goto_location(double latitude_deg, double longitude_deg, float altitude_amsl_m, float yaw_deg)
```


Send command to move the vehicle to a specific global position.

The latitude and longitude are given in degrees (WGS84 frame) and the altitude in meters AMSL (above mean sea level).

**Parameters**

* double **latitude_deg** - Latitude in degrees.
* double **longitude_deg** - Longitude in degrees.
* float **altitude_amsl_m** - Altitude AMSL in meters.
* float **yaw_deg** - Yaw angle in degrees (Frame is NED, 0 is North, positive is clockwise).

**Returns**

&emsp;[Result](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1a7075ba49da42a7e5122b3c9a1979df6d) - Result of request.

### transition_to_fixedwing() {#classdronecode__sdk_1_1_action_1a80c1336efa7b165df4beadb64435f31a}
```cpp
Result dronecode_sdk::Action::transition_to_fixedwing() const
```


Send command to transition the drone to fixedwing.

The associated action will only be executed for VTOL vehicles (on other vehicle types the command will fail with an Result). The command will succeed if called when the vehicle is already in fixedwing mode.

**Returns**

&emsp;[Result](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1a7075ba49da42a7e5122b3c9a1979df6d) - Result of request.

### transition_to_multicopter() {#classdronecode__sdk_1_1_action_1ab18e5b60e262e5dc9e6cb9479a285b2a}
```cpp
Result dronecode_sdk::Action::transition_to_multicopter() const
```


Send command to transition the drone to multicopter.

The associated action will only be executed for VTOL vehicles (on other vehicle types the command will fail with an Result). The command will succeed if called when the vehicle is already in multicopter mode.

**Returns**

&emsp;[Result](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1a7075ba49da42a7e5122b3c9a1979df6d) - Result of request.

### arm_async() {#classdronecode__sdk_1_1_action_1ad295c4f5fb38636d1603dd1c401ca4a1}
```cpp
void dronecode_sdk::Action::arm_async(result_callback_t callback)
```


Send command to *arm* the drone (asynchronous).

Note that arming a drone normally means that the motors will spin at idle. Therefore, before arming take all safety precautions and stand clear of the drone.

**Parameters**

* [result_callback_t](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1ac20e209e6ad3fce8e1b755f025a6581b) **callback** - Function to call with result of request.

### disarm_async() {#classdronecode__sdk_1_1_action_1a0bbbc62bb4562d9ed6b9870b530ba297}
```cpp
void dronecode_sdk::Action::disarm_async(result_callback_t callback)
```


Send command to *disarm* the drone (asynchronous).

This will disarm a drone that considers itself landed. If flying, the drone should reject the disarm command. Disarming means that all motors will stop.

**Parameters**

* [result_callback_t](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1ac20e209e6ad3fce8e1b755f025a6581b) **callback** - Function to call with result of request.

### kill_async() {#classdronecode__sdk_1_1_action_1ae4fd776f8b26fe79410925713c621e11}
```cpp
void dronecode_sdk::Action::kill_async(result_callback_t callback)
```


Send command to *kill* the drone (asynchronous).

This will disarm a drone irrespective of whether it is landed or flying. Note that the drone will fall out of the sky if you use this command while flying.

**Parameters**

* [result_callback_t](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1ac20e209e6ad3fce8e1b755f025a6581b) **callback** - Function to call with result of request.

### takeoff_async() {#classdronecode__sdk_1_1_action_1a602ed5e630a57edd01667f17f7843a80}
```cpp
void dronecode_sdk::Action::takeoff_async(result_callback_t callback)
```


Send command to *take off and hover* (asynchronous).

This switches the drone into position control mode and commands it to take off and hover at the takeoff altitude set using [set_takeoff_altitude()](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1a4ff70ee80d704e913f71d8cca7a85a77).


Note that the vehicle must be armed before it can take off.

**Parameters**

* [result_callback_t](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1ac20e209e6ad3fce8e1b755f025a6581b) **callback** - Function to call with result of request

### land_async() {#classdronecode__sdk_1_1_action_1a69b781f22f5d624fe36d3af99c3aa5f3}
```cpp
void dronecode_sdk::Action::land_async(result_callback_t callback)
```


Send command to *land* at the current position (asynchronous).

This switches the drone to [Land mode](https://docs.px4.io/en/flight_modes/land.html).

**Parameters**

* [result_callback_t](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1ac20e209e6ad3fce8e1b755f025a6581b) **callback** - Function to call with result of request.

### return_to_launch_async() {#classdronecode__sdk_1_1_action_1a722a90a796c69ece78742fda4a90fc82}
```cpp
void dronecode_sdk::Action::return_to_launch_async(result_callback_t callback)
```


Send command to *return to the launch* (takeoff) position and *land* (asynchronous).

This switches the drone into [RTL mode](https://docs.px4.io/en/flight_modes/rtl.html) which generally means it will rise up to a certain altitude to clear any obstacles before heading back to the launch (takeoff) position and land there.

**Parameters**

* [result_callback_t](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1ac20e209e6ad3fce8e1b755f025a6581b) **callback** - Function to call with result of request.

### transition_to_fixedwing_async() {#classdronecode__sdk_1_1_action_1a6d544dca4db484867fbe702fcfaddf84}
```cpp
void dronecode_sdk::Action::transition_to_fixedwing_async(result_callback_t callback)
```


Send command to transition the drone to fixedwing (asynchronous).

The associated action will only be executed for VTOL vehicles (on other vehicle types the command will fail with an Result). The command will succeed if called when the vehicle is already in fixedwing mode.

**Parameters**

* [result_callback_t](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1ac20e209e6ad3fce8e1b755f025a6581b) **callback** - Function to call with result of request.

### transition_to_multicopter_async() {#classdronecode__sdk_1_1_action_1abecc30198261ac816519a4f33ebfbc4d}
```cpp
void dronecode_sdk::Action::transition_to_multicopter_async(result_callback_t callback)
```


Send command to transition the drone to multicopter (asynchronous).

The associated action will only be executed for VTOL vehicles (on other vehicle types the command will fail with an Result). The command will succeed if called when the vehicle is already in multicopter mode.

**Parameters**

* [result_callback_t](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1ac20e209e6ad3fce8e1b755f025a6581b) **callback** - Function to call with result of request.

### set_takeoff_altitude() {#classdronecode__sdk_1_1_action_1a4ff70ee80d704e913f71d8cca7a85a77}
```cpp
Result dronecode_sdk::Action::set_takeoff_altitude(float relative_altitude_m)
```


Set takeoff altitude above ground.


**Parameters**

* float **relative_altitude_m** - Takeoff altitude relative to takeoff location, in meters.

**Returns**

&emsp;[Result](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1a7075ba49da42a7e5122b3c9a1979df6d) - Result of request.

### get_takeoff_altitude() {#classdronecode__sdk_1_1_action_1a1caf91de10314878863dc11a0b156ff3}
```cpp
std::pair<Result, float> dronecode_sdk::Action::get_takeoff_altitude() const
```


Get the takeoff altitude.


**Returns**

&emsp;std::pair< [Result](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1a7075ba49da42a7e5122b3c9a1979df6d), float > - A pair containing the result of request and if successful, the takeoff altitude relative to ground/takeoff location, in meters.

### set_max_speed() {#classdronecode__sdk_1_1_action_1ab16f13152fdee5819777b3bafbdc602d}
```cpp
Result dronecode_sdk::Action::set_max_speed(float speed_m_s)
```


Set vehicle maximum speed.


**Parameters**

* float **speed_m_s** - Maximum speed in metres/second.

**Returns**

&emsp;[Result](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1a7075ba49da42a7e5122b3c9a1979df6d) - Result of request.

### get_max_speed() {#classdronecode__sdk_1_1_action_1a2dfd2990216533a1c085c13fef0d97fc}
```cpp
std::pair<Result, float> dronecode_sdk::Action::get_max_speed() const
```


Get the vehicle maximum speed.


**Returns**

&emsp;std::pair< [Result](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1a7075ba49da42a7e5122b3c9a1979df6d), float > - A pair containing the result of the request and if successful, the maximum speed in metres/second.

### set_return_to_launch_return_altitude() {#classdronecode__sdk_1_1_action_1a9c05835f0fbd616f8f96617a32d0c440}
```cpp
Result dronecode_sdk::Action::set_return_to_launch_return_altitude(float relative_altitude_m)
```


Set the return to launch minimum return altitude.

When return to launch is initiated, the vehicle climbs to the return altitude if it is lower and stays at the current altitude if higher than the return altitude. Then it returns to the home location and lands there.

**Parameters**

* float **relative_altitude_m** - Return altitude relative to takeoff location, in meters.

**Returns**

&emsp;[Result](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1a7075ba49da42a7e5122b3c9a1979df6d) - Result of request.

### get_return_to_launch_return_altitude() {#classdronecode__sdk_1_1_action_1a2f6e890fb8f0bbcdd90c85f9ba4eb9f1}
```cpp
std::pair<Result, float> dronecode_sdk::Action::get_return_to_launch_return_altitude() const
```


Get the return to launch minimum return altitude.


**Returns**

&emsp;std::pair< [Result](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1a7075ba49da42a7e5122b3c9a1979df6d), float > - A pair containing the result of the request and if successful, the return altitude relative to takeoff location, in meters.

**See Also:**
- [set_return_to_launch_return_altitude](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1a9c05835f0fbd616f8f96617a32d0c440).


### operator=() {#classdronecode__sdk_1_1_action_1a823b493fd0bc5219fb13ca5ca05e4cff}
```cpp
const Action& dronecode_sdk::Action::operator=(const Action &)=delete
```


Equality operator (object is not copyable).


**Parameters**

* const [Action](classdronecode__sdk_1_1_action.md)&  - 

**Returns**

&emsp;const [Action](classdronecode__sdk_1_1_action.md) & - 

### result_str() {#classdronecode__sdk_1_1_action_1a1826cfa3b217437d6fccf861c4249a10}
```cpp
static const char* dronecode_sdk::Action::result_str(Result result)
```


Returns a human-readable English string for an Result.


**Parameters**

* [Result](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1a7075ba49da42a7e5122b3c9a1979df6d) **result** - The enum value for which a human readable string is required.

**Returns**

&emsp;const char * - Human readable string for the Result.