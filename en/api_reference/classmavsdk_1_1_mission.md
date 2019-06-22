# mavsdk::Mission Class Reference
`#include: mission.h`

----


The [Mission](classmavsdk_1_1_mission.md) class enables waypoint missions. 


## Public Types


Type | Description
--- | ---
enum [Result](#classmavsdk_1_1_mission_1ab3114c63db76bdc37460939a1f3316f6) | Possible results returned for mission requests.
std::function< void([Result](classmavsdk_1_1_mission.md#classmavsdk_1_1_mission_1ab3114c63db76bdc37460939a1f3316f6))> [result_callback_t](#classmavsdk_1_1_mission_1a2dfe79d7f58c5b76ab6b245f9d516dbc) | Callback type for async mission calls.
std::vector< std::shared_ptr< [MissionItem](classmavsdk_1_1_mission_item.md) > > [mission_items_t](#classmavsdk_1_1_mission_1a08460b5a56a9720ca150739528da9b78) | Type for vector of mission items.
std::function< void([Result](classmavsdk_1_1_mission.md#classmavsdk_1_1_mission_1ab3114c63db76bdc37460939a1f3316f6), std::vector< std::shared_ptr< [MissionItem](classmavsdk_1_1_mission_item.md) > >)> [mission_items_and_result_callback_t](#classmavsdk_1_1_mission_1a23dc8d2ec8de9434d0c7afaca66b1993) | Callback type for [download_mission_async()](classmavsdk_1_1_mission.md#classmavsdk_1_1_mission_1a23173385eef570b9802402fc047104c1) call to get mission items and result.
std::function< void(int current, int total)> [progress_callback_t](#classmavsdk_1_1_mission_1a6cb9b3e10db0ed921cec79b3f91cbecc) | Callback type to receive mission progress.

## Public Member Functions


Type | Name | Description
---: | --- | ---
&nbsp; | [Mission](#classmavsdk_1_1_mission_1ab02ae9aada51b483e45d88948fe62c29) ([System](classmavsdk_1_1_system.md) & system) | Constructor. Creates the plugin for a specific [System](classmavsdk_1_1_system.md).
&nbsp; | [~Mission](#classmavsdk_1_1_mission_1a0a0e9ee6ff15fc2231277d929add95ef) () | Destructor (internal use only).
&nbsp; | [Mission](#classmavsdk_1_1_mission_1a395b1f9530c6c7a1c60638dbe5ec07c7) (const [Mission](classmavsdk_1_1_mission.md) &)=delete | Copy constructor (object is not copyable).
void | [upload_mission_async](#classmavsdk_1_1_mission_1ad6117cf541865249900201fe6305f5a1) (const std::vector< std::shared_ptr< [MissionItem](classmavsdk_1_1_mission_item.md) >> & mission_items, [result_callback_t](classmavsdk_1_1_mission.md#classmavsdk_1_1_mission_1a2dfe79d7f58c5b76ab6b245f9d516dbc) callback) | Uploads a vector of mission items to the system (asynchronous).
void | [upload_mission_cancel](#classmavsdk_1_1_mission_1a1a21bbf4bcda9a51ef06858bb2a2a3f1) () | Cancel a mission upload (asynchronous).
void | [download_mission_async](#classmavsdk_1_1_mission_1a23173385eef570b9802402fc047104c1) ([mission_items_and_result_callback_t](classmavsdk_1_1_mission.md#classmavsdk_1_1_mission_1a23dc8d2ec8de9434d0c7afaca66b1993) callback) | Downloads a vector of mission items from the system (asynchronous).
void | [download_mission_cancel](#classmavsdk_1_1_mission_1aec094d35ff746f25f668cfdd10125c3d) () | Cancel a mission download (asynchronous).
void | [set_return_to_launch_after_mission](#classmavsdk_1_1_mission_1a3ef85af6f74b879aca9b816c34fc67d6) (bool enable) | Set whether to trigger Return-to-Launch (RTL) after mission is complete.
bool | [get_return_to_launch_after_mission](#classmavsdk_1_1_mission_1a03af92b98026a6a3d1911e0a501161f0) () | Get whether to trigger Return-to-Launch (RTL) after mission is complete.
void | [start_mission_async](#classmavsdk_1_1_mission_1af0a6404b7af085759bc6dad518eea525) ([result_callback_t](classmavsdk_1_1_mission.md#classmavsdk_1_1_mission_1a2dfe79d7f58c5b76ab6b245f9d516dbc) callback) | Starts the mission (asynchronous).
void | [pause_mission_async](#classmavsdk_1_1_mission_1a39a0434bb2e731ccca7c0f2d579b0ee8) ([result_callback_t](classmavsdk_1_1_mission.md#classmavsdk_1_1_mission_1a2dfe79d7f58c5b76ab6b245f9d516dbc) callback) | Pauses the mission (asynchronous).
void | [set_current_mission_item_async](#classmavsdk_1_1_mission_1aca6c73c22175c7d5afe6ade0476b4ad3) (int current, [result_callback_t](classmavsdk_1_1_mission.md#classmavsdk_1_1_mission_1a2dfe79d7f58c5b76ab6b245f9d516dbc) callback) | Sets the mission item index to go to (asynchronous).
bool | [mission_finished](#classmavsdk_1_1_mission_1a5861a4c6325ca1eeb1cc1d37004a7f61) () const | Checks if mission has been finished (synchronous).
int | [current_mission_item](#classmavsdk_1_1_mission_1a25afa022a4206bd1055a692937f9b916) () const | Returns the current mission item index (synchronous).
int | [total_mission_items](#classmavsdk_1_1_mission_1a97c07cbcf5e9c54d5776cd86e4228311) () const | Returns the total number of mission items (synchronous).
void | [subscribe_progress](#classmavsdk_1_1_mission_1aa882278b493a2390ca0b3cf7027b3a01) ([progress_callback_t](classmavsdk_1_1_mission.md#classmavsdk_1_1_mission_1a6cb9b3e10db0ed921cec79b3f91cbecc) callback) | Subscribes to mission progress (asynchronous).
const [Mission](classmavsdk_1_1_mission.md) & | [operator=](#classmavsdk_1_1_mission_1a30d49ea769f358cb4e4fe3056728838c) (const [Mission](classmavsdk_1_1_mission.md) &)=delete | Equality operator (object is not copyable).

## Static Public Member Functions


Type | Name | Description
---: | --- | ---
const char * | [result_str](#classmavsdk_1_1_mission_1aa1e238f8f13b0089b848d9189de4414d) ([Result](classmavsdk_1_1_mission.md#classmavsdk_1_1_mission_1ab3114c63db76bdc37460939a1f3316f6) result) | Gets a human-readable English string for an [Mission::Result](classmavsdk_1_1_mission.md#classmavsdk_1_1_mission_1ab3114c63db76bdc37460939a1f3316f6).
[Result](classmavsdk_1_1_mission.md#classmavsdk_1_1_mission_1ab3114c63db76bdc37460939a1f3316f6) | [import_qgroundcontrol_mission](#classmavsdk_1_1_mission_1aa0a937d18e9ce2c4f346aa9ee8a1a6d9) ([mission_items_t](classmavsdk_1_1_mission.md#classmavsdk_1_1_mission_1a08460b5a56a9720ca150739528da9b78) & mission_items, const std::string & qgc_plan_file) | Imports a **QGroundControl** (QGC) mission plan.


## Constructor & Destructor Documentation


### Mission() {#classmavsdk_1_1_mission_1ab02ae9aada51b483e45d88948fe62c29}
```cpp
mavsdk::Mission::Mission(System &system)
```


Constructor. Creates the plugin for a specific [System](classmavsdk_1_1_system.md).

The plugin is typically created as shown below: 

```cpp
auto mission = std::make_shared<Mission>(system);
```

**Parameters**

* [System](classmavsdk_1_1_system.md)& **system** - The specific system associated with this plugin.

### ~Mission() {#classmavsdk_1_1_mission_1a0a0e9ee6ff15fc2231277d929add95ef}
```cpp
mavsdk::Mission::~Mission()
```


Destructor (internal use only).


### Mission() {#classmavsdk_1_1_mission_1a395b1f9530c6c7a1c60638dbe5ec07c7}
```cpp
mavsdk::Mission::Mission(const Mission &)=delete
```


Copy constructor (object is not copyable).


**Parameters**

* const [Mission](classmavsdk_1_1_mission.md)&  - 

## Member Typdef Documentation


### typedef result_callback_t {#classmavsdk_1_1_mission_1a2dfe79d7f58c5b76ab6b245f9d516dbc}

```cpp
typedef std::function<void(Result)> mavsdk::Mission::result_callback_t
```


Callback type for async mission calls.


### typedef mission_items_t {#classmavsdk_1_1_mission_1a08460b5a56a9720ca150739528da9b78}

```cpp
typedef std::vector<std::shared_ptr<MissionItem> > mavsdk::Mission::mission_items_t
```


Type for vector of mission items.


### typedef mission_items_and_result_callback_t {#classmavsdk_1_1_mission_1a23dc8d2ec8de9434d0c7afaca66b1993}

```cpp
typedef std::function<void(Result, std::vector<std::shared_ptr<MissionItem> >)> mavsdk::Mission::mission_items_and_result_callback_t
```


Callback type for [download_mission_async()](classmavsdk_1_1_mission.md#classmavsdk_1_1_mission_1a23173385eef570b9802402fc047104c1) call to get mission items and result.


### typedef progress_callback_t {#classmavsdk_1_1_mission_1a6cb9b3e10db0ed921cec79b3f91cbecc}

```cpp
typedef std::function<void(int current, int total)> mavsdk::Mission::progress_callback_t
```


Callback type to receive mission progress.

The mission is finished if current == total.

**Parameters**

* **current** - Current mission item index (0 based).
* **total** - Total number of mission items.

## Member Enumeration Documentation


### enum Result {#classmavsdk_1_1_mission_1ab3114c63db76bdc37460939a1f3316f6}


Possible results returned for mission requests.


Value | Description
--- | ---
<span id="classmavsdk_1_1_mission_1ab3114c63db76bdc37460939a1f3316f6a696b031073e74bf2cb98e5ef201d4aa3"></span> `UNKNOWN` | Unknown error. 
<span id="classmavsdk_1_1_mission_1ab3114c63db76bdc37460939a1f3316f6ad0749aaba8b833466dfcbb0428e4f89c"></span> `SUCCESS` | Request succeeded. 
<span id="classmavsdk_1_1_mission_1ab3114c63db76bdc37460939a1f3316f6abb1ca97ec761fc37101737ba0aa2e7c5"></span> `ERROR` | Error. 
<span id="classmavsdk_1_1_mission_1ab3114c63db76bdc37460939a1f3316f6ab6968a2ae2835d0d36126e1d12e5d1a1"></span> `TOO_MANY_MISSION_ITEMS` | Too many [MissionItem](classmavsdk_1_1_mission_item.md) objects in the mission. 
<span id="classmavsdk_1_1_mission_1ab3114c63db76bdc37460939a1f3316f6a802706a9238e2928077f97736854bad4"></span> `BUSY` | Vehicle busy. 
<span id="classmavsdk_1_1_mission_1ab3114c63db76bdc37460939a1f3316f6a070a0fb40f6c308ab544b227660aadff"></span> `TIMEOUT` | Request timed out. 
<span id="classmavsdk_1_1_mission_1ab3114c63db76bdc37460939a1f3316f6af295a0c3e37c94f078e1c5476479132d"></span> `INVALID_ARGUMENT` | Invalid argument. 
<span id="classmavsdk_1_1_mission_1ab3114c63db76bdc37460939a1f3316f6a40aa75f8e8cfdf7b660c5620e953229f"></span> `UNSUPPORTED` | The mission downloaded from the system is not supported. 
<span id="classmavsdk_1_1_mission_1ab3114c63db76bdc37460939a1f3316f6a1d25c4b5260709868a0c57ae60ae815e"></span> `NO_MISSION_AVAILABLE` | No mission available on system. 
<span id="classmavsdk_1_1_mission_1ab3114c63db76bdc37460939a1f3316f6a44090b5626a9be3103d4e3624470635c"></span> `FAILED_TO_OPEN_QGC_PLAN` | Failed to open QGroundControl plan. 
<span id="classmavsdk_1_1_mission_1ab3114c63db76bdc37460939a1f3316f6a503c552313ebdaf4cd93b1e5b5525a4f"></span> `FAILED_TO_PARSE_QGC_PLAN` | Failed to parse QGroundControl plan. 
<span id="classmavsdk_1_1_mission_1ab3114c63db76bdc37460939a1f3316f6a0118056c7c9e890a242c9bdb961dac82"></span> `UNSUPPORTED_MISSION_CMD` | Unsupported mission command. 
<span id="classmavsdk_1_1_mission_1ab3114c63db76bdc37460939a1f3316f6a9f935beb31030ad0d4d26126c0f39bf2"></span> `CANCELLED` | [Mission](classmavsdk_1_1_mission.md) upload or download has been cancelled. 

## Member Function Documentation


### upload_mission_async() {#classmavsdk_1_1_mission_1ad6117cf541865249900201fe6305f5a1}
```cpp
void mavsdk::Mission::upload_mission_async(const std::vector< std::shared_ptr< MissionItem >> &mission_items, result_callback_t callback)
```


Uploads a vector of mission items to the system (asynchronous).

The mission items are uploaded to a drone. Once uploaded the mission can be started and executed even if a connection is lost.

**Parameters**

* const std::vector< std::shared_ptr< [MissionItem](classmavsdk_1_1_mission_item.md) >>& **mission_items** - Reference to vector of mission items.
* [result_callback_t](classmavsdk_1_1_mission.md#classmavsdk_1_1_mission_1a2dfe79d7f58c5b76ab6b245f9d516dbc) **callback** - Callback to receive result of this request.

### upload_mission_cancel() {#classmavsdk_1_1_mission_1a1a21bbf4bcda9a51ef06858bb2a2a3f1}
```cpp
void mavsdk::Mission::upload_mission_cancel()
```


Cancel a mission upload (asynchronous).

This cancels an ongoing mission upload. The mission upload will fail with the result [Result::CANCELLED](classmavsdk_1_1_mission.md#classmavsdk_1_1_mission_1ab3114c63db76bdc37460939a1f3316f6a9f935beb31030ad0d4d26126c0f39bf2).

### download_mission_async() {#classmavsdk_1_1_mission_1a23173385eef570b9802402fc047104c1}
```cpp
void mavsdk::Mission::download_mission_async(mission_items_and_result_callback_t callback)
```


Downloads a vector of mission items from the system (asynchronous).

The method will fail if any of the downloaded mission items are not supported by the Dronecode SDK API.

**Parameters**

* [mission_items_and_result_callback_t](classmavsdk_1_1_mission.md#classmavsdk_1_1_mission_1a23dc8d2ec8de9434d0c7afaca66b1993) **callback** - Callback to receive mission items and result of this request.

### download_mission_cancel() {#classmavsdk_1_1_mission_1aec094d35ff746f25f668cfdd10125c3d}
```cpp
void mavsdk::Mission::download_mission_cancel()
```


Cancel a mission download (asynchronous).

This cancels an ongoing mission download. The mission download will fail with the result [Result::CANCELLED](classmavsdk_1_1_mission.md#classmavsdk_1_1_mission_1ab3114c63db76bdc37460939a1f3316f6a9f935beb31030ad0d4d26126c0f39bf2).

### set_return_to_launch_after_mission() {#classmavsdk_1_1_mission_1a3ef85af6f74b879aca9b816c34fc67d6}
```cpp
void mavsdk::Mission::set_return_to_launch_after_mission(bool enable)
```


Set whether to trigger Return-to-Launch (RTL) after mission is complete.

This enables/disables to command RTL at the end of a mission.


> **Note** After setting this option, the mission needs to be re-uploaded.

**Parameters**

* bool **enable** - Enables RTL after mission is complete.

### get_return_to_launch_after_mission() {#classmavsdk_1_1_mission_1a03af92b98026a6a3d1911e0a501161f0}
```cpp
bool mavsdk::Mission::get_return_to_launch_after_mission()
```


Get whether to trigger Return-to-Launch (RTL) after mission is complete.

> **Note** Before getting this option, it needs to be set, or a mission needs to be downloaded.

**Returns**

&emsp;bool - True if RTL after mission is complete is enabled.

### start_mission_async() {#classmavsdk_1_1_mission_1af0a6404b7af085759bc6dad518eea525}
```cpp
void mavsdk::Mission::start_mission_async(result_callback_t callback)
```


Starts the mission (asynchronous).

Note that the mission must be uploaded to the vehicle using [upload_mission_async()](classmavsdk_1_1_mission.md#classmavsdk_1_1_mission_1ad6117cf541865249900201fe6305f5a1) before this method is called.

**Parameters**

* [result_callback_t](classmavsdk_1_1_mission.md#classmavsdk_1_1_mission_1a2dfe79d7f58c5b76ab6b245f9d516dbc) **callback** - callback to receive result of this request.

### pause_mission_async() {#classmavsdk_1_1_mission_1a39a0434bb2e731ccca7c0f2d579b0ee8}
```cpp
void mavsdk::Mission::pause_mission_async(result_callback_t callback)
```


Pauses the mission (asynchronous).

Pausing the mission puts the vehicle into [HOLD mode](https://docs.px4.io/en/flight_modes/hold.html). A multicopter should just hover at the spot while a fixedwing vehicle should loiter around the location where it paused.

**Parameters**

* [result_callback_t](classmavsdk_1_1_mission.md#classmavsdk_1_1_mission_1a2dfe79d7f58c5b76ab6b245f9d516dbc) **callback** - Callback to receive result of this request.

### set_current_mission_item_async() {#classmavsdk_1_1_mission_1aca6c73c22175c7d5afe6ade0476b4ad3}
```cpp
void mavsdk::Mission::set_current_mission_item_async(int current, result_callback_t callback)
```


Sets the mission item index to go to (asynchronous).

By setting the current index to 0, the mission is restarted from the beginning. If it is set to a specific index of a mission item, the mission will be set to this item.


Note that this is not necessarily true for general missions using MAVLink if loop counters are used.

**Parameters**

* int **current** - Index for mission index to go to next (0 based).
* [result_callback_t](classmavsdk_1_1_mission.md#classmavsdk_1_1_mission_1a2dfe79d7f58c5b76ab6b245f9d516dbc) **callback** - Callback to receive result of this request.

### mission_finished() {#classmavsdk_1_1_mission_1a5861a4c6325ca1eeb1cc1d37004a7f61}
```cpp
bool mavsdk::Mission::mission_finished() const
```


Checks if mission has been finished (synchronous).


**Returns**

&emsp;bool - true if mission is finished and the last mission item has been reached.

### current_mission_item() {#classmavsdk_1_1_mission_1a25afa022a4206bd1055a692937f9b916}
```cpp
int mavsdk::Mission::current_mission_item() const
```


Returns the current mission item index (synchronous).

If the mission is finished, the current mission item will be the total number of mission items (so the last mission item index + 1).

**Returns**

&emsp;int - current mission item index (0 based).

### total_mission_items() {#classmavsdk_1_1_mission_1a97c07cbcf5e9c54d5776cd86e4228311}
```cpp
int mavsdk::Mission::total_mission_items() const
```


Returns the total number of mission items (synchronous).


**Returns**

&emsp;int - total number of mission items

### subscribe_progress() {#classmavsdk_1_1_mission_1aa882278b493a2390ca0b3cf7027b3a01}
```cpp
void mavsdk::Mission::subscribe_progress(progress_callback_t callback)
```


Subscribes to mission progress (asynchronous).


**Parameters**

* [progress_callback_t](classmavsdk_1_1_mission.md#classmavsdk_1_1_mission_1a6cb9b3e10db0ed921cec79b3f91cbecc) **callback** - Callback to receive mission progress.

### operator=() {#classmavsdk_1_1_mission_1a30d49ea769f358cb4e4fe3056728838c}
```cpp
const Mission& mavsdk::Mission::operator=(const Mission &)=delete
```


Equality operator (object is not copyable).


**Parameters**

* const [Mission](classmavsdk_1_1_mission.md)&  - 

**Returns**

&emsp;const [Mission](classmavsdk_1_1_mission.md) & - 

### result_str() {#classmavsdk_1_1_mission_1aa1e238f8f13b0089b848d9189de4414d}
```cpp
static const char* mavsdk::Mission::result_str(Result result)
```


Gets a human-readable English string for an [Mission::Result](classmavsdk_1_1_mission.md#classmavsdk_1_1_mission_1ab3114c63db76bdc37460939a1f3316f6).


**Parameters**

* [Result](classmavsdk_1_1_mission.md#classmavsdk_1_1_mission_1ab3114c63db76bdc37460939a1f3316f6) **result** - Enum for which string is required.

**Returns**

&emsp;const char * - Human readable string for the [Mission::Result](classmavsdk_1_1_mission.md#classmavsdk_1_1_mission_1ab3114c63db76bdc37460939a1f3316f6).

### import_qgroundcontrol_mission() {#classmavsdk_1_1_mission_1aa0a937d18e9ce2c4f346aa9ee8a1a6d9}
```cpp
static Result mavsdk::Mission::import_qgroundcontrol_mission(mission_items_t &mission_items, const std::string &qgc_plan_file)
```


Imports a **QGroundControl** (QGC) mission plan.

The method composes the plan into a vector of [MissionItem](classmavsdk_1_1_mission_item.md) shared pointers that can then be uploaded to a vehicle. The method will fail if any of the imported mission items are not supported by the Dronecode SDK API.

**Parameters**

* [mission_items_t](classmavsdk_1_1_mission.md#classmavsdk_1_1_mission_1a08460b5a56a9720ca150739528da9b78)& **mission_items** - Vector of mission items imported from QGC plan.
* const std::string& **qgc_plan_file** - File path of the QGC plan.

**Returns**

&emsp;[Result](classmavsdk_1_1_mission.md#classmavsdk_1_1_mission_1ab3114c63db76bdc37460939a1f3316f6) - [Result::SUCCESS](classmavsdk_1_1_mission.md#classmavsdk_1_1_mission_1ab3114c63db76bdc37460939a1f3316f6ad0749aaba8b833466dfcbb0428e4f89c) if successful in importing QGC mission items. Otherwise one of the error codes: [Result::FAILED_TO_OPEN_QGC_PLAN](classmavsdk_1_1_mission.md#classmavsdk_1_1_mission_1ab3114c63db76bdc37460939a1f3316f6a44090b5626a9be3103d4e3624470635c), [Result::FAILED_TO_PARSE_QGC_PLAN](classmavsdk_1_1_mission.md#classmavsdk_1_1_mission_1ab3114c63db76bdc37460939a1f3316f6a503c552313ebdaf4cd93b1e5b5525a4f), [Result::UNSUPPORTED_MISSION_CMD](classmavsdk_1_1_mission.md#classmavsdk_1_1_mission_1ab3114c63db76bdc37460939a1f3316f6a0118056c7c9e890a242c9bdb961dac82).

**See Also:**
- [QGroundControl Plan file format](https://dev.qgroundcontrol.com/en/file_formats/plan.html) (QGroundControl Dev Guide)

