# dronecore::Action Class Reference
`#include: action.h`

----


The [Action](classdronecore_1_1_action.md) class enables simple actions for a drone such as arming, taking off, and landing. 


Synchronous and asynchronous variants of the action methods are supplied.


The action methods send their associated MAVLink commands to the vehicle and complete (return synchronously or callback asynchronously) with an ActionResult value indicating whether the vehicle has accepted or rejected the command, or that there has been some error. If the command is accepted, the vehicle will then start to perform the associated action. 


## Public Types


Type | Description
--- | ---
std::function< void([ActionResult](namespacedronecore.md#namespacedronecore_1aedb56a8f642ce3cb7bc4b940c67033c5))> [result_callback_t](#classdronecore_1_1_action_1a24edb68003d96a52c80de6851ca1dde5) | Callback type for asynchronous [Action](classdronecore_1_1_action.md) calls.

## Public Member Functions


Type | Name | Description
---: | --- | ---
&nbsp; | [Action](#classdronecore_1_1_action_1a116c75c6b2cd6dc19788b777e56299a9) ([System](classdronecore_1_1_system.md) & system) | Constructor. Creates the plugin for a specific [System](classdronecore_1_1_system.md).
&nbsp; | [~Action](#classdronecore_1_1_action_1a6bb0301fecf66d75ca3b27bda25af7f2) () | Destructor (internal use only).
&nbsp; | [Action](#classdronecore_1_1_action_1ae48b0e06ca2b4b7544a10c7734a03f63) (const [Action](classdronecore_1_1_action.md) &)=delete | Copy constructor (object is not copyable).
[ActionResult](namespacedronecore.md#namespacedronecore_1aedb56a8f642ce3cb7bc4b940c67033c5) | [arm](#classdronecore_1_1_action_1af71179444e1c67550202d498c19ad2ff) () const | Send command to *arm* the drone (synchronous).
[ActionResult](namespacedronecore.md#namespacedronecore_1aedb56a8f642ce3cb7bc4b940c67033c5) | [disarm](#classdronecore_1_1_action_1a0ab29022df5d93d4f590d83a3e9c4349) () const | Send command to *disarm* the drone (synchronous).
[ActionResult](namespacedronecore.md#namespacedronecore_1aedb56a8f642ce3cb7bc4b940c67033c5) | [kill](#classdronecore_1_1_action_1a615cff3ac4321340a9871416d2ca1db8) () const | Send command to *kill* the drone (synchronous).
[ActionResult](namespacedronecore.md#namespacedronecore_1aedb56a8f642ce3cb7bc4b940c67033c5) | [takeoff](#classdronecore_1_1_action_1a1d6244edfd39272d97bf8b126eb98629) () const | Send command to *take off and hover* (synchronous).
[ActionResult](namespacedronecore.md#namespacedronecore_1aedb56a8f642ce3cb7bc4b940c67033c5) | [land](#classdronecore_1_1_action_1a08367528cdf25404b7db6db457e3c6f9) () const | Send command to *land* at the current position (synchronous).
[ActionResult](namespacedronecore.md#namespacedronecore_1aedb56a8f642ce3cb7bc4b940c67033c5) | [return_to_launch](#classdronecore_1_1_action_1a740a3bf125560edaf810865a616b2d24) () const | Send command to *return to the launch* (takeoff) position and *land* (asynchronous).
[ActionResult](namespacedronecore.md#namespacedronecore_1aedb56a8f642ce3cb7bc4b940c67033c5) | [transition_to_fixedwing](#classdronecore_1_1_action_1a559e6cfa22f937acc0bbd1f9ac4e54fa) () const | Send command to transition the drone to fixedwing.
[ActionResult](namespacedronecore.md#namespacedronecore_1aedb56a8f642ce3cb7bc4b940c67033c5) | [transition_to_multicopter](#classdronecore_1_1_action_1a3af080379382fedbc3ad8bdbaf3c4e4c) () const | Send command to transition the drone to multicopter.
void | [arm_async](#classdronecore_1_1_action_1a1a27165400d2a8419c2d96a1c0f2aa78) ([result_callback_t](classdronecore_1_1_action.md#classdronecore_1_1_action_1a24edb68003d96a52c80de6851ca1dde5) callback) | Send command to *arm* the drone (asynchronous).
void | [disarm_async](#classdronecore_1_1_action_1acc0a17411a25f5641ae21046b459e79e) ([result_callback_t](classdronecore_1_1_action.md#classdronecore_1_1_action_1a24edb68003d96a52c80de6851ca1dde5) callback) | Send command to *disarm* the drone (asynchronous).
void | [kill_async](#classdronecore_1_1_action_1a1d7d09191d9319c7912962b2dd02caa7) ([result_callback_t](classdronecore_1_1_action.md#classdronecore_1_1_action_1a24edb68003d96a52c80de6851ca1dde5) callback) | Send command to *kill* the drone (asynchronous).
void | [takeoff_async](#classdronecore_1_1_action_1a2aec10a2b14f5e82f05edc6e2feac83e) ([result_callback_t](classdronecore_1_1_action.md#classdronecore_1_1_action_1a24edb68003d96a52c80de6851ca1dde5) callback) | Send command to *take off and hover* (asynchronous).
void | [land_async](#classdronecore_1_1_action_1a7f10240cde2ff237795e3688802d857b) ([result_callback_t](classdronecore_1_1_action.md#classdronecore_1_1_action_1a24edb68003d96a52c80de6851ca1dde5) callback) | Send command to *land* at the current position (asynchronous).
void | [return_to_launch_async](#classdronecore_1_1_action_1aa1253c356c7628d329dfa98d78eb39ee) ([result_callback_t](classdronecore_1_1_action.md#classdronecore_1_1_action_1a24edb68003d96a52c80de6851ca1dde5) callback) | Send command to *return to the launch* (takeoff) position and *land* (asynchronous).
void | [transition_to_fixedwing_async](#classdronecore_1_1_action_1af5b02f05ffdc2e0787a7633410710d9d) ([result_callback_t](classdronecore_1_1_action.md#classdronecore_1_1_action_1a24edb68003d96a52c80de6851ca1dde5) callback) | Send command to transition the drone to fixedwing (asynchronous).
void | [transition_to_multicopter_async](#classdronecore_1_1_action_1a053aa7430852a4200b201abda1b3b3e4) ([result_callback_t](classdronecore_1_1_action.md#classdronecore_1_1_action_1a24edb68003d96a52c80de6851ca1dde5) callback) | Send command to transition the drone to multicopter (asynchronous).
void | [set_takeoff_altitude](#classdronecore_1_1_action_1adc6f7f6668d3681afa4d820095154c9d) (float relative_altitude_m) | Set takeoff altitude above ground.
float | [get_takeoff_altitude_m](#classdronecore_1_1_action_1a1888deebcc48d906c3c19473596e6fec) () const | Get the takeoff altitude.
void | [set_max_speed](#classdronecore_1_1_action_1abc27410a9b2a938b21ab59c5ef9ee941) (float speed_m_s) | Set vehicle maximum speed.
float | [get_max_speed_m_s](#classdronecore_1_1_action_1ad6c8a98e0c331666c14cb996fa5dc605) () const | Get the vehicle maximum speed.
const [Action](classdronecore_1_1_action.md) & | [operator=](#classdronecore_1_1_action_1a89f6cdf19fc05054fa746ebd3d88e17a) (const [Action](classdronecore_1_1_action.md) &)=delete | Equality operator (object is not copyable).


## Constructor & Destructor Documentation


### Action() {#classdronecore_1_1_action_1a116c75c6b2cd6dc19788b777e56299a9}
```cpp
dronecore::Action::Action(System &system)
```


Constructor. Creates the plugin for a specific [System](classdronecore_1_1_system.md).

The plugin is typically created as shown below: 

```cpp
auto action = std::make_shared<Action>(system);
```

**Parameters**

* [System](classdronecore_1_1_system.md)& **system** - The specific system associated with this plugin.

### ~Action() {#classdronecore_1_1_action_1a6bb0301fecf66d75ca3b27bda25af7f2}
```cpp
dronecore::Action::~Action()
```


Destructor (internal use only).


### Action() {#classdronecore_1_1_action_1ae48b0e06ca2b4b7544a10c7734a03f63}
```cpp
dronecore::Action::Action(const Action &)=delete
```


Copy constructor (object is not copyable).


**Parameters**

* const [Action](classdronecore_1_1_action.md)&  - 

## Member Typdef Documentation


### typedef result_callback_t {#classdronecore_1_1_action_1a24edb68003d96a52c80de6851ca1dde5}

```cpp
typedef std::function<void(ActionResult)> dronecore::Action::result_callback_t
```


Callback type for asynchronous [Action](classdronecore_1_1_action.md) calls.


## Member Function Documentation


### arm() {#classdronecore_1_1_action_1af71179444e1c67550202d498c19ad2ff}
```cpp
ActionResult dronecore::Action::arm() const
```


Send command to *arm* the drone (synchronous).

> **Note** Arming a drone normally causes motors to spin at idle. Before arming take all safety precautions and stand clear of the drone!

**Returns**

&emsp;[ActionResult](namespacedronecore.md#namespacedronecore_1aedb56a8f642ce3cb7bc4b940c67033c5) - ActionResult of request.

### disarm() {#classdronecore_1_1_action_1a0ab29022df5d93d4f590d83a3e9c4349}
```cpp
ActionResult dronecore::Action::disarm() const
```


Send command to *disarm* the drone (synchronous).

This will disarm a drone that considers itself landed. If flying, the drone should reject the disarm command. Disarming means that all motors will stop.

**Returns**

&emsp;[ActionResult](namespacedronecore.md#namespacedronecore_1aedb56a8f642ce3cb7bc4b940c67033c5) - ActionResult of request.

### kill() {#classdronecore_1_1_action_1a615cff3ac4321340a9871416d2ca1db8}
```cpp
ActionResult dronecore::Action::kill() const
```


Send command to *kill* the drone (synchronous).

This will disarm a drone irrespective of whether it is landed or flying. Note that the drone will fall out of the sky if this command is used while flying.

**Returns**

&emsp;[ActionResult](namespacedronecore.md#namespacedronecore_1aedb56a8f642ce3cb7bc4b940c67033c5) - ActionResult of request.

### takeoff() {#classdronecore_1_1_action_1a1d6244edfd39272d97bf8b126eb98629}
```cpp
ActionResult dronecore::Action::takeoff() const
```


Send command to *take off and hover* (synchronous).

This switches the drone into position control mode and commands it to take off and hover at the takeoff altitude (set using [set_takeoff_altitude()](classdronecore_1_1_action.md#classdronecore_1_1_action_1adc6f7f6668d3681afa4d820095154c9d)).


Note that the vehicle must be armed before it can take off.

**Returns**

&emsp;[ActionResult](namespacedronecore.md#namespacedronecore_1aedb56a8f642ce3cb7bc4b940c67033c5) - ActionResult of request.

### land() {#classdronecore_1_1_action_1a08367528cdf25404b7db6db457e3c6f9}
```cpp
ActionResult dronecore::Action::land() const
```


Send command to *land* at the current position (synchronous).

This switches the drone to [Land mode](https://docs.px4.io/en/flight_modes/land.html).

**Returns**

&emsp;[ActionResult](namespacedronecore.md#namespacedronecore_1aedb56a8f642ce3cb7bc4b940c67033c5) - ActionResult of request.

### return_to_launch() {#classdronecore_1_1_action_1a740a3bf125560edaf810865a616b2d24}
```cpp
ActionResult dronecore::Action::return_to_launch() const
```


Send command to *return to the launch* (takeoff) position and *land* (asynchronous).

This switches the drone into [RTL mode](https://docs.px4.io/en/flight_modes/rtl.html) which generally means it will rise up to a certain altitude to clear any obstacles before heading back to the launch (takeoff) position and land there.

**Returns**

&emsp;[ActionResult](namespacedronecore.md#namespacedronecore_1aedb56a8f642ce3cb7bc4b940c67033c5) - ActionResult of request.

### transition_to_fixedwing() {#classdronecore_1_1_action_1a559e6cfa22f937acc0bbd1f9ac4e54fa}
```cpp
ActionResult dronecore::Action::transition_to_fixedwing() const
```


Send command to transition the drone to fixedwing.

The associated action will only be executed for VTOL vehicles (on other vehicle types the command will fail with an ActionResult). The command will succeed if called when the vehicle is already in fixedwing mode.

**Returns**

&emsp;[ActionResult](namespacedronecore.md#namespacedronecore_1aedb56a8f642ce3cb7bc4b940c67033c5) - ActionResult of request.

### transition_to_multicopter() {#classdronecore_1_1_action_1a3af080379382fedbc3ad8bdbaf3c4e4c}
```cpp
ActionResult dronecore::Action::transition_to_multicopter() const
```


Send command to transition the drone to multicopter.

The associated action will only be executed for VTOL vehicles (on other vehicle types the command will fail with an ActionResult). The command will succeed if called when the vehicle is already in multicopter mode.

**Returns**

&emsp;[ActionResult](namespacedronecore.md#namespacedronecore_1aedb56a8f642ce3cb7bc4b940c67033c5) - ActionResult of request.

### arm_async() {#classdronecore_1_1_action_1a1a27165400d2a8419c2d96a1c0f2aa78}
```cpp
void dronecore::Action::arm_async(result_callback_t callback)
```


Send command to *arm* the drone (asynchronous).

Note that arming a drone normally means that the motors will spin at idle. Therefore, before arming take all safety precautions and stand clear of the drone.

**Parameters**

* [result_callback_t](classdronecore_1_1_action.md#classdronecore_1_1_action_1a24edb68003d96a52c80de6851ca1dde5) **callback** - Function to call with result of request.

### disarm_async() {#classdronecore_1_1_action_1acc0a17411a25f5641ae21046b459e79e}
```cpp
void dronecore::Action::disarm_async(result_callback_t callback)
```


Send command to *disarm* the drone (asynchronous).

This will disarm a drone that considers itself landed. If flying, the drone should reject the disarm command. Disarming means that all motors will stop.

**Parameters**

* [result_callback_t](classdronecore_1_1_action.md#classdronecore_1_1_action_1a24edb68003d96a52c80de6851ca1dde5) **callback** - Function to call with result of request.

### kill_async() {#classdronecore_1_1_action_1a1d7d09191d9319c7912962b2dd02caa7}
```cpp
void dronecore::Action::kill_async(result_callback_t callback)
```


Send command to *kill* the drone (asynchronous).

This will disarm a drone irrespective of whether it is landed or flying. Note that the drone will fall out of the sky if you use this command while flying.

**Parameters**

* [result_callback_t](classdronecore_1_1_action.md#classdronecore_1_1_action_1a24edb68003d96a52c80de6851ca1dde5) **callback** - Function to call with result of request.

### takeoff_async() {#classdronecore_1_1_action_1a2aec10a2b14f5e82f05edc6e2feac83e}
```cpp
void dronecore::Action::takeoff_async(result_callback_t callback)
```


Send command to *take off and hover* (asynchronous).

This switches the drone into position control mode and commands it to take off and hover at the takeoff altitude set using [set_takeoff_altitude()](classdronecore_1_1_action.md#classdronecore_1_1_action_1adc6f7f6668d3681afa4d820095154c9d).


Note that the vehicle must be armed before it can take off.

**Parameters**

* [result_callback_t](classdronecore_1_1_action.md#classdronecore_1_1_action_1a24edb68003d96a52c80de6851ca1dde5) **callback** - Function to call with result of request

### land_async() {#classdronecore_1_1_action_1a7f10240cde2ff237795e3688802d857b}
```cpp
void dronecore::Action::land_async(result_callback_t callback)
```


Send command to *land* at the current position (asynchronous).

This switches the drone to [Land mode](https://docs.px4.io/en/flight_modes/land.html).

**Parameters**

* [result_callback_t](classdronecore_1_1_action.md#classdronecore_1_1_action_1a24edb68003d96a52c80de6851ca1dde5) **callback** - Function to call with result of request.

### return_to_launch_async() {#classdronecore_1_1_action_1aa1253c356c7628d329dfa98d78eb39ee}
```cpp
void dronecore::Action::return_to_launch_async(result_callback_t callback)
```


Send command to *return to the launch* (takeoff) position and *land* (asynchronous).

This switches the drone into [RTL mode](https://docs.px4.io/en/flight_modes/rtl.html) which generally means it will rise up to a certain altitude to clear any obstacles before heading back to the launch (takeoff) position and land there.

**Parameters**

* [result_callback_t](classdronecore_1_1_action.md#classdronecore_1_1_action_1a24edb68003d96a52c80de6851ca1dde5) **callback** - Function to call with result of request.

### transition_to_fixedwing_async() {#classdronecore_1_1_action_1af5b02f05ffdc2e0787a7633410710d9d}
```cpp
void dronecore::Action::transition_to_fixedwing_async(result_callback_t callback)
```


Send command to transition the drone to fixedwing (asynchronous).

The associated action will only be executed for VTOL vehicles (on other vehicle types the command will fail with an ActionResult). The command will succeed if called when the vehicle is already in fixedwing mode.

**Parameters**

* [result_callback_t](classdronecore_1_1_action.md#classdronecore_1_1_action_1a24edb68003d96a52c80de6851ca1dde5) **callback** - Function to call with result of request.

### transition_to_multicopter_async() {#classdronecore_1_1_action_1a053aa7430852a4200b201abda1b3b3e4}
```cpp
void dronecore::Action::transition_to_multicopter_async(result_callback_t callback)
```


Send command to transition the drone to multicopter (asynchronous).

The associated action will only be executed for VTOL vehicles (on other vehicle types the command will fail with an ActionResult). The command will succeed if called when the vehicle is already in multicopter mode.

**Parameters**

* [result_callback_t](classdronecore_1_1_action.md#classdronecore_1_1_action_1a24edb68003d96a52c80de6851ca1dde5) **callback** - Function to call with result of request.

### set_takeoff_altitude() {#classdronecore_1_1_action_1adc6f7f6668d3681afa4d820095154c9d}
```cpp
void dronecore::Action::set_takeoff_altitude(float relative_altitude_m)
```


Set takeoff altitude above ground.


**Parameters**

* float **relative_altitude_m** - Takeoff altitude relative to takeoff location, in meters.

### get_takeoff_altitude_m() {#classdronecore_1_1_action_1a1888deebcc48d906c3c19473596e6fec}
```cpp
float dronecore::Action::get_takeoff_altitude_m() const
```


Get the takeoff altitude.


**Returns**

&emsp;float - takeoff Takeoff altitude relative to ground/takeoff location, in meters.

### set_max_speed() {#classdronecore_1_1_action_1abc27410a9b2a938b21ab59c5ef9ee941}
```cpp
void dronecore::Action::set_max_speed(float speed_m_s)
```


Set vehicle maximum speed.


**Parameters**

* float **speed_m_s** - Maximum speed in metres/second.

### get_max_speed_m_s() {#classdronecore_1_1_action_1ad6c8a98e0c331666c14cb996fa5dc605}
```cpp
float dronecore::Action::get_max_speed_m_s() const
```


Get the vehicle maximum speed.


**Returns**

&emsp;float - Maximum speed in metres/second.

### operator=() {#classdronecore_1_1_action_1a89f6cdf19fc05054fa746ebd3d88e17a}
```cpp
const Action& dronecore::Action::operator=(const Action &)=delete
```


Equality operator (object is not copyable).


**Parameters**

* const [Action](classdronecore_1_1_action.md)&  - 

**Returns**

&emsp;const [Action](classdronecore_1_1_action.md) & - 