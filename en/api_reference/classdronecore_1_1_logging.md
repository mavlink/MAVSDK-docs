# dronecore::Logging Class Reference
`#include: logging.h`

----


The [Logging](classdronecore_1_1_logging.md) class allows log data using logger and log streaming from the vehicle. 


**This feature is not yet implemented**. 


## Public Types


Type | Description
--- | ---
enum [Result](#classdronecore_1_1_logging_1ab11e242369717d9510de1ab93bfad086) | Results for logging requests.
std::function< void([Result](classdronecore_1_1_logging.md#classdronecore_1_1_logging_1ab11e242369717d9510de1ab93bfad086))> [result_callback_t](#classdronecore_1_1_logging_1a16c5eb728571a59a552ca6706166b427) | Callback type for logging requests.

## Public Member Functions


Type | Name | Description
---: | --- | ---
| [Logging](#classdronecore_1_1_logging_1ac543ff1d6a0e9980eeb113d39fff39bf) (LoggingImpl *impl) | Constructor (internal use only).
| [~Logging](#classdronecore_1_1_logging_1a49e75d77f900ba5ef59a960ae9b8dc55) () | Destructor (internal use only).
| [Logging](#classdronecore_1_1_logging_1a62a17eb90e3ec9253f1b40e94d3c1fd7) (const Logging &)=delete | Copy constructor (object is not copyable).
[Result](classdronecore_1_1_logging.md#classdronecore_1_1_logging_1ab11e242369717d9510de1ab93bfad086) | [start_logging](#classdronecore_1_1_logging_1a4684d8226742b575fce423c9ce758fc0) () const | Start logging (synchronous).
[Result](classdronecore_1_1_logging.md#classdronecore_1_1_logging_1ab11e242369717d9510de1ab93bfad086) | [stop_logging](#classdronecore_1_1_logging_1a258affbec05c9c2ca229a3e12e5c8a1b) () const | Stop logging (synchronous).
void | [start_logging_async](#classdronecore_1_1_logging_1a5ee9b37891aa66fd98f17fbf871c383b) (result_callback_t callback) | Start logging (asynchronous).
void | [stop_logging_async](#classdronecore_1_1_logging_1a643b9a80157464d6ac94c8c2987099a0) (result_callback_t callback) | Stop logging (asynchronous).
const [Logging](classdronecore_1_1_logging.md) & | [operator=](#classdronecore_1_1_logging_1a43d8bd32d59a2b5e728e221d7bba4aef) (const Logging &)=delete | Equality operator (object is not copyable).

## Static Public Member Functions


Type | Name | Description
---: | --- | ---
const char * | [result_str](#classdronecore_1_1_logging_1adc5a7560f1a27996fc05f2b761f0b177) (Result result) | Returns human-readable English string for [Logging::Result](classdronecore_1_1_logging.md#classdronecore_1_1_logging_1ab11e242369717d9510de1ab93bfad086).


## Constructor & Destructor Documentation


### Logging() {#classdronecore_1_1_logging_1ac543ff1d6a0e9980eeb113d39fff39bf}
```cpp
dronecore::Logging::Logging(LoggingImpl *impl)
```


Constructor (internal use only).


**Parameters**

* LoggingImpl * **impl** - 

### ~Logging() {#classdronecore_1_1_logging_1a49e75d77f900ba5ef59a960ae9b8dc55}
```cpp
dronecore::Logging::~Logging()
```


Destructor (internal use only).


### Logging() {#classdronecore_1_1_logging_1a62a17eb90e3ec9253f1b40e94d3c1fd7}
```cpp
dronecore::Logging::Logging(const Logging &)=delete
```


Copy constructor (object is not copyable).


**Parameters**

* const [Logging](classdronecore_1_1_logging.md) & - 

## Member Typdef Documentation


### typedef result_callback_t {#classdronecore_1_1_logging_1a16c5eb728571a59a552ca6706166b427}

```cpp
typedef std::function<void(Result)> dronecore::Logging::result_callback_t
```


Callback type for logging requests.


## Member Enumeration Documentation


### enum Result {#classdronecore_1_1_logging_1ab11e242369717d9510de1ab93bfad086}


Results for logging requests.


 Value | Description
--- | ---
<span id="classdronecore_1_1_logging_1ab11e242369717d9510de1ab93bfad086ad0749aaba8b833466dfcbb0428e4f89c"></span> `SUCCESS` | Request succeeded. 
<span id="classdronecore_1_1_logging_1ab11e242369717d9510de1ab93bfad086a23514014e50da2b2583cae24ab1ecd88"></span> `NO_DEVICE` | No device connected. 
<span id="classdronecore_1_1_logging_1ab11e242369717d9510de1ab93bfad086ac77f1f09dab2c0c9980fca7cfae02518"></span> `CONNECTION_ERROR` | Connection error. 
<span id="classdronecore_1_1_logging_1ab11e242369717d9510de1ab93bfad086a802706a9238e2928077f97736854bad4"></span> `BUSY` | Device busy. 
<span id="classdronecore_1_1_logging_1ab11e242369717d9510de1ab93bfad086a6fa4dbf368cea972db8d9156799d5dbe"></span> `COMMAND_DENIED` | Command denied. 
<span id="classdronecore_1_1_logging_1ab11e242369717d9510de1ab93bfad086a070a0fb40f6c308ab544b227660aadff"></span> `TIMEOUT` | Timeout. 
<span id="classdronecore_1_1_logging_1ab11e242369717d9510de1ab93bfad086a696b031073e74bf2cb98e5ef201d4aa3"></span> `UNKNOWN` | Unknown error. 

## Member Function Documentation


### start_logging() {#classdronecore_1_1_logging_1a4684d8226742b575fce423c9ce758fc0}
```cpp
Result dronecore::Logging::start_logging() const
```


Start logging (synchronous).

**This feature is not yet implemented**.

**Returns**

&emsp;[Result](classdronecore_1_1_logging.md#classdronecore_1_1_logging_1ab11e242369717d9510de1ab93bfad086) - Result of request.

### stop_logging() {#classdronecore_1_1_logging_1a258affbec05c9c2ca229a3e12e5c8a1b}
```cpp
Result dronecore::Logging::stop_logging() const
```


Stop logging (synchronous).

**This feature is not yet implemented**.

**Returns**

&emsp;[Result](classdronecore_1_1_logging.md#classdronecore_1_1_logging_1ab11e242369717d9510de1ab93bfad086) - Result of request.

### start_logging_async() {#classdronecore_1_1_logging_1a5ee9b37891aa66fd98f17fbf871c383b}
```cpp
void dronecore::Logging::start_logging_async(result_callback_t callback)
```


Start logging (asynchronous).

**This feature is not yet implemented**.

**Parameters**

* [result_callback_t](classdronecore_1_1_logging.md#classdronecore_1_1_logging_1a16c5eb728571a59a552ca6706166b427) **callback** - Callback to get result of request.

### stop_logging_async() {#classdronecore_1_1_logging_1a643b9a80157464d6ac94c8c2987099a0}
```cpp
void dronecore::Logging::stop_logging_async(result_callback_t callback)
```


Stop logging (asynchronous).

**This feature is not yet implemented**.

**Parameters**

* [result_callback_t](classdronecore_1_1_logging.md#classdronecore_1_1_logging_1a16c5eb728571a59a552ca6706166b427) **callback** - Callback to get result of request.

### operator=() {#classdronecore_1_1_logging_1a43d8bd32d59a2b5e728e221d7bba4aef}
```cpp
const Logging& dronecore::Logging::operator=(const Logging &)=delete
```


Equality operator (object is not copyable).


**Parameters**

* const [Logging](classdronecore_1_1_logging.md) & - 

**Returns**

&emsp;const [Logging](classdronecore_1_1_logging.md) & - 

### result_str() {#classdronecore_1_1_logging_1adc5a7560f1a27996fc05f2b761f0b177}
```cpp
static const char* dronecore::Logging::result_str(Result result)
```


Returns human-readable English string for [Logging::Result](classdronecore_1_1_logging.md#classdronecore_1_1_logging_1ab11e242369717d9510de1ab93bfad086).


**Parameters**

* [Result](classdronecore_1_1_logging.md#classdronecore_1_1_logging_1ab11e242369717d9510de1ab93bfad086) **result** - Enum for which string is required.

**Returns**

&emsp;const char * - result Human-readable string for [Logging::Result](classdronecore_1_1_logging.md#classdronecore_1_1_logging_1ab11e242369717d9510de1ab93bfad086).