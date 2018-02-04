# dronecore::Offboard Class Reference
`#include: offboard.h`

----


This class is used to control a drone with velocity commands. 


The module is called offboard because the velocity commands can be sent from external sources as opposed to onboard control right inside the autopilot "board".


Client code must specify a setpoint before starting offboard mode. [DroneCore](classdronecore_1_1_drone_core.md) automatically resends setpoints at 20Hz (PX4 [Offboard](classdronecore_1_1_offboard.md) mode requires that setpoints are minimally resent at 2Hz). If more precise control is required, clients can call the setpoint methods at whatever rate is required.


**Attention:** this is work in progress, use with caution! 


## Data Structures


struct [VelocityBodyYawspeed](structdronecore_1_1_offboard_1_1_velocity_body_yawspeed.md)

struct [VelocityNEDYaw](structdronecore_1_1_offboard_1_1_velocity_n_e_d_yaw.md)

## Public Types


Type | Description
--- | ---
enum [Result](#classdronecore_1_1_offboard_1a0f6e5e9f73289f27dc99abbb3ab572ed) | Results for offboard requests.
std::function< void([Result](classdronecore_1_1_offboard.md#classdronecore_1_1_offboard_1a0f6e5e9f73289f27dc99abbb3ab572ed))> [result_callback_t](#classdronecore_1_1_offboard_1a75eeca649293887ac9d398e6432e431f) | Callback type for offboard requests.

## Public Member Functions


Type | Name | Description
---: | --- | ---
| [Offboard](#classdronecore_1_1_offboard_1a333ac94793dc29ed95158fb2af286fa1) (Device *device) | Constructor (internal use only).
| [~Offboard](#classdronecore_1_1_offboard_1a7cb4eff36c37fed1c6d973aa41b059b8) () | Destructor (internal use only).
| [Offboard](#classdronecore_1_1_offboard_1ac586be55cb24aa0ccd29c97352dd2ee5) (const Offboard &)=delete | Copy constructor (object is not copyable).
[Offboard::Result](classdronecore_1_1_offboard.md#classdronecore_1_1_offboard_1a0f6e5e9f73289f27dc99abbb3ab572ed) | [start](#classdronecore_1_1_offboard_1a658454f130f7b19d56f23347a448f1b9) () | Start offboard control (synchronous).
[Offboard::Result](classdronecore_1_1_offboard.md#classdronecore_1_1_offboard_1a0f6e5e9f73289f27dc99abbb3ab572ed) | [stop](#classdronecore_1_1_offboard_1ae223c08f1ffc694b26d847cab7738406) () | Stop offboard control (synchronous).
void | [start_async](#classdronecore_1_1_offboard_1a5dd9d18eedb0e4a8f1bbbeebf6f99aa8) (result_callback_t callback) | Start offboard control (asynchronous).
void | [stop_async](#classdronecore_1_1_offboard_1afbe6f50f63d3bc43acc4dfc2f797ca0a) (result_callback_t callback) | Stop offboard control (asynchronous).
bool | [is_active](#classdronecore_1_1_offboard_1a44d9284ef03c8cf6f37a77b2f3cadaf0) () const | Check if offboard control is active.
void | [set_velocity_ned](#classdronecore_1_1_offboard_1a9e7f369a8f7459dc7705f4453a8c307d) (VelocityNEDYaw velocity_ned_yaw) | Set the velocity in NED coordinates and yaw.
void | [set_velocity_body](#classdronecore_1_1_offboard_1ad9dc585be1bc2dba699cf089d4c274cc) (VelocityBodyYawspeed velocity_body_yawspeed) | Set the velocity body coordinates and yaw angular rate.
const [Offboard](classdronecore_1_1_offboard.md) & | [operator=](#classdronecore_1_1_offboard_1aa6bf966e606cdd361364791d06aca977) (const Offboard &)=delete | Equality operator (object is not copyable).

## Static Public Member Functions


Type | Name | Description
---: | --- | ---
const char * | [result_str](#classdronecore_1_1_offboard_1a8eb7467e48fe354d34bc45637ca9f5b8) (Result result) | Get human-readable English string for [Offboard::Result](classdronecore_1_1_offboard.md#classdronecore_1_1_offboard_1a0f6e5e9f73289f27dc99abbb3ab572ed).


## Constructor & Destructor Documentation


### Offboard() {#classdronecore_1_1_offboard_1a333ac94793dc29ed95158fb2af286fa1}
```cpp
dronecore::Offboard::Offboard(Device *device)
```


Constructor (internal use only).


**Parameters**

* [Device](classdronecore_1_1_device.md) * **device** - 

### ~Offboard() {#classdronecore_1_1_offboard_1a7cb4eff36c37fed1c6d973aa41b059b8}
```cpp
dronecore::Offboard::~Offboard()
```


Destructor (internal use only).


### Offboard() {#classdronecore_1_1_offboard_1ac586be55cb24aa0ccd29c97352dd2ee5}
```cpp
dronecore::Offboard::Offboard(const Offboard &)=delete
```


Copy constructor (object is not copyable).


**Parameters**

* const [Offboard](classdronecore_1_1_offboard.md) & - 

## Member Typdef Documentation


### typedef result_callback_t {#classdronecore_1_1_offboard_1a75eeca649293887ac9d398e6432e431f}

```cpp
typedef std::function<void(Result)> dronecore::Offboard::result_callback_t
```


Callback type for offboard requests.


## Member Enumeration Documentation


### enum Result {#classdronecore_1_1_offboard_1a0f6e5e9f73289f27dc99abbb3ab572ed}


Results for offboard requests.


Value | Description
--- | ---
<span id="classdronecore_1_1_offboard_1a0f6e5e9f73289f27dc99abbb3ab572edad0749aaba8b833466dfcbb0428e4f89c"></span> `SUCCESS` | Request succeeded. 
<span id="classdronecore_1_1_offboard_1a0f6e5e9f73289f27dc99abbb3ab572eda23514014e50da2b2583cae24ab1ecd88"></span> `NO_DEVICE` | No device connected. 
<span id="classdronecore_1_1_offboard_1a0f6e5e9f73289f27dc99abbb3ab572edac77f1f09dab2c0c9980fca7cfae02518"></span> `CONNECTION_ERROR` | Connection error. 
<span id="classdronecore_1_1_offboard_1a0f6e5e9f73289f27dc99abbb3ab572eda802706a9238e2928077f97736854bad4"></span> `BUSY` | Vehicle busy. 
<span id="classdronecore_1_1_offboard_1a0f6e5e9f73289f27dc99abbb3ab572eda6fa4dbf368cea972db8d9156799d5dbe"></span> `COMMAND_DENIED` | Command denied. 
<span id="classdronecore_1_1_offboard_1a0f6e5e9f73289f27dc99abbb3ab572eda070a0fb40f6c308ab544b227660aadff"></span> `TIMEOUT` | Request timeout. 
<span id="classdronecore_1_1_offboard_1a0f6e5e9f73289f27dc99abbb3ab572edabe5140e11d47ef100aaf22a20c6f46b2"></span> `NO_SETPOINT_SET` |  Can't start without setpoint set.
<span id="classdronecore_1_1_offboard_1a0f6e5e9f73289f27dc99abbb3ab572eda696b031073e74bf2cb98e5ef201d4aa3"></span> `UNKNOWN` | Unknown error. 

## Member Function Documentation


### start() {#classdronecore_1_1_offboard_1a658454f130f7b19d56f23347a448f1b9}
```cpp
Offboard::Result dronecore::Offboard::start()
```


Start offboard control (synchronous).

**Attention:** this is work in progress, use with caution!

**Returns**

&emsp;[Offboard::Result](classdronecore_1_1_offboard.md#classdronecore_1_1_offboard_1a0f6e5e9f73289f27dc99abbb3ab572ed) - Result of request.

### stop() {#classdronecore_1_1_offboard_1ae223c08f1ffc694b26d847cab7738406}
```cpp
Offboard::Result dronecore::Offboard::stop()
```


Stop offboard control (synchronous).

The vehicle will be put into Hold mode: [https://docs.px4.io/en/flight_modes/hold.html](https://docs.px4.io/en/flight_modes/hold.html)

**Returns**

&emsp;[Offboard::Result](classdronecore_1_1_offboard.md#classdronecore_1_1_offboard_1a0f6e5e9f73289f27dc99abbb3ab572ed) - Result of request.

### start_async() {#classdronecore_1_1_offboard_1a5dd9d18eedb0e4a8f1bbbeebf6f99aa8}
```cpp
void dronecore::Offboard::start_async(result_callback_t callback)
```


Start offboard control (asynchronous).

**Attention:** This is work in progress, use with caution!

**Parameters**

* [result_callback_t](classdronecore_1_1_offboard.md#classdronecore_1_1_offboard_1a75eeca649293887ac9d398e6432e431f) **callback** - Callback to receive request result.

### stop_async() {#classdronecore_1_1_offboard_1afbe6f50f63d3bc43acc4dfc2f797ca0a}
```cpp
void dronecore::Offboard::stop_async(result_callback_t callback)
```


Stop offboard control (asynchronous).

The vehicle will be put into Hold mode: [https://docs.px4.io/en/flight_modes/hold.html](https://docs.px4.io/en/flight_modes/hold.html)

**Parameters**

* [result_callback_t](classdronecore_1_1_offboard.md#classdronecore_1_1_offboard_1a75eeca649293887ac9d398e6432e431f) **callback** - Callback to receive request result.

### is_active() {#classdronecore_1_1_offboard_1a44d9284ef03c8cf6f37a77b2f3cadaf0}
```cpp
bool dronecore::Offboard::is_active() const
```


Check if offboard control is active.

`true` means that the vehicle is in offboard mode and we are actively sending setpoints.

**Returns**

&emsp;bool - `true` if active

### set_velocity_ned() {#classdronecore_1_1_offboard_1a9e7f369a8f7459dc7705f4453a8c307d}
```cpp
void dronecore::Offboard::set_velocity_ned(VelocityNEDYaw velocity_ned_yaw)
```


Set the velocity in NED coordinates and yaw.


**Parameters**

* [VelocityNEDYaw](structdronecore_1_1_offboard_1_1_velocity_n_e_d_yaw.md) **velocity_ned_yaw** - Velocity and yaw `struct`.

### set_velocity_body() {#classdronecore_1_1_offboard_1ad9dc585be1bc2dba699cf089d4c274cc}
```cpp
void dronecore::Offboard::set_velocity_body(VelocityBodyYawspeed velocity_body_yawspeed)
```


Set the velocity body coordinates and yaw angular rate.


**Parameters**

* [VelocityBodyYawspeed](structdronecore_1_1_offboard_1_1_velocity_body_yawspeed.md) **velocity_body_yawspeed** - Velocity and yaw angular rate `struct`.

### operator=() {#classdronecore_1_1_offboard_1aa6bf966e606cdd361364791d06aca977}
```cpp
const Offboard& dronecore::Offboard::operator=(const Offboard &)=delete
```


Equality operator (object is not copyable).


**Parameters**

* const [Offboard](classdronecore_1_1_offboard.md) & - 

**Returns**

&emsp;const [Offboard](classdronecore_1_1_offboard.md) & - 

### result_str() {#classdronecore_1_1_offboard_1a8eb7467e48fe354d34bc45637ca9f5b8}
```cpp
static const char* dronecore::Offboard::result_str(Result result)
```


Get human-readable English string for [Offboard::Result](classdronecore_1_1_offboard.md#classdronecore_1_1_offboard_1a0f6e5e9f73289f27dc99abbb3ab572ed).


**Parameters**

* [Result](classdronecore_1_1_offboard.md#classdronecore_1_1_offboard_1a0f6e5e9f73289f27dc99abbb3ab572ed) **result** - The enum value for which a string is required.

**Returns**

&emsp;const char * - Human-readable string for enum value.