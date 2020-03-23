# mavsdk::Action Class Reference
`#include: action.h`

----


Enable simple actions such as arming, taking off, and landing. 


## Public Types


Type | Description
--- | ---
enum [Result](#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) | Possible results returned for action requests.
std::function< void([Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51))> [result_callback_t](#classmavsdk_1_1_action_1a11dc8f4beffb082ced5aa4da1f16a2a8) | Callback type for asynchronous [Action](classmavsdk_1_1_action.md) calls.
std::function< void([Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51), float)> [altitude_callback_t](#classmavsdk_1_1_action_1a99dcb321637de8a4f15cfc7eee45a145) | Callback type for get_takeoff_altitude_async.
std::function< void([Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51), float)> [speed_callback_t](#classmavsdk_1_1_action_1a600b3e42c0c56c3e2fa0cfe85e05cbe4) | Callback type for get_maximum_speed_async.
std::function< void([Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51), float)> [relative_altitude_m_callback_t](#classmavsdk_1_1_action_1a675354bc6ae189c03ff3de1c54b9e60e) | Callback type for get_return_to_launch_altitude_async.

## Public Member Functions


Type | Name | Description
---: | --- | ---
&nbsp; | [Action](#classmavsdk_1_1_action_1a5e2a4d65f85d821be691a837453e56ee) ([System](classmavsdk_1_1_system.md) & system) | Constructor. Creates the plugin for a specific [System](classmavsdk_1_1_system.md).
&nbsp; | [~Action](#classmavsdk_1_1_action_1a20428abedfcd9fe413e16d2398ff99b4) () | Destructor (internal use only).
&nbsp; | [Action](#classmavsdk_1_1_action_1a890855f6b3350166a9b0d191e322526b) (const [Action](classmavsdk_1_1_action.md) &)=delete | Copy constructor (object is not copyable).
void | [arm_async](#classmavsdk_1_1_action_1ac82706236482edd67e2f226731f221c1) (const [result_callback_t](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a11dc8f4beffb082ced5aa4da1f16a2a8) callback) | Send command to arm the drone.
[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) | [arm](#classmavsdk_1_1_action_1a3ee123973982842f46a9f8b6cb952566) () const | Synchronous wrapper for [arm_async()](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1ac82706236482edd67e2f226731f221c1).
void | [disarm_async](#classmavsdk_1_1_action_1a56b39e81fec142ac0ce7abe6b6313a80) (const [result_callback_t](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a11dc8f4beffb082ced5aa4da1f16a2a8) callback) | Send command to disarm the drone.
[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) | [disarm](#classmavsdk_1_1_action_1a44c61110965bcdd3dfb90a08d3c6b6b9) () const | Synchronous wrapper for [disarm_async()](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a56b39e81fec142ac0ce7abe6b6313a80).
void | [takeoff_async](#classmavsdk_1_1_action_1a05325bd5c29aa533b95c344e25aa47dd) (const [result_callback_t](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a11dc8f4beffb082ced5aa4da1f16a2a8) callback) | Send command to take off and hover.
[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) | [takeoff](#classmavsdk_1_1_action_1a0121d39baf922b1d88283230207ab5d0) () const | Synchronous wrapper for [takeoff_async()](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a05325bd5c29aa533b95c344e25aa47dd).
void | [land_async](#classmavsdk_1_1_action_1a386b5425dea3449bfd6e20e58a06ab99) (const [result_callback_t](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a11dc8f4beffb082ced5aa4da1f16a2a8) callback) | Send command to land at the current position.
[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) | [land](#classmavsdk_1_1_action_1af6429e1bdb2875deebfe98ed53da3d41) () const | Synchronous wrapper for [land_async()](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a386b5425dea3449bfd6e20e58a06ab99).
void | [reboot_async](#classmavsdk_1_1_action_1a451d9181f96fedc444b4bc99323354e3) (const [result_callback_t](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a11dc8f4beffb082ced5aa4da1f16a2a8) callback) | Send command to reboot the drone components.
[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) | [reboot](#classmavsdk_1_1_action_1a7f1e1911ca234e5572b3162a45d83c5d) () const | Synchronous wrapper for [reboot_async()](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a451d9181f96fedc444b4bc99323354e3).
void | [shutdown_async](#classmavsdk_1_1_action_1a0895fce498339d10b311605afa05b70e) (const [result_callback_t](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a11dc8f4beffb082ced5aa4da1f16a2a8) callback) | <ul>
<li><p>Send command to shut down the drone components. </p></li>
</ul>
[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) | [shutdown](#classmavsdk_1_1_action_1a44522a60732d3968831f0cf6097c5360) () const | Synchronous wrapper for [shutdown_async()](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a0895fce498339d10b311605afa05b70e).
void | [kill_async](#classmavsdk_1_1_action_1a1a6d69c174df758b6f06a45e429265db) (const [result_callback_t](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a11dc8f4beffb082ced5aa4da1f16a2a8) callback) | Send command to kill the drone.
[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) | [kill](#classmavsdk_1_1_action_1af40fc1ddf588b3796134a9303ebc3667) () const | Synchronous wrapper for [kill_async()](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a1a6d69c174df758b6f06a45e429265db).
void | [return_to_launch_async](#classmavsdk_1_1_action_1a3b3d5dc86e0d177280b89ec021b94803) (const [result_callback_t](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a11dc8f4beffb082ced5aa4da1f16a2a8) callback) | Send command to return to the launch (takeoff) position and land.
[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) | [return_to_launch](#classmavsdk_1_1_action_1afd7c225df0495b0947f00e7d2dd64877) () const | Synchronous wrapper for [return_to_launch_async()](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a3b3d5dc86e0d177280b89ec021b94803).
void | [goto_location_async](#classmavsdk_1_1_action_1a66bc4099b8fff338138fb954671ef07d) (double latitude_deg, double longitude_deg, float absolute_altitude_m, float yaw_deg, const [result_callback_t](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a11dc8f4beffb082ced5aa4da1f16a2a8) callback) | <ul>
<li><p>Send command to move the vehicle to a specific global position. </p></li>
</ul>
[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) | [goto_location](#classmavsdk_1_1_action_1afb3546fa994357e491816f2032716818) (double latitude_deg, double longitude_deg, float absolute_altitude_m, float yaw_deg)const | Synchronous wrapper for [goto_location_async()](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a66bc4099b8fff338138fb954671ef07d).
void | [transition_to_fixedwing_async](#classmavsdk_1_1_action_1ace04a08fdcdd171bc27a86f5f33daeef) (const [result_callback_t](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a11dc8f4beffb082ced5aa4da1f16a2a8) callback) | Send command to transition the drone to fixedwing.
[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) | [transition_to_fixedwing](#classmavsdk_1_1_action_1a8d5cf999a48ea3859ec75db27cf4fbda) () const | Synchronous wrapper for [transition_to_fixedwing_async()](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1ace04a08fdcdd171bc27a86f5f33daeef).
void | [transition_to_multicopter_async](#classmavsdk_1_1_action_1afc5b0e0502685c0a894cbb8445828e8c) (const [result_callback_t](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a11dc8f4beffb082ced5aa4da1f16a2a8) callback) | Send command to transition the drone to multicopter.
[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) | [transition_to_multicopter](#classmavsdk_1_1_action_1aac94bfb8613a8e9869e3620b3dc9bb8e) () const | Synchronous wrapper for [transition_to_multicopter_async()](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1afc5b0e0502685c0a894cbb8445828e8c).
void | [get_takeoff_altitude_async](#classmavsdk_1_1_action_1af4b49c79f3007503d283deccec8aede3) (const [altitude_callback_t](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a99dcb321637de8a4f15cfc7eee45a145) callback) | Get the takeoff altitude (in meters above ground).
std::pair< [Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51), float > | [get_takeoff_altitude](#classmavsdk_1_1_action_1a85df48432c5ed2c6e23831409139ed39) () const | Synchronous wrapper for [get_takeoff_altitude_async()](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1af4b49c79f3007503d283deccec8aede3).
void | [set_takeoff_altitude_async](#classmavsdk_1_1_action_1adef26b58a4d4b9eeff606e6e69e01017) (float altitude, const [result_callback_t](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a11dc8f4beffb082ced5aa4da1f16a2a8) callback) | Set takeoff altitude (in meters above ground).
[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) | [set_takeoff_altitude](#classmavsdk_1_1_action_1ace2188fe367b3bb10b17b89c88d1f952) (float altitude)const | Synchronous wrapper for [set_takeoff_altitude_async()](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adef26b58a4d4b9eeff606e6e69e01017).
void | [get_maximum_speed_async](#classmavsdk_1_1_action_1a71e49cd3da04d18e1442b9eb8fbc9752) (const [speed_callback_t](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a600b3e42c0c56c3e2fa0cfe85e05cbe4) callback) | Get the vehicle maximum speed (in metres/second).
std::pair< [Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51), float > | [get_maximum_speed](#classmavsdk_1_1_action_1a128bf73fe8d0d359f36a3a9a327799ee) () const | Synchronous wrapper for [get_maximum_speed_async()](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a71e49cd3da04d18e1442b9eb8fbc9752).
void | [set_maximum_speed_async](#classmavsdk_1_1_action_1aee7d56cc4702d9003bb359fcc819819e) (float speed, const [result_callback_t](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a11dc8f4beffb082ced5aa4da1f16a2a8) callback) | Set vehicle maximum speed (in metres/second).
[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) | [set_maximum_speed](#classmavsdk_1_1_action_1a5fccee1636215bccf8d77d9dca15134e) (float speed)const | Synchronous wrapper for [set_maximum_speed_async()](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1aee7d56cc4702d9003bb359fcc819819e).
void | [get_return_to_launch_altitude_async](#classmavsdk_1_1_action_1a68c2d091da83b661afb1b01afcf76687) (const [relative_altitude_m_callback_t](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a675354bc6ae189c03ff3de1c54b9e60e) callback) | Get the return to launch minimum return altitude (in meters).
std::pair< [Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51), float > | [get_return_to_launch_altitude](#classmavsdk_1_1_action_1aeffd084ea51c8a784e28b44b859b6586) () const | Synchronous wrapper for [get_return_to_launch_altitude_async()](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a68c2d091da83b661afb1b01afcf76687).
void | [set_return_to_launch_altitude_async](#classmavsdk_1_1_action_1a5603b6ff2ee3ad12b29d9a1e2d055e53) (float relative_altitude_m, const [result_callback_t](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a11dc8f4beffb082ced5aa4da1f16a2a8) callback) | Set the return to launch minimum return altitude (in meters).
[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) | [set_return_to_launch_altitude](#classmavsdk_1_1_action_1a5b05e84d35fad5b0ba2837aae1b3686e) (float relative_altitude_m)const | Synchronous wrapper for [set_return_to_launch_altitude_async()](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a5603b6ff2ee3ad12b29d9a1e2d055e53).
const [Action](classmavsdk_1_1_action.md) & | [operator=](#classmavsdk_1_1_action_1a1ff7e178b7ededc41bd9ccab0ca07457) (const [Action](classmavsdk_1_1_action.md) &)=delete | Equality operator (object is not copyable).

## Static Public Member Functions


Type | Name | Description
---: | --- | ---
const char * | [result_str](#classmavsdk_1_1_action_1a0c6e1120f26f1921ee14caab9099d07b) ([Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) result) | Returns a human-readable English string for a Result.


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


### typedef altitude_callback_t {#classmavsdk_1_1_action_1a99dcb321637de8a4f15cfc7eee45a145}

```cpp
typedef std::function<void(Result, float)> mavsdk::Action::altitude_callback_t
```


Callback type for get_takeoff_altitude_async.


### typedef speed_callback_t {#classmavsdk_1_1_action_1a600b3e42c0c56c3e2fa0cfe85e05cbe4}

```cpp
typedef std::function<void(Result, float)> mavsdk::Action::speed_callback_t
```


Callback type for get_maximum_speed_async.


### typedef relative_altitude_m_callback_t {#classmavsdk_1_1_action_1a675354bc6ae189c03ff3de1c54b9e60e}

```cpp
typedef std::function<void(Result, float)> mavsdk::Action::relative_altitude_m_callback_t
```


Callback type for get_return_to_launch_altitude_async.


## Member Enumeration Documentation


### enum Result {#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51}


Possible results returned for action requests.


Value | Description
--- | ---
<span id="classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51a88183b946cc5f0e8c96b2e66e1c74a7e"></span> `Unknown` | Unknown error. 
<span id="classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51a505a83f220c02df2f85c3810cd9ceb38"></span> `Success` | Success: the action command was accepted by the vehicle. 
<span id="classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51a1119faf72ba0dfb23aeea644fed960ad"></span> `NoSystem` | No system is connected. 
<span id="classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51a094a6f6b0868122a9dd008cb91c083e4"></span> `ConnectionError` | Connection error. 
<span id="classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51ad8a942ef2b04672adfafef0ad817a407"></span> `Busy` | Vehicle is busy. 
<span id="classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51a3398e12855176d55f43d53e04f472c8a"></span> `CommandDenied` | Command refused by vehicle. 
<span id="classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51a2dfd6d9491cefa8820ce47f77471e5e3"></span> `CommandDeniedLandedStateUnknown` | Command refused because landed state is unknown. 
<span id="classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51a73d9a6e3b34d98fa3c4fac08f3434a9a"></span> `CommandDeniedNotLanded` | Command refused because vehicle not landed. 
<span id="classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51ac85a251cc457840f1e032f1b733e9398"></span> `Timeout` | Request timed out. 
<span id="classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51a7006c2f81a7a1a65a23cfc16b0326336"></span> `VtolTransitionSupportUnknown` | Hybrid/VTOL transition refused because VTOL support is unknown. 
<span id="classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51a5039f02d708e3874858b22610ed63d1e"></span> `NoVtolTransitionSupport` | Vehicle does not support hybrid/VTOL transitions. 
<span id="classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51a189976b733e988a6903e4d19d8cd2fea"></span> `ParameterError` | Error getting or setting parameter. 

## Member Function Documentation


### arm_async() {#classmavsdk_1_1_action_1ac82706236482edd67e2f226731f221c1}
```cpp
void mavsdk::Action::arm_async(const result_callback_t callback)
```


Send command to arm the drone.

Arming a drone normally causes motors to spin at idle. Before arming take all safety precautions and stand clear of the drone!

**Parameters**

* const [result_callback_t](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a11dc8f4beffb082ced5aa4da1f16a2a8) **callback** - 

### arm() {#classmavsdk_1_1_action_1a3ee123973982842f46a9f8b6cb952566}
```cpp
Result mavsdk::Action::arm() const
```


Synchronous wrapper for [arm_async()](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1ac82706236482edd67e2f226731f221c1).


**Returns**

&emsp;[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) - Result of request.

### disarm_async() {#classmavsdk_1_1_action_1a56b39e81fec142ac0ce7abe6b6313a80}
```cpp
void mavsdk::Action::disarm_async(const result_callback_t callback)
```


Send command to disarm the drone.

This will disarm a drone that considers itself landed. If flying, the drone should reject the disarm command. Disarming means that all motors will stop.

**Parameters**

* const [result_callback_t](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a11dc8f4beffb082ced5aa4da1f16a2a8) **callback** - 

### disarm() {#classmavsdk_1_1_action_1a44c61110965bcdd3dfb90a08d3c6b6b9}
```cpp
Result mavsdk::Action::disarm() const
```


Synchronous wrapper for [disarm_async()](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a56b39e81fec142ac0ce7abe6b6313a80).


**Returns**

&emsp;[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) - Result of request.

### takeoff_async() {#classmavsdk_1_1_action_1a05325bd5c29aa533b95c344e25aa47dd}
```cpp
void mavsdk::Action::takeoff_async(const result_callback_t callback)
```


Send command to take off and hover.

This switches the drone into position control mode and commands it to take off and hover at the takeoff altitude.


Note that the vehicle must be armed before it can take off.

**Parameters**

* const [result_callback_t](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a11dc8f4beffb082ced5aa4da1f16a2a8) **callback** - 

### takeoff() {#classmavsdk_1_1_action_1a0121d39baf922b1d88283230207ab5d0}
```cpp
Result mavsdk::Action::takeoff() const
```


Synchronous wrapper for [takeoff_async()](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a05325bd5c29aa533b95c344e25aa47dd).


**Returns**

&emsp;[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) - Result of request.

### land_async() {#classmavsdk_1_1_action_1a386b5425dea3449bfd6e20e58a06ab99}
```cpp
void mavsdk::Action::land_async(const result_callback_t callback)
```


Send command to land at the current position.

This switches the drone to 'Land' flight mode.

**Parameters**

* const [result_callback_t](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a11dc8f4beffb082ced5aa4da1f16a2a8) **callback** - 

### land() {#classmavsdk_1_1_action_1af6429e1bdb2875deebfe98ed53da3d41}
```cpp
Result mavsdk::Action::land() const
```


Synchronous wrapper for [land_async()](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a386b5425dea3449bfd6e20e58a06ab99).


**Returns**

&emsp;[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) - Result of request.

### reboot_async() {#classmavsdk_1_1_action_1a451d9181f96fedc444b4bc99323354e3}
```cpp
void mavsdk::Action::reboot_async(const result_callback_t callback)
```


Send command to reboot the drone components.

This will reboot the autopilot, companion computer, camera and gimbal.

**Parameters**

* const [result_callback_t](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a11dc8f4beffb082ced5aa4da1f16a2a8) **callback** - 

### reboot() {#classmavsdk_1_1_action_1a7f1e1911ca234e5572b3162a45d83c5d}
```cpp
Result mavsdk::Action::reboot() const
```


Synchronous wrapper for [reboot_async()](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a451d9181f96fedc444b4bc99323354e3).


**Returns**

&emsp;[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) - Result of request.

### shutdown_async() {#classmavsdk_1_1_action_1a0895fce498339d10b311605afa05b70e}
```cpp
void mavsdk::Action::shutdown_async(const result_callback_t callback)
```


<ul>
<li><p>Send command to shut down the drone components. </p></li>
</ul>

This will shut down the autopilot, onboard computer, camera and gimbal. This command should only be used when the autopilot is disarmed and autopilots commonly reject it if they are not already ready to shut down.

**Parameters**

* const [result_callback_t](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a11dc8f4beffb082ced5aa4da1f16a2a8) **callback** - 

### shutdown() {#classmavsdk_1_1_action_1a44522a60732d3968831f0cf6097c5360}
```cpp
Result mavsdk::Action::shutdown() const
```


Synchronous wrapper for [shutdown_async()](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a0895fce498339d10b311605afa05b70e).


**Returns**

&emsp;[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) - Result of request.

### kill_async() {#classmavsdk_1_1_action_1a1a6d69c174df758b6f06a45e429265db}
```cpp
void mavsdk::Action::kill_async(const result_callback_t callback)
```


Send command to kill the drone.

This will disarm a drone irrespective of whether it is landed or flying. Note that the drone will fall out of the sky if this command is used while flying.

**Parameters**

* const [result_callback_t](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a11dc8f4beffb082ced5aa4da1f16a2a8) **callback** - 

### kill() {#classmavsdk_1_1_action_1af40fc1ddf588b3796134a9303ebc3667}
```cpp
Result mavsdk::Action::kill() const
```


Synchronous wrapper for [kill_async()](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a1a6d69c174df758b6f06a45e429265db).


**Returns**

&emsp;[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) - Result of request.

### return_to_launch_async() {#classmavsdk_1_1_action_1a3b3d5dc86e0d177280b89ec021b94803}
```cpp
void mavsdk::Action::return_to_launch_async(const result_callback_t callback)
```


Send command to return to the launch (takeoff) position and land.

This switches the drone into [RTL mode](https://docs.px4.io/master/en/flight_modes/rtl.html) which generally means it will rise up to a certain altitude to clear any obstacles before heading back to the launch (takeoff) position and land there.

**Parameters**

* const [result_callback_t](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a11dc8f4beffb082ced5aa4da1f16a2a8) **callback** - 

### return_to_launch() {#classmavsdk_1_1_action_1afd7c225df0495b0947f00e7d2dd64877}
```cpp
Result mavsdk::Action::return_to_launch() const
```


Synchronous wrapper for [return_to_launch_async()](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a3b3d5dc86e0d177280b89ec021b94803).


**Returns**

&emsp;[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) - Result of request.

### goto_location_async() {#classmavsdk_1_1_action_1a66bc4099b8fff338138fb954671ef07d}
```cpp
void mavsdk::Action::goto_location_async(double latitude_deg, double longitude_deg, float absolute_altitude_m, float yaw_deg, const result_callback_t callback)
```


<ul>
<li><p>Send command to move the vehicle to a specific global position. </p></li>
</ul>

The latitude and longitude are given in degrees (WGS84 frame) and the altitude in meters AMSL (above mean sea level).


The yaw angle is in degrees (frame is NED, 0 is North, positive is clockwise).

**Parameters**

* double **latitude_deg** - 
* double **longitude_deg** - 
* float **absolute_altitude_m** - 
* float **yaw_deg** - 
* const [result_callback_t](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a11dc8f4beffb082ced5aa4da1f16a2a8) **callback** - 

### goto_location() {#classmavsdk_1_1_action_1afb3546fa994357e491816f2032716818}
```cpp
Result mavsdk::Action::goto_location(double latitude_deg, double longitude_deg, float absolute_altitude_m, float yaw_deg) const
```


Synchronous wrapper for [goto_location_async()](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a66bc4099b8fff338138fb954671ef07d).


**Parameters**

* double **latitude_deg** - 
* double **longitude_deg** - 
* float **absolute_altitude_m** - 
* float **yaw_deg** - 

**Returns**

&emsp;[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) - Result of request.

### transition_to_fixedwing_async() {#classmavsdk_1_1_action_1ace04a08fdcdd171bc27a86f5f33daeef}
```cpp
void mavsdk::Action::transition_to_fixedwing_async(const result_callback_t callback)
```


Send command to transition the drone to fixedwing.

The associated action will only be executed for VTOL vehicles (on other vehicle types the command will fail). The command will succeed if called when the vehicle is already in fixedwing mode.

**Parameters**

* const [result_callback_t](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a11dc8f4beffb082ced5aa4da1f16a2a8) **callback** - 

### transition_to_fixedwing() {#classmavsdk_1_1_action_1a8d5cf999a48ea3859ec75db27cf4fbda}
```cpp
Result mavsdk::Action::transition_to_fixedwing() const
```


Synchronous wrapper for [transition_to_fixedwing_async()](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1ace04a08fdcdd171bc27a86f5f33daeef).


**Returns**

&emsp;[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) - Result of request.

### transition_to_multicopter_async() {#classmavsdk_1_1_action_1afc5b0e0502685c0a894cbb8445828e8c}
```cpp
void mavsdk::Action::transition_to_multicopter_async(const result_callback_t callback)
```


Send command to transition the drone to multicopter.

The associated action will only be executed for VTOL vehicles (on other vehicle types the command will fail). The command will succeed if called when the vehicle is already in multicopter mode.

**Parameters**

* const [result_callback_t](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a11dc8f4beffb082ced5aa4da1f16a2a8) **callback** - 

### transition_to_multicopter() {#classmavsdk_1_1_action_1aac94bfb8613a8e9869e3620b3dc9bb8e}
```cpp
Result mavsdk::Action::transition_to_multicopter() const
```


Synchronous wrapper for [transition_to_multicopter_async()](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1afc5b0e0502685c0a894cbb8445828e8c).


**Returns**

&emsp;[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) - Result of request.

### get_takeoff_altitude_async() {#classmavsdk_1_1_action_1af4b49c79f3007503d283deccec8aede3}
```cpp
void mavsdk::Action::get_takeoff_altitude_async(const altitude_callback_t callback)
```


Get the takeoff altitude (in meters above ground).


**Parameters**

* const [altitude_callback_t](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a99dcb321637de8a4f15cfc7eee45a145) **callback** - 

### get_takeoff_altitude() {#classmavsdk_1_1_action_1a85df48432c5ed2c6e23831409139ed39}
```cpp
std::pair<Result, float> mavsdk::Action::get_takeoff_altitude() const
```


Synchronous wrapper for [get_takeoff_altitude_async()](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1af4b49c79f3007503d283deccec8aede3).


**Returns**

&emsp;std::pair< [Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51), float > - Result of request.

### set_takeoff_altitude_async() {#classmavsdk_1_1_action_1adef26b58a4d4b9eeff606e6e69e01017}
```cpp
void mavsdk::Action::set_takeoff_altitude_async(float altitude, const result_callback_t callback)
```


Set takeoff altitude (in meters above ground).


**Parameters**

* float **altitude** - 
* const [result_callback_t](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a11dc8f4beffb082ced5aa4da1f16a2a8) **callback** - 

### set_takeoff_altitude() {#classmavsdk_1_1_action_1ace2188fe367b3bb10b17b89c88d1f952}
```cpp
Result mavsdk::Action::set_takeoff_altitude(float altitude) const
```


Synchronous wrapper for [set_takeoff_altitude_async()](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adef26b58a4d4b9eeff606e6e69e01017).


**Parameters**

* float **altitude** - 

**Returns**

&emsp;[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) - Result of request.

### get_maximum_speed_async() {#classmavsdk_1_1_action_1a71e49cd3da04d18e1442b9eb8fbc9752}
```cpp
void mavsdk::Action::get_maximum_speed_async(const speed_callback_t callback)
```


Get the vehicle maximum speed (in metres/second).


**Parameters**

* const [speed_callback_t](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a600b3e42c0c56c3e2fa0cfe85e05cbe4) **callback** - 

### get_maximum_speed() {#classmavsdk_1_1_action_1a128bf73fe8d0d359f36a3a9a327799ee}
```cpp
std::pair<Result, float> mavsdk::Action::get_maximum_speed() const
```


Synchronous wrapper for [get_maximum_speed_async()](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a71e49cd3da04d18e1442b9eb8fbc9752).


**Returns**

&emsp;std::pair< [Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51), float > - Result of request.

### set_maximum_speed_async() {#classmavsdk_1_1_action_1aee7d56cc4702d9003bb359fcc819819e}
```cpp
void mavsdk::Action::set_maximum_speed_async(float speed, const result_callback_t callback)
```


Set vehicle maximum speed (in metres/second).


**Parameters**

* float **speed** - 
* const [result_callback_t](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a11dc8f4beffb082ced5aa4da1f16a2a8) **callback** - 

### set_maximum_speed() {#classmavsdk_1_1_action_1a5fccee1636215bccf8d77d9dca15134e}
```cpp
Result mavsdk::Action::set_maximum_speed(float speed) const
```


Synchronous wrapper for [set_maximum_speed_async()](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1aee7d56cc4702d9003bb359fcc819819e).


**Parameters**

* float **speed** - 

**Returns**

&emsp;[Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) - Result of request.

### get_return_to_launch_altitude_async() {#classmavsdk_1_1_action_1a68c2d091da83b661afb1b01afcf76687}
```cpp
void mavsdk::Action::get_return_to_launch_altitude_async(const relative_altitude_m_callback_t callback)
```


Get the return to launch minimum return altitude (in meters).


**Parameters**

* const [relative_altitude_m_callback_t](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a675354bc6ae189c03ff3de1c54b9e60e) **callback** - 

### get_return_to_launch_altitude() {#classmavsdk_1_1_action_1aeffd084ea51c8a784e28b44b859b6586}
```cpp
std::pair<Result, float> mavsdk::Action::get_return_to_launch_altitude() const
```


Synchronous wrapper for [get_return_to_launch_altitude_async()](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a68c2d091da83b661afb1b01afcf76687).


**Returns**

&emsp;std::pair< [Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51), float > - Result of request.

### set_return_to_launch_altitude_async() {#classmavsdk_1_1_action_1a5603b6ff2ee3ad12b29d9a1e2d055e53}
```cpp
void mavsdk::Action::set_return_to_launch_altitude_async(float relative_altitude_m, const result_callback_t callback)
```


Set the return to launch minimum return altitude (in meters).


**Parameters**

* float **relative_altitude_m** - 
* const [result_callback_t](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a11dc8f4beffb082ced5aa4da1f16a2a8) **callback** - 

### set_return_to_launch_altitude() {#classmavsdk_1_1_action_1a5b05e84d35fad5b0ba2837aae1b3686e}
```cpp
Result mavsdk::Action::set_return_to_launch_altitude(float relative_altitude_m) const
```


Synchronous wrapper for [set_return_to_launch_altitude_async()](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a5603b6ff2ee3ad12b29d9a1e2d055e53).


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

### result_str() {#classmavsdk_1_1_action_1a0c6e1120f26f1921ee14caab9099d07b}
```cpp
static const char* mavsdk::Action::result_str(Result result)
```


Returns a human-readable English string for a Result.


**Parameters**

* [Result](classmavsdk_1_1_action.md#classmavsdk_1_1_action_1adc2e13257ef13de0e7610cf879a0ec51) **result** - The enum value for which a human readable string is required.

**Returns**

&emsp;const char * - Human readable string for the Result.