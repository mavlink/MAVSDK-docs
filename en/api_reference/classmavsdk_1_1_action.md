# mavsdk::Action Class Reference
`#include: action.h`

----


Enable simple actions such as arming, taking off, and landing. 


## Public Types


Type | Description
--- | ---
enum [Result](#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) | Possible results returned for action requests.
std::function< void([Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51))> [ResultCallback](#classmavsdk_1_1_action_1a70a7b6e742d0c86728dc2e1827dacccd) | Callback type for asynchronous [Action](classmavsdk_1_1_action.md) calls.
std::function< void([Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51), float)> [GetTakeoffAltitudeCallback](#classmavsdk_1_1_action_1ad1ae6edb8ea375a3472ef14313b591e2) | Callback type for get_takeoff_altitude_async.
std::function< void([Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51), float)> [GetMaximumSpeedCallback](#classmavsdk_1_1_action_1a6993096d3e1424a817ad58ce8217a73c) | Callback type for get_maximum_speed_async.
std::function< void([Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51), float)> [GetReturnToLaunchAltitudeCallback](#classmavsdk_1_1_action_1af28acf6f7cff11f3c583761edb7d7415) | Callback type for get_return_to_launch_altitude_async.

## Public Member Functions


Type | Name | Description
---: | --- | ---
&nbsp; | [Action](#classmavsdk_1_1_action_1a5e2a4d65f85d821be691a837453e56ee) ([System](classmavsdk_1_1_system.md) & system) | Constructor. Creates the plugin for a specific [System](classmavsdk_1_1_system.md).
&nbsp; | [~Action](#classmavsdk_1_1_action_1a20428abedfcd9fe413e16d2398ff99b4) () | Destructor (internal use only).
&nbsp; | [Action](#classmavsdk_1_1_action_1a890855f6b3350166a9b0d191e322526b) (const [Action](classmavsdk_1_1_action.md) &)=delete | Copy constructor (object is not copyable).
void | [arm_async](#classmavsdk_1_1_action_1a570a3799ca5dbbf8aab30ce465687796) (const [ResultCallback](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a70a7b6e742d0c86728dc2e1827dacccd) callback) | Send command to arm the drone.
[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) | [arm](#classmavsdk_1_1_action_1a3ee123973982842f46a9f8b6cb952566) () const | Send command to arm the drone.
void | [disarm_async](#classmavsdk_1_1_action_1a3107f7f5a2f4a478024667f187f8f2aa) (const [ResultCallback](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a70a7b6e742d0c86728dc2e1827dacccd) callback) | Send command to disarm the drone.
[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) | [disarm](#classmavsdk_1_1_action_1a44c61110965bcdd3dfb90a08d3c6b6b9) () const | Send command to disarm the drone.
void | [takeoff_async](#classmavsdk_1_1_action_1ab658d938970326db41709d83e02b41e6) (const [ResultCallback](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a70a7b6e742d0c86728dc2e1827dacccd) callback) | Send command to take off and hover.
[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) | [takeoff](#classmavsdk_1_1_action_1a0121d39baf922b1d88283230207ab5d0) () const | Send command to take off and hover.
void | [land_async](#classmavsdk_1_1_action_1a89d146a766d49f1c706c66a3e2b9252d) (const [ResultCallback](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a70a7b6e742d0c86728dc2e1827dacccd) callback) | Send command to land at the current position.
[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) | [land](#classmavsdk_1_1_action_1af6429e1bdb2875deebfe98ed53da3d41) () const | Send command to land at the current position.
void | [reboot_async](#classmavsdk_1_1_action_1a32cfcc71a00afc28f43d2a22c319618c) (const [ResultCallback](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a70a7b6e742d0c86728dc2e1827dacccd) callback) | Send command to reboot the drone components.
[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) | [reboot](#classmavsdk_1_1_action_1a7f1e1911ca234e5572b3162a45d83c5d) () const | Send command to reboot the drone components.
void | [shutdown_async](#classmavsdk_1_1_action_1a1658a5499c61c46340428bb819453615) (const [ResultCallback](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a70a7b6e742d0c86728dc2e1827dacccd) callback) | Send command to shut down the drone components.
[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) | [shutdown](#classmavsdk_1_1_action_1a44522a60732d3968831f0cf6097c5360) () const | Send command to shut down the drone components.
void | [kill_async](#classmavsdk_1_1_action_1a78c1f15c3b190ba94793045621819e69) (const [ResultCallback](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a70a7b6e742d0c86728dc2e1827dacccd) callback) | Send command to kill the drone.
[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) | [kill](#classmavsdk_1_1_action_1af40fc1ddf588b3796134a9303ebc3667) () const | Send command to kill the drone.
void | [return_to_launch_async](#classmavsdk_1_1_action_1abe5bd426de588b246644ee3ddb12517d) (const [ResultCallback](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a70a7b6e742d0c86728dc2e1827dacccd) callback) | Send command to return to the launch (takeoff) position and land.
[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) | [return_to_launch](#classmavsdk_1_1_action_1afd7c225df0495b0947f00e7d2dd64877) () const | Send command to return to the launch (takeoff) position and land.
void | [goto_location_async](#classmavsdk_1_1_action_1a6fd615e5571d6e7e3c53a79d2160ffc5) (double latitude_deg, double longitude_deg, float absolute_altitude_m, float yaw_deg, const [ResultCallback](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a70a7b6e742d0c86728dc2e1827dacccd) callback) | Send command to move the vehicle to a specific global position.
[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) | [goto_location](#classmavsdk_1_1_action_1afb3546fa994357e491816f2032716818) (double latitude_deg, double longitude_deg, float absolute_altitude_m, float yaw_deg)const | Send command to move the vehicle to a specific global position.
void | [transition_to_fixedwing_async](#classmavsdk_1_1_action_1aa56181441cd64e092a8fb91a38c7c9fd) (const [ResultCallback](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a70a7b6e742d0c86728dc2e1827dacccd) callback) | Send command to transition the drone to fixedwing.
[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) | [transition_to_fixedwing](#classmavsdk_1_1_action_1a8d5cf999a48ea3859ec75db27cf4fbda) () const | Send command to transition the drone to fixedwing.
void | [transition_to_multicopter_async](#classmavsdk_1_1_action_1a8c109076641b5c9aa6dd78ea8b913529) (const [ResultCallback](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a70a7b6e742d0c86728dc2e1827dacccd) callback) | Send command to transition the drone to multicopter.
[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) | [transition_to_multicopter](#classmavsdk_1_1_action_1aac94bfb8613a8e9869e3620b3dc9bb8e) () const | Send command to transition the drone to multicopter.
void | [get_takeoff_altitude_async](#classmavsdk_1_1_action_1a0a600e6ef75a69341d8b21243e7b1a71) (const [GetTakeoffAltitudeCallback](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1ad1ae6edb8ea375a3472ef14313b591e2) callback) | Get the takeoff altitude (in meters above ground).
std::pair< [Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51), float > | [get_takeoff_altitude](#classmavsdk_1_1_action_1a85df48432c5ed2c6e23831409139ed39) () const | Get the takeoff altitude (in meters above ground).
void | [set_takeoff_altitude_async](#classmavsdk_1_1_action_1a9027c3e5f9eaf37cdfe8c426727c7693) (float altitude, const [ResultCallback](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a70a7b6e742d0c86728dc2e1827dacccd) callback) | Set takeoff altitude (in meters above ground).
[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) | [set_takeoff_altitude](#classmavsdk_1_1_action_1ace2188fe367b3bb10b17b89c88d1f952) (float altitude)const | Set takeoff altitude (in meters above ground).
void | [get_maximum_speed_async](#classmavsdk_1_1_action_1a30aada232be0f805950a78e2005ade75) (const [GetMaximumSpeedCallback](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a6993096d3e1424a817ad58ce8217a73c) callback) | Get the vehicle maximum speed (in metres/second).
std::pair< [Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51), float > | [get_maximum_speed](#classmavsdk_1_1_action_1a128bf73fe8d0d359f36a3a9a327799ee) () const | Get the vehicle maximum speed (in metres/second).
void | [set_maximum_speed_async](#classmavsdk_1_1_action_1abc99f14481f0d961228c6535da9017a6) (float speed, const [ResultCallback](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a70a7b6e742d0c86728dc2e1827dacccd) callback) | Set vehicle maximum speed (in metres/second).
[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) | [set_maximum_speed](#classmavsdk_1_1_action_1a5fccee1636215bccf8d77d9dca15134e) (float speed)const | Set vehicle maximum speed (in metres/second).
void | [get_return_to_launch_altitude_async](#classmavsdk_1_1_action_1aa19935b55d80f63e06397b3ea4b51c22) (const [GetReturnToLaunchAltitudeCallback](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1af28acf6f7cff11f3c583761edb7d7415) callback) | Get the return to launch minimum return altitude (in meters).
std::pair< [Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51), float > | [get_return_to_launch_altitude](#classmavsdk_1_1_action_1aeffd084ea51c8a784e28b44b859b6586) () const | Get the return to launch minimum return altitude (in meters).
void | [set_return_to_launch_altitude_async](#classmavsdk_1_1_action_1acdc4360c21ec82c57125023c552b3410) (float relative_altitude_m, const [ResultCallback](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a70a7b6e742d0c86728dc2e1827dacccd) callback) | Set the return to launch minimum return altitude (in meters).
[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) | [set_return_to_launch_altitude](#classmavsdk_1_1_action_1a5b05e84d35fad5b0ba2837aae1b3686e) (float relative_altitude_m)const | Set the return to launch minimum return altitude (in meters).
const [Action](classmavsdk_1_1_action.md) & | [operator=](#classmavsdk_1_1_action_1a1ff7e178b7ededc41bd9ccab0ca07457) (const [Action](classmavsdk_1_1_action.md) &)=delete | Equality operator (object is not copyable).


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


### typedef ResultCallback {#classmavsdk_1_1_action_1a70a7b6e742d0c86728dc2e1827dacccd}

```cpp
using mavsdk::Action::ResultCallback =  std::function<void(Result)>
```


Callback type for asynchronous [Action](classmavsdk_1_1_action.md) calls.


### typedef GetTakeoffAltitudeCallback {#classmavsdk_1_1_action_1ad1ae6edb8ea375a3472ef14313b591e2}

```cpp
using mavsdk::Action::GetTakeoffAltitudeCallback =  std::function<void(Result, float)>
```


Callback type for get_takeoff_altitude_async.


### typedef GetMaximumSpeedCallback {#classmavsdk_1_1_action_1a6993096d3e1424a817ad58ce8217a73c}

```cpp
using mavsdk::Action::GetMaximumSpeedCallback =  std::function<void(Result, float)>
```


Callback type for get_maximum_speed_async.


### typedef GetReturnToLaunchAltitudeCallback {#classmavsdk_1_1_action_1af28acf6f7cff11f3c583761edb7d7415}

```cpp
using mavsdk::Action::GetReturnToLaunchAltitudeCallback =  std::function<void(Result, float)>
```


Callback type for get_return_to_launch_altitude_async.


## Member Enumeration Documentation


### enum Result {#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51}


Possible results returned for action requests.


Value | Description
--- | ---
<span id="classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51a88183b946cc5f0e8c96b2e66e1c74a7e"></span> `Unknown` | Unknown result. 
<span id="classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51a505a83f220c02df2f85c3810cd9ceb38"></span> `Success` | Request was successful. 
<span id="classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51a1119faf72ba0dfb23aeea644fed960ad"></span> `NoSystem` | No system is connected. 
<span id="classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51a094a6f6b0868122a9dd008cb91c083e4"></span> `ConnectionError` | Connection error. 
<span id="classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51ad8a942ef2b04672adfafef0ad817a407"></span> `Busy` | Vehicle is busy. 
<span id="classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51a3398e12855176d55f43d53e04f472c8a"></span> `CommandDenied` | Command refused by vehicle. 
<span id="classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51a2dfd6d9491cefa8820ce47f77471e5e3"></span> `CommandDeniedLandedStateUnknown` | Command refused because landed state is unknown. 
<span id="classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51a73d9a6e3b34d98fa3c4fac08f3434a9a"></span> `CommandDeniedNotLanded` | Command refused because vehicle not landed. 
<span id="classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51ac85a251cc457840f1e032f1b733e9398"></span> `Timeout` | Request timed out. 
<span id="classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51a7006c2f81a7a1a65a23cfc16b0326336"></span> `VtolTransitionSupportUnknown` | Hybrid/VTOL transition support is unknown. 
<span id="classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51a5039f02d708e3874858b22610ed63d1e"></span> `NoVtolTransitionSupport` | Vehicle does not support hybrid/VTOL transitions. 
<span id="classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51a189976b733e988a6903e4d19d8cd2fea"></span> `ParameterError` | Error getting or setting parameter. 

## Member Function Documentation


### arm_async() {#classmavsdk_1_1_action_1a570a3799ca5dbbf8aab30ce465687796}
```cpp
void mavsdk::Action::arm_async(const ResultCallback callback)
```


Send command to arm the drone.

Arming a drone normally causes motors to spin at idle. Before arming take all safety precautions and stand clear of the drone!


This function is non-blocking. See 'arm' for the blocking counterpart.

**Parameters**

* const [ResultCallback](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a70a7b6e742d0c86728dc2e1827dacccd) **callback** - 

### arm() {#classmavsdk_1_1_action_1a3ee123973982842f46a9f8b6cb952566}
```cpp
Result mavsdk::Action::arm() const
```


Send command to arm the drone.

Arming a drone normally causes motors to spin at idle. Before arming take all safety precautions and stand clear of the drone!


This function is blocking. See 'arm_async' for the non-blocking counterpart.

**Returns**

&emsp;[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) - Result of request.

### disarm_async() {#classmavsdk_1_1_action_1a3107f7f5a2f4a478024667f187f8f2aa}
```cpp
void mavsdk::Action::disarm_async(const ResultCallback callback)
```


Send command to disarm the drone.

This will disarm a drone that considers itself landed. If flying, the drone should reject the disarm command. Disarming means that all motors will stop.


This function is non-blocking. See 'disarm' for the blocking counterpart.

**Parameters**

* const [ResultCallback](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a70a7b6e742d0c86728dc2e1827dacccd) **callback** - 

### disarm() {#classmavsdk_1_1_action_1a44c61110965bcdd3dfb90a08d3c6b6b9}
```cpp
Result mavsdk::Action::disarm() const
```


Send command to disarm the drone.

This will disarm a drone that considers itself landed. If flying, the drone should reject the disarm command. Disarming means that all motors will stop.


This function is blocking. See 'disarm_async' for the non-blocking counterpart.

**Returns**

&emsp;[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) - Result of request.

### takeoff_async() {#classmavsdk_1_1_action_1ab658d938970326db41709d83e02b41e6}
```cpp
void mavsdk::Action::takeoff_async(const ResultCallback callback)
```


Send command to take off and hover.

This switches the drone into position control mode and commands it to take off and hover at the takeoff altitude.


Note that the vehicle must be armed before it can take off.


This function is non-blocking. See 'takeoff' for the blocking counterpart.

**Parameters**

* const [ResultCallback](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a70a7b6e742d0c86728dc2e1827dacccd) **callback** - 

### takeoff() {#classmavsdk_1_1_action_1a0121d39baf922b1d88283230207ab5d0}
```cpp
Result mavsdk::Action::takeoff() const
```


Send command to take off and hover.

This switches the drone into position control mode and commands it to take off and hover at the takeoff altitude.


Note that the vehicle must be armed before it can take off.


This function is blocking. See 'takeoff_async' for the non-blocking counterpart.

**Returns**

&emsp;[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) - Result of request.

### land_async() {#classmavsdk_1_1_action_1a89d146a766d49f1c706c66a3e2b9252d}
```cpp
void mavsdk::Action::land_async(const ResultCallback callback)
```


Send command to land at the current position.

This switches the drone to 'Land' flight mode.


This function is non-blocking. See 'land' for the blocking counterpart.

**Parameters**

* const [ResultCallback](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a70a7b6e742d0c86728dc2e1827dacccd) **callback** - 

### land() {#classmavsdk_1_1_action_1af6429e1bdb2875deebfe98ed53da3d41}
```cpp
Result mavsdk::Action::land() const
```


Send command to land at the current position.

This switches the drone to 'Land' flight mode.


This function is blocking. See 'land_async' for the non-blocking counterpart.

**Returns**

&emsp;[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) - Result of request.

### reboot_async() {#classmavsdk_1_1_action_1a32cfcc71a00afc28f43d2a22c319618c}
```cpp
void mavsdk::Action::reboot_async(const ResultCallback callback)
```


Send command to reboot the drone components.

This will reboot the autopilot, companion computer, camera and gimbal.


This function is non-blocking. See 'reboot' for the blocking counterpart.

**Parameters**

* const [ResultCallback](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a70a7b6e742d0c86728dc2e1827dacccd) **callback** - 

### reboot() {#classmavsdk_1_1_action_1a7f1e1911ca234e5572b3162a45d83c5d}
```cpp
Result mavsdk::Action::reboot() const
```


Send command to reboot the drone components.

This will reboot the autopilot, companion computer, camera and gimbal.


This function is blocking. See 'reboot_async' for the non-blocking counterpart.

**Returns**

&emsp;[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) - Result of request.

### shutdown_async() {#classmavsdk_1_1_action_1a1658a5499c61c46340428bb819453615}
```cpp
void mavsdk::Action::shutdown_async(const ResultCallback callback)
```


Send command to shut down the drone components.

This will shut down the autopilot, onboard computer, camera and gimbal. This command should only be used when the autopilot is disarmed and autopilots commonly reject it if they are not already ready to shut down.


This function is non-blocking. See 'shutdown' for the blocking counterpart.

**Parameters**

* const [ResultCallback](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a70a7b6e742d0c86728dc2e1827dacccd) **callback** - 

### shutdown() {#classmavsdk_1_1_action_1a44522a60732d3968831f0cf6097c5360}
```cpp
Result mavsdk::Action::shutdown() const
```


Send command to shut down the drone components.

This will shut down the autopilot, onboard computer, camera and gimbal. This command should only be used when the autopilot is disarmed and autopilots commonly reject it if they are not already ready to shut down.


This function is blocking. See 'shutdown_async' for the non-blocking counterpart.

**Returns**

&emsp;[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) - Result of request.

### kill_async() {#classmavsdk_1_1_action_1a78c1f15c3b190ba94793045621819e69}
```cpp
void mavsdk::Action::kill_async(const ResultCallback callback)
```


Send command to kill the drone.

This will disarm a drone irrespective of whether it is landed or flying. Note that the drone will fall out of the sky if this command is used while flying.


This function is non-blocking. See 'kill' for the blocking counterpart.

**Parameters**

* const [ResultCallback](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a70a7b6e742d0c86728dc2e1827dacccd) **callback** - 

### kill() {#classmavsdk_1_1_action_1af40fc1ddf588b3796134a9303ebc3667}
```cpp
Result mavsdk::Action::kill() const
```


Send command to kill the drone.

This will disarm a drone irrespective of whether it is landed or flying. Note that the drone will fall out of the sky if this command is used while flying.


This function is blocking. See 'kill_async' for the non-blocking counterpart.

**Returns**

&emsp;[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) - Result of request.

### return_to_launch_async() {#classmavsdk_1_1_action_1abe5bd426de588b246644ee3ddb12517d}
```cpp
void mavsdk::Action::return_to_launch_async(const ResultCallback callback)
```


Send command to return to the launch (takeoff) position and land.

This switches the drone into [Return mode](https://docs.px4.io/master/en/flight_modes/return.html) which generally means it will rise up to a certain altitude to clear any obstacles before heading back to the launch (takeoff) position and land there.


This function is non-blocking. See 'return_to_launch' for the blocking counterpart.

**Parameters**

* const [ResultCallback](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a70a7b6e742d0c86728dc2e1827dacccd) **callback** - 

### return_to_launch() {#classmavsdk_1_1_action_1afd7c225df0495b0947f00e7d2dd64877}
```cpp
Result mavsdk::Action::return_to_launch() const
```


Send command to return to the launch (takeoff) position and land.

This switches the drone into [Return mode](https://docs.px4.io/master/en/flight_modes/return.html) which generally means it will rise up to a certain altitude to clear any obstacles before heading back to the launch (takeoff) position and land there.


This function is blocking. See 'return_to_launch_async' for the non-blocking counterpart.

**Returns**

&emsp;[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) - Result of request.

### goto_location_async() {#classmavsdk_1_1_action_1a6fd615e5571d6e7e3c53a79d2160ffc5}
```cpp
void mavsdk::Action::goto_location_async(double latitude_deg, double longitude_deg, float absolute_altitude_m, float yaw_deg, const ResultCallback callback)
```


Send command to move the vehicle to a specific global position.

The latitude and longitude are given in degrees (WGS84 frame) and the altitude in meters AMSL (above mean sea level).


The yaw angle is in degrees (frame is NED, 0 is North, positive is clockwise).


This function is non-blocking. See 'goto_location' for the blocking counterpart.

**Parameters**

* double **latitude_deg** - 
* double **longitude_deg** - 
* float **absolute_altitude_m** - 
* float **yaw_deg** - 
* const [ResultCallback](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a70a7b6e742d0c86728dc2e1827dacccd) **callback** - 

### goto_location() {#classmavsdk_1_1_action_1afb3546fa994357e491816f2032716818}
```cpp
Result mavsdk::Action::goto_location(double latitude_deg, double longitude_deg, float absolute_altitude_m, float yaw_deg) const
```


Send command to move the vehicle to a specific global position.

The latitude and longitude are given in degrees (WGS84 frame) and the altitude in meters AMSL (above mean sea level).


The yaw angle is in degrees (frame is NED, 0 is North, positive is clockwise).


This function is blocking. See 'goto_location_async' for the non-blocking counterpart.

**Parameters**

* double **latitude_deg** - 
* double **longitude_deg** - 
* float **absolute_altitude_m** - 
* float **yaw_deg** - 

**Returns**

&emsp;[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) - Result of request.

### transition_to_fixedwing_async() {#classmavsdk_1_1_action_1aa56181441cd64e092a8fb91a38c7c9fd}
```cpp
void mavsdk::Action::transition_to_fixedwing_async(const ResultCallback callback)
```


Send command to transition the drone to fixedwing.

The associated action will only be executed for VTOL vehicles (on other vehicle types the command will fail). The command will succeed if called when the vehicle is already in fixedwing mode.


This function is non-blocking. See 'transition_to_fixedwing' for the blocking counterpart.

**Parameters**

* const [ResultCallback](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a70a7b6e742d0c86728dc2e1827dacccd) **callback** - 

### transition_to_fixedwing() {#classmavsdk_1_1_action_1a8d5cf999a48ea3859ec75db27cf4fbda}
```cpp
Result mavsdk::Action::transition_to_fixedwing() const
```


Send command to transition the drone to fixedwing.

The associated action will only be executed for VTOL vehicles (on other vehicle types the command will fail). The command will succeed if called when the vehicle is already in fixedwing mode.


This function is blocking. See 'transition_to_fixedwing_async' for the non-blocking counterpart.

**Returns**

&emsp;[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) - Result of request.

### transition_to_multicopter_async() {#classmavsdk_1_1_action_1a8c109076641b5c9aa6dd78ea8b913529}
```cpp
void mavsdk::Action::transition_to_multicopter_async(const ResultCallback callback)
```


Send command to transition the drone to multicopter.

The associated action will only be executed for VTOL vehicles (on other vehicle types the command will fail). The command will succeed if called when the vehicle is already in multicopter mode.


This function is non-blocking. See 'transition_to_multicopter' for the blocking counterpart.

**Parameters**

* const [ResultCallback](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a70a7b6e742d0c86728dc2e1827dacccd) **callback** - 

### transition_to_multicopter() {#classmavsdk_1_1_action_1aac94bfb8613a8e9869e3620b3dc9bb8e}
```cpp
Result mavsdk::Action::transition_to_multicopter() const
```


Send command to transition the drone to multicopter.

The associated action will only be executed for VTOL vehicles (on other vehicle types the command will fail). The command will succeed if called when the vehicle is already in multicopter mode.


This function is blocking. See 'transition_to_multicopter_async' for the non-blocking counterpart.

**Returns**

&emsp;[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) - Result of request.

### get_takeoff_altitude_async() {#classmavsdk_1_1_action_1a0a600e6ef75a69341d8b21243e7b1a71}
```cpp
void mavsdk::Action::get_takeoff_altitude_async(const GetTakeoffAltitudeCallback callback)
```


Get the takeoff altitude (in meters above ground).

This function is non-blocking. See 'get_takeoff_altitude' for the blocking counterpart.

**Parameters**

* const [GetTakeoffAltitudeCallback](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1ad1ae6edb8ea375a3472ef14313b591e2) **callback** - 

### get_takeoff_altitude() {#classmavsdk_1_1_action_1a85df48432c5ed2c6e23831409139ed39}
```cpp
std::pair<Result, float> mavsdk::Action::get_takeoff_altitude() const
```


Get the takeoff altitude (in meters above ground).

This function is blocking. See 'get_takeoff_altitude_async' for the non-blocking counterpart.

**Returns**

&emsp;std::pair< [Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51), float > - Result of request.

### set_takeoff_altitude_async() {#classmavsdk_1_1_action_1a9027c3e5f9eaf37cdfe8c426727c7693}
```cpp
void mavsdk::Action::set_takeoff_altitude_async(float altitude, const ResultCallback callback)
```


Set takeoff altitude (in meters above ground).

This function is non-blocking. See 'set_takeoff_altitude' for the blocking counterpart.

**Parameters**

* float **altitude** - 
* const [ResultCallback](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a70a7b6e742d0c86728dc2e1827dacccd) **callback** - 

### set_takeoff_altitude() {#classmavsdk_1_1_action_1ace2188fe367b3bb10b17b89c88d1f952}
```cpp
Result mavsdk::Action::set_takeoff_altitude(float altitude) const
```


Set takeoff altitude (in meters above ground).

This function is blocking. See 'set_takeoff_altitude_async' for the non-blocking counterpart.

**Parameters**

* float **altitude** - 

**Returns**

&emsp;[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) - Result of request.

### get_maximum_speed_async() {#classmavsdk_1_1_action_1a30aada232be0f805950a78e2005ade75}
```cpp
void mavsdk::Action::get_maximum_speed_async(const GetMaximumSpeedCallback callback)
```


Get the vehicle maximum speed (in metres/second).

This function is non-blocking. See 'get_maximum_speed' for the blocking counterpart.

**Parameters**

* const [GetMaximumSpeedCallback](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a6993096d3e1424a817ad58ce8217a73c) **callback** - 

### get_maximum_speed() {#classmavsdk_1_1_action_1a128bf73fe8d0d359f36a3a9a327799ee}
```cpp
std::pair<Result, float> mavsdk::Action::get_maximum_speed() const
```


Get the vehicle maximum speed (in metres/second).

This function is blocking. See 'get_maximum_speed_async' for the non-blocking counterpart.

**Returns**

&emsp;std::pair< [Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51), float > - Result of request.

### set_maximum_speed_async() {#classmavsdk_1_1_action_1abc99f14481f0d961228c6535da9017a6}
```cpp
void mavsdk::Action::set_maximum_speed_async(float speed, const ResultCallback callback)
```


Set vehicle maximum speed (in metres/second).

This function is non-blocking. See 'set_maximum_speed' for the blocking counterpart.

**Parameters**

* float **speed** - 
* const [ResultCallback](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a70a7b6e742d0c86728dc2e1827dacccd) **callback** - 

### set_maximum_speed() {#classmavsdk_1_1_action_1a5fccee1636215bccf8d77d9dca15134e}
```cpp
Result mavsdk::Action::set_maximum_speed(float speed) const
```


Set vehicle maximum speed (in metres/second).

This function is blocking. See 'set_maximum_speed_async' for the non-blocking counterpart.

**Parameters**

* float **speed** - 

**Returns**

&emsp;[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) - Result of request.

### get_return_to_launch_altitude_async() {#classmavsdk_1_1_action_1aa19935b55d80f63e06397b3ea4b51c22}
```cpp
void mavsdk::Action::get_return_to_launch_altitude_async(const GetReturnToLaunchAltitudeCallback callback)
```


Get the return to launch minimum return altitude (in meters).

This function is non-blocking. See 'get_return_to_launch_altitude' for the blocking counterpart.

**Parameters**

* const [GetReturnToLaunchAltitudeCallback](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1af28acf6f7cff11f3c583761edb7d7415) **callback** - 

### get_return_to_launch_altitude() {#classmavsdk_1_1_action_1aeffd084ea51c8a784e28b44b859b6586}
```cpp
std::pair<Result, float> mavsdk::Action::get_return_to_launch_altitude() const
```


Get the return to launch minimum return altitude (in meters).

This function is blocking. See 'get_return_to_launch_altitude_async' for the non-blocking counterpart.

**Returns**

&emsp;std::pair< [Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51), float > - Result of request.

### set_return_to_launch_altitude_async() {#classmavsdk_1_1_action_1acdc4360c21ec82c57125023c552b3410}
```cpp
void mavsdk::Action::set_return_to_launch_altitude_async(float relative_altitude_m, const ResultCallback callback)
```


Set the return to launch minimum return altitude (in meters).

This function is non-blocking. See 'set_return_to_launch_altitude' for the blocking counterpart.

**Parameters**

* float **relative_altitude_m** - 
* const [ResultCallback](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a70a7b6e742d0c86728dc2e1827dacccd) **callback** - 

### set_return_to_launch_altitude() {#classmavsdk_1_1_action_1a5b05e84d35fad5b0ba2837aae1b3686e}
```cpp
Result mavsdk::Action::set_return_to_launch_altitude(float relative_altitude_m) const
```


Set the return to launch minimum return altitude (in meters).

This function is blocking. See 'set_return_to_launch_altitude_async' for the non-blocking counterpart.

**Parameters**

* float **relative_altitude_m** - 

**Returns**

&emsp;[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) - Result of request.

### operator=() {#classmavsdk_1_1_action_1a1ff7e178b7ededc41bd9ccab0ca07457}
```cpp
const Action& mavsdk::Action::operator=(const Action &)=delete
```


Equality operator (object is not copyable).


**Parameters**

* const [Action](classmavsdk_1_1_action.md)&  - 

**Returns**

&emsp;const [Action](classmavsdk_1_1_action.md) & - 