# dronecode_sdk::Action Class Reference
`#include: action.h`

----


The [Action](classdronecode__sdk_1_1_action.md) class enables simple actions for a drone such as arming, taking off, and landing. 


Synchronous and asynchronous variants of the action methods are supplied.


The action methods send their associated MAVLink commands to the vehicle and complete (return synchronously or callback asynchronously) with an ActionResult value indicating whether the vehicle has accepted or rejected the command, or that there has been some error. If the command is accepted, the vehicle will then start to perform the associated action. 


## Public Types


Type | Description
--- | ---
std::function< void([ActionResult](namespacedronecode__sdk.md#namespacedronecode__sdk_1a03f15ca37e363d61087d14b709b1861e))> [result_callback_t](#classdronecode__sdk_1_1_action_1af8c876ed20fc97dc1338578028638949) | Callback type for asynchronous [Action](classdronecode__sdk_1_1_action.md) calls.

## Public Member Functions


Type | Name | Description
---: | --- | ---
&nbsp; | [Action](#classdronecode__sdk_1_1_action_1a45dbd7f3b0517a9b6e8caa0adc78ce62) ([System](classdronecode__sdk_1_1_system.md) & system) | Constructor. Creates the plugin for a specific [System](classdronecode__sdk_1_1_system.md).
&nbsp; | [~Action](#classdronecode__sdk_1_1_action_1a741bc86dbdb6069afb2b5877af67479b) () | Destructor (internal use only).
&nbsp; | [Action](#classdronecode__sdk_1_1_action_1a9610491e1c478f35b7c20c5a195ebe64) (const [Action](classdronecode__sdk_1_1_action.md) &)=delete | Copy constructor (object is not copyable).
[ActionResult](namespacedronecode__sdk.md#namespacedronecode__sdk_1a03f15ca37e363d61087d14b709b1861e) | [arm](#classdronecode__sdk_1_1_action_1a9c967b6dc0df5ce1de591fea76169153) () const | Send command to *arm* the drone (synchronous).
[ActionResult](namespacedronecode__sdk.md#namespacedronecode__sdk_1a03f15ca37e363d61087d14b709b1861e) | [disarm](#classdronecode__sdk_1_1_action_1a00cda2e6285f1bc2e654c3d4121ac713) () const | Send command to *disarm* the drone (synchronous).
[ActionResult](namespacedronecode__sdk.md#namespacedronecode__sdk_1a03f15ca37e363d61087d14b709b1861e) | [kill](#classdronecode__sdk_1_1_action_1aa027b3f706e5e1d8e986900bcf59eeea) () const | Send command to *kill* the drone (synchronous).
[ActionResult](namespacedronecode__sdk.md#namespacedronecode__sdk_1a03f15ca37e363d61087d14b709b1861e) | [reboot](#classdronecode__sdk_1_1_action_1ac6a075d39f2e5ddeaf13fc550ad780fd) () const | Send command to *reboot* the drone components.
[ActionResult](namespacedronecode__sdk.md#namespacedronecode__sdk_1a03f15ca37e363d61087d14b709b1861e) | [takeoff](#classdronecode__sdk_1_1_action_1a968b8d7370d707578cda0c67395a760e) () const | Send command to *take off and hover* (synchronous).
[ActionResult](namespacedronecode__sdk.md#namespacedronecode__sdk_1a03f15ca37e363d61087d14b709b1861e) | [land](#classdronecode__sdk_1_1_action_1a25490d09fd2905b96de2c2c6e52e5f7b) () const | Send command to *land* at the current position (synchronous).
[ActionResult](namespacedronecode__sdk.md#namespacedronecode__sdk_1a03f15ca37e363d61087d14b709b1861e) | [return_to_launch](#classdronecode__sdk_1_1_action_1a4a9c2107d7c9fd5f558fa35c0cc15d0c) () const | Send command to *return to the launch* (takeoff) position and *land* (asynchronous).
[ActionResult](namespacedronecode__sdk.md#namespacedronecode__sdk_1a03f15ca37e363d61087d14b709b1861e) | [goto_location](#classdronecode__sdk_1_1_action_1a05d56d9e9bf1c4d68ccf20c6607bab5c) (double latitude_deg, double longitude_deg, float altitude_amsl_m, float yaw_deg) | Send command to reposition the vehicle to a specific WGS84 global position.
[ActionResult](namespacedronecode__sdk.md#namespacedronecode__sdk_1a03f15ca37e363d61087d14b709b1861e) | [transition_to_fixedwing](#classdronecode__sdk_1_1_action_1af2955e3dafa2133eae1d137c06d68e85) () const | Send command to transition the drone to fixedwing.
[ActionResult](namespacedronecode__sdk.md#namespacedronecode__sdk_1a03f15ca37e363d61087d14b709b1861e) | [transition_to_multicopter](#classdronecode__sdk_1_1_action_1a10d5dfab8141cb66b94c22f05cda89cf) () const | Send command to transition the drone to multicopter.
void | [arm_async](#classdronecode__sdk_1_1_action_1ad295c4f5fb38636d1603dd1c401ca4a1) ([result_callback_t](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1af8c876ed20fc97dc1338578028638949) callback) | Send command to *arm* the drone (asynchronous).
void | [disarm_async](#classdronecode__sdk_1_1_action_1a0bbbc62bb4562d9ed6b9870b530ba297) ([result_callback_t](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1af8c876ed20fc97dc1338578028638949) callback) | Send command to *disarm* the drone (asynchronous).
void | [kill_async](#classdronecode__sdk_1_1_action_1ae4fd776f8b26fe79410925713c621e11) ([result_callback_t](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1af8c876ed20fc97dc1338578028638949) callback) | Send command to *kill* the drone (asynchronous).
void | [takeoff_async](#classdronecode__sdk_1_1_action_1a602ed5e630a57edd01667f17f7843a80) ([result_callback_t](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1af8c876ed20fc97dc1338578028638949) callback) | Send command to *take off and hover* (asynchronous).
void | [land_async](#classdronecode__sdk_1_1_action_1a69b781f22f5d624fe36d3af99c3aa5f3) ([result_callback_t](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1af8c876ed20fc97dc1338578028638949) callback) | Send command to *land* at the current position (asynchronous).
void | [return_to_launch_async](#classdronecode__sdk_1_1_action_1a722a90a796c69ece78742fda4a90fc82) ([result_callback_t](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1af8c876ed20fc97dc1338578028638949) callback) | Send command to *return to the launch* (takeoff) position and *land* (asynchronous).
void | [transition_to_fixedwing_async](#classdronecode__sdk_1_1_action_1a6d544dca4db484867fbe702fcfaddf84) ([result_callback_t](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1af8c876ed20fc97dc1338578028638949) callback) | Send command to transition the drone to fixedwing (asynchronous).
void | [transition_to_multicopter_async](#classdronecode__sdk_1_1_action_1abecc30198261ac816519a4f33ebfbc4d) ([result_callback_t](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1af8c876ed20fc97dc1338578028638949) callback) | Send command to transition the drone to multicopter (asynchronous).
[ActionResult](namespacedronecode__sdk.md#namespacedronecode__sdk_1a03f15ca37e363d61087d14b709b1861e) | [set_takeoff_altitude](#classdronecode__sdk_1_1_action_1ab1d989fb0ecddb92b16d02ed53cab1f7) (float relative_altitude_m) | Set takeoff altitude above ground.
std::pair< [ActionResult](namespacedronecode__sdk.md#namespacedronecode__sdk_1a03f15ca37e363d61087d14b709b1861e), float > | [get_takeoff_altitude](#classdronecode__sdk_1_1_action_1ab32c557ca167a41631042f9ce75b97f1) () const | Get the takeoff altitude.
[ActionResult](namespacedronecode__sdk.md#namespacedronecode__sdk_1a03f15ca37e363d61087d14b709b1861e) | [set_max_speed](#classdronecode__sdk_1_1_action_1a19e8bdfd64b87799da6ff0dbdf65923f) (float speed_m_s) | Set vehicle maximum speed.
std::pair< [ActionResult](namespacedronecode__sdk.md#namespacedronecode__sdk_1a03f15ca37e363d61087d14b709b1861e), float > | [get_max_speed](#classdronecode__sdk_1_1_action_1a610034c63aa08e85ed3b8f7a8b34e0c2) () const | Get the vehicle maximum speed.
[ActionResult](namespacedronecode__sdk.md#namespacedronecode__sdk_1a03f15ca37e363d61087d14b709b1861e) | [set_return_to_launch_return_altitude](#classdronecode__sdk_1_1_action_1a916cbb12d886b51ae5fbc1a9460aaeaf) (float relative_altitude_m) | Set the return to launch minimum return altitude.
std::pair< [ActionResult](namespacedronecode__sdk.md#namespacedronecode__sdk_1a03f15ca37e363d61087d14b709b1861e), float > | [get_return_to_launch_return_altitude](#classdronecode__sdk_1_1_action_1a44a22fbf70f16b7c253c1bf6ffc0db4a) () const | Get the return to launch minimum return altitude.
const [Action](classdronecode__sdk_1_1_action.md) & | [operator=](#classdronecode__sdk_1_1_action_1a823b493fd0bc5219fb13ca5ca05e4cff) (const [Action](classdronecode__sdk_1_1_action.md) &)=delete | Equality operator (object is not copyable).


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


### typedef result_callback_t {#classdronecode__sdk_1_1_action_1af8c876ed20fc97dc1338578028638949}

```cpp
typedef std::function<void(ActionResult)> dronecode_sdk::Action::result_callback_t
```


Callback type for asynchronous [Action](classdronecode__sdk_1_1_action.md) calls.


## Member Function Documentation


### arm() {#classdronecode__sdk_1_1_action_1a9c967b6dc0df5ce1de591fea76169153}
```cpp
ActionResult dronecode_sdk::Action::arm() const
```


Send command to *arm* the drone (synchronous).

> **Note** Arming a drone normally causes motors to spin at idle. Before arming take all safety precautions and stand clear of the drone!

**Returns**

&emsp;[ActionResult](namespacedronecode__sdk.md#namespacedronecode__sdk_1a03f15ca37e363d61087d14b709b1861e) - ActionResult of request.

### disarm() {#classdronecode__sdk_1_1_action_1a00cda2e6285f1bc2e654c3d4121ac713}
```cpp
ActionResult dronecode_sdk::Action::disarm() const
```


Send command to *disarm* the drone (synchronous).

This will disarm a drone that considers itself landed. If flying, the drone should reject the disarm command. Disarming means that all motors will stop.

**Returns**

&emsp;[ActionResult](namespacedronecode__sdk.md#namespacedronecode__sdk_1a03f15ca37e363d61087d14b709b1861e) - ActionResult of request.

### kill() {#classdronecode__sdk_1_1_action_1aa027b3f706e5e1d8e986900bcf59eeea}
```cpp
ActionResult dronecode_sdk::Action::kill() const
```


Send command to *kill* the drone (synchronous).

This will disarm a drone irrespective of whether it is landed or flying. Note that the drone will fall out of the sky if this command is used while flying.

**Returns**

&emsp;[ActionResult](namespacedronecode__sdk.md#namespacedronecode__sdk_1a03f15ca37e363d61087d14b709b1861e) - ActionResult of request.

### reboot() {#classdronecode__sdk_1_1_action_1ac6a075d39f2e5ddeaf13fc550ad780fd}
```cpp
ActionResult dronecode_sdk::Action::reboot() const
```


Send command to *reboot* the drone components.

This will reboot the autopilot, onboard computer, camera and gimbal.

**Returns**

&emsp;[ActionResult](namespacedronecode__sdk.md#namespacedronecode__sdk_1a03f15ca37e363d61087d14b709b1861e) - ActionResult of request.

### takeoff() {#classdronecode__sdk_1_1_action_1a968b8d7370d707578cda0c67395a760e}
```cpp
ActionResult dronecode_sdk::Action::takeoff() const
```


Send command to *take off and hover* (synchronous).

This switches the drone into position control mode and commands it to take off and hover at the takeoff altitude (set using [set_takeoff_altitude()](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1ab1d989fb0ecddb92b16d02ed53cab1f7)).


Note that the vehicle must be armed before it can take off.

**Returns**

&emsp;[ActionResult](namespacedronecode__sdk.md#namespacedronecode__sdk_1a03f15ca37e363d61087d14b709b1861e) - ActionResult of request.

### land() {#classdronecode__sdk_1_1_action_1a25490d09fd2905b96de2c2c6e52e5f7b}
```cpp
ActionResult dronecode_sdk::Action::land() const
```


Send command to *land* at the current position (synchronous).

This switches the drone to [Land mode](https://docs.px4.io/en/flight_modes/land.html).

**Returns**

&emsp;[ActionResult](namespacedronecode__sdk.md#namespacedronecode__sdk_1a03f15ca37e363d61087d14b709b1861e) - ActionResult of request.

### return_to_launch() {#classdronecode__sdk_1_1_action_1a4a9c2107d7c9fd5f558fa35c0cc15d0c}
```cpp
ActionResult dronecode_sdk::Action::return_to_launch() const
```


Send command to *return to the launch* (takeoff) position and *land* (asynchronous).

This switches the drone into [RTL mode](https://docs.px4.io/en/flight_modes/rtl.html) which generally means it will rise up to a certain altitude to clear any obstacles before heading back to the launch (takeoff) position and land there.

**Returns**

&emsp;[ActionResult](namespacedronecode__sdk.md#namespacedronecode__sdk_1a03f15ca37e363d61087d14b709b1861e) - ActionResult of request.

### goto_location() {#classdronecode__sdk_1_1_action_1a05d56d9e9bf1c4d68ccf20c6607bab5c}
```cpp
ActionResult dronecode_sdk::Action::goto_location(double latitude_deg, double longitude_deg, float altitude_amsl_m, float yaw_deg)
```


Send command to reposition the vehicle to a specific WGS84 global position.

This sends the vehicle to a specified lattitude/longitude/altitude coordinates.

**Parameters**

* double **latitude_deg** - Latitude in degrees
* double **longitude_deg** - Longitude in degrees
* float **altitude_amsl_m** - Altitude AMSL in meters
* float **yaw_deg** - Yaw angle in degrees

**Returns**

&emsp;[ActionResult](namespacedronecode__sdk.md#namespacedronecode__sdk_1a03f15ca37e363d61087d14b709b1861e) - ActionResult of request.

### transition_to_fixedwing() {#classdronecode__sdk_1_1_action_1af2955e3dafa2133eae1d137c06d68e85}
```cpp
ActionResult dronecode_sdk::Action::transition_to_fixedwing() const
```


Send command to transition the drone to fixedwing.

The associated action will only be executed for VTOL vehicles (on other vehicle types the command will fail with an ActionResult). The command will succeed if called when the vehicle is already in fixedwing mode.

**Returns**

&emsp;[ActionResult](namespacedronecode__sdk.md#namespacedronecode__sdk_1a03f15ca37e363d61087d14b709b1861e) - ActionResult of request.

### transition_to_multicopter() {#classdronecode__sdk_1_1_action_1a10d5dfab8141cb66b94c22f05cda89cf}
```cpp
ActionResult dronecode_sdk::Action::transition_to_multicopter() const
```


Send command to transition the drone to multicopter.

The associated action will only be executed for VTOL vehicles (on other vehicle types the command will fail with an ActionResult). The command will succeed if called when the vehicle is already in multicopter mode.

**Returns**

&emsp;[ActionResult](namespacedronecode__sdk.md#namespacedronecode__sdk_1a03f15ca37e363d61087d14b709b1861e) - ActionResult of request.

### arm_async() {#classdronecode__sdk_1_1_action_1ad295c4f5fb38636d1603dd1c401ca4a1}
```cpp
void dronecode_sdk::Action::arm_async(result_callback_t callback)
```


Send command to *arm* the drone (asynchronous).

Note that arming a drone normally means that the motors will spin at idle. Therefore, before arming take all safety precautions and stand clear of the drone.

**Parameters**

* [result_callback_t](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1af8c876ed20fc97dc1338578028638949) **callback** - Function to call with result of request.

### disarm_async() {#classdronecode__sdk_1_1_action_1a0bbbc62bb4562d9ed6b9870b530ba297}
```cpp
void dronecode_sdk::Action::disarm_async(result_callback_t callback)
```


Send command to *disarm* the drone (asynchronous).

This will disarm a drone that considers itself landed. If flying, the drone should reject the disarm command. Disarming means that all motors will stop.

**Parameters**

* [result_callback_t](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1af8c876ed20fc97dc1338578028638949) **callback** - Function to call with result of request.

### kill_async() {#classdronecode__sdk_1_1_action_1ae4fd776f8b26fe79410925713c621e11}
```cpp
void dronecode_sdk::Action::kill_async(result_callback_t callback)
```


Send command to *kill* the drone (asynchronous).

This will disarm a drone irrespective of whether it is landed or flying. Note that the drone will fall out of the sky if you use this command while flying.

**Parameters**

* [result_callback_t](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1af8c876ed20fc97dc1338578028638949) **callback** - Function to call with result of request.

### takeoff_async() {#classdronecode__sdk_1_1_action_1a602ed5e630a57edd01667f17f7843a80}
```cpp
void dronecode_sdk::Action::takeoff_async(result_callback_t callback)
```


Send command to *take off and hover* (asynchronous).

This switches the drone into position control mode and commands it to take off and hover at the takeoff altitude set using [set_takeoff_altitude()](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1ab1d989fb0ecddb92b16d02ed53cab1f7).


Note that the vehicle must be armed before it can take off.

**Parameters**

* [result_callback_t](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1af8c876ed20fc97dc1338578028638949) **callback** - Function to call with result of request

### land_async() {#classdronecode__sdk_1_1_action_1a69b781f22f5d624fe36d3af99c3aa5f3}
```cpp
void dronecode_sdk::Action::land_async(result_callback_t callback)
```


Send command to *land* at the current position (asynchronous).

This switches the drone to [Land mode](https://docs.px4.io/en/flight_modes/land.html).

**Parameters**

* [result_callback_t](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1af8c876ed20fc97dc1338578028638949) **callback** - Function to call with result of request.

### return_to_launch_async() {#classdronecode__sdk_1_1_action_1a722a90a796c69ece78742fda4a90fc82}
```cpp
void dronecode_sdk::Action::return_to_launch_async(result_callback_t callback)
```


Send command to *return to the launch* (takeoff) position and *land* (asynchronous).

This switches the drone into [RTL mode](https://docs.px4.io/en/flight_modes/rtl.html) which generally means it will rise up to a certain altitude to clear any obstacles before heading back to the launch (takeoff) position and land there.

**Parameters**

* [result_callback_t](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1af8c876ed20fc97dc1338578028638949) **callback** - Function to call with result of request.

### transition_to_fixedwing_async() {#classdronecode__sdk_1_1_action_1a6d544dca4db484867fbe702fcfaddf84}
```cpp
void dronecode_sdk::Action::transition_to_fixedwing_async(result_callback_t callback)
```


Send command to transition the drone to fixedwing (asynchronous).

The associated action will only be executed for VTOL vehicles (on other vehicle types the command will fail with an ActionResult). The command will succeed if called when the vehicle is already in fixedwing mode.

**Parameters**

* [result_callback_t](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1af8c876ed20fc97dc1338578028638949) **callback** - Function to call with result of request.

### transition_to_multicopter_async() {#classdronecode__sdk_1_1_action_1abecc30198261ac816519a4f33ebfbc4d}
```cpp
void dronecode_sdk::Action::transition_to_multicopter_async(result_callback_t callback)
```


Send command to transition the drone to multicopter (asynchronous).

The associated action will only be executed for VTOL vehicles (on other vehicle types the command will fail with an ActionResult). The command will succeed if called when the vehicle is already in multicopter mode.

**Parameters**

* [result_callback_t](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1af8c876ed20fc97dc1338578028638949) **callback** - Function to call with result of request.

### set_takeoff_altitude() {#classdronecode__sdk_1_1_action_1ab1d989fb0ecddb92b16d02ed53cab1f7}
```cpp
ActionResult dronecode_sdk::Action::set_takeoff_altitude(float relative_altitude_m)
```


Set takeoff altitude above ground.


**Parameters**

* float **relative_altitude_m** - Takeoff altitude relative to takeoff location, in meters.

**Returns**

&emsp;[ActionResult](namespacedronecode__sdk.md#namespacedronecode__sdk_1a03f15ca37e363d61087d14b709b1861e) - Result of request.

### get_takeoff_altitude() {#classdronecode__sdk_1_1_action_1ab32c557ca167a41631042f9ce75b97f1}
```cpp
std::pair<ActionResult, float> dronecode_sdk::Action::get_takeoff_altitude() const
```


Get the takeoff altitude.


**Returns**

&emsp;std::pair< [ActionResult](namespacedronecode__sdk.md#namespacedronecode__sdk_1a03f15ca37e363d61087d14b709b1861e), float > - A pair containing the result of request and if successful, the takeoff altitude relative to ground/takeoff location, in meters.

### set_max_speed() {#classdronecode__sdk_1_1_action_1a19e8bdfd64b87799da6ff0dbdf65923f}
```cpp
ActionResult dronecode_sdk::Action::set_max_speed(float speed_m_s)
```


Set vehicle maximum speed.


**Parameters**

* float **speed_m_s** - Maximum speed in metres/second.

**Returns**

&emsp;[ActionResult](namespacedronecode__sdk.md#namespacedronecode__sdk_1a03f15ca37e363d61087d14b709b1861e) - Result of request.

### get_max_speed() {#classdronecode__sdk_1_1_action_1a610034c63aa08e85ed3b8f7a8b34e0c2}
```cpp
std::pair<ActionResult, float> dronecode_sdk::Action::get_max_speed() const
```


Get the vehicle maximum speed.


**Returns**

&emsp;std::pair< [ActionResult](namespacedronecode__sdk.md#namespacedronecode__sdk_1a03f15ca37e363d61087d14b709b1861e), float > - A pair containing the result of the request and if successful, the maximum speed in metres/second.

### set_return_to_launch_return_altitude() {#classdronecode__sdk_1_1_action_1a916cbb12d886b51ae5fbc1a9460aaeaf}
```cpp
ActionResult dronecode_sdk::Action::set_return_to_launch_return_altitude(float relative_altitude_m)
```


Set the return to launch minimum return altitude.

When return to launch is initiated, the vehicle climbs to the return altitude if it is lower and stays at the current altitude if higher than the return altitude. Then it returns to the home location and lands there.

**Parameters**

* float **relative_altitude_m** - Return altitude relative to takeoff location, in meters.

**Returns**

&emsp;[ActionResult](namespacedronecode__sdk.md#namespacedronecode__sdk_1a03f15ca37e363d61087d14b709b1861e) - Result of request.

### get_return_to_launch_return_altitude() {#classdronecode__sdk_1_1_action_1a44a22fbf70f16b7c253c1bf6ffc0db4a}
```cpp
std::pair<ActionResult, float> dronecode_sdk::Action::get_return_to_launch_return_altitude() const
```


Get the return to launch minimum return altitude.


**Returns**

&emsp;std::pair< [ActionResult](namespacedronecode__sdk.md#namespacedronecode__sdk_1a03f15ca37e363d61087d14b709b1861e), float > - A pair containing the result of the request and if successful, the return altitude relative to takeoff location, in meters.

**See Also:**
- [set_return_to_launch_return_altitude](classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1a916cbb12d886b51ae5fbc1a9460aaeaf).


### operator=() {#classdronecode__sdk_1_1_action_1a823b493fd0bc5219fb13ca5ca05e4cff}
```cpp
const Action& dronecode_sdk::Action::operator=(const Action &)=delete
```


Equality operator (object is not copyable).


**Parameters**

* const [Action](classdronecode__sdk_1_1_action.md)&  - 

**Returns**

&emsp;const [Action](classdronecode__sdk_1_1_action.md) & - 