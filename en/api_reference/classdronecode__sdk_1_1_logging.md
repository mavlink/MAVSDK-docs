# dronecode_sdk::Logging Class Reference
`#include: logging.h`

----


The [Logging](classdronecode__sdk_1_1_logging.md) class allows log data using logger and log streaming from the vehicle. 


**This feature is not yet implemented**. 


## Public Types


Type | Description
--- | ---
enum [Result](#classdronecode__sdk_1_1_logging_1a32fc0cf9d246861285cdbf57ce1e28a1) | Results for logging requests.
std::function< void([Result](classdronecode__sdk_1_1_logging.md#classdronecode__sdk_1_1_logging_1a32fc0cf9d246861285cdbf57ce1e28a1))> [result_callback_t](#classdronecode__sdk_1_1_logging_1a9aecb40a3b3739903880c023367238ae) | Callback type for logging requests.

## Public Member Functions


Type | Name | Description
---: | --- | ---
&nbsp; | [Logging](#classdronecode__sdk_1_1_logging_1a96e1af50455be75f699d4ff012e329f4) ([System](classdronecode__sdk_1_1_system.md) & system) | Constructor. Creates the plugin for a specific [System](classdronecode__sdk_1_1_system.md).
&nbsp; | [~Logging](#classdronecode__sdk_1_1_logging_1a493c2d8f116598c23be60b5c7a6f7617) () | Destructor (internal use only).
&nbsp; | [Logging](#classdronecode__sdk_1_1_logging_1a67e9b4efc8b0a969ecd7622513ae66f3) (const [Logging](classdronecode__sdk_1_1_logging.md) &)=delete | Copy constructor (object is not copyable).
[Result](classdronecode__sdk_1_1_logging.md#classdronecode__sdk_1_1_logging_1a32fc0cf9d246861285cdbf57ce1e28a1) | [start_logging](#classdronecode__sdk_1_1_logging_1a2da50f1025aa574dd6f018167e83880e) () const | Start logging (synchronous).
[Result](classdronecode__sdk_1_1_logging.md#classdronecode__sdk_1_1_logging_1a32fc0cf9d246861285cdbf57ce1e28a1) | [stop_logging](#classdronecode__sdk_1_1_logging_1af686937343fa35e5db58c06cb3a002d2) () const | Stop logging (synchronous).
void | [start_logging_async](#classdronecode__sdk_1_1_logging_1adc772d3469ebfeb7fadd59f86971bc65) ([result_callback_t](classdronecode__sdk_1_1_logging.md#classdronecode__sdk_1_1_logging_1a9aecb40a3b3739903880c023367238ae) callback) | Start logging (asynchronous).
void | [stop_logging_async](#classdronecode__sdk_1_1_logging_1af483f7246ed474e55df4af8ca0ca72f1) ([result_callback_t](classdronecode__sdk_1_1_logging.md#classdronecode__sdk_1_1_logging_1a9aecb40a3b3739903880c023367238ae) callback) | Stop logging (asynchronous).
const [Logging](classdronecode__sdk_1_1_logging.md) & | [operator=](#classdronecode__sdk_1_1_logging_1a9801dea9b236a4d922edcb78da5d9b15) (const [Logging](classdronecode__sdk_1_1_logging.md) &)=delete | Equality operator (object is not copyable).

## Static Public Member Functions


Type | Name | Description
---: | --- | ---
const char * | [result_str](#classdronecode__sdk_1_1_logging_1a1aec028a376b62ed0bdab140e63fd0ce) ([Result](classdronecode__sdk_1_1_logging.md#classdronecode__sdk_1_1_logging_1a32fc0cf9d246861285cdbf57ce1e28a1) result) | Returns human-readable English string for [Logging::Result](classdronecode__sdk_1_1_logging.md#classdronecode__sdk_1_1_logging_1a32fc0cf9d246861285cdbf57ce1e28a1).


## Constructor & Destructor Documentation


### Logging() {#classdronecode__sdk_1_1_logging_1a96e1af50455be75f699d4ff012e329f4}
```cpp
dronecode_sdk::Logging::Logging(System &system)
```


Constructor. Creates the plugin for a specific [System](classdronecode__sdk_1_1_system.md).

The plugin is typically created as shown below: 

```cpp
auto logging = std::make_shared<Logging>(system);
```

**Parameters**

* [System](classdronecode__sdk_1_1_system.md)& **system** - The specific system associated with this plugin.

### ~Logging() {#classdronecode__sdk_1_1_logging_1a493c2d8f116598c23be60b5c7a6f7617}
```cpp
dronecode_sdk::Logging::~Logging()
```


Destructor (internal use only).


### Logging() {#classdronecode__sdk_1_1_logging_1a67e9b4efc8b0a969ecd7622513ae66f3}
```cpp
dronecode_sdk::Logging::Logging(const Logging &)=delete
```


Copy constructor (object is not copyable).


**Parameters**

* const [Logging](classdronecode__sdk_1_1_logging.md)&  - 

## Member Typdef Documentation


### typedef result_callback_t {#classdronecode__sdk_1_1_logging_1a9aecb40a3b3739903880c023367238ae}

```cpp
typedef std::function<void(Result)> dronecode_sdk::Logging::result_callback_t
```


Callback type for logging requests.


## Member Enumeration Documentation


### enum Result {#classdronecode__sdk_1_1_logging_1a32fc0cf9d246861285cdbf57ce1e28a1}


Results for logging requests.


Value | Description
--- | ---
<span id="classdronecode__sdk_1_1_logging_1a32fc0cf9d246861285cdbf57ce1e28a1ad0749aaba8b833466dfcbb0428e4f89c"></span> `SUCCESS` | Request succeeded. 
<span id="classdronecode__sdk_1_1_logging_1a32fc0cf9d246861285cdbf57ce1e28a1afeae72a3a2feec3c92c2a79a30d31186"></span> `NO_SYSTEM` | No system connected. 
<span id="classdronecode__sdk_1_1_logging_1a32fc0cf9d246861285cdbf57ce1e28a1ac77f1f09dab2c0c9980fca7cfae02518"></span> `CONNECTION_ERROR` | Connection error. 
<span id="classdronecode__sdk_1_1_logging_1a32fc0cf9d246861285cdbf57ce1e28a1a802706a9238e2928077f97736854bad4"></span> `BUSY` | System busy. 
<span id="classdronecode__sdk_1_1_logging_1a32fc0cf9d246861285cdbf57ce1e28a1a6fa4dbf368cea972db8d9156799d5dbe"></span> `COMMAND_DENIED` | Command denied. 
<span id="classdronecode__sdk_1_1_logging_1a32fc0cf9d246861285cdbf57ce1e28a1a070a0fb40f6c308ab544b227660aadff"></span> `TIMEOUT` | Timeout. 
<span id="classdronecode__sdk_1_1_logging_1a32fc0cf9d246861285cdbf57ce1e28a1a696b031073e74bf2cb98e5ef201d4aa3"></span> `UNKNOWN` | Unknown error. 

## Member Function Documentation


### start_logging() {#classdronecode__sdk_1_1_logging_1a2da50f1025aa574dd6f018167e83880e}
```cpp
Result dronecode_sdk::Logging::start_logging() const
```


Start logging (synchronous).

**This feature is not yet implemented**.

**Returns**

&emsp;[Result](classdronecode__sdk_1_1_logging.md#classdronecode__sdk_1_1_logging_1a32fc0cf9d246861285cdbf57ce1e28a1) - Result of request.

### stop_logging() {#classdronecode__sdk_1_1_logging_1af686937343fa35e5db58c06cb3a002d2}
```cpp
Result dronecode_sdk::Logging::stop_logging() const
```


Stop logging (synchronous).

**This feature is not yet implemented**.

**Returns**

&emsp;[Result](classdronecode__sdk_1_1_logging.md#classdronecode__sdk_1_1_logging_1a32fc0cf9d246861285cdbf57ce1e28a1) - Result of request.

### start_logging_async() {#classdronecode__sdk_1_1_logging_1adc772d3469ebfeb7fadd59f86971bc65}
```cpp
void dronecode_sdk::Logging::start_logging_async(result_callback_t callback)
```


Start logging (asynchronous).

**This feature is not yet implemented**.

**Parameters**

* [result_callback_t](classdronecode__sdk_1_1_logging.md#classdronecode__sdk_1_1_logging_1a9aecb40a3b3739903880c023367238ae) **callback** - Callback to get result of request.

### stop_logging_async() {#classdronecode__sdk_1_1_logging_1af483f7246ed474e55df4af8ca0ca72f1}
```cpp
void dronecode_sdk::Logging::stop_logging_async(result_callback_t callback)
```


Stop logging (asynchronous).

**This feature is not yet implemented**.

**Parameters**

* [result_callback_t](classdronecode__sdk_1_1_logging.md#classdronecode__sdk_1_1_logging_1a9aecb40a3b3739903880c023367238ae) **callback** - Callback to get result of request.

### operator=() {#classdronecode__sdk_1_1_logging_1a9801dea9b236a4d922edcb78da5d9b15}
```cpp
const Logging& dronecode_sdk::Logging::operator=(const Logging &)=delete
```


Equality operator (object is not copyable).


**Parameters**

* const [Logging](classdronecode__sdk_1_1_logging.md)&  - 

**Returns**

&emsp;const [Logging](classdronecode__sdk_1_1_logging.md) & - 

### result_str() {#classdronecode__sdk_1_1_logging_1a1aec028a376b62ed0bdab140e63fd0ce}
```cpp
static const char* dronecode_sdk::Logging::result_str(Result result)
```


Returns human-readable English string for [Logging::Result](classdronecode__sdk_1_1_logging.md#classdronecode__sdk_1_1_logging_1a32fc0cf9d246861285cdbf57ce1e28a1).


**Parameters**

* [Result](classdronecode__sdk_1_1_logging.md#classdronecode__sdk_1_1_logging_1a32fc0cf9d246861285cdbf57ce1e28a1) **result** - Enum for which string is required.

**Returns**

&emsp;const char * - result Human-readable string for [Logging::Result](classdronecode__sdk_1_1_logging.md#classdronecode__sdk_1_1_logging_1a32fc0cf9d246861285cdbf57ce1e28a1).