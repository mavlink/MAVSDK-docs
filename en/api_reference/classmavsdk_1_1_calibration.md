# mavsdk::Calibration Class Reference
`#include: calibration.h`

----


The [Calibration](classmavsdk_1_1_calibration.md) class enables to calibrate sensors of a drone such as gyro, accelerometer, and magnetometer. 


## Data Structures


struct [ProgressData](structmavsdk_1_1_calibration_1_1_progress_data.md)

## Public Types


Type | Description
--- | ---
enum [Result](#classmavsdk_1_1_calibration_1a6e1ce7a3a07eb098edc06821d23a8ec1) | Possible results returned for calibration commands.
std::function< void(const [Result](classmavsdk_1_1_calibration.md#classmavsdk_1_1_calibration_1a6e1ce7a3a07eb098edc06821d23a8ec1) result, const [ProgressData](structmavsdk_1_1_calibration_1_1_progress_data.md))> [calibration_callback_t](#classmavsdk_1_1_calibration_1a709b4faec8a5b9f80407cbb2bf2bdce6) | Callback type for asynchronous calibration call.

## Public Member Functions


Type | Name | Description
---: | --- | ---
&nbsp; | [Calibration](#classmavsdk_1_1_calibration_1ac86c794a9ca1043e21b501218346f2b1) ([System](classmavsdk_1_1_system.md) & system) | Constructor. Creates the plugin for a specific [System](classmavsdk_1_1_system.md).
&nbsp; | [~Calibration](#classmavsdk_1_1_calibration_1a9bfe7b366c142b90b4f35cb3b2dfda2e) () | Destructor (internal use only).
&nbsp; | [Calibration](#classmavsdk_1_1_calibration_1a8665891ac02e50c2017793af665c5f4f) (const [Calibration](classmavsdk_1_1_calibration.md) &)=delete | Copy constructor (object is not copyable).
void | [calibrate_gyro_async](#classmavsdk_1_1_calibration_1a0987ce14551c5144534cc620b8ce5b3d) ([calibration_callback_t](classmavsdk_1_1_calibration.md#classmavsdk_1_1_calibration_1a709b4faec8a5b9f80407cbb2bf2bdce6) callback) | Perform gyro calibration (asynchronous call).
void | [calibrate_accelerometer_async](#classmavsdk_1_1_calibration_1a861628d9e8e769c53119b82c96b37f07) ([calibration_callback_t](classmavsdk_1_1_calibration.md#classmavsdk_1_1_calibration_1a709b4faec8a5b9f80407cbb2bf2bdce6) callback) | Perform accelerometer calibration (asynchronous call).
void | [calibrate_magnetometer_async](#classmavsdk_1_1_calibration_1a4188289bb3222d277b885ccbd9b850d4) ([calibration_callback_t](classmavsdk_1_1_calibration.md#classmavsdk_1_1_calibration_1a709b4faec8a5b9f80407cbb2bf2bdce6) callback) | Perform magnetometer calibration (asynchronous call).
void | [calibrate_gimbal_accelerometer_async](#classmavsdk_1_1_calibration_1aede59780e588cdb8009c479f9138ec0f) ([calibration_callback_t](classmavsdk_1_1_calibration.md#classmavsdk_1_1_calibration_1a709b4faec8a5b9f80407cbb2bf2bdce6) callback) | Perform gimbal accelerometer calibration (asynchronous call).
void | [cancel_calibration](#classmavsdk_1_1_calibration_1a82a6349cde24d7632bce1fd47b26eb57) () | Cancel ongoing calibration.
const [Calibration](classmavsdk_1_1_calibration.md) & | [operator=](#classmavsdk_1_1_calibration_1ada12d974bb516745ea67f94c72abf59b) (const [Calibration](classmavsdk_1_1_calibration.md) &)=delete | Equality operator (object is not copyable).

## Static Public Member Functions


Type | Name | Description
---: | --- | ---
const char * | [result_str](#classmavsdk_1_1_calibration_1a892c5cc79ceb669ec73bcd78e075d66d) ([Result](classmavsdk_1_1_calibration.md#classmavsdk_1_1_calibration_1a6e1ce7a3a07eb098edc06821d23a8ec1) result) | Returns a human-readable English string for [Calibration::Result](classmavsdk_1_1_calibration.md#classmavsdk_1_1_calibration_1a6e1ce7a3a07eb098edc06821d23a8ec1).


## Constructor & Destructor Documentation


### Calibration() {#classmavsdk_1_1_calibration_1ac86c794a9ca1043e21b501218346f2b1}
```cpp
mavsdk::Calibration::Calibration(System &system)
```


Constructor. Creates the plugin for a specific [System](classmavsdk_1_1_system.md).

The plugin is typically created as shown below: 

```cpp
auto calibration = std::make_shared<Calibration>(system);
```

**Parameters**

* [System](classmavsdk_1_1_system.md)& **system** - The specific system associated with this plugin.

### ~Calibration() {#classmavsdk_1_1_calibration_1a9bfe7b366c142b90b4f35cb3b2dfda2e}
```cpp
mavsdk::Calibration::~Calibration()
```


Destructor (internal use only).


### Calibration() {#classmavsdk_1_1_calibration_1a8665891ac02e50c2017793af665c5f4f}
```cpp
mavsdk::Calibration::Calibration(const Calibration &)=delete
```


Copy constructor (object is not copyable).


**Parameters**

* const [Calibration](classmavsdk_1_1_calibration.md)&  - 

## Member Typdef Documentation


### typedef calibration_callback_t {#classmavsdk_1_1_calibration_1a709b4faec8a5b9f80407cbb2bf2bdce6}

```cpp
typedef std::function<void(const Result result, const ProgressData)> mavsdk::Calibration::calibration_callback_t
```


Callback type for asynchronous calibration call.


## Member Enumeration Documentation


### enum Result {#classmavsdk_1_1_calibration_1a6e1ce7a3a07eb098edc06821d23a8ec1}


Possible results returned for calibration commands.


Value | Description
--- | ---
<span id="classmavsdk_1_1_calibration_1a6e1ce7a3a07eb098edc06821d23a8ec1a696b031073e74bf2cb98e5ef201d4aa3"></span> `UNKNOWN` |  
<span id="classmavsdk_1_1_calibration_1a6e1ce7a3a07eb098edc06821d23a8ec1ad0749aaba8b833466dfcbb0428e4f89c"></span> `SUCCESS` |  
<span id="classmavsdk_1_1_calibration_1a6e1ce7a3a07eb098edc06821d23a8ec1aca69f96c768067fbff6c911ca87bccc9"></span> `IN_PROGRESS` |  
<span id="classmavsdk_1_1_calibration_1a6e1ce7a3a07eb098edc06821d23a8ec1a40cb2f2c740ed5a8dec7dc25e0b5aacb"></span> `INSTRUCTION` |  
<span id="classmavsdk_1_1_calibration_1a6e1ce7a3a07eb098edc06821d23a8ec1ab9e14d9b2886bcff408b85aefa780419"></span> `FAILED` |  
<span id="classmavsdk_1_1_calibration_1a6e1ce7a3a07eb098edc06821d23a8ec1afeae72a3a2feec3c92c2a79a30d31186"></span> `NO_SYSTEM` |  
<span id="classmavsdk_1_1_calibration_1a6e1ce7a3a07eb098edc06821d23a8ec1ac77f1f09dab2c0c9980fca7cfae02518"></span> `CONNECTION_ERROR` |  
<span id="classmavsdk_1_1_calibration_1a6e1ce7a3a07eb098edc06821d23a8ec1a802706a9238e2928077f97736854bad4"></span> `BUSY` |  
<span id="classmavsdk_1_1_calibration_1a6e1ce7a3a07eb098edc06821d23a8ec1a6fa4dbf368cea972db8d9156799d5dbe"></span> `COMMAND_DENIED` |  
<span id="classmavsdk_1_1_calibration_1a6e1ce7a3a07eb098edc06821d23a8ec1a070a0fb40f6c308ab544b227660aadff"></span> `TIMEOUT` |  
<span id="classmavsdk_1_1_calibration_1a6e1ce7a3a07eb098edc06821d23a8ec1a9f935beb31030ad0d4d26126c0f39bf2"></span> `CANCELLED` |  

## Member Function Documentation


### calibrate_gyro_async() {#classmavsdk_1_1_calibration_1a0987ce14551c5144534cc620b8ce5b3d}
```cpp
void mavsdk::Calibration::calibrate_gyro_async(calibration_callback_t callback)
```


Perform gyro calibration (asynchronous call).


**Parameters**

* [calibration_callback_t](classmavsdk_1_1_calibration.md#classmavsdk_1_1_calibration_1a709b4faec8a5b9f80407cbb2bf2bdce6) **callback** - Function to receive result and progress of calibration.

### calibrate_accelerometer_async() {#classmavsdk_1_1_calibration_1a861628d9e8e769c53119b82c96b37f07}
```cpp
void mavsdk::Calibration::calibrate_accelerometer_async(calibration_callback_t callback)
```


Perform accelerometer calibration (asynchronous call).


**Parameters**

* [calibration_callback_t](classmavsdk_1_1_calibration.md#classmavsdk_1_1_calibration_1a709b4faec8a5b9f80407cbb2bf2bdce6) **callback** - Function to receive result and progress of calibration.

### calibrate_magnetometer_async() {#classmavsdk_1_1_calibration_1a4188289bb3222d277b885ccbd9b850d4}
```cpp
void mavsdk::Calibration::calibrate_magnetometer_async(calibration_callback_t callback)
```


Perform magnetometer calibration (asynchronous call).


**Parameters**

* [calibration_callback_t](classmavsdk_1_1_calibration.md#classmavsdk_1_1_calibration_1a709b4faec8a5b9f80407cbb2bf2bdce6) **callback** - Function to receive result and progress of calibration.

### calibrate_gimbal_accelerometer_async() {#classmavsdk_1_1_calibration_1aede59780e588cdb8009c479f9138ec0f}
```cpp
void mavsdk::Calibration::calibrate_gimbal_accelerometer_async(calibration_callback_t callback)
```


Perform gimbal accelerometer calibration (asynchronous call).


**Parameters**

* [calibration_callback_t](classmavsdk_1_1_calibration.md#classmavsdk_1_1_calibration_1a709b4faec8a5b9f80407cbb2bf2bdce6) **callback** - Function to receive result and progress of calibration.

### cancel_calibration() {#classmavsdk_1_1_calibration_1a82a6349cde24d7632bce1fd47b26eb57}
```cpp
void mavsdk::Calibration::cancel_calibration()
```


Cancel ongoing calibration.


### operator=() {#classmavsdk_1_1_calibration_1ada12d974bb516745ea67f94c72abf59b}
```cpp
const Calibration& mavsdk::Calibration::operator=(const Calibration &)=delete
```


Equality operator (object is not copyable).


**Parameters**

* const [Calibration](classmavsdk_1_1_calibration.md)&  - 

**Returns**

&emsp;const [Calibration](classmavsdk_1_1_calibration.md) & - 

### result_str() {#classmavsdk_1_1_calibration_1a892c5cc79ceb669ec73bcd78e075d66d}
```cpp
static const char* mavsdk::Calibration::result_str(Result result)
```


Returns a human-readable English string for [Calibration::Result](classmavsdk_1_1_calibration.md#classmavsdk_1_1_calibration_1a6e1ce7a3a07eb098edc06821d23a8ec1).


**Parameters**

* [Result](classmavsdk_1_1_calibration.md#classmavsdk_1_1_calibration_1a6e1ce7a3a07eb098edc06821d23a8ec1) **result** - The enum value for which a human readable string is required.

**Returns**

&emsp;const char * - Human readable string for the [Calibration::Result](classmavsdk_1_1_calibration.md#classmavsdk_1_1_calibration_1a6e1ce7a3a07eb098edc06821d23a8ec1).