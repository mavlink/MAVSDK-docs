# mavsdk::LogFiles Class Reference
`#include: log_files.h`

----


The [LogFiles](classmavsdk_1_1_log_files.md) class allows to download log files from the vehicle after a flight is completed. 


## Data Structures


struct [Entry](structmavsdk_1_1_log_files_1_1_entry.md)

## Public Types


Type | Description
--- | ---
enum [Result](#classmavsdk_1_1_log_files_1a43e5425f17cd8a6830ff6fd952a724cd) | Results for log file requests.
std::function< void([Result](classmavsdk_1_1_log_files.md#classmavsdk_1_1_log_files_1a43e5425f17cd8a6830ff6fd952a724cd), std::vector< [Entry](structmavsdk_1_1_log_files_1_1_entry.md) >)> [get_entries_callback_t](#classmavsdk_1_1_log_files_1a2bccfb05283a6bd34288e3a614ed8fd4) | Callback type for logging requests.
std::function< void([Result](classmavsdk_1_1_log_files.md#classmavsdk_1_1_log_files_1a43e5425f17cd8a6830ff6fd952a724cd) result, float progress)> [download_log_file_callback_t](#classmavsdk_1_1_log_files_1ab0e38d46309bf99ba3d35acb93b0b096) | Callback type for logging requests.

## Public Member Functions


Type | Name | Description
---: | --- | ---
&nbsp; | [LogFiles](#classmavsdk_1_1_log_files_1a4a487863501b7ef30db5179bebc45a3a) ([System](classmavsdk_1_1_system.md) & system) | Constructor. Creates the plugin for a specific [System](classmavsdk_1_1_system.md).
&nbsp; | [~LogFiles](#classmavsdk_1_1_log_files_1a051ae59e72ddb9be39f128592604ded6) () | Destructor (internal use only).
&nbsp; | [LogFiles](#classmavsdk_1_1_log_files_1aa7edd3ce17708f6be95a1c9d4acf1757) (const [LogFiles](classmavsdk_1_1_log_files.md) &)=delete | Copy constructor (object is not copyable).
std::pair< [Result](classmavsdk_1_1_log_files.md#classmavsdk_1_1_log_files_1a43e5425f17cd8a6830ff6fd952a724cd), std::vector< [Entry](structmavsdk_1_1_log_files_1_1_entry.md) > > | [get_entries](#classmavsdk_1_1_log_files_1a5d97060616682275a0e559f50db4334f) () | Get list of log files (synchronous).
void | [get_entries_async](#classmavsdk_1_1_log_files_1a26572d7b1e01f9c698283744ac78d004) ([get_entries_callback_t](classmavsdk_1_1_log_files.md#classmavsdk_1_1_log_files_1a2bccfb05283a6bd34288e3a614ed8fd4) callback) | Get list of log files (asynchronous).
[Result](classmavsdk_1_1_log_files.md#classmavsdk_1_1_log_files_1a43e5425f17cd8a6830ff6fd952a724cd) | [download_log_file](#classmavsdk_1_1_log_files_1a488856ade4330866251091b26642bf00) (unsigned id, const std::string & file_path) | Download log file (synchronous).
void | [download_log_file_async](#classmavsdk_1_1_log_files_1a06924885b20e46ce581f86e369b83c0d) (unsigned id, const std::string & file_path, [download_log_file_callback_t](classmavsdk_1_1_log_files.md#classmavsdk_1_1_log_files_1ab0e38d46309bf99ba3d35acb93b0b096) callback) | Download log file (asynchronous).
const [LogFiles](classmavsdk_1_1_log_files.md) & | [operator=](#classmavsdk_1_1_log_files_1a2ba9f188f7644a647f5dcdadb034e300) (const [LogFiles](classmavsdk_1_1_log_files.md) &)=delete | Equality operator (object is not copyable).

## Static Public Member Functions


Type | Name | Description
---: | --- | ---
const char * | [result_str](#classmavsdk_1_1_log_files_1a29525caeb008a8171739e994515ef53d) ([Result](classmavsdk_1_1_log_files.md#classmavsdk_1_1_log_files_1a43e5425f17cd8a6830ff6fd952a724cd) result) | Returns human-readable English string for [LogFiles::Result](classmavsdk_1_1_log_files.md#classmavsdk_1_1_log_files_1a43e5425f17cd8a6830ff6fd952a724cd).


## Constructor & Destructor Documentation


### LogFiles() {#classmavsdk_1_1_log_files_1a4a487863501b7ef30db5179bebc45a3a}
```cpp
mavsdk::LogFiles::LogFiles(System &system)
```


Constructor. Creates the plugin for a specific [System](classmavsdk_1_1_system.md).

The plugin is typically created as shown below: 

```cpp
auto log_files = std::make_shared<LogFiles>(system);
```

**Parameters**

* [System](classmavsdk_1_1_system.md)& **system** - The specific system associated with this plugin.

### ~LogFiles() {#classmavsdk_1_1_log_files_1a051ae59e72ddb9be39f128592604ded6}
```cpp
mavsdk::LogFiles::~LogFiles()
```


Destructor (internal use only).


### LogFiles() {#classmavsdk_1_1_log_files_1aa7edd3ce17708f6be95a1c9d4acf1757}
```cpp
mavsdk::LogFiles::LogFiles(const LogFiles &)=delete
```


Copy constructor (object is not copyable).


**Parameters**

* const [LogFiles](classmavsdk_1_1_log_files.md)&  - 

## Member Typdef Documentation


### typedef get_entries_callback_t {#classmavsdk_1_1_log_files_1a2bccfb05283a6bd34288e3a614ed8fd4}

```cpp
typedef std::function<void(Result, std::vector<Entry>)> mavsdk::LogFiles::get_entries_callback_t
```


Callback type for logging requests.


### typedef download_log_file_callback_t {#classmavsdk_1_1_log_files_1ab0e38d46309bf99ba3d35acb93b0b096}

```cpp
typedef std::function<void(Result result, float progress)> mavsdk::LogFiles::download_log_file_callback_t
```


Callback type for logging requests.


## Member Enumeration Documentation


### enum Result {#classmavsdk_1_1_log_files_1a43e5425f17cd8a6830ff6fd952a724cd}


Results for log file requests.


Value | Description
--- | ---
<span id="classmavsdk_1_1_log_files_1a43e5425f17cd8a6830ff6fd952a724cdad0749aaba8b833466dfcbb0428e4f89c"></span> `SUCCESS` | Request succeeded. 
<span id="classmavsdk_1_1_log_files_1a43e5425f17cd8a6830ff6fd952a724cdac2a27e3817de51257fae9f1251409316"></span> `NO_LOGFILES` | No logfiles found. 
<span id="classmavsdk_1_1_log_files_1a43e5425f17cd8a6830ff6fd952a724cda032a7a92e5df105629ad882f7d12532f"></span> `TOO_MANY_RETRIES` | Too many retries. 
<span id="classmavsdk_1_1_log_files_1a43e5425f17cd8a6830ff6fd952a724cdaee88634543eb5c2b123bab1abd32c497"></span> `PROGRESS` | Progress update. 
<span id="classmavsdk_1_1_log_files_1a43e5425f17cd8a6830ff6fd952a724cda696b031073e74bf2cb98e5ef201d4aa3"></span> `UNKNOWN` | Unknown error. 

## Member Function Documentation


### get_entries() {#classmavsdk_1_1_log_files_1a5d97060616682275a0e559f50db4334f}
```cpp
std::pair<Result, std::vector<Entry> > mavsdk::LogFiles::get_entries()
```


Get list of log files (synchronous).


**Returns**

&emsp;std::pair< [Result](classmavsdk_1_1_log_files.md#classmavsdk_1_1_log_files_1a43e5425f17cd8a6830ff6fd952a724cd), std::vector< [Entry](structmavsdk_1_1_log_files_1_1_entry.md) > > - Pair of result and list of entries.

### get_entries_async() {#classmavsdk_1_1_log_files_1a26572d7b1e01f9c698283744ac78d004}
```cpp
void mavsdk::LogFiles::get_entries_async(get_entries_callback_t callback)
```


Get list of log files (asynchronous).


**Parameters**

* [get_entries_callback_t](classmavsdk_1_1_log_files.md#classmavsdk_1_1_log_files_1a2bccfb05283a6bd34288e3a614ed8fd4) **callback** - Callback to get result from.

### download_log_file() {#classmavsdk_1_1_log_files_1a488856ade4330866251091b26642bf00}
```cpp
Result mavsdk::LogFiles::download_log_file(unsigned id, const std::string &file_path)
```


Download log file (synchronous).

> **Note** The synchronous method does only report progress through console logs.

**Parameters**

* unsigned **id** - [Entry](structmavsdk_1_1_log_files_1_1_entry.md) id of log file to download.
* const std::string& **file_path** - File path where to download file to.

**Returns**

&emsp;[Result](classmavsdk_1_1_log_files.md#classmavsdk_1_1_log_files_1a43e5425f17cd8a6830ff6fd952a724cd) - Result of request

### download_log_file_async() {#classmavsdk_1_1_log_files_1a06924885b20e46ce581f86e369b83c0d}
```cpp
void mavsdk::LogFiles::download_log_file_async(unsigned id, const std::string &file_path, download_log_file_callback_t callback)
```


Download log file (asynchronous).


**Parameters**

* unsigned **id** - [Entry](structmavsdk_1_1_log_files_1_1_entry.md) id of log file to download.
* const std::string& **file_path** - File path where to download file to.
* [download_log_file_callback_t](classmavsdk_1_1_log_files.md#classmavsdk_1_1_log_files_1ab0e38d46309bf99ba3d35acb93b0b096) **callback** - Callback to get result and progress.

### operator=() {#classmavsdk_1_1_log_files_1a2ba9f188f7644a647f5dcdadb034e300}
```cpp
const LogFiles& mavsdk::LogFiles::operator=(const LogFiles &)=delete
```


Equality operator (object is not copyable).


**Parameters**

* const [LogFiles](classmavsdk_1_1_log_files.md)&  - 

**Returns**

&emsp;const [LogFiles](classmavsdk_1_1_log_files.md) & - 

### result_str() {#classmavsdk_1_1_log_files_1a29525caeb008a8171739e994515ef53d}
```cpp
static const char* mavsdk::LogFiles::result_str(Result result)
```


Returns human-readable English string for [LogFiles::Result](classmavsdk_1_1_log_files.md#classmavsdk_1_1_log_files_1a43e5425f17cd8a6830ff6fd952a724cd).


**Parameters**

* [Result](classmavsdk_1_1_log_files.md#classmavsdk_1_1_log_files_1a43e5425f17cd8a6830ff6fd952a724cd) **result** - Enum for which string is required.

**Returns**

&emsp;const char * - result Human-readable string for [LogFiles::Result](classmavsdk_1_1_log_files.md#classmavsdk_1_1_log_files_1a43e5425f17cd8a6830ff6fd952a724cd).