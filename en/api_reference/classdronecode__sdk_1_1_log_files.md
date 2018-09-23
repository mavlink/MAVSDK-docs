# dronecode_sdk::LogFiles Class Reference
`#include: log_files.h`

----


The [LogFiles](classdronecode__sdk_1_1_log_files.md) class allows to download log files from the vehicle after a flight is completed. 


## Data Structures


struct [Entry](structdronecode__sdk_1_1_log_files_1_1_entry.md)

## Public Types


Type | Description
--- | ---
enum [Result](#classdronecode__sdk_1_1_log_files_1ab026a334b2b2f8f212d909c1adc6970c) | Results for log file requests.
std::function< void([Result](classdronecode__sdk_1_1_log_files.md#classdronecode__sdk_1_1_log_files_1ab026a334b2b2f8f212d909c1adc6970c), std::vector< [Entry](structdronecode__sdk_1_1_log_files_1_1_entry.md) >)> [get_entries_callback_t](#classdronecode__sdk_1_1_log_files_1aa73fc81925042eae353d2d155d97d761) | Callback type for logging requests.
std::function< void([Result](classdronecode__sdk_1_1_log_files.md#classdronecode__sdk_1_1_log_files_1ab026a334b2b2f8f212d909c1adc6970c) result, float progress)> [download_log_file_callback_t](#classdronecode__sdk_1_1_log_files_1a2b14e2cc0832bb8a379c487f40e9c3e1) | Callback type for logging requests.

## Public Member Functions


Type | Name | Description
---: | --- | ---
&nbsp; | [LogFiles](#classdronecode__sdk_1_1_log_files_1a1a77e4f16e452668423a1cc2fabed952) ([System](classdronecode__sdk_1_1_system.md) & system) | Constructor. Creates the plugin for a specific [System](classdronecode__sdk_1_1_system.md).
&nbsp; | [~LogFiles](#classdronecode__sdk_1_1_log_files_1a45cb31678e5d1d08a93e9188c76ab5ef) () | Destructor (internal use only).
&nbsp; | [LogFiles](#classdronecode__sdk_1_1_log_files_1afb55f43eb066026d47155f0c263fc2a4) (const [LogFiles](classdronecode__sdk_1_1_log_files.md) &)=delete | Copy constructor (object is not copyable).
std::pair< [Result](classdronecode__sdk_1_1_log_files.md#classdronecode__sdk_1_1_log_files_1ab026a334b2b2f8f212d909c1adc6970c), std::vector< [Entry](structdronecode__sdk_1_1_log_files_1_1_entry.md) > > | [get_entries](#classdronecode__sdk_1_1_log_files_1a7a13a6c5deea8df95366a7b011e43af9) () | Get list of log files (synchronous).
void | [get_entries_async](#classdronecode__sdk_1_1_log_files_1a46d8f4b90f87b771a24db1f82c6dccc2) ([get_entries_callback_t](classdronecode__sdk_1_1_log_files.md#classdronecode__sdk_1_1_log_files_1aa73fc81925042eae353d2d155d97d761) callback) | Get list of log files (asynchronous).
[Result](classdronecode__sdk_1_1_log_files.md#classdronecode__sdk_1_1_log_files_1ab026a334b2b2f8f212d909c1adc6970c) | [download_log_file](#classdronecode__sdk_1_1_log_files_1affe79c274a3531adb4a2469500953b7f) (unsigned id, const std::string & file_path) | Download log file (synchronous).
void | [download_log_file_async](#classdronecode__sdk_1_1_log_files_1a079a76df72ac7d65e580e53cc799b084) (unsigned id, const std::string & file_path, [download_log_file_callback_t](classdronecode__sdk_1_1_log_files.md#classdronecode__sdk_1_1_log_files_1a2b14e2cc0832bb8a379c487f40e9c3e1) callback) | Download log file (asynchronous).
const [LogFiles](classdronecode__sdk_1_1_log_files.md) & | [operator=](#classdronecode__sdk_1_1_log_files_1acd67357a9d48c3125f9fdcdf7733470d) (const [LogFiles](classdronecode__sdk_1_1_log_files.md) &)=delete | Equality operator (object is not copyable).

## Static Public Member Functions


Type | Name | Description
---: | --- | ---
const char * | [result_str](#classdronecode__sdk_1_1_log_files_1aeeeddf66507fa1efa6b6cc2e003e3bb9) ([Result](classdronecode__sdk_1_1_log_files.md#classdronecode__sdk_1_1_log_files_1ab026a334b2b2f8f212d909c1adc6970c) result) | Returns human-readable English string for [LogFiles::Result](classdronecode__sdk_1_1_log_files.md#classdronecode__sdk_1_1_log_files_1ab026a334b2b2f8f212d909c1adc6970c).


## Constructor & Destructor Documentation


### LogFiles() {#classdronecode__sdk_1_1_log_files_1a1a77e4f16e452668423a1cc2fabed952}
```cpp
dronecode_sdk::LogFiles::LogFiles(System &system)
```


Constructor. Creates the plugin for a specific [System](classdronecode__sdk_1_1_system.md).

The plugin is typically created as shown below: 

```cpp
auto log_files = std::make_shared<LogFiles>(system);
```

**Parameters**

* [System](classdronecode__sdk_1_1_system.md)& **system** - The specific system associated with this plugin.

### ~LogFiles() {#classdronecode__sdk_1_1_log_files_1a45cb31678e5d1d08a93e9188c76ab5ef}
```cpp
dronecode_sdk::LogFiles::~LogFiles()
```


Destructor (internal use only).


### LogFiles() {#classdronecode__sdk_1_1_log_files_1afb55f43eb066026d47155f0c263fc2a4}
```cpp
dronecode_sdk::LogFiles::LogFiles(const LogFiles &)=delete
```


Copy constructor (object is not copyable).


**Parameters**

* const [LogFiles](classdronecode__sdk_1_1_log_files.md)&  - 

## Member Typdef Documentation


### typedef get_entries_callback_t {#classdronecode__sdk_1_1_log_files_1aa73fc81925042eae353d2d155d97d761}

```cpp
typedef std::function<void(Result, std::vector<Entry>)> dronecode_sdk::LogFiles::get_entries_callback_t
```


Callback type for logging requests.


### typedef download_log_file_callback_t {#classdronecode__sdk_1_1_log_files_1a2b14e2cc0832bb8a379c487f40e9c3e1}

```cpp
typedef std::function<void(Result result, float progress)> dronecode_sdk::LogFiles::download_log_file_callback_t
```


Callback type for logging requests.


## Member Enumeration Documentation


### enum Result {#classdronecode__sdk_1_1_log_files_1ab026a334b2b2f8f212d909c1adc6970c}


Results for log file requests.


Value | Description
--- | ---
<span id="classdronecode__sdk_1_1_log_files_1ab026a334b2b2f8f212d909c1adc6970cad0749aaba8b833466dfcbb0428e4f89c"></span> `SUCCESS` | Request succeeded. 
<span id="classdronecode__sdk_1_1_log_files_1ab026a334b2b2f8f212d909c1adc6970cac2a27e3817de51257fae9f1251409316"></span> `NO_LOGFILES` | No logfiles found. 
<span id="classdronecode__sdk_1_1_log_files_1ab026a334b2b2f8f212d909c1adc6970ca032a7a92e5df105629ad882f7d12532f"></span> `TOO_MANY_RETRIES` | Too many retries. 
<span id="classdronecode__sdk_1_1_log_files_1ab026a334b2b2f8f212d909c1adc6970caee88634543eb5c2b123bab1abd32c497"></span> `PROGRESS` | Progress update. 
<span id="classdronecode__sdk_1_1_log_files_1ab026a334b2b2f8f212d909c1adc6970ca696b031073e74bf2cb98e5ef201d4aa3"></span> `UNKNOWN` | Unknown error. 

## Member Function Documentation


### get_entries() {#classdronecode__sdk_1_1_log_files_1a7a13a6c5deea8df95366a7b011e43af9}
```cpp
std::pair<Result, std::vector<Entry> > dronecode_sdk::LogFiles::get_entries()
```


Get list of log files (synchronous).


**Returns**

&emsp;std::pair< [Result](classdronecode__sdk_1_1_log_files.md#classdronecode__sdk_1_1_log_files_1ab026a334b2b2f8f212d909c1adc6970c), std::vector< [Entry](structdronecode__sdk_1_1_log_files_1_1_entry.md) > > - Pair of result and list of entries.

### get_entries_async() {#classdronecode__sdk_1_1_log_files_1a46d8f4b90f87b771a24db1f82c6dccc2}
```cpp
void dronecode_sdk::LogFiles::get_entries_async(get_entries_callback_t callback)
```


Get list of log files (asynchronous).


**Parameters**

* [get_entries_callback_t](classdronecode__sdk_1_1_log_files.md#classdronecode__sdk_1_1_log_files_1aa73fc81925042eae353d2d155d97d761) **callback** - Callback to get result from.

### download_log_file() {#classdronecode__sdk_1_1_log_files_1affe79c274a3531adb4a2469500953b7f}
```cpp
Result dronecode_sdk::LogFiles::download_log_file(unsigned id, const std::string &file_path)
```


Download log file (synchronous).

> **Note** The synchronous method does only report progress through console logs.

**Parameters**

* unsigned **id** - [Entry](structdronecode__sdk_1_1_log_files_1_1_entry.md) id of log file to download.
* const std::string& **file_path** - File path where to download file to.

**Returns**

&emsp;[Result](classdronecode__sdk_1_1_log_files.md#classdronecode__sdk_1_1_log_files_1ab026a334b2b2f8f212d909c1adc6970c) - Result of request

### download_log_file_async() {#classdronecode__sdk_1_1_log_files_1a079a76df72ac7d65e580e53cc799b084}
```cpp
void dronecode_sdk::LogFiles::download_log_file_async(unsigned id, const std::string &file_path, download_log_file_callback_t callback)
```


Download log file (asynchronous).


**Parameters**

* unsigned **id** - [Entry](structdronecode__sdk_1_1_log_files_1_1_entry.md) id of log file to download.
* const std::string& **file_path** - File path where to download file to.
* [download_log_file_callback_t](classdronecode__sdk_1_1_log_files.md#classdronecode__sdk_1_1_log_files_1a2b14e2cc0832bb8a379c487f40e9c3e1) **callback** - Callback to get result and progress.

### operator=() {#classdronecode__sdk_1_1_log_files_1acd67357a9d48c3125f9fdcdf7733470d}
```cpp
const LogFiles& dronecode_sdk::LogFiles::operator=(const LogFiles &)=delete
```


Equality operator (object is not copyable).


**Parameters**

* const [LogFiles](classdronecode__sdk_1_1_log_files.md)&  - 

**Returns**

&emsp;const [LogFiles](classdronecode__sdk_1_1_log_files.md) & - 

### result_str() {#classdronecode__sdk_1_1_log_files_1aeeeddf66507fa1efa6b6cc2e003e3bb9}
```cpp
static const char* dronecode_sdk::LogFiles::result_str(Result result)
```


Returns human-readable English string for [LogFiles::Result](classdronecode__sdk_1_1_log_files.md#classdronecode__sdk_1_1_log_files_1ab026a334b2b2f8f212d909c1adc6970c).


**Parameters**

* [Result](classdronecode__sdk_1_1_log_files.md#classdronecode__sdk_1_1_log_files_1ab026a334b2b2f8f212d909c1adc6970c) **result** - Enum for which string is required.

**Returns**

&emsp;const char * - result Human-readable string for [LogFiles::Result](classdronecode__sdk_1_1_log_files.md#classdronecode__sdk_1_1_log_files_1ab026a334b2b2f8f212d909c1adc6970c).