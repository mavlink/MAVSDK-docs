# dronecore::Gimbal Class Reference
`#include: gimbal.h`

----


The [Gimbal](classdronecore_1_1_gimbal.md) class enables to control a gimbal. 


Synchronous and asynchronous variants of the gimbal methods are supplied. 


## Public Types


Type | Description
--- | ---
enum [Result](#classdronecore_1_1_gimbal_1a2404686489b502fbc58e940701ba1e6f) | Possible results returned for gimbal commands.
std::function< void([Result](classdronecore_1_1_gimbal.md#classdronecore_1_1_gimbal_1a2404686489b502fbc58e940701ba1e6f))> [result_callback_t](#classdronecore_1_1_gimbal_1a309448760ba62635fce7139be44788ff) | Callback type for asynchronous [Gimbal](classdronecore_1_1_gimbal.md) calls.

## Public Member Functions


Type | Name | Description
---: | --- | ---
| [Gimbal](#classdronecore_1_1_gimbal_1a14f51547abcaabeb212ec04439e497be) (GimbalImpl *impl) | Constructor (internal use only).
| [~Gimbal](#classdronecore_1_1_gimbal_1a4f8b2a6cf5a7347a474f8e47618ad838) () | Destructor (internal use only).
| [Gimbal](#classdronecore_1_1_gimbal_1a82637c62da14ae39db96724d4273cad4) (const Gimbal &)=delete | Copy constructor (object is not copyable).
[Result](classdronecore_1_1_gimbal.md#classdronecore_1_1_gimbal_1a2404686489b502fbc58e940701ba1e6f) | [set_pitch_and_yaw](#classdronecore_1_1_gimbal_1ac8ac49d29f11b2107da6b043bb57b54e) (float pitch_deg, float yaw_deg) | Set gimbal pitch and yaw angles (synchronous).
void | [set_pitch_and_yaw_async](#classdronecore_1_1_gimbal_1a3aea07049f32f8bc5b2edaee8cb2ac16) (float pitch_deg, float yaw_deg, result_callback_t callback) | Set gimbal pitch and yaw angles (asynchronous).
const [Gimbal](classdronecore_1_1_gimbal.md) & | [operator=](#classdronecore_1_1_gimbal_1ad15551254ea56674c576bbcbec6e7eac) (const Gimbal &)=delete | Equality operator (object is not copyable).

## Static Public Member Functions


Type | Name | Description
---: | --- | ---
const char * | [result_str](#classdronecore_1_1_gimbal_1ad60c5378cc7d160be67432f4d6daa30d) (Result result) | Returns a human-readable English string for [Gimbal::Result](classdronecore_1_1_gimbal.md#classdronecore_1_1_gimbal_1a2404686489b502fbc58e940701ba1e6f).


## Constructor & Destructor Documentation


### Gimbal() {#classdronecore_1_1_gimbal_1a14f51547abcaabeb212ec04439e497be}
```cpp
dronecore::Gimbal::Gimbal(GimbalImpl *impl)
```


Constructor (internal use only).


**Parameters**

* GimbalImpl * **impl** - Private internal implementation.

### ~Gimbal() {#classdronecore_1_1_gimbal_1a4f8b2a6cf5a7347a474f8e47618ad838}
```cpp
dronecore::Gimbal::~Gimbal()
```


Destructor (internal use only).


### Gimbal() {#classdronecore_1_1_gimbal_1a82637c62da14ae39db96724d4273cad4}
```cpp
dronecore::Gimbal::Gimbal(const Gimbal &)=delete
```


Copy constructor (object is not copyable).


**Parameters**

* const [Gimbal](classdronecore_1_1_gimbal.md) & - 

## Member Typdef Documentation


### typedef result_callback_t {#classdronecore_1_1_gimbal_1a309448760ba62635fce7139be44788ff}

```cpp
typedef std::function<void(Result)> dronecore::Gimbal::result_callback_t
```


Callback type for asynchronous [Gimbal](classdronecore_1_1_gimbal.md) calls.


## Member Enumeration Documentation


### enum Result {#classdronecore_1_1_gimbal_1a2404686489b502fbc58e940701ba1e6f}


Possible results returned for gimbal commands.


 Value | Description
--- | ---
<span id="classdronecore_1_1_gimbal_1a2404686489b502fbc58e940701ba1e6fad0749aaba8b833466dfcbb0428e4f89c"></span> `SUCCESS` | Success. The gimbal command was accepted. 
<span id="classdronecore_1_1_gimbal_1a2404686489b502fbc58e940701ba1e6fabb1ca97ec761fc37101737ba0aa2e7c5"></span> `ERROR` | Error. An error occured sending the command. 
<span id="classdronecore_1_1_gimbal_1a2404686489b502fbc58e940701ba1e6fa070a0fb40f6c308ab544b227660aadff"></span> `TIMEOUT` | Timeout. A timeout occured sending the command. 
<span id="classdronecore_1_1_gimbal_1a2404686489b502fbc58e940701ba1e6fa696b031073e74bf2cb98e5ef201d4aa3"></span> `UNKNOWN` | Unspecified error. 

## Member Function Documentation


### set_pitch_and_yaw() {#classdronecore_1_1_gimbal_1ac8ac49d29f11b2107da6b043bb57b54e}
```cpp
Result dronecore::Gimbal::set_pitch_and_yaw(float pitch_deg, float yaw_deg)
```


Set gimbal pitch and yaw angles (synchronous).

This sets the desired pitch and yaw angles of a gimbal. The function will return when the command is accepted, however, it might take the gimbal longer to actually be set to the new angles.

**Parameters**

* float **pitch_deg** - The pitch angle in degrees. Negative to point down.
* float **yaw_deg** - The yaw angle in degrees. Positive for clock-wise, range -180..180 or 0..360.

**Returns**

&emsp;[Result](classdronecore_1_1_gimbal.md#classdronecore_1_1_gimbal_1a2404686489b502fbc58e940701ba1e6f) - Result of request.

### set_pitch_and_yaw_async() {#classdronecore_1_1_gimbal_1a3aea07049f32f8bc5b2edaee8cb2ac16}
```cpp
void dronecore::Gimbal::set_pitch_and_yaw_async(float pitch_deg, float yaw_deg, result_callback_t callback)
```


Set gimbal pitch and yaw angles (asynchronous).

This sets the desired pitch and yaw angles of a gimbal. The callback will be called when the command is accepted, however, it might take the gimbal longer to actually be set to the new angles.

**Parameters**

* float **pitch_deg** - The pitch angle in degrees. Negative to point down.
* float **yaw_deg** - The yaw angle in degrees. Positive for clock-wise, range -180..180 or 0..360.
* [result_callback_t](classdronecore_1_1_gimbal.md#classdronecore_1_1_gimbal_1a309448760ba62635fce7139be44788ff) **callback** - Function to call with result of request.

### operator=() {#classdronecore_1_1_gimbal_1ad15551254ea56674c576bbcbec6e7eac}
```cpp
const Gimbal& dronecore::Gimbal::operator=(const Gimbal &)=delete
```


Equality operator (object is not copyable).


**Parameters**

* const [Gimbal](classdronecore_1_1_gimbal.md) & - 

**Returns**

&emsp;const [Gimbal](classdronecore_1_1_gimbal.md) & - 

### result_str() {#classdronecore_1_1_gimbal_1ad60c5378cc7d160be67432f4d6daa30d}
```cpp
static const char* dronecore::Gimbal::result_str(Result result)
```


Returns a human-readable English string for [Gimbal::Result](classdronecore_1_1_gimbal.md#classdronecore_1_1_gimbal_1a2404686489b502fbc58e940701ba1e6f).


**Parameters**

* [Result](classdronecore_1_1_gimbal.md#classdronecore_1_1_gimbal_1a2404686489b502fbc58e940701ba1e6f) **result** - The enum value for which a human readable string is required.

**Returns**

&emsp;const char * - Human readable string for the [Gimbal::Result](classdronecore_1_1_gimbal.md#classdronecore_1_1_gimbal_1a2404686489b502fbc58e940701ba1e6f).