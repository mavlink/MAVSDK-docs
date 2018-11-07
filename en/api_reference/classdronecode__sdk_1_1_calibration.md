# dronecode_sdk::Calibration Class Reference
`#include: calibration.h`

----


The [Calibration](classdronecode__sdk_1_1_calibration.md) class enables to calibrate sensors of a drone such as gyro, accelerometer, and magnetometer. 


## Data Structures


struct [ProgressData](structdronecode__sdk_1_1_calibration_1_1_progress_data.md)

## Public Types


Type | Description
--- | ---
enum [Result](#classdronecode__sdk_1_1_calibration_1a425b76c213bb478762a375d3aef4e644) | Possible results returned for calibration commands.
std::function< void(const [Result](classdronecode__sdk_1_1_calibration.md#classdronecode__sdk_1_1_calibration_1a425b76c213bb478762a375d3aef4e644) result, const [ProgressData](structdronecode__sdk_1_1_calibration_1_1_progress_data.md))> [calibration_callback_t](#classdronecode__sdk_1_1_calibration_1a80de297cc0a8a77d81902cf765aa77a1) | Callback type for asynchronous calibration call.

## Public Member Functions


Type | Name | Description
---: | --- | ---
&nbsp; | [Calibration](#classdronecode__sdk_1_1_calibration_1aa559a3d7bffccf86b37e17e180c9dc0f) ([System](classdronecode__sdk_1_1_system.md) & system) | Constructor. Creates the plugin for a specific [System](classdronecode__sdk_1_1_system.md).
&nbsp; | [~Calibration](#classdronecode__sdk_1_1_calibration_1a0b012f09aa192147e3f50068625dd094) () | Destructor (internal use only).
&nbsp; | [Calibration](#classdronecode__sdk_1_1_calibration_1a7e28c4fcb6244db88fa91bc56dee9a37) (const [Calibration](classdronecode__sdk_1_1_calibration.md) &)=delete | Copy constructor (object is not copyable).
void | [calibrate_gyro_async](#classdronecode__sdk_1_1_calibration_1aa7ec9bc9ed62fa23d0d370ec2809b44b) ([calibration_callback_t](classdronecode__sdk_1_1_calibration.md#classdronecode__sdk_1_1_calibration_1a80de297cc0a8a77d81902cf765aa77a1) callback) | Perform gyro calibration (asynchronous call).
void | [calibrate_accelerometer_async](#classdronecode__sdk_1_1_calibration_1ac82675b0235bc7ed8c0a3259739e0bea) ([calibration_callback_t](classdronecode__sdk_1_1_calibration.md#classdronecode__sdk_1_1_calibration_1a80de297cc0a8a77d81902cf765aa77a1) callback) | Perform accelerometer calibration (asynchronous call).
void | [calibrate_magnetometer_async](#classdronecode__sdk_1_1_calibration_1ae69b7a5e7308f7f9176152a30ff9049f) ([calibration_callback_t](classdronecode__sdk_1_1_calibration.md#classdronecode__sdk_1_1_calibration_1a80de297cc0a8a77d81902cf765aa77a1) callback) | Perform magnetometer calibration (asynchronous call).
void | [calibrate_gimbal_accelerometer_async](#classdronecode__sdk_1_1_calibration_1a1a5fe007db8e548b1305126a94f441af) ([calibration_callback_t](classdronecode__sdk_1_1_calibration.md#classdronecode__sdk_1_1_calibration_1a80de297cc0a8a77d81902cf765aa77a1) callback) | Perform gimbal accelerometer calibration (asynchronous call).
const [Calibration](classdronecode__sdk_1_1_calibration.md) & | [operator=](#classdronecode__sdk_1_1_calibration_1a347cb2bc05828fc1cbb40bebfc50cabc) (const [Calibration](classdronecode__sdk_1_1_calibration.md) &)=delete | Equality operator (object is not copyable).

## Static Public Member Functions


Type | Name | Description
---: | --- | ---
const char * | [result_str](#classdronecode__sdk_1_1_calibration_1abdecc0953344ca1f771133a8be571116) ([Result](classdronecode__sdk_1_1_calibration.md#classdronecode__sdk_1_1_calibration_1a425b76c213bb478762a375d3aef4e644) result) | Returns a human-readable English string for [Calibration::Result](classdronecode__sdk_1_1_calibration.md#classdronecode__sdk_1_1_calibration_1a425b76c213bb478762a375d3aef4e644).


## Constructor & Destructor Documentation


### Calibration() {#classdronecode__sdk_1_1_calibration_1aa559a3d7bffccf86b37e17e180c9dc0f}
```cpp
dronecode_sdk::Calibration::Calibration(System &system)
```


Constructor. Creates the plugin for a specific [System](classdronecode__sdk_1_1_system.md).

The plugin is typically created as shown below: 

```cpp
auto calibration = std::make_shared<Calibration>(system);
```

**Parameters**

* [System](classdronecode__sdk_1_1_system.md)& **system** - The specific system associated with this plugin.

### ~Calibration() {#classdronecode__sdk_1_1_calibration_1a0b012f09aa192147e3f50068625dd094}
```cpp
dronecode_sdk::Calibration::~Calibration()
```


Destructor (internal use only).


### Calibration() {#classdronecode__sdk_1_1_calibration_1a7e28c4fcb6244db88fa91bc56dee9a37}
```cpp
dronecode_sdk::Calibration::Calibration(const Calibration &)=delete
```


Copy constructor (object is not copyable).


**Parameters**

* const [Calibration](classdronecode__sdk_1_1_calibration.md)&  - 

## Member Typdef Documentation


### typedef calibration_callback_t {#classdronecode__sdk_1_1_calibration_1a80de297cc0a8a77d81902cf765aa77a1}

```cpp
typedef std::function<void(const Result result, const ProgressData)> dronecode_sdk::Calibration::calibration_callback_t
```


Callback type for asynchronous calibration call.


## Member Enumeration Documentation


### enum Result {#classdronecode__sdk_1_1_calibration_1a425b76c213bb478762a375d3aef4e644}


Possible results returned for calibration commands.


Value | Description
--- | ---
<span id="classdronecode__sdk_1_1_calibration_1a425b76c213bb478762a375d3aef4e644a696b031073e74bf2cb98e5ef201d4aa3"></span> `UNKNOWN` |  
<span id="classdronecode__sdk_1_1_calibration_1a425b76c213bb478762a375d3aef4e644ad0749aaba8b833466dfcbb0428e4f89c"></span> `SUCCESS` |  
<span id="classdronecode__sdk_1_1_calibration_1a425b76c213bb478762a375d3aef4e644aca69f96c768067fbff6c911ca87bccc9"></span> `IN_PROGRESS` |  
<span id="classdronecode__sdk_1_1_calibration_1a425b76c213bb478762a375d3aef4e644a40cb2f2c740ed5a8dec7dc25e0b5aacb"></span> `INSTRUCTION` |  
<span id="classdronecode__sdk_1_1_calibration_1a425b76c213bb478762a375d3aef4e644ab9e14d9b2886bcff408b85aefa780419"></span> `FAILED` |  
<span id="classdronecode__sdk_1_1_calibration_1a425b76c213bb478762a375d3aef4e644afeae72a3a2feec3c92c2a79a30d31186"></span> `NO_SYSTEM` |  
<span id="classdronecode__sdk_1_1_calibration_1a425b76c213bb478762a375d3aef4e644ac77f1f09dab2c0c9980fca7cfae02518"></span> `CONNECTION_ERROR` |  
<span id="classdronecode__sdk_1_1_calibration_1a425b76c213bb478762a375d3aef4e644a802706a9238e2928077f97736854bad4"></span> `BUSY` |  
<span id="classdronecode__sdk_1_1_calibration_1a425b76c213bb478762a375d3aef4e644a6fa4dbf368cea972db8d9156799d5dbe"></span> `COMMAND_DENIED` |  
<span id="classdronecode__sdk_1_1_calibration_1a425b76c213bb478762a375d3aef4e644a070a0fb40f6c308ab544b227660aadff"></span> `TIMEOUT` |  
<span id="classdronecode__sdk_1_1_calibration_1a425b76c213bb478762a375d3aef4e644a9f935beb31030ad0d4d26126c0f39bf2"></span> `CANCELLED` |  

## Member Function Documentation


### calibrate_gyro_async() {#classdronecode__sdk_1_1_calibration_1aa7ec9bc9ed62fa23d0d370ec2809b44b}
```cpp
void dronecode_sdk::Calibration::calibrate_gyro_async(calibration_callback_t callback)
```


Perform gyro calibration (asynchronous call).


**Parameters**

* [calibration_callback_t](classdronecode__sdk_1_1_calibration.md#classdronecode__sdk_1_1_calibration_1a80de297cc0a8a77d81902cf765aa77a1) **callback** - Function to receive result and progress of calibration.

### calibrate_accelerometer_async() {#classdronecode__sdk_1_1_calibration_1ac82675b0235bc7ed8c0a3259739e0bea}
```cpp
void dronecode_sdk::Calibration::calibrate_accelerometer_async(calibration_callback_t callback)
```


Perform accelerometer calibration (asynchronous call).


**Parameters**

* [calibration_callback_t](classdronecode__sdk_1_1_calibration.md#classdronecode__sdk_1_1_calibration_1a80de297cc0a8a77d81902cf765aa77a1) **callback** - Function to receive result and progress of calibration.

### calibrate_magnetometer_async() {#classdronecode__sdk_1_1_calibration_1ae69b7a5e7308f7f9176152a30ff9049f}
```cpp
void dronecode_sdk::Calibration::calibrate_magnetometer_async(calibration_callback_t callback)
```


Perform magnetometer calibration (asynchronous call).


**Parameters**

* [calibration_callback_t](classdronecode__sdk_1_1_calibration.md#classdronecode__sdk_1_1_calibration_1a80de297cc0a8a77d81902cf765aa77a1) **callback** - Function to receive result and progress of calibration.

### calibrate_gimbal_accelerometer_async() {#classdronecode__sdk_1_1_calibration_1a1a5fe007db8e548b1305126a94f441af}
```cpp
void dronecode_sdk::Calibration::calibrate_gimbal_accelerometer_async(calibration_callback_t callback)
```


Perform gimbal accelerometer calibration (asynchronous call).


**Parameters**

* [calibration_callback_t](classdronecode__sdk_1_1_calibration.md#classdronecode__sdk_1_1_calibration_1a80de297cc0a8a77d81902cf765aa77a1) **callback** - Function to receive result and progress of calibration.

### operator=() {#classdronecode__sdk_1_1_calibration_1a347cb2bc05828fc1cbb40bebfc50cabc}
```cpp
const Calibration& dronecode_sdk::Calibration::operator=(const Calibration &)=delete
```


Equality operator (object is not copyable).


**Parameters**

* const [Calibration](classdronecode__sdk_1_1_calibration.md)&  - 

**Returns**

&emsp;const [Calibration](classdronecode__sdk_1_1_calibration.md) & - 

### result_str() {#classdronecode__sdk_1_1_calibration_1abdecc0953344ca1f771133a8be571116}
```cpp
static const char* dronecode_sdk::Calibration::result_str(Result result)
```


Returns a human-readable English string for [Calibration::Result](classdronecode__sdk_1_1_calibration.md#classdronecode__sdk_1_1_calibration_1a425b76c213bb478762a375d3aef4e644).


**Parameters**

* [Result](classdronecode__sdk_1_1_calibration.md#classdronecode__sdk_1_1_calibration_1a425b76c213bb478762a375d3aef4e644) **result** - The enum value for which a human readable string is required.

**Returns**

&emsp;const char * - Human readable string for the [Calibration::Result](classdronecode__sdk_1_1_calibration.md#classdronecode__sdk_1_1_calibration_1a425b76c213bb478762a375d3aef4e644).