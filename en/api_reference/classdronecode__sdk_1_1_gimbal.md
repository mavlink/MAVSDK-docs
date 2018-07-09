# dronecode_sdk::Gimbal Class Reference
`#include: gimbal.h`

----


The [Gimbal](classdronecode__sdk_1_1_gimbal.md) class provides control over a gimbal. 


Synchronous and asynchronous variants of the gimbal methods are supplied. 


## Public Types


Type | Description
--- | ---
enum [Result](#classdronecode__sdk_1_1_gimbal_1abfa6fa8cc3ed417e7a6b2593de0c5031) | Possible results returned for gimbal commands.
std::function< void([Result](classdronecode__sdk_1_1_gimbal.md#classdronecode__sdk_1_1_gimbal_1abfa6fa8cc3ed417e7a6b2593de0c5031))> [result_callback_t](#classdronecode__sdk_1_1_gimbal_1a5b8bd4a8280b82ce0a87777df7865769) | Callback type for asynchronous [Gimbal](classdronecode__sdk_1_1_gimbal.md) calls.

## Public Member Functions


Type | Name | Description
---: | --- | ---
&nbsp; | [Gimbal](#classdronecode__sdk_1_1_gimbal_1af43112c1316d756142b327bbb27ea4f6) ([System](classdronecode__sdk_1_1_system.md) & system) | Constructor. Creates the plugin for a specific [System](classdronecode__sdk_1_1_system.md).
&nbsp; | [~Gimbal](#classdronecode__sdk_1_1_gimbal_1a215ea0210eb857c7621eaa231fc7b106) () | Destructor (internal use only).
&nbsp; | [Gimbal](#classdronecode__sdk_1_1_gimbal_1a0764af7a7286024466de7fb39948275a) (const [Gimbal](classdronecode__sdk_1_1_gimbal.md) &)=delete | Copy constructor (object is not copyable).
[Result](classdronecode__sdk_1_1_gimbal.md#classdronecode__sdk_1_1_gimbal_1abfa6fa8cc3ed417e7a6b2593de0c5031) | [set_pitch_and_yaw](#classdronecode__sdk_1_1_gimbal_1a7dcfa459648c9bf57cac013500c5d259) (float pitch_deg, float yaw_deg) | Set gimbal pitch and yaw angles (synchronous).
void | [set_pitch_and_yaw_async](#classdronecode__sdk_1_1_gimbal_1a91307f28c05bce935902c6e7bcd7d7b7) (float pitch_deg, float yaw_deg, [result_callback_t](classdronecode__sdk_1_1_gimbal.md#classdronecode__sdk_1_1_gimbal_1a5b8bd4a8280b82ce0a87777df7865769) callback) | Set gimbal pitch and yaw angles (asynchronous).
[Result](classdronecode__sdk_1_1_gimbal.md#classdronecode__sdk_1_1_gimbal_1abfa6fa8cc3ed417e7a6b2593de0c5031) | [set_roi_location](#classdronecode__sdk_1_1_gimbal_1a5bfbebf258cda0c161f8702d809215d4) (double latitude_deg, double longitude_deg, float altitude_m) | Set gimbal region of interest (ROI).
void | [set_roi_location_async](#classdronecode__sdk_1_1_gimbal_1a758b3dded5929e95b215a12d2aac7aa9) (double latitude_deg, double longitude_deg, float altitude_m, [result_callback_t](classdronecode__sdk_1_1_gimbal.md#classdronecode__sdk_1_1_gimbal_1a5b8bd4a8280b82ce0a87777df7865769) callback) | Set gimbal region of interest (ROI) (asynchronous).
const [Gimbal](classdronecode__sdk_1_1_gimbal.md) & | [operator=](#classdronecode__sdk_1_1_gimbal_1a81809c8c9a149f0d8fefe2635c0880e2) (const [Gimbal](classdronecode__sdk_1_1_gimbal.md) &)=delete | Equality operator (object is not copyable).

## Static Public Member Functions


Type | Name | Description
---: | --- | ---
const char * | [result_str](#classdronecode__sdk_1_1_gimbal_1ac9b3c56c3c93b9949ad7651014b2c04b) ([Result](classdronecode__sdk_1_1_gimbal.md#classdronecode__sdk_1_1_gimbal_1abfa6fa8cc3ed417e7a6b2593de0c5031) result) | Returns a human-readable English string for [Gimbal::Result](classdronecode__sdk_1_1_gimbal.md#classdronecode__sdk_1_1_gimbal_1abfa6fa8cc3ed417e7a6b2593de0c5031).


## Constructor & Destructor Documentation


### Gimbal() {#classdronecode__sdk_1_1_gimbal_1af43112c1316d756142b327bbb27ea4f6}
```cpp
dronecode_sdk::Gimbal::Gimbal(System &system)
```


Constructor. Creates the plugin for a specific [System](classdronecode__sdk_1_1_system.md).

The plugin is typically created as shown below: 

```cpp
auto gimbal = std::make_shared<Gimbal>(system);
```

**Parameters**

* [System](classdronecode__sdk_1_1_system.md)& **system** - The specific system associated with this plugin.

### ~Gimbal() {#classdronecode__sdk_1_1_gimbal_1a215ea0210eb857c7621eaa231fc7b106}
```cpp
dronecode_sdk::Gimbal::~Gimbal()
```


Destructor (internal use only).


### Gimbal() {#classdronecode__sdk_1_1_gimbal_1a0764af7a7286024466de7fb39948275a}
```cpp
dronecode_sdk::Gimbal::Gimbal(const Gimbal &)=delete
```


Copy constructor (object is not copyable).


**Parameters**

* const [Gimbal](classdronecode__sdk_1_1_gimbal.md)&  - 

## Member Typdef Documentation


### typedef result_callback_t {#classdronecode__sdk_1_1_gimbal_1a5b8bd4a8280b82ce0a87777df7865769}

```cpp
typedef std::function<void(Result)> dronecode_sdk::Gimbal::result_callback_t
```


Callback type for asynchronous [Gimbal](classdronecode__sdk_1_1_gimbal.md) calls.


## Member Enumeration Documentation


### enum Result {#classdronecode__sdk_1_1_gimbal_1abfa6fa8cc3ed417e7a6b2593de0c5031}


Possible results returned for gimbal commands.


Value | Description
--- | ---
<span id="classdronecode__sdk_1_1_gimbal_1abfa6fa8cc3ed417e7a6b2593de0c5031ad0749aaba8b833466dfcbb0428e4f89c"></span> `SUCCESS` | Success. The gimbal command was accepted. 
<span id="classdronecode__sdk_1_1_gimbal_1abfa6fa8cc3ed417e7a6b2593de0c5031abb1ca97ec761fc37101737ba0aa2e7c5"></span> `ERROR` | Error. An error occured sending the command. 
<span id="classdronecode__sdk_1_1_gimbal_1abfa6fa8cc3ed417e7a6b2593de0c5031a070a0fb40f6c308ab544b227660aadff"></span> `TIMEOUT` | Timeout. A timeout occured sending the command. 
<span id="classdronecode__sdk_1_1_gimbal_1abfa6fa8cc3ed417e7a6b2593de0c5031a696b031073e74bf2cb98e5ef201d4aa3"></span> `UNKNOWN` | Unspecified error. 

## Member Function Documentation


### set_pitch_and_yaw() {#classdronecode__sdk_1_1_gimbal_1a7dcfa459648c9bf57cac013500c5d259}
```cpp
Result dronecode_sdk::Gimbal::set_pitch_and_yaw(float pitch_deg, float yaw_deg)
```


Set gimbal pitch and yaw angles (synchronous).

This sets the desired pitch and yaw angles of a gimbal. The function will return when the command is accepted, however, it might take the gimbal longer to actually be set to the new angles.

**Parameters**

* float **pitch_deg** - The pitch angle in degrees. Negative to point down.
* float **yaw_deg** - The yaw angle in degrees. Positive for clock-wise, range -180..180 or 0..360.

**Returns**

&emsp;[Result](classdronecode__sdk_1_1_gimbal.md#classdronecode__sdk_1_1_gimbal_1abfa6fa8cc3ed417e7a6b2593de0c5031) - Result of request.

### set_pitch_and_yaw_async() {#classdronecode__sdk_1_1_gimbal_1a91307f28c05bce935902c6e7bcd7d7b7}
```cpp
void dronecode_sdk::Gimbal::set_pitch_and_yaw_async(float pitch_deg, float yaw_deg, result_callback_t callback)
```


Set gimbal pitch and yaw angles (asynchronous).

This sets the desired pitch and yaw angles of a gimbal. The callback will be called when the command is accepted, however, it might take the gimbal longer to actually be set to the new angles.

**Parameters**

* float **pitch_deg** - The pitch angle in degrees. Negative to point down.
* float **yaw_deg** - The yaw angle in degrees. Positive for clock-wise, range -180..180 or 0..360.
* [result_callback_t](classdronecode__sdk_1_1_gimbal.md#classdronecode__sdk_1_1_gimbal_1a5b8bd4a8280b82ce0a87777df7865769) **callback** - Function to call with result of request.

### set_roi_location() {#classdronecode__sdk_1_1_gimbal_1a5bfbebf258cda0c161f8702d809215d4}
```cpp
Result dronecode_sdk::Gimbal::set_roi_location(double latitude_deg, double longitude_deg, float altitude_m)
```


Set gimbal region of interest (ROI).

This sets a region of interest that the gimbal will point to. The gimbal will continue to point to the specified region until it receives a new command. The function will return when the command is accepted, however, it might take the gimbal longer to actually rotate to the ROI.

**Parameters**

* double **latitude_deg** - Latitude in degrees.
* double **longitude_deg** - Longitude in degrees.
* float **altitude_m** - Altitude in meters (ASML).

**Returns**

&emsp;[Result](classdronecode__sdk_1_1_gimbal.md#classdronecode__sdk_1_1_gimbal_1abfa6fa8cc3ed417e7a6b2593de0c5031) - Result of request.

### set_roi_location_async() {#classdronecode__sdk_1_1_gimbal_1a758b3dded5929e95b215a12d2aac7aa9}
```cpp
void dronecode_sdk::Gimbal::set_roi_location_async(double latitude_deg, double longitude_deg, float altitude_m, result_callback_t callback)
```


Set gimbal region of interest (ROI) (asynchronous).

This sets a region of interest that the gimbal will point to. The gimbal will continue to point to the specified region until it receives a new command. The callback will be called when the command is accepted, however, it might take the gimbal longer to actually be set to the new angles.

**Parameters**

* double **latitude_deg** - Latitude in degrees.
* double **longitude_deg** - Longitude in degrees.
* float **altitude_m** - Altitude in meters (ASML).
* [result_callback_t](classdronecode__sdk_1_1_gimbal.md#classdronecode__sdk_1_1_gimbal_1a5b8bd4a8280b82ce0a87777df7865769) **callback** - Function to call with result of request.

### operator=() {#classdronecode__sdk_1_1_gimbal_1a81809c8c9a149f0d8fefe2635c0880e2}
```cpp
const Gimbal& dronecode_sdk::Gimbal::operator=(const Gimbal &)=delete
```


Equality operator (object is not copyable).


**Parameters**

* const [Gimbal](classdronecode__sdk_1_1_gimbal.md)&  - 

**Returns**

&emsp;const [Gimbal](classdronecode__sdk_1_1_gimbal.md) & - 

### result_str() {#classdronecode__sdk_1_1_gimbal_1ac9b3c56c3c93b9949ad7651014b2c04b}
```cpp
static const char* dronecode_sdk::Gimbal::result_str(Result result)
```


Returns a human-readable English string for [Gimbal::Result](classdronecode__sdk_1_1_gimbal.md#classdronecode__sdk_1_1_gimbal_1abfa6fa8cc3ed417e7a6b2593de0c5031).


**Parameters**

* [Result](classdronecode__sdk_1_1_gimbal.md#classdronecode__sdk_1_1_gimbal_1abfa6fa8cc3ed417e7a6b2593de0c5031) **result** - The enum value for which a human readable string is required.

**Returns**

&emsp;const char * - Human readable string for the [Gimbal::Result](classdronecode__sdk_1_1_gimbal.md#classdronecode__sdk_1_1_gimbal_1abfa6fa8cc3ed417e7a6b2593de0c5031).