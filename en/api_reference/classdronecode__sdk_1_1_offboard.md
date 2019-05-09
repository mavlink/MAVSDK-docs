# dronecode_sdk::Offboard Class Reference
`#include: offboard.h`

----


This class is used to control a drone with velocity commands. 


The module is called offboard because the velocity commands can be sent from external sources as opposed to onboard control right inside the autopilot "board".


Client code must specify a setpoint before starting offboard mode. [DronecodeSDK](classdronecode__sdk_1_1_dronecode_s_d_k.md) automatically resends setpoints at 20Hz (PX4 [Offboard](classdronecode__sdk_1_1_offboard.md) mode requires that setpoints are minimally resent at 2Hz). If more precise control is required, clients can call the setpoint methods at whatever rate is required.


**Attention:** this is work in progress, use with caution! 


## Data Structures


struct [Attitude](structdronecode__sdk_1_1_offboard_1_1_attitude.md)

struct [AttitudeRate](structdronecode__sdk_1_1_offboard_1_1_attitude_rate.md)

struct [PositionNEDYaw](structdronecode__sdk_1_1_offboard_1_1_position_n_e_d_yaw.md)

struct [VelocityBodyYawspeed](structdronecode__sdk_1_1_offboard_1_1_velocity_body_yawspeed.md)

struct [VelocityNEDYaw](structdronecode__sdk_1_1_offboard_1_1_velocity_n_e_d_yaw.md)

## Public Types


Type | Description
--- | ---
enum [Result](#classdronecode__sdk_1_1_offboard_1a1f515eed9d23c450254233ea87131c09) | Results for offboard requests.
std::function< void([Result](classdronecode__sdk_1_1_offboard.md#classdronecode__sdk_1_1_offboard_1a1f515eed9d23c450254233ea87131c09))> [result_callback_t](#classdronecode__sdk_1_1_offboard_1a02563418f94499b40d27543b3f486034) | Callback type for offboard requests.

## Public Member Functions


Type | Name | Description
---: | --- | ---
&nbsp; | [Offboard](#classdronecode__sdk_1_1_offboard_1a3cb25aa0429db49a265279740480bd21) ([System](classdronecode__sdk_1_1_system.md) & system) | Constructor. Creates the plugin for a specific [System](classdronecode__sdk_1_1_system.md).
&nbsp; | [~Offboard](#classdronecode__sdk_1_1_offboard_1a039e97d28da3fff608d723801535785e) () | Destructor (internal use only).
&nbsp; | [Offboard](#classdronecode__sdk_1_1_offboard_1a4a66247be2f1277f5ff52fe21b1b6f45) (const [Offboard](classdronecode__sdk_1_1_offboard.md) &)=delete | Copy constructor (object is not copyable).
[Offboard::Result](classdronecode__sdk_1_1_offboard.md#classdronecode__sdk_1_1_offboard_1a1f515eed9d23c450254233ea87131c09) | [start](#classdronecode__sdk_1_1_offboard_1a1d67617a9da5364a7cb981f9ba5710bd) () | Start offboard control (synchronous).
[Offboard::Result](classdronecode__sdk_1_1_offboard.md#classdronecode__sdk_1_1_offboard_1a1f515eed9d23c450254233ea87131c09) | [stop](#classdronecode__sdk_1_1_offboard_1aaab6abfad63644d202a533359d26e29a) () | Stop offboard control (synchronous).
void | [start_async](#classdronecode__sdk_1_1_offboard_1a8181092c3a3cac5e62dfcef4f10363de) ([result_callback_t](classdronecode__sdk_1_1_offboard.md#classdronecode__sdk_1_1_offboard_1a02563418f94499b40d27543b3f486034) callback) | Start offboard control (asynchronous).
void | [stop_async](#classdronecode__sdk_1_1_offboard_1a2ff3262dbc6194def28bb9b3d5684e68) ([result_callback_t](classdronecode__sdk_1_1_offboard.md#classdronecode__sdk_1_1_offboard_1a02563418f94499b40d27543b3f486034) callback) | Stop offboard control (asynchronous).
bool | [is_active](#classdronecode__sdk_1_1_offboard_1ac3c75fcd1ae1e6b00090eccd03696479) () const | Check if offboard control is active.
void | [set_position_ned](#classdronecode__sdk_1_1_offboard_1a127749d168fe4e7ddb40ba4c6747bb4a) ([PositionNEDYaw](structdronecode__sdk_1_1_offboard_1_1_position_n_e_d_yaw.md) position_ned_yaw) | Set the position in NED coordinates and yaw.
void | [set_velocity_ned](#classdronecode__sdk_1_1_offboard_1a95dfbe096a363e21bfd035258e786350) ([VelocityNEDYaw](structdronecode__sdk_1_1_offboard_1_1_velocity_n_e_d_yaw.md) velocity_ned_yaw) | Set the velocity in NED coordinates and yaw.
void | [set_velocity_body](#classdronecode__sdk_1_1_offboard_1ad87778386509911269b87766c0f1830f) ([VelocityBodyYawspeed](structdronecode__sdk_1_1_offboard_1_1_velocity_body_yawspeed.md) velocity_body_yawspeed) | Set the velocity body coordinates and yaw angular rate.
void | [set_attitude](#classdronecode__sdk_1_1_offboard_1aa8210f10366afadd99787b1df3e601a9) ([Attitude](structdronecode__sdk_1_1_offboard_1_1_attitude.md) attitude) | Set the attitude in terms of roll, pitch and yaw in degrees with thrust in percentage.
void | [set_attitude_rate](#classdronecode__sdk_1_1_offboard_1a511ba0314a4217c3ac3020ab2b0dfd23) ([AttitudeRate](structdronecode__sdk_1_1_offboard_1_1_attitude_rate.md) attitude_rate) | Set the attitude rate in terms of pitch, roll and yaw angular rate along with thrust in percentage.
const [Offboard](classdronecode__sdk_1_1_offboard.md) & | [operator=](#classdronecode__sdk_1_1_offboard_1a8cfbf6cbcb4fbdcf1574f0455632a372) (const [Offboard](classdronecode__sdk_1_1_offboard.md) &)=delete | Equality operator (object is not copyable).

## Static Public Member Functions


Type | Name | Description
---: | --- | ---
const char * | [result_str](#classdronecode__sdk_1_1_offboard_1a78d6d7fe6372c5672da42f336bf4785b) ([Result](classdronecode__sdk_1_1_offboard.md#classdronecode__sdk_1_1_offboard_1a1f515eed9d23c450254233ea87131c09) result) | Get human-readable English string for [Offboard::Result](classdronecode__sdk_1_1_offboard.md#classdronecode__sdk_1_1_offboard_1a1f515eed9d23c450254233ea87131c09).


## Constructor & Destructor Documentation


### Offboard() {#classdronecode__sdk_1_1_offboard_1a3cb25aa0429db49a265279740480bd21}
```cpp
dronecode_sdk::Offboard::Offboard(System &system)
```


Constructor. Creates the plugin for a specific [System](classdronecode__sdk_1_1_system.md).

The plugin is typically created as shown below: 

```cpp
auto offboard = std::make_shared<Offboard>(system);
```

**Parameters**

* [System](classdronecode__sdk_1_1_system.md)& **system** - The specific system associated with this plugin.

### ~Offboard() {#classdronecode__sdk_1_1_offboard_1a039e97d28da3fff608d723801535785e}
```cpp
dronecode_sdk::Offboard::~Offboard()
```


Destructor (internal use only).


### Offboard() {#classdronecode__sdk_1_1_offboard_1a4a66247be2f1277f5ff52fe21b1b6f45}
```cpp
dronecode_sdk::Offboard::Offboard(const Offboard &)=delete
```


Copy constructor (object is not copyable).


**Parameters**

* const [Offboard](classdronecode__sdk_1_1_offboard.md)&  - 

## Member Typdef Documentation


### typedef result_callback_t {#classdronecode__sdk_1_1_offboard_1a02563418f94499b40d27543b3f486034}

```cpp
typedef std::function<void(Result)> dronecode_sdk::Offboard::result_callback_t
```


Callback type for offboard requests.


## Member Enumeration Documentation


### enum Result {#classdronecode__sdk_1_1_offboard_1a1f515eed9d23c450254233ea87131c09}


Results for offboard requests.


Value | Description
--- | ---
<span id="classdronecode__sdk_1_1_offboard_1a1f515eed9d23c450254233ea87131c09a696b031073e74bf2cb98e5ef201d4aa3"></span> `UNKNOWN` | Unknown error. 
<span id="classdronecode__sdk_1_1_offboard_1a1f515eed9d23c450254233ea87131c09ad0749aaba8b833466dfcbb0428e4f89c"></span> `SUCCESS` | Request succeeded. 
<span id="classdronecode__sdk_1_1_offboard_1a1f515eed9d23c450254233ea87131c09afeae72a3a2feec3c92c2a79a30d31186"></span> `NO_SYSTEM` | No system connected. 
<span id="classdronecode__sdk_1_1_offboard_1a1f515eed9d23c450254233ea87131c09ac77f1f09dab2c0c9980fca7cfae02518"></span> `CONNECTION_ERROR` | Connection error. 
<span id="classdronecode__sdk_1_1_offboard_1a1f515eed9d23c450254233ea87131c09a802706a9238e2928077f97736854bad4"></span> `BUSY` | Vehicle busy. 
<span id="classdronecode__sdk_1_1_offboard_1a1f515eed9d23c450254233ea87131c09a6fa4dbf368cea972db8d9156799d5dbe"></span> `COMMAND_DENIED` | Command denied. 
<span id="classdronecode__sdk_1_1_offboard_1a1f515eed9d23c450254233ea87131c09a070a0fb40f6c308ab544b227660aadff"></span> `TIMEOUT` | Request timeout. 
<span id="classdronecode__sdk_1_1_offboard_1a1f515eed9d23c450254233ea87131c09abe5140e11d47ef100aaf22a20c6f46b2"></span> `NO_SETPOINT_SET` |  Can't start without setpoint set.

## Member Function Documentation


### start() {#classdronecode__sdk_1_1_offboard_1a1d67617a9da5364a7cb981f9ba5710bd}
```cpp
Offboard::Result dronecode_sdk::Offboard::start()
```


Start offboard control (synchronous).

**Attention:** this is work in progress, use with caution!

**Returns**

&emsp;[Offboard::Result](classdronecode__sdk_1_1_offboard.md#classdronecode__sdk_1_1_offboard_1a1f515eed9d23c450254233ea87131c09) - Result of request.

### stop() {#classdronecode__sdk_1_1_offboard_1aaab6abfad63644d202a533359d26e29a}
```cpp
Offboard::Result dronecode_sdk::Offboard::stop()
```


Stop offboard control (synchronous).

The vehicle will be put into Hold mode: [https://docs.px4.io/en/flight_modes/hold.html](https://docs.px4.io/en/flight_modes/hold.html)

**Returns**

&emsp;[Offboard::Result](classdronecode__sdk_1_1_offboard.md#classdronecode__sdk_1_1_offboard_1a1f515eed9d23c450254233ea87131c09) - Result of request.

### start_async() {#classdronecode__sdk_1_1_offboard_1a8181092c3a3cac5e62dfcef4f10363de}
```cpp
void dronecode_sdk::Offboard::start_async(result_callback_t callback)
```


Start offboard control (asynchronous).

**Attention:** This is work in progress, use with caution!

**Parameters**

* [result_callback_t](classdronecode__sdk_1_1_offboard.md#classdronecode__sdk_1_1_offboard_1a02563418f94499b40d27543b3f486034) **callback** - Callback to receive request result.

### stop_async() {#classdronecode__sdk_1_1_offboard_1a2ff3262dbc6194def28bb9b3d5684e68}
```cpp
void dronecode_sdk::Offboard::stop_async(result_callback_t callback)
```


Stop offboard control (asynchronous).

The vehicle will be put into Hold mode: [https://docs.px4.io/en/flight_modes/hold.html](https://docs.px4.io/en/flight_modes/hold.html)

**Parameters**

* [result_callback_t](classdronecode__sdk_1_1_offboard.md#classdronecode__sdk_1_1_offboard_1a02563418f94499b40d27543b3f486034) **callback** - Callback to receive request result.

### is_active() {#classdronecode__sdk_1_1_offboard_1ac3c75fcd1ae1e6b00090eccd03696479}
```cpp
bool dronecode_sdk::Offboard::is_active() const
```


Check if offboard control is active.

`true` means that the vehicle is in offboard mode and we are actively sending setpoints.

**Returns**

&emsp;bool - `true` if active

### set_position_ned() {#classdronecode__sdk_1_1_offboard_1a127749d168fe4e7ddb40ba4c6747bb4a}
```cpp
void dronecode_sdk::Offboard::set_position_ned(PositionNEDYaw position_ned_yaw)
```


Set the position in NED coordinates and yaw.


**Parameters**

* [PositionNEDYaw](structdronecode__sdk_1_1_offboard_1_1_position_n_e_d_yaw.md) **position_ned_yaw** - Position and yaw `struct`.

### set_velocity_ned() {#classdronecode__sdk_1_1_offboard_1a95dfbe096a363e21bfd035258e786350}
```cpp
void dronecode_sdk::Offboard::set_velocity_ned(VelocityNEDYaw velocity_ned_yaw)
```


Set the velocity in NED coordinates and yaw.


**Parameters**

* [VelocityNEDYaw](structdronecode__sdk_1_1_offboard_1_1_velocity_n_e_d_yaw.md) **velocity_ned_yaw** - Velocity and yaw `struct`.

### set_velocity_body() {#classdronecode__sdk_1_1_offboard_1ad87778386509911269b87766c0f1830f}
```cpp
void dronecode_sdk::Offboard::set_velocity_body(VelocityBodyYawspeed velocity_body_yawspeed)
```


Set the velocity body coordinates and yaw angular rate.


**Parameters**

* [VelocityBodyYawspeed](structdronecode__sdk_1_1_offboard_1_1_velocity_body_yawspeed.md) **velocity_body_yawspeed** - Velocity and yaw angular rate `struct`.

### set_attitude() {#classdronecode__sdk_1_1_offboard_1aa8210f10366afadd99787b1df3e601a9}
```cpp
void dronecode_sdk::Offboard::set_attitude(Attitude attitude)
```


Set the attitude in terms of roll, pitch and yaw in degrees with thrust in percentage.


**Parameters**

* [Attitude](structdronecode__sdk_1_1_offboard_1_1_attitude.md) **attitude** - roll, pitch and yaw in degrees along with thrust in percentage.

### set_attitude_rate() {#classdronecode__sdk_1_1_offboard_1a511ba0314a4217c3ac3020ab2b0dfd23}
```cpp
void dronecode_sdk::Offboard::set_attitude_rate(AttitudeRate attitude_rate)
```


Set the attitude rate in terms of pitch, roll and yaw angular rate along with thrust in percentage.


**Parameters**

* [AttitudeRate](structdronecode__sdk_1_1_offboard_1_1_attitude_rate.md) **attitude_rate** - roll, pitch and yaw angular rate along with thrust in percentage.

### operator=() {#classdronecode__sdk_1_1_offboard_1a8cfbf6cbcb4fbdcf1574f0455632a372}
```cpp
const Offboard& dronecode_sdk::Offboard::operator=(const Offboard &)=delete
```


Equality operator (object is not copyable).


**Parameters**

* const [Offboard](classdronecode__sdk_1_1_offboard.md)&  - 

**Returns**

&emsp;const [Offboard](classdronecode__sdk_1_1_offboard.md) & - 

### result_str() {#classdronecode__sdk_1_1_offboard_1a78d6d7fe6372c5672da42f336bf4785b}
```cpp
static const char* dronecode_sdk::Offboard::result_str(Result result)
```


Get human-readable English string for [Offboard::Result](classdronecode__sdk_1_1_offboard.md#classdronecode__sdk_1_1_offboard_1a1f515eed9d23c450254233ea87131c09).


**Parameters**

* [Result](classdronecode__sdk_1_1_offboard.md#classdronecode__sdk_1_1_offboard_1a1f515eed9d23c450254233ea87131c09) **result** - The enum value for which a string is required.

**Returns**

&emsp;const char * - Human-readable string for enum value.