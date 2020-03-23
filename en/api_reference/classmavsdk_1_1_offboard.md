# mavsdk::Offboard Class Reference
`#include: offboard.h`

----


This class is used to control a drone with velocity commands. 


The module is called offboard because the velocity commands can be sent from external sources as opposed to onboard control right inside the autopilot "board".


Client code must specify a setpoint before starting offboard mode. [Mavsdk](classmavsdk_1_1_mavsdk.md) automatically resends setpoints at 20Hz (PX4 [Offboard](classmavsdk_1_1_offboard.md) mode requires that setpoints are minimally resent at 2Hz). If more precise control is required, clients can call the setpoint methods at whatever rate is required.


**Attention:** this is work in progress, use with caution! 


## Data Structures


struct [ActuatorControl](structmavsdk_1_1_offboard_1_1_actuator_control.md)

struct [Attitude](structmavsdk_1_1_offboard_1_1_attitude.md)

struct [AttitudeRate](structmavsdk_1_1_offboard_1_1_attitude_rate.md)

struct [PositionNEDYaw](structmavsdk_1_1_offboard_1_1_position_n_e_d_yaw.md)

struct [VelocityBodyYawspeed](structmavsdk_1_1_offboard_1_1_velocity_body_yawspeed.md)

struct [VelocityNEDYaw](structmavsdk_1_1_offboard_1_1_velocity_n_e_d_yaw.md)

## Public Types


Type | Description
--- | ---
enum [Result](#classmavsdk_1_1_offboard_1a2d4d594301d8c756429457b0982130e9) | Results for offboard requests.
std::function< void([Result](classmavsdk_1_1_offboard.md#classmavsdk_1_1_offboard_1a2d4d594301d8c756429457b0982130e9))> [result_callback_t](#classmavsdk_1_1_offboard_1a740ace65ac87d920f44fb024e198c15a) | Callback type for offboard requests.

## Public Member Functions


Type | Name | Description
---: | --- | ---
&nbsp; | [Offboard](#classmavsdk_1_1_offboard_1aedb8ed185acabd2caa3b536f51b68dcb) ([System](classmavsdk_1_1_system.md) & system) | Constructor. Creates the plugin for a specific [System](classmavsdk_1_1_system.md).
&nbsp; | [~Offboard](#classmavsdk_1_1_offboard_1a999a6df78e148fee89fa4ae4f6f2e0e4) () | Destructor (internal use only).
&nbsp; | [Offboard](#classmavsdk_1_1_offboard_1abf3926e90b315d9e5ba05b51eb6c6631) (const [Offboard](classmavsdk_1_1_offboard.md) &)=delete | Copy constructor (object is not copyable).
[Offboard::Result](classmavsdk_1_1_offboard.md#classmavsdk_1_1_offboard_1a2d4d594301d8c756429457b0982130e9) | [start](#classmavsdk_1_1_offboard_1a3f0b71195ae6cb445237b192e3b8343f) () | Start offboard control (synchronous).
[Offboard::Result](classmavsdk_1_1_offboard.md#classmavsdk_1_1_offboard_1a2d4d594301d8c756429457b0982130e9) | [stop](#classmavsdk_1_1_offboard_1a9a54e588bcfd5b0ffca27833ad4f6b10) () | Stop offboard control (synchronous).
void | [start_async](#classmavsdk_1_1_offboard_1a8d52d710dbfcd77a33d8657ea55ab606) ([result_callback_t](classmavsdk_1_1_offboard.md#classmavsdk_1_1_offboard_1a740ace65ac87d920f44fb024e198c15a) callback) | Start offboard control (asynchronous).
void | [stop_async](#classmavsdk_1_1_offboard_1a243e63e27d3e6d4b927e6d9a3fe2e8e9) ([result_callback_t](classmavsdk_1_1_offboard.md#classmavsdk_1_1_offboard_1a740ace65ac87d920f44fb024e198c15a) callback) | Stop offboard control (asynchronous).
bool | [is_active](#classmavsdk_1_1_offboard_1aa5e0f3c02a03f2667f82d5e162221ff5) () const | Check if offboard control is active.
void | [set_position_ned](#classmavsdk_1_1_offboard_1a0bcbc79ba1277f0e7ad110f86b902cc7) ([PositionNEDYaw](structmavsdk_1_1_offboard_1_1_position_n_e_d_yaw.md) position_ned_yaw) | Set the position in NED coordinates and yaw.
void | [set_velocity_ned](#classmavsdk_1_1_offboard_1a689fec126f8da55dadfc13e67bf9bb39) ([VelocityNEDYaw](structmavsdk_1_1_offboard_1_1_velocity_n_e_d_yaw.md) velocity_ned_yaw) | Set the velocity in NED coordinates and yaw.
void | [set_velocity_body](#classmavsdk_1_1_offboard_1aab32b36b4396cecbac9c745507b2fb81) ([VelocityBodyYawspeed](structmavsdk_1_1_offboard_1_1_velocity_body_yawspeed.md) velocity_body_yawspeed) | Set the velocity body coordinates and yaw angular rate.
void | [set_attitude](#classmavsdk_1_1_offboard_1a49f92abcd755b71f92b79454c8b6c82f) ([Attitude](structmavsdk_1_1_offboard_1_1_attitude.md) attitude) | Set the attitude in terms of roll, pitch and yaw in degrees with thrust in percentage.
void | [set_attitude_rate](#classmavsdk_1_1_offboard_1a862d78aa5c57ad77b249b69d028630c0) ([AttitudeRate](structmavsdk_1_1_offboard_1_1_attitude_rate.md) attitude_rate) | Set the attitude rate in terms of pitch, roll and yaw angular rate along with thrust in percentage.
void | [set_actuator_control](#classmavsdk_1_1_offboard_1af4b95e2ea3397e42e8ea8f8bd7d175cc) (const [ActuatorControl](structmavsdk_1_1_offboard_1_1_actuator_control.md) actuator_control) | Set direct actuator control values to groups #0 and #1. First 8 controls will go to control group 0, the following 8 controls to control group 1 (if actuator_control.num_controls more than 8).
const [Offboard](classmavsdk_1_1_offboard.md) & | [operator=](#classmavsdk_1_1_offboard_1acb01657624668251c0a022bc3f8135cd) (const [Offboard](classmavsdk_1_1_offboard.md) &)=delete | Equality operator (object is not copyable).

## Static Public Member Functions


Type | Name | Description
---: | --- | ---
const char * | [result_str](#classmavsdk_1_1_offboard_1a3402d7e3dc8b4ff15598dfd67af0644b) ([Result](classmavsdk_1_1_offboard.md#classmavsdk_1_1_offboard_1a2d4d594301d8c756429457b0982130e9) result) | Get human-readable English string for [Offboard::Result](classmavsdk_1_1_offboard.md#classmavsdk_1_1_offboard_1a2d4d594301d8c756429457b0982130e9).


## Constructor & Destructor Documentation


### Offboard() {#classmavsdk_1_1_offboard_1aedb8ed185acabd2caa3b536f51b68dcb}
```cpp
mavsdk::Offboard::Offboard(System &system)
```


Constructor. Creates the plugin for a specific [System](classmavsdk_1_1_system.md).

The plugin is typically created as shown below: 

```cpp
auto offboard = std::make_shared<Offboard>(system);
```

**Parameters**

* [System](classmavsdk_1_1_system.md)& **system** - The specific system associated with this plugin.

### ~Offboard() {#classmavsdk_1_1_offboard_1a999a6df78e148fee89fa4ae4f6f2e0e4}
```cpp
mavsdk::Offboard::~Offboard()
```


Destructor (internal use only).


### Offboard() {#classmavsdk_1_1_offboard_1abf3926e90b315d9e5ba05b51eb6c6631}
```cpp
mavsdk::Offboard::Offboard(const Offboard &)=delete
```


Copy constructor (object is not copyable).


**Parameters**

* const [Offboard](classmavsdk_1_1_offboard.md)&  - 

## Member Typdef Documentation


### typedef result_callback_t {#classmavsdk_1_1_offboard_1a740ace65ac87d920f44fb024e198c15a}

```cpp
typedef std::function<void(Result)> mavsdk::Offboard::result_callback_t
```


Callback type for offboard requests.


## Member Enumeration Documentation


### enum Result {#classmavsdk_1_1_offboard_1a2d4d594301d8c756429457b0982130e9}


Results for offboard requests.


Value | Description
--- | ---
<span id="classmavsdk_1_1_offboard_1a2d4d594301d8c756429457b0982130e9a696b031073e74bf2cb98e5ef201d4aa3"></span> `UNKNOWN` | Unknown error. 
<span id="classmavsdk_1_1_offboard_1a2d4d594301d8c756429457b0982130e9ad0749aaba8b833466dfcbb0428e4f89c"></span> `SUCCESS` | Request succeeded. 
<span id="classmavsdk_1_1_offboard_1a2d4d594301d8c756429457b0982130e9afeae72a3a2feec3c92c2a79a30d31186"></span> `NO_SYSTEM` | No system connected. 
<span id="classmavsdk_1_1_offboard_1a2d4d594301d8c756429457b0982130e9ac77f1f09dab2c0c9980fca7cfae02518"></span> `CONNECTION_ERROR` | Connection error. 
<span id="classmavsdk_1_1_offboard_1a2d4d594301d8c756429457b0982130e9a802706a9238e2928077f97736854bad4"></span> `BUSY` | Vehicle busy. 
<span id="classmavsdk_1_1_offboard_1a2d4d594301d8c756429457b0982130e9a6fa4dbf368cea972db8d9156799d5dbe"></span> `COMMAND_DENIED` | Command denied. 
<span id="classmavsdk_1_1_offboard_1a2d4d594301d8c756429457b0982130e9a070a0fb40f6c308ab544b227660aadff"></span> `TIMEOUT` | Request timeout. 
<span id="classmavsdk_1_1_offboard_1a2d4d594301d8c756429457b0982130e9abe5140e11d47ef100aaf22a20c6f46b2"></span> `NO_SETPOINT_SET` |  Can't start without setpoint set.

## Member Function Documentation


### start() {#classmavsdk_1_1_offboard_1a3f0b71195ae6cb445237b192e3b8343f}
```cpp
Offboard::Result mavsdk::Offboard::start()
```


Start offboard control (synchronous).

**Attention:** this is work in progress, use with caution!

**Returns**

&emsp;[Offboard::Result](classmavsdk_1_1_offboard.md#classmavsdk_1_1_offboard_1a2d4d594301d8c756429457b0982130e9) - Result of request.

### stop() {#classmavsdk_1_1_offboard_1a9a54e588bcfd5b0ffca27833ad4f6b10}
```cpp
Offboard::Result mavsdk::Offboard::stop()
```


Stop offboard control (synchronous).

The vehicle will be put into Hold mode: [https://docs.px4.io/master/en/flight_modes/hold.html](https://docs.px4.io/master/en/flight_modes/hold.html)

**Returns**

&emsp;[Offboard::Result](classmavsdk_1_1_offboard.md#classmavsdk_1_1_offboard_1a2d4d594301d8c756429457b0982130e9) - Result of request.

### start_async() {#classmavsdk_1_1_offboard_1a8d52d710dbfcd77a33d8657ea55ab606}
```cpp
void mavsdk::Offboard::start_async(result_callback_t callback)
```


Start offboard control (asynchronous).

**Attention:** This is work in progress, use with caution!

**Parameters**

* [result_callback_t](classmavsdk_1_1_offboard.md#classmavsdk_1_1_offboard_1a740ace65ac87d920f44fb024e198c15a) **callback** - Callback to receive request result.

### stop_async() {#classmavsdk_1_1_offboard_1a243e63e27d3e6d4b927e6d9a3fe2e8e9}
```cpp
void mavsdk::Offboard::stop_async(result_callback_t callback)
```


Stop offboard control (asynchronous).

The vehicle will be put into Hold mode: [https://docs.px4.io/master/en/flight_modes/hold.html](https://docs.px4.io/master/en/flight_modes/hold.html)

**Parameters**

* [result_callback_t](classmavsdk_1_1_offboard.md#classmavsdk_1_1_offboard_1a740ace65ac87d920f44fb024e198c15a) **callback** - Callback to receive request result.

### is_active() {#classmavsdk_1_1_offboard_1aa5e0f3c02a03f2667f82d5e162221ff5}
```cpp
bool mavsdk::Offboard::is_active() const
```


Check if offboard control is active.

`true` means that the vehicle is in offboard mode and we are actively sending setpoints.

**Returns**

&emsp;bool - `true` if active

### set_position_ned() {#classmavsdk_1_1_offboard_1a0bcbc79ba1277f0e7ad110f86b902cc7}
```cpp
void mavsdk::Offboard::set_position_ned(PositionNEDYaw position_ned_yaw)
```


Set the position in NED coordinates and yaw.


**Parameters**

* [PositionNEDYaw](structmavsdk_1_1_offboard_1_1_position_n_e_d_yaw.md) **position_ned_yaw** - Position and yaw `struct`.

### set_velocity_ned() {#classmavsdk_1_1_offboard_1a689fec126f8da55dadfc13e67bf9bb39}
```cpp
void mavsdk::Offboard::set_velocity_ned(VelocityNEDYaw velocity_ned_yaw)
```


Set the velocity in NED coordinates and yaw.


**Parameters**

* [VelocityNEDYaw](structmavsdk_1_1_offboard_1_1_velocity_n_e_d_yaw.md) **velocity_ned_yaw** - Velocity and yaw `struct`.

### set_velocity_body() {#classmavsdk_1_1_offboard_1aab32b36b4396cecbac9c745507b2fb81}
```cpp
void mavsdk::Offboard::set_velocity_body(VelocityBodyYawspeed velocity_body_yawspeed)
```


Set the velocity body coordinates and yaw angular rate.


**Parameters**

* [VelocityBodyYawspeed](structmavsdk_1_1_offboard_1_1_velocity_body_yawspeed.md) **velocity_body_yawspeed** - Velocity and yaw angular rate `struct`.

### set_attitude() {#classmavsdk_1_1_offboard_1a49f92abcd755b71f92b79454c8b6c82f}
```cpp
void mavsdk::Offboard::set_attitude(Attitude attitude)
```


Set the attitude in terms of roll, pitch and yaw in degrees with thrust in percentage.


**Parameters**

* [Attitude](structmavsdk_1_1_offboard_1_1_attitude.md) **attitude** - roll, pitch and yaw in degrees along with thrust in percentage.

### set_attitude_rate() {#classmavsdk_1_1_offboard_1a862d78aa5c57ad77b249b69d028630c0}
```cpp
void mavsdk::Offboard::set_attitude_rate(AttitudeRate attitude_rate)
```


Set the attitude rate in terms of pitch, roll and yaw angular rate along with thrust in percentage.


**Parameters**

* [AttitudeRate](structmavsdk_1_1_offboard_1_1_attitude_rate.md) **attitude_rate** - roll, pitch and yaw angular rate along with thrust in percentage.

### set_actuator_control() {#classmavsdk_1_1_offboard_1af4b95e2ea3397e42e8ea8f8bd7d175cc}
```cpp
void mavsdk::Offboard::set_actuator_control(const ActuatorControl actuator_control)
```


Set direct actuator control values to groups #0 and #1. First 8 controls will go to control group 0, the following 8 controls to control group 1 (if actuator_control.num_controls more than 8).


**Parameters**

* const [ActuatorControl](structmavsdk_1_1_offboard_1_1_actuator_control.md) **actuator_control** - actuators control values

### operator=() {#classmavsdk_1_1_offboard_1acb01657624668251c0a022bc3f8135cd}
```cpp
const Offboard& mavsdk::Offboard::operator=(const Offboard &)=delete
```


Equality operator (object is not copyable).


**Parameters**

* const [Offboard](classmavsdk_1_1_offboard.md)&  - 

**Returns**

&emsp;const [Offboard](classmavsdk_1_1_offboard.md) & - 

### result_str() {#classmavsdk_1_1_offboard_1a3402d7e3dc8b4ff15598dfd67af0644b}
```cpp
static const char* mavsdk::Offboard::result_str(Result result)
```


Get human-readable English string for [Offboard::Result](classmavsdk_1_1_offboard.md#classmavsdk_1_1_offboard_1a2d4d594301d8c756429457b0982130e9).


**Parameters**

* [Result](classmavsdk_1_1_offboard.md#classmavsdk_1_1_offboard_1a2d4d594301d8c756429457b0982130e9) **result** - The enum value for which a string is required.

**Returns**

&emsp;const char * - Human-readable string for enum value.