# mavsdk::ActionServer Class Reference
`#include: action_server.h`

----


Provide vehicle actions (as a server) such as arming, taking off, and landing. 


## Data Structures


struct [AllowableFlightModes](structmavsdk_1_1_action_server_1_1_allowable_flight_modes.md)

struct [ArmDisarm](structmavsdk_1_1_action_server_1_1_arm_disarm.md)

## Public Types


Type | Description
--- | ---
enum [FlightMode](#classmavsdk_1_1_action_server_1aee12027f5d9380f2c13fa7813c6ae1d8) | Flight modes.
enum [Result](#classmavsdk_1_1_action_server_1a4a8eb4fe9d098a5b7891232fc5bf32f8) | Possible results returned for action requests.
std::function< void([Result](classmavsdk_1_1_action_server.md#classmavsdk_1_1_action_server_1a4a8eb4fe9d098a5b7891232fc5bf32f8))> [ResultCallback](#classmavsdk_1_1_action_server_1affc7fcdc5f60e367bb9032b938223b95) | Callback type for asynchronous [ActionServer](classmavsdk_1_1_action_server.md) calls.
std::function< void([Result](classmavsdk_1_1_action_server.md#classmavsdk_1_1_action_server_1a4a8eb4fe9d098a5b7891232fc5bf32f8), [ArmDisarm](structmavsdk_1_1_action_server_1_1_arm_disarm.md))> [ArmDisarmCallback](#classmavsdk_1_1_action_server_1a8ef1c6ec94f6bf5173d208be15b14910) | Callback type for subscribe_arm_disarm.
std::function< void([Result](classmavsdk_1_1_action_server.md#classmavsdk_1_1_action_server_1a4a8eb4fe9d098a5b7891232fc5bf32f8), [FlightMode](classmavsdk_1_1_action_server.md#classmavsdk_1_1_action_server_1aee12027f5d9380f2c13fa7813c6ae1d8))> [FlightModeChangeCallback](#classmavsdk_1_1_action_server_1a58a1284a240908bf4d9dd998d5939f6f) | Callback type for subscribe_flight_mode_change.
std::function< void([Result](classmavsdk_1_1_action_server.md#classmavsdk_1_1_action_server_1a4a8eb4fe9d098a5b7891232fc5bf32f8), bool)> [TakeoffCallback](#classmavsdk_1_1_action_server_1a23074d52d687eff2c4fc0184ac1b61fd) | Callback type for subscribe_takeoff.
std::function< void([Result](classmavsdk_1_1_action_server.md#classmavsdk_1_1_action_server_1a4a8eb4fe9d098a5b7891232fc5bf32f8), bool)> [LandCallback](#classmavsdk_1_1_action_server_1af2eb6d32c9f903a6e9f773ddf2acf4a0) | Callback type for subscribe_land.
std::function< void([Result](classmavsdk_1_1_action_server.md#classmavsdk_1_1_action_server_1a4a8eb4fe9d098a5b7891232fc5bf32f8), bool)> [RebootCallback](#classmavsdk_1_1_action_server_1a8b2ad3a5fc6a5ac256e21b60043093bd) | Callback type for subscribe_reboot.
std::function< void([Result](classmavsdk_1_1_action_server.md#classmavsdk_1_1_action_server_1a4a8eb4fe9d098a5b7891232fc5bf32f8), bool)> [ShutdownCallback](#classmavsdk_1_1_action_server_1aaa5057d10ec2b242c4a35fec46e5602a) | Callback type for subscribe_shutdown.
std::function< void([Result](classmavsdk_1_1_action_server.md#classmavsdk_1_1_action_server_1a4a8eb4fe9d098a5b7891232fc5bf32f8), bool)> [TerminateCallback](#classmavsdk_1_1_action_server_1a5eb879b36b5efc4f14bed82ed7655384) | Callback type for subscribe_terminate.

## Public Member Functions


Type | Name | Description
---: | --- | ---
&nbsp; | [ActionServer](#classmavsdk_1_1_action_server_1aac3c57a877077b47143dcd22a7843187) ([System](classmavsdk_1_1_system.md) & system) | Constructor. Creates the plugin for a specific [System](classmavsdk_1_1_system.md).
&nbsp; | [ActionServer](#classmavsdk_1_1_action_server_1af79849116682eefccb72756406f665c9) (std::shared_ptr< [System](classmavsdk_1_1_system.md) > system) | Constructor. Creates the plugin for a specific [System](classmavsdk_1_1_system.md).
&nbsp; | [~ActionServer](#classmavsdk_1_1_action_server_1a381d9ac6c56ab6e6881c3523f61e6aad) () | Destructor (internal use only).
&nbsp; | [ActionServer](#classmavsdk_1_1_action_server_1a42228e948d6a50b42ac8e506dc9d094c) (const [ActionServer](classmavsdk_1_1_action_server.md) & other) | Copy constructor.
void | [subscribe_arm_disarm](#classmavsdk_1_1_action_server_1a325b1aa857abaf845ecd4aff36915051) ([ArmDisarmCallback](classmavsdk_1_1_action_server.md#classmavsdk_1_1_action_server_1a8ef1c6ec94f6bf5173d208be15b14910) callback) | Subscribe to ARM/DISARM commands.
void | [subscribe_flight_mode_change](#classmavsdk_1_1_action_server_1adaae0026c0e5faa00fd71e294d10c058) ([FlightModeChangeCallback](classmavsdk_1_1_action_server.md#classmavsdk_1_1_action_server_1a58a1284a240908bf4d9dd998d5939f6f) callback) | Subscribe to DO_SET_MODE.
void | [subscribe_takeoff](#classmavsdk_1_1_action_server_1ab6e180cf678d1b62988137c22e890a9f) ([TakeoffCallback](classmavsdk_1_1_action_server.md#classmavsdk_1_1_action_server_1a23074d52d687eff2c4fc0184ac1b61fd) callback) | Subscribe to takeoff command.
void | [subscribe_land](#classmavsdk_1_1_action_server_1a6374cc32922d7fba59d76f9e19605eb9) ([LandCallback](classmavsdk_1_1_action_server.md#classmavsdk_1_1_action_server_1af2eb6d32c9f903a6e9f773ddf2acf4a0) callback) | Subscribe to land command.
void | [subscribe_reboot](#classmavsdk_1_1_action_server_1af7ba1a3e5a4e070d287a25d487ef0c79) ([RebootCallback](classmavsdk_1_1_action_server.md#classmavsdk_1_1_action_server_1a8b2ad3a5fc6a5ac256e21b60043093bd) callback) | Subscribe to reboot command.
void | [subscribe_shutdown](#classmavsdk_1_1_action_server_1abcb5318ba88b79eb8c5a3300c97fb313) ([ShutdownCallback](classmavsdk_1_1_action_server.md#classmavsdk_1_1_action_server_1aaa5057d10ec2b242c4a35fec46e5602a) callback) | Subscribe to shutdown command.
void | [subscribe_terminate](#classmavsdk_1_1_action_server_1a195412691db1d8fc02c2852a7ca180a6) ([TerminateCallback](classmavsdk_1_1_action_server.md#classmavsdk_1_1_action_server_1a5eb879b36b5efc4f14bed82ed7655384) callback) | Subscribe to terminate command.
[Result](classmavsdk_1_1_action_server.md#classmavsdk_1_1_action_server_1a4a8eb4fe9d098a5b7891232fc5bf32f8) | [set_allow_takeoff](#classmavsdk_1_1_action_server_1a250a8a8d1aed87d7c4125c6cfe797250) (bool allow_takeoff)const | Can the vehicle takeoff.
[Result](classmavsdk_1_1_action_server.md#classmavsdk_1_1_action_server_1a4a8eb4fe9d098a5b7891232fc5bf32f8) | [set_armable](#classmavsdk_1_1_action_server_1ab5b21457f69f9f315d54dbc06e745a7a) (bool armable, bool force_armable)const | Can the vehicle arm when requested.
[Result](classmavsdk_1_1_action_server.md#classmavsdk_1_1_action_server_1a4a8eb4fe9d098a5b7891232fc5bf32f8) | [set_disarmable](#classmavsdk_1_1_action_server_1afae1336100d7a91a4f4521cee56a1ecb) (bool disarmable, bool force_disarmable)const | Can the vehicle disarm when requested.
[Result](classmavsdk_1_1_action_server.md#classmavsdk_1_1_action_server_1a4a8eb4fe9d098a5b7891232fc5bf32f8) | [set_allowable_flight_modes](#classmavsdk_1_1_action_server_1a3041d1b923a3b01021433ad43ab93b3a) ([AllowableFlightModes](structmavsdk_1_1_action_server_1_1_allowable_flight_modes.md) flight_modes)const | Set which modes the vehicle can transition to (Manual always allowed)
[ActionServer::AllowableFlightModes](structmavsdk_1_1_action_server_1_1_allowable_flight_modes.md) | [get_allowable_flight_modes](#classmavsdk_1_1_action_server_1a0960a6ec243823729a418a3c68feaf2a) () const | Get which modes the vehicle can transition to (Manual always allowed)
const [ActionServer](classmavsdk_1_1_action_server.md) & | [operator=](#classmavsdk_1_1_action_server_1aa80e34dd72d2e31005085c78892bab8c) (const [ActionServer](classmavsdk_1_1_action_server.md) &)=delete | Equality operator (object is not copyable).


## Constructor & Destructor Documentation


### ActionServer() {#classmavsdk_1_1_action_server_1aac3c57a877077b47143dcd22a7843187}
```cpp
mavsdk::ActionServer::ActionServer(System &system)
```


Constructor. Creates the plugin for a specific [System](classmavsdk_1_1_system.md).

The plugin is typically created as shown below: 

```cpp
auto action_server = ActionServer(system);
```

**Parameters**

* [System](classmavsdk_1_1_system.md)& **system** - The specific system associated with this plugin.

### ActionServer() {#classmavsdk_1_1_action_server_1af79849116682eefccb72756406f665c9}
```cpp
mavsdk::ActionServer::ActionServer(std::shared_ptr< System > system)
```


Constructor. Creates the plugin for a specific [System](classmavsdk_1_1_system.md).

The plugin is typically created as shown below: 

```cpp
auto action_server = ActionServer(system);
```

**Parameters**

* std::shared_ptr< [System](classmavsdk_1_1_system.md) > **system** - The specific system associated with this plugin.

### ~ActionServer() {#classmavsdk_1_1_action_server_1a381d9ac6c56ab6e6881c3523f61e6aad}
```cpp
mavsdk::ActionServer::~ActionServer()
```


Destructor (internal use only).


### ActionServer() {#classmavsdk_1_1_action_server_1a42228e948d6a50b42ac8e506dc9d094c}
```cpp
mavsdk::ActionServer::ActionServer(const ActionServer &other)
```


Copy constructor.


**Parameters**

* const [ActionServer](classmavsdk_1_1_action_server.md)& **other** - 

## Member Typdef Documentation


### typedef ResultCallback {#classmavsdk_1_1_action_server_1affc7fcdc5f60e367bb9032b938223b95}

```cpp
using mavsdk::ActionServer::ResultCallback =  std::function<void(Result)>
```


Callback type for asynchronous [ActionServer](classmavsdk_1_1_action_server.md) calls.


### typedef ArmDisarmCallback {#classmavsdk_1_1_action_server_1a8ef1c6ec94f6bf5173d208be15b14910}

```cpp
using mavsdk::ActionServer::ArmDisarmCallback =  std::function<void(Result, ArmDisarm)>
```


Callback type for subscribe_arm_disarm.


### typedef FlightModeChangeCallback {#classmavsdk_1_1_action_server_1a58a1284a240908bf4d9dd998d5939f6f}

```cpp
using mavsdk::ActionServer::FlightModeChangeCallback =  std::function<void(Result, FlightMode)>
```


Callback type for subscribe_flight_mode_change.


### typedef TakeoffCallback {#classmavsdk_1_1_action_server_1a23074d52d687eff2c4fc0184ac1b61fd}

```cpp
using mavsdk::ActionServer::TakeoffCallback =  std::function<void(Result, bool)>
```


Callback type for subscribe_takeoff.


### typedef LandCallback {#classmavsdk_1_1_action_server_1af2eb6d32c9f903a6e9f773ddf2acf4a0}

```cpp
using mavsdk::ActionServer::LandCallback =  std::function<void(Result, bool)>
```


Callback type for subscribe_land.


### typedef RebootCallback {#classmavsdk_1_1_action_server_1a8b2ad3a5fc6a5ac256e21b60043093bd}

```cpp
using mavsdk::ActionServer::RebootCallback =  std::function<void(Result, bool)>
```


Callback type for subscribe_reboot.


### typedef ShutdownCallback {#classmavsdk_1_1_action_server_1aaa5057d10ec2b242c4a35fec46e5602a}

```cpp
using mavsdk::ActionServer::ShutdownCallback =  std::function<void(Result, bool)>
```


Callback type for subscribe_shutdown.


### typedef TerminateCallback {#classmavsdk_1_1_action_server_1a5eb879b36b5efc4f14bed82ed7655384}

```cpp
using mavsdk::ActionServer::TerminateCallback =  std::function<void(Result, bool)>
```


Callback type for subscribe_terminate.


## Member Enumeration Documentation


### enum FlightMode {#classmavsdk_1_1_action_server_1aee12027f5d9380f2c13fa7813c6ae1d8}


Flight modes.

For more information about flight modes, check out [https://docs.px4.io/master/en/config/flight_mode.html](https://docs.px4.io/master/en/config/flight_mode.html).

Value | Description
--- | ---
<span id="classmavsdk_1_1_action_server_1aee12027f5d9380f2c13fa7813c6ae1d8a88183b946cc5f0e8c96b2e66e1c74a7e"></span> `Unknown` | Mode not known. 
<span id="classmavsdk_1_1_action_server_1aee12027f5d9380f2c13fa7813c6ae1d8ae7d31fc0602fb2ede144d18cdffd816b"></span> `Ready` | Armed and ready to take off. 
<span id="classmavsdk_1_1_action_server_1aee12027f5d9380f2c13fa7813c6ae1d8a56373a80447c41b9a29e500e62d6884e"></span> `Takeoff` | Taking off. 
<span id="classmavsdk_1_1_action_server_1aee12027f5d9380f2c13fa7813c6ae1d8abcd8db575b47c838e5d551e3973db4ac"></span> `Hold` | Holding (hovering in place (or circling for fixed-wing vehicles). 
<span id="classmavsdk_1_1_action_server_1aee12027f5d9380f2c13fa7813c6ae1d8a70d529695c253d17e992cb9265abc57f"></span> `Mission` | In mission. 
<span id="classmavsdk_1_1_action_server_1aee12027f5d9380f2c13fa7813c6ae1d8a146115c3278581584dcbaac1a77a2588"></span> `ReturnToLaunch` | Returning to launch position (then landing). 
<span id="classmavsdk_1_1_action_server_1aee12027f5d9380f2c13fa7813c6ae1d8a512ef7c688a2c8572d5e16f44e17e869"></span> `Land` | Landing. 
<span id="classmavsdk_1_1_action_server_1aee12027f5d9380f2c13fa7813c6ae1d8abb085f1e0d3843dda2a4c70437ad1410"></span> `Offboard` | In 'offboard' mode. 
<span id="classmavsdk_1_1_action_server_1aee12027f5d9380f2c13fa7813c6ae1d8a08bb3de7dafcf47f05b8c5a9dc0983c0"></span> `FollowMe` | In 'follow-me' mode. 
<span id="classmavsdk_1_1_action_server_1aee12027f5d9380f2c13fa7813c6ae1d8ae1ba155a9f2e8c3be94020eef32a0301"></span> `Manual` | In 'Manual' mode. 
<span id="classmavsdk_1_1_action_server_1aee12027f5d9380f2c13fa7813c6ae1d8aa7a697581399b9be37a545416d4cd2d9"></span> `Altctl` | In 'Altitude Control' mode. 
<span id="classmavsdk_1_1_action_server_1aee12027f5d9380f2c13fa7813c6ae1d8a46780e4f8c113481c868da4dd16fcd41"></span> `Posctl` | In 'Position Control' mode. 
<span id="classmavsdk_1_1_action_server_1aee12027f5d9380f2c13fa7813c6ae1d8ae10e0f017fee32a9bb2fa9fae53afd70"></span> `Acro` | In 'Acro' mode. 
<span id="classmavsdk_1_1_action_server_1aee12027f5d9380f2c13fa7813c6ae1d8afda22026db89cdc5e88b262ad9424b41"></span> `Stabilized` | In 'Stabilize' mode. 

### enum Result {#classmavsdk_1_1_action_server_1a4a8eb4fe9d098a5b7891232fc5bf32f8}


Possible results returned for action requests.


Value | Description
--- | ---
<span id="classmavsdk_1_1_action_server_1a4a8eb4fe9d098a5b7891232fc5bf32f8a88183b946cc5f0e8c96b2e66e1c74a7e"></span> `Unknown` | Unknown result. 
<span id="classmavsdk_1_1_action_server_1a4a8eb4fe9d098a5b7891232fc5bf32f8a505a83f220c02df2f85c3810cd9ceb38"></span> `Success` | Request was successful. 
<span id="classmavsdk_1_1_action_server_1a4a8eb4fe9d098a5b7891232fc5bf32f8a1119faf72ba0dfb23aeea644fed960ad"></span> `NoSystem` | No system is connected. 
<span id="classmavsdk_1_1_action_server_1a4a8eb4fe9d098a5b7891232fc5bf32f8a094a6f6b0868122a9dd008cb91c083e4"></span> `ConnectionError` | Connection error. 
<span id="classmavsdk_1_1_action_server_1a4a8eb4fe9d098a5b7891232fc5bf32f8ad8a942ef2b04672adfafef0ad817a407"></span> `Busy` | Vehicle is busy. 
<span id="classmavsdk_1_1_action_server_1a4a8eb4fe9d098a5b7891232fc5bf32f8a3398e12855176d55f43d53e04f472c8a"></span> `CommandDenied` | Command refused by vehicle. 
<span id="classmavsdk_1_1_action_server_1a4a8eb4fe9d098a5b7891232fc5bf32f8a2dfd6d9491cefa8820ce47f77471e5e3"></span> `CommandDeniedLandedStateUnknown` | Command refused because landed state is unknown. 
<span id="classmavsdk_1_1_action_server_1a4a8eb4fe9d098a5b7891232fc5bf32f8a73d9a6e3b34d98fa3c4fac08f3434a9a"></span> `CommandDeniedNotLanded` | Command refused because vehicle not landed. 
<span id="classmavsdk_1_1_action_server_1a4a8eb4fe9d098a5b7891232fc5bf32f8ac85a251cc457840f1e032f1b733e9398"></span> `Timeout` | Request timed out. 
<span id="classmavsdk_1_1_action_server_1a4a8eb4fe9d098a5b7891232fc5bf32f8a7006c2f81a7a1a65a23cfc16b0326336"></span> `VtolTransitionSupportUnknown` | Hybrid/VTOL transition support is unknown. 
<span id="classmavsdk_1_1_action_server_1a4a8eb4fe9d098a5b7891232fc5bf32f8a5039f02d708e3874858b22610ed63d1e"></span> `NoVtolTransitionSupport` | Vehicle does not support hybrid/VTOL transitions. 
<span id="classmavsdk_1_1_action_server_1a4a8eb4fe9d098a5b7891232fc5bf32f8a189976b733e988a6903e4d19d8cd2fea"></span> `ParameterError` | Error getting or setting parameter. 
<span id="classmavsdk_1_1_action_server_1a4a8eb4fe9d098a5b7891232fc5bf32f8a10ac3d04253ef7e1ddc73e6091c0cd55"></span> `Next` | Intermediate message showing progress or instructions on the next steps. 

## Member Function Documentation


### subscribe_arm_disarm() {#classmavsdk_1_1_action_server_1a325b1aa857abaf845ecd4aff36915051}
```cpp
void mavsdk::ActionServer::subscribe_arm_disarm(ArmDisarmCallback callback)
```


Subscribe to ARM/DISARM commands.


**Parameters**

* [ArmDisarmCallback](classmavsdk_1_1_action_server.md#classmavsdk_1_1_action_server_1a8ef1c6ec94f6bf5173d208be15b14910) **callback** - 

### subscribe_flight_mode_change() {#classmavsdk_1_1_action_server_1adaae0026c0e5faa00fd71e294d10c058}
```cpp
void mavsdk::ActionServer::subscribe_flight_mode_change(FlightModeChangeCallback callback)
```


Subscribe to DO_SET_MODE.


**Parameters**

* [FlightModeChangeCallback](classmavsdk_1_1_action_server.md#classmavsdk_1_1_action_server_1a58a1284a240908bf4d9dd998d5939f6f) **callback** - 

### subscribe_takeoff() {#classmavsdk_1_1_action_server_1ab6e180cf678d1b62988137c22e890a9f}
```cpp
void mavsdk::ActionServer::subscribe_takeoff(TakeoffCallback callback)
```


Subscribe to takeoff command.


**Parameters**

* [TakeoffCallback](classmavsdk_1_1_action_server.md#classmavsdk_1_1_action_server_1a23074d52d687eff2c4fc0184ac1b61fd) **callback** - 

### subscribe_land() {#classmavsdk_1_1_action_server_1a6374cc32922d7fba59d76f9e19605eb9}
```cpp
void mavsdk::ActionServer::subscribe_land(LandCallback callback)
```


Subscribe to land command.


**Parameters**

* [LandCallback](classmavsdk_1_1_action_server.md#classmavsdk_1_1_action_server_1af2eb6d32c9f903a6e9f773ddf2acf4a0) **callback** - 

### subscribe_reboot() {#classmavsdk_1_1_action_server_1af7ba1a3e5a4e070d287a25d487ef0c79}
```cpp
void mavsdk::ActionServer::subscribe_reboot(RebootCallback callback)
```


Subscribe to reboot command.


**Parameters**

* [RebootCallback](classmavsdk_1_1_action_server.md#classmavsdk_1_1_action_server_1a8b2ad3a5fc6a5ac256e21b60043093bd) **callback** - 

### subscribe_shutdown() {#classmavsdk_1_1_action_server_1abcb5318ba88b79eb8c5a3300c97fb313}
```cpp
void mavsdk::ActionServer::subscribe_shutdown(ShutdownCallback callback)
```


Subscribe to shutdown command.


**Parameters**

* [ShutdownCallback](classmavsdk_1_1_action_server.md#classmavsdk_1_1_action_server_1aaa5057d10ec2b242c4a35fec46e5602a) **callback** - 

### subscribe_terminate() {#classmavsdk_1_1_action_server_1a195412691db1d8fc02c2852a7ca180a6}
```cpp
void mavsdk::ActionServer::subscribe_terminate(TerminateCallback callback)
```


Subscribe to terminate command.


**Parameters**

* [TerminateCallback](classmavsdk_1_1_action_server.md#classmavsdk_1_1_action_server_1a5eb879b36b5efc4f14bed82ed7655384) **callback** - 

### set_allow_takeoff() {#classmavsdk_1_1_action_server_1a250a8a8d1aed87d7c4125c6cfe797250}
```cpp
Result mavsdk::ActionServer::set_allow_takeoff(bool allow_takeoff) const
```


Can the vehicle takeoff.

This function is blocking.

**Parameters**

* bool **allow_takeoff** - 

**Returns**

&emsp;[Result](classmavsdk_1_1_action_server.md#classmavsdk_1_1_action_server_1a4a8eb4fe9d098a5b7891232fc5bf32f8) - Result of request.

### set_armable() {#classmavsdk_1_1_action_server_1ab5b21457f69f9f315d54dbc06e745a7a}
```cpp
Result mavsdk::ActionServer::set_armable(bool armable, bool force_armable) const
```


Can the vehicle arm when requested.

This function is blocking.

**Parameters**

* bool **armable** - 
* bool **force_armable** - 

**Returns**

&emsp;[Result](classmavsdk_1_1_action_server.md#classmavsdk_1_1_action_server_1a4a8eb4fe9d098a5b7891232fc5bf32f8) - Result of request.

### set_disarmable() {#classmavsdk_1_1_action_server_1afae1336100d7a91a4f4521cee56a1ecb}
```cpp
Result mavsdk::ActionServer::set_disarmable(bool disarmable, bool force_disarmable) const
```


Can the vehicle disarm when requested.

This function is blocking.

**Parameters**

* bool **disarmable** - 
* bool **force_disarmable** - 

**Returns**

&emsp;[Result](classmavsdk_1_1_action_server.md#classmavsdk_1_1_action_server_1a4a8eb4fe9d098a5b7891232fc5bf32f8) - Result of request.

### set_allowable_flight_modes() {#classmavsdk_1_1_action_server_1a3041d1b923a3b01021433ad43ab93b3a}
```cpp
Result mavsdk::ActionServer::set_allowable_flight_modes(AllowableFlightModes flight_modes) const
```


Set which modes the vehicle can transition to (Manual always allowed)

This function is blocking.

**Parameters**

* [AllowableFlightModes](structmavsdk_1_1_action_server_1_1_allowable_flight_modes.md) **flight_modes** - 

**Returns**

&emsp;[Result](classmavsdk_1_1_action_server.md#classmavsdk_1_1_action_server_1a4a8eb4fe9d098a5b7891232fc5bf32f8) - Result of request.

### get_allowable_flight_modes() {#classmavsdk_1_1_action_server_1a0960a6ec243823729a418a3c68feaf2a}
```cpp
ActionServer::AllowableFlightModes mavsdk::ActionServer::get_allowable_flight_modes() const
```


Get which modes the vehicle can transition to (Manual always allowed)

This function is blocking.

**Returns**

&emsp;[ActionServer::AllowableFlightModes](structmavsdk_1_1_action_server_1_1_allowable_flight_modes.md) - Result of request.

### operator=() {#classmavsdk_1_1_action_server_1aa80e34dd72d2e31005085c78892bab8c}
```cpp
const ActionServer & mavsdk::ActionServer::operator=(const ActionServer &)=delete
```


Equality operator (object is not copyable).


**Parameters**

* const [ActionServer](classmavsdk_1_1_action_server.md)&  - 

**Returns**

&emsp;const [ActionServer](classmavsdk_1_1_action_server.md) & - 