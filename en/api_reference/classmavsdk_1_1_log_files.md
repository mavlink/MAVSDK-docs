# mavsdk::LogFiles Class Reference
`#include: log_files.h`

----


Allow to download log files from the vehicle after a flight is complete. For log streaming during flight check the logging plugin. 


## Data Structures


struct [Entry](structmavsdk_1_1_log_files_1_1_entry.md)

struct [ProgressData](structmavsdk_1_1_log_files_1_1_progress_data.md)

## Public Types


Type | Description
--- | ---
enum [Result](#classmavsdk_1_1_log_files_1a43e5425f17cd8a6830ff6fd952a724cd) | Possible results returned for calibration commands.
std::function< void([Result](classmavsdk_1_1_log_files.md#classmavsdk_1_1_log_files_1a43e5425f17cd8a6830ff6fd952a724cd))> [ResultCallback](#classmavsdk_1_1_log_files_1a64cd003ea9110b4a11eb08753a360a59) | Callback type for asynchronous [LogFiles](classmavsdk_1_1_log_files.md) calls.
std::function< void([Result](classmavsdk_1_1_log_files.md#classmavsdk_1_1_log_files_1a43e5425f17cd8a6830ff6fd952a724cd), std::vector< [Entry](structmavsdk_1_1_log_files_1_1_entry.md) >)> [GetEntriesCallback](#classmavsdk_1_1_log_files_1a0bb101777daba9e87cb33baf55389403) | Callback type for get_entries_async.
std::function< void([LogFiles::Result](classmavsdk_1_1_log_files.md#classmavsdk_1_1_log_files_1a43e5425f17cd8a6830ff6fd952a724cd), [ProgressData](structmavsdk_1_1_log_files_1_1_progress_data.md))> [DownloadLogFileCallback](#classmavsdk_1_1_log_files_1a0a02c3e91339ac34fdb637603691cfa3) | Callback type for download_log_file_async.

## Public Member Functions


Type | Name | Description
---: | --- | ---
&nbsp; | [LogFiles](#classmavsdk_1_1_log_files_1a4a487863501b7ef30db5179bebc45a3a) ([System](classmavsdk_1_1_system.md) & system) | Constructor. Creates the plugin for a specific [System](classmavsdk_1_1_system.md).
&nbsp; | [~LogFiles](#classmavsdk_1_1_log_files_1a051ae59e72ddb9be39f128592604ded6) () | Destructor (internal use only).
&nbsp; | [LogFiles](#classmavsdk_1_1_log_files_1aa7edd3ce17708f6be95a1c9d4acf1757) (const [LogFiles](classmavsdk_1_1_log_files.md) &)=delete | Copy constructor (object is not copyable).
void | [get_entries_async](#classmavsdk_1_1_log_files_1a6a922097850fb43fbb9d3348fe0b3bb7) (const [GetEntriesCallback](classmavsdk_1_1_log_files.md#classmavsdk_1_1_log_files_1a0bb101777daba9e87cb33baf55389403) callback) | Get List of log files.
std::pair< [Result](classmavsdk_1_1_log_files.md#classmavsdk_1_1_log_files_1a43e5425f17cd8a6830ff6fd952a724cd), std::vector< [LogFiles::Entry](structmavsdk_1_1_log_files_1_1_entry.md) > > | [get_entries](#classmavsdk_1_1_log_files_1ab06a17009589c57aa90ac31a24aa9064) () const | Get List of log files.
void | [download_log_file_async](#classmavsdk_1_1_log_files_1a2db94afd60d6211cfbdb17c1092476d5) (uint32_t id, std::string path, [DownloadLogFileCallback](classmavsdk_1_1_log_files.md#classmavsdk_1_1_log_files_1a0a02c3e91339ac34fdb637603691cfa3) callback) | Download log file.
const [LogFiles](classmavsdk_1_1_log_files.md) & | [operator=](#classmavsdk_1_1_log_files_1a2ba9f188f7644a647f5dcdadb034e300) (const [LogFiles](classmavsdk_1_1_log_files.md) &)=delete | Equality operator (object is not copyable).


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


### typedef ResultCallback {#classmavsdk_1_1_log_files_1a64cd003ea9110b4a11eb08753a360a59}

```cpp
using mavsdk::LogFiles::ResultCallback =  std::function<void(Result)>
```


Callback type for asynchronous [LogFiles](classmavsdk_1_1_log_files.md) calls.


### typedef GetEntriesCallback {#classmavsdk_1_1_log_files_1a0bb101777daba9e87cb33baf55389403}

```cpp
using mavsdk::LogFiles::GetEntriesCallback =  std::function<void(Result, std::vector<Entry>)>
```


Callback type for get_entries_async.


### typedef DownloadLogFileCallback {#classmavsdk_1_1_log_files_1a0a02c3e91339ac34fdb637603691cfa3}

```cpp
using mavsdk::LogFiles::DownloadLogFileCallback =  std::function<void(LogFiles::Result, ProgressData)>
```


Callback type for download_log_file_async.


## Member Enumeration Documentation


### enum Result {#classmavsdk_1_1_log_files_1a43e5425f17cd8a6830ff6fd952a724cd}


Possible results returned for calibration commands.


Value | Description
--- | ---
<span id="classmavsdk_1_1_log_files_1a43e5425f17cd8a6830ff6fd952a724cda88183b946cc5f0e8c96b2e66e1c74a7e"></span> `Unknown` | Unknown result. 
<span id="classmavsdk_1_1_log_files_1a43e5425f17cd8a6830ff6fd952a724cda505a83f220c02df2f85c3810cd9ceb38"></span> `Success` | Request succeeded. 
<span id="classmavsdk_1_1_log_files_1a43e5425f17cd8a6830ff6fd952a724cda46b5f8c58b679b4243cbdb5749642c86"></span> `Progress` | Progress update. 
<span id="classmavsdk_1_1_log_files_1a43e5425f17cd8a6830ff6fd952a724cda63fe239cf100e5ce5032703da6ca8310"></span> `NoLogfiles` | No log files found. 
<span id="classmavsdk_1_1_log_files_1a43e5425f17cd8a6830ff6fd952a724cdac85a251cc457840f1e032f1b733e9398"></span> `Timeout` | A timeout happened. 
<span id="classmavsdk_1_1_log_files_1a43e5425f17cd8a6830ff6fd952a724cda253ca7dd096ee0956cccee4d376cab8b"></span> `InvalidArgument` | Invalid argument. 
<span id="classmavsdk_1_1_log_files_1a43e5425f17cd8a6830ff6fd952a724cda17fd85d9b010cda721a6aa7db5af2b28"></span> `FileOpenFailed` | File open failed. 

## Member Function Documentation


### get_entries_async() {#classmavsdk_1_1_log_files_1a6a922097850fb43fbb9d3348fe0b3bb7}
```cpp
void mavsdk::LogFiles::get_entries_async(const GetEntriesCallback callback)
```


Get List of log files.

This function is non-blocking. See 'get_entries' for the blocking counterpart.

**Parameters**

* const [GetEntriesCallback](classmavsdk_1_1_log_files.md#classmavsdk_1_1_log_files_1a0bb101777daba9e87cb33baf55389403) **callback** - 

### get_entries() {#classmavsdk_1_1_log_files_1ab06a17009589c57aa90ac31a24aa9064}
```cpp
std::pair<Result, std::vector<LogFiles::Entry> > mavsdk::LogFiles::get_entries() const
```


Get List of log files.

This function is blocking. See 'get_entries_async' for the non-blocking counterpart.

**Returns**

&emsp;std::pair< [Result](classmavsdk_1_1_log_files.md#classmavsdk_1_1_log_files_1a43e5425f17cd8a6830ff6fd952a724cd), std::vector< [LogFiles::Entry](structmavsdk_1_1_log_files_1_1_entry.md) > > - Result of request.

### download_log_file_async() {#classmavsdk_1_1_log_files_1a2db94afd60d6211cfbdb17c1092476d5}
```cpp
void mavsdk::LogFiles::download_log_file_async(uint32_t id, std::string path, DownloadLogFileCallback callback)
```


Download log file.


**Parameters**

* uint32_t **id** - 
* std::string **path** - 
* [DownloadLogFileCallback](classmavsdk_1_1_log_files.md#classmavsdk_1_1_log_files_1a0a02c3e91339ac34fdb637603691cfa3) **callback** - 

### operator=() {#classmavsdk_1_1_log_files_1a2ba9f188f7644a647f5dcdadb034e300}
```cpp
const LogFiles& mavsdk::LogFiles::operator=(const LogFiles &)=delete
```


Equality operator (object is not copyable).


**Parameters**

* const [LogFiles](classmavsdk_1_1_log_files.md)&  - 

**Returns**

&emsp;const [LogFiles](classmavsdk_1_1_log_files.md) & - 