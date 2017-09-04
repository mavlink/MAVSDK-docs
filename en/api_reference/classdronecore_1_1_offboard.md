# dronecore::Offboard Class Reference
`#include: offboard.h`

----


This class is used to control a drone with velocity commands. 


The module is called offboard because the velocity commands can be sent from external sources as opposed to onboard control right inside the autopilot "board".


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
| [Offboard](#classdronecore_1_1_offboard_1a8015934ad2d766f8b37b7d5b43f2b089) (OffboardImpl *impl) | Constructor (internal use only).
| [~Offboard](#classdronecore_1_1_offboard_1a7cb4eff36c37fed1c6d973aa41b059b8) () | Destructor (internal use only).
| [Offboard](#classdronecore_1_1_offboard_1ac586be55cb24aa0ccd29c97352dd2ee5) (const Offboard &)=delete | Copy constructor (object is not copyable).
[Offboard::Result](classdronecore_1_1_offboard.md#classdronecore_1_1_offboard_1a0f6e5e9f73289f27dc99abbb3ab572ed) | [start](#classdronecore_1_1_offboard_1ab1965b77299ea46d4cff749385ab8bd1) () const | Start offboard control (synchronous).
[Offboard::Result](classdronecore_1_1_offboard.md#classdronecore_1_1_offboard_1a0f6e5e9f73289f27dc99abbb3ab572ed) | [stop](#classdronecore_1_1_offboard_1a1239beddb7d1be0ab8287b122db70ebc) () const | Stop offboard control (synchronous).
void | [start_async](#classdronecore_1_1_offboard_1a5dd9d18eedb0e4a8f1bbbeebf6f99aa8) (result_callback_t callback) |
void | [stop_async](#classdronecore_1_1_offboard_1afbe6f50f63d3bc43acc4dfc2f797ca0a) (result_callback_t callback) | Stop offboard control (asynchronous).
void | [set_velocity_ned](#classdronecore_1_1_offboard_1a9e7f369a8f7459dc7705f4453a8c307d) (VelocityNEDYaw velocity_ned_yaw) | Set the velocity in NED coordinates and yaw.
void | [set_velocity_body](#classdronecore_1_1_offboard_1ad9dc585be1bc2dba699cf089d4c274cc) (VelocityBodyYawspeed velocity_body_yawspeed) | Set the velocity body coordinates coordinates and yaw angular rate.
const [Offboard](classdronecore_1_1_offboard.md) & | [operator=](#classdronecore_1_1_offboard_1aa6bf966e606cdd361364791d06aca977) (const Offboard &)=delete | Equality operator (object is not copyable).
## Static Public Member Functions


Type | Name | Description
---: | --- | ---
const char * | [result_str](#classdronecore_1_1_offboard_1a97a03a7bde9946b098844b44a5782220) (Result result) | Get human-readable English string for [Offboard::Result](classdronecore_1_1_offboard.md#classdronecore_1_1_offboard_1a0f6e5e9f73289f27dc99abbb3ab572ed).


## Constructor & Destructor Documentation


### Offboard() {#classdronecore_1_1_offboard_1a8015934ad2d766f8b37b7d5b43f2b089}
```cpp
dronecore::Offboard::Offboard(OffboardImpl *impl)
```


Constructor (internal use only).


**Parameters**

* [OffboardImpl](classdronecore_1_1_offboard_impl.md) * **impl** - 

<!-- inbodydescription:  --> 
<!-- return_type:  -->
<!-- return_type_comment:  -->
<!-- prot: public -->
<!-- static: no -->
<!-- const: no -->
<!-- explicit: yes -->
<!-- virt: non-virtual -->
<!-- inline: no -->


### ~Offboard() {#classdronecore_1_1_offboard_1a7cb4eff36c37fed1c6d973aa41b059b8}
```cpp
dronecore::Offboard::~Offboard()
```


Destructor (internal use only).


<!-- inbodydescription:  --> 
<!-- return_type:  -->
<!-- return_type_comment:  -->
<!-- prot: public -->
<!-- static: no -->
<!-- const: no -->
<!-- explicit: no -->
<!-- virt: non-virtual -->
<!-- inline: no -->


### Offboard() {#classdronecore_1_1_offboard_1ac586be55cb24aa0ccd29c97352dd2ee5}
```cpp
dronecore::Offboard::Offboard(const Offboard &)=delete
```


Copy constructor (object is not copyable).


**Parameters**

* const [Offboard](classdronecore_1_1_offboard.md) & **** - 

<!-- inbodydescription:  --> 
<!-- return_type:  -->
<!-- return_type_comment:  -->
<!-- prot: public -->
<!-- static: no -->
<!-- const: no -->
<!-- explicit: no -->
<!-- virt: non-virtual -->
<!-- inline: no -->

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
<span id="classdronecore_1_1_offboard_1a0f6e5e9f73289f27dc99abbb3ab572eda696b031073e74bf2cb98e5ef201d4aa3"></span> `UNKNOWN` | Unknown error. 

<!-- inbodydescription:  --> 
<!-- prot: public -->
<!-- static: no -->

## Member Function Documentation


### start() {#classdronecore_1_1_offboard_1ab1965b77299ea46d4cff749385ab8bd1}
```cpp
Offboard::Result dronecore::Offboard::start() const
```


Start offboard control (synchronous).

**Attention:** this is work in progress, use with caution!

**Returns**

&emsp;[Offboard::Result](classdronecore_1_1_offboard.md#classdronecore_1_1_offboard_1a0f6e5e9f73289f27dc99abbb3ab572ed) - Result of request.

<!-- inbodydescription:  --> 
<!-- return_type: [Offboard::Result](classdronecore_1_1_offboard.md#classdronecore_1_1_offboard_1a0f6e5e9f73289f27dc99abbb3ab572ed) -->
<!-- return_type_comment: Result of request. -->
<!-- prot: public -->
<!-- static: no -->
<!-- const: yes -->
<!-- explicit: no -->
<!-- virt: non-virtual -->
<!-- inline: no -->


### stop() {#classdronecore_1_1_offboard_1a1239beddb7d1be0ab8287b122db70ebc}
```cpp
Offboard::Result dronecore::Offboard::stop() const
```


Stop offboard control (synchronous).


**Returns**

&emsp;[Offboard::Result](classdronecore_1_1_offboard.md#classdronecore_1_1_offboard_1a0f6e5e9f73289f27dc99abbb3ab572ed) - Result of request.

<!-- inbodydescription:  --> 
<!-- return_type: [Offboard::Result](classdronecore_1_1_offboard.md#classdronecore_1_1_offboard_1a0f6e5e9f73289f27dc99abbb3ab572ed) -->
<!-- return_type_comment: Result of request. -->
<!-- prot: public -->
<!-- static: no -->
<!-- const: yes -->
<!-- explicit: no -->
<!-- virt: non-virtual -->
<!-- inline: no -->


### start_async() {#classdronecore_1_1_offboard_1a5dd9d18eedb0e4a8f1bbbeebf6f99aa8}
```cpp
void dronecore::Offboard::start_async(result_callback_t callback)
```


Start offboard control (asynchronous).


**Attention:** This is work in progress, use with caution!

**Parameters**

* [result_callback_t](classdronecore_1_1_offboard.md#classdronecore_1_1_offboard_1a75eeca649293887ac9d398e6432e431f) **callback** - Callback to receive request result.

<!-- inbodydescription:  --> 
<!-- return_type: void -->
<!-- return_type_comment:  -->
<!-- prot: public -->
<!-- static: no -->
<!-- const: no -->
<!-- explicit: no -->
<!-- virt: non-virtual -->
<!-- inline: no -->


### stop_async() {#classdronecore_1_1_offboard_1afbe6f50f63d3bc43acc4dfc2f797ca0a}
```cpp
void dronecore::Offboard::stop_async(result_callback_t callback)
```


Stop offboard control (asynchronous).


**Parameters**

* [result_callback_t](classdronecore_1_1_offboard.md#classdronecore_1_1_offboard_1a75eeca649293887ac9d398e6432e431f) **callback** - Callback to receive request result.

<!-- inbodydescription:  --> 
<!-- return_type: void -->
<!-- return_type_comment:  -->
<!-- prot: public -->
<!-- static: no -->
<!-- const: no -->
<!-- explicit: no -->
<!-- virt: non-virtual -->
<!-- inline: no -->


### set_velocity_ned() {#classdronecore_1_1_offboard_1a9e7f369a8f7459dc7705f4453a8c307d}
```cpp
void dronecore::Offboard::set_velocity_ned(VelocityNEDYaw velocity_ned_yaw)
```


Set the velocity in NED coordinates and yaw.


**Parameters**

* [VelocityNEDYaw](structdronecore_1_1_offboard_1_1_velocity_n_e_d_yaw.md) **velocity_ned_yaw** - Velocity and yaw struct.

<!-- inbodydescription:  --> 
<!-- return_type: void -->
<!-- return_type_comment:  -->
<!-- prot: public -->
<!-- static: no -->
<!-- const: no -->
<!-- explicit: no -->
<!-- virt: non-virtual -->
<!-- inline: no -->


### set_velocity_body() {#classdronecore_1_1_offboard_1ad9dc585be1bc2dba699cf089d4c274cc}
```cpp
void dronecore::Offboard::set_velocity_body(VelocityBodyYawspeed velocity_body_yawspeed)
```


Set the velocity body coordinates coordinates and yaw angular rate.


**Parameters**

* [VelocityBodyYawspeed](structdronecore_1_1_offboard_1_1_velocity_body_yawspeed.md) **velocity_body_yawspeed** - Velocity and yaw angular rate struct.

<!-- inbodydescription:  --> 
<!-- return_type: void -->
<!-- return_type_comment:  -->
<!-- prot: public -->
<!-- static: no -->
<!-- const: no -->
<!-- explicit: no -->
<!-- virt: non-virtual -->
<!-- inline: no -->


### operator=() {#classdronecore_1_1_offboard_1aa6bf966e606cdd361364791d06aca977}
```cpp
const Offboard& dronecore::Offboard::operator=(const Offboard &)=delete
```


Equality operator (object is not copyable).


**Parameters**

* const [Offboard](classdronecore_1_1_offboard.md) & **** - 

**Returns**

&emsp;const [Offboard](classdronecore_1_1_offboard.md) & - 

<!-- inbodydescription:  --> 
<!-- return_type: const [Offboard](classdronecore_1_1_offboard.md) & -->
<!-- return_type_comment:  -->
<!-- prot: public -->
<!-- static: no -->
<!-- const: no -->
<!-- explicit: no -->
<!-- virt: non-virtual -->
<!-- inline: no -->


### result_str() {#classdronecore_1_1_offboard_1a97a03a7bde9946b098844b44a5782220}
```cpp
static const char * dronecore::Offboard::result_str(Result result)
```


Get human-readable English string for [Offboard::Result](classdronecore_1_1_offboard.md#classdronecore_1_1_offboard_1a0f6e5e9f73289f27dc99abbb3ab572ed).


**Parameters**

* [Result](classdronecore_1_1_offboard.md#classdronecore_1_1_offboard_1a0f6e5e9f73289f27dc99abbb3ab572ed) **result** - The enum value for which a string is required.

**Returns**

&emsp;const char * - 

<!-- inbodydescription:  --> 
<!-- return_type: const char * -->
<!-- return_type_comment:  -->
<!-- prot: public -->
<!-- static: yes -->
<!-- const: no -->
<!-- explicit: no -->
<!-- virt: non-virtual -->
<!-- inline: no -->
