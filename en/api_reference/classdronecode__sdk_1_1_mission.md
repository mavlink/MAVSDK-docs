# dronecode_sdk::Mission Class Reference
`#include: mission.h`

----


The [Mission](classdronecode__sdk_1_1_mission.md) class enables waypoint missions. 


## Public Types


Type | Description
--- | ---
enum [Result](#classdronecode__sdk_1_1_mission_1a819b8fdcf5a49f76e690c2c16adf572d) | Possible results returned for mission requests.
std::function< void([Result](classdronecode__sdk_1_1_mission.md#classdronecode__sdk_1_1_mission_1a819b8fdcf5a49f76e690c2c16adf572d))> [result_callback_t](#classdronecode__sdk_1_1_mission_1adab3125b28a8d7b7ed90a81ea56b0115) | Callback type for async mission calls.
std::vector< std::shared_ptr< [MissionItem](classdronecode__sdk_1_1_mission_item.md) > > [mission_items_t](#classdronecode__sdk_1_1_mission_1a4ceae9b6eda5553b91c47e0c5b94f1ec) | Type for vector of mission items.
std::function< void([Result](classdronecode__sdk_1_1_mission.md#classdronecode__sdk_1_1_mission_1a819b8fdcf5a49f76e690c2c16adf572d), std::vector< std::shared_ptr< [MissionItem](classdronecode__sdk_1_1_mission_item.md) > >)> [mission_items_and_result_callback_t](#classdronecode__sdk_1_1_mission_1a319a5311e997cf351557e8663abc7d84) | Callback type for [download_mission_async()](classdronecode__sdk_1_1_mission.md#classdronecode__sdk_1_1_mission_1a786b73a354af0b45b75caa36d197c336) call to get mission items and result.
std::function< void(int current, int total)> [progress_callback_t](#classdronecode__sdk_1_1_mission_1ab2fefd005c7c1f420ddcc32cba046760) | Callback type to receive mission progress.

## Public Member Functions


Type | Name | Description
---: | --- | ---
&nbsp; | [Mission](#classdronecode__sdk_1_1_mission_1a2dafe9cf424acb1db902e49f22412071) ([System](classdronecode__sdk_1_1_system.md) & system) | Constructor. Creates the plugin for a specific [System](classdronecode__sdk_1_1_system.md).
&nbsp; | [~Mission](#classdronecode__sdk_1_1_mission_1a21637e7a71c29a95f573a5c44ee0bd26) () | Destructor (internal use only).
&nbsp; | [Mission](#classdronecode__sdk_1_1_mission_1a1fbfbebf4812b806af482188490f12a1) (const [Mission](classdronecode__sdk_1_1_mission.md) &)=delete | Copy constructor (object is not copyable).
void | [upload_mission_async](#classdronecode__sdk_1_1_mission_1abe18ceecd0afba9c109ed216c77212f0) (const std::vector< std::shared_ptr< [MissionItem](classdronecode__sdk_1_1_mission_item.md) >> & mission_items, [result_callback_t](classdronecode__sdk_1_1_mission.md#classdronecode__sdk_1_1_mission_1adab3125b28a8d7b7ed90a81ea56b0115) callback) | Uploads a vector of mission items to the system (asynchronous).
void | [download_mission_async](#classdronecode__sdk_1_1_mission_1a786b73a354af0b45b75caa36d197c336) ([mission_items_and_result_callback_t](classdronecode__sdk_1_1_mission.md#classdronecode__sdk_1_1_mission_1a319a5311e997cf351557e8663abc7d84) callback) | Downloads a vector of mission items from the system (asynchronous).
void | [start_mission_async](#classdronecode__sdk_1_1_mission_1aa4bfbd0e5e06692a96f0301fbe7bbbc3) ([result_callback_t](classdronecode__sdk_1_1_mission.md#classdronecode__sdk_1_1_mission_1adab3125b28a8d7b7ed90a81ea56b0115) callback) | Starts the mission (asynchronous).
void | [pause_mission_async](#classdronecode__sdk_1_1_mission_1a720993b72dcea4634aab3ed206124101) ([result_callback_t](classdronecode__sdk_1_1_mission.md#classdronecode__sdk_1_1_mission_1adab3125b28a8d7b7ed90a81ea56b0115) callback) | Pauses the mission (asynchronous).
void | [set_current_mission_item_async](#classdronecode__sdk_1_1_mission_1a48410e3f4e104d9db139418d9200c560) (int current, [result_callback_t](classdronecode__sdk_1_1_mission.md#classdronecode__sdk_1_1_mission_1adab3125b28a8d7b7ed90a81ea56b0115) callback) | Sets the mission item index to go to (asynchronous).
bool | [mission_finished](#classdronecode__sdk_1_1_mission_1a0ee8f797121687152529a7ebf054e3f0) () const | Checks if mission has been finished (synchronous).
int | [current_mission_item](#classdronecode__sdk_1_1_mission_1a1a58040494426a318828621177c455d2) () const | Returns the current mission item index (synchronous).
int | [total_mission_items](#classdronecode__sdk_1_1_mission_1a5ff976af79aa39a0d388b535bc508e20) () const | Returns the total number of mission items (synchronous).
void | [subscribe_progress](#classdronecode__sdk_1_1_mission_1a319eeb2918a24e2f0dcb8ffbf0f84685) ([progress_callback_t](classdronecode__sdk_1_1_mission.md#classdronecode__sdk_1_1_mission_1ab2fefd005c7c1f420ddcc32cba046760) callback) | Subscribes to mission progress (asynchronous).
const [Mission](classdronecode__sdk_1_1_mission.md) & | [operator=](#classdronecode__sdk_1_1_mission_1a01b702ceeeb9c4673c763fcf7d2a2c36) (const [Mission](classdronecode__sdk_1_1_mission.md) &)=delete | Equality operator (object is not copyable).

## Static Public Member Functions


Type | Name | Description
---: | --- | ---
const char * | [result_str](#classdronecode__sdk_1_1_mission_1ae8a4e4af6ae0d2485837afb88f2e66b1) ([Result](classdronecode__sdk_1_1_mission.md#classdronecode__sdk_1_1_mission_1a819b8fdcf5a49f76e690c2c16adf572d) result) | Gets a human-readable English string for an [Mission::Result](classdronecode__sdk_1_1_mission.md#classdronecode__sdk_1_1_mission_1a819b8fdcf5a49f76e690c2c16adf572d).
[Result](classdronecode__sdk_1_1_mission.md#classdronecode__sdk_1_1_mission_1a819b8fdcf5a49f76e690c2c16adf572d) | [import_qgroundcontrol_mission](#classdronecode__sdk_1_1_mission_1a326d3ef45f0080e543ef5f1832246c5f) ([mission_items_t](classdronecode__sdk_1_1_mission.md#classdronecode__sdk_1_1_mission_1a4ceae9b6eda5553b91c47e0c5b94f1ec) & mission_items, const std::string & qgc_plan_file) | Imports a **QGroundControl** (QGC) mission plan.


## Constructor & Destructor Documentation


### Mission() {#classdronecode__sdk_1_1_mission_1a2dafe9cf424acb1db902e49f22412071}
```cpp
dronecode_sdk::Mission::Mission(System &system)
```


Constructor. Creates the plugin for a specific [System](classdronecode__sdk_1_1_system.md).

The plugin is typically created as shown below: 

```cpp
auto mission = std::make_shared<Mission>(system);
```

**Parameters**

* [System](classdronecode__sdk_1_1_system.md)& **system** - The specific system associated with this plugin.

### ~Mission() {#classdronecode__sdk_1_1_mission_1a21637e7a71c29a95f573a5c44ee0bd26}
```cpp
dronecode_sdk::Mission::~Mission()
```


Destructor (internal use only).


### Mission() {#classdronecode__sdk_1_1_mission_1a1fbfbebf4812b806af482188490f12a1}
```cpp
dronecode_sdk::Mission::Mission(const Mission &)=delete
```


Copy constructor (object is not copyable).


**Parameters**

* const [Mission](classdronecode__sdk_1_1_mission.md)&  - 

## Member Typdef Documentation


### typedef result_callback_t {#classdronecode__sdk_1_1_mission_1adab3125b28a8d7b7ed90a81ea56b0115}

```cpp
typedef std::function<void(Result)> dronecode_sdk::Mission::result_callback_t
```


Callback type for async mission calls.


### typedef mission_items_t {#classdronecode__sdk_1_1_mission_1a4ceae9b6eda5553b91c47e0c5b94f1ec}

```cpp
typedef std::vector<std::shared_ptr<MissionItem> > dronecode_sdk::Mission::mission_items_t
```


Type for vector of mission items.


### typedef mission_items_and_result_callback_t {#classdronecode__sdk_1_1_mission_1a319a5311e997cf351557e8663abc7d84}

```cpp
typedef std::function<void(Result, std::vector<std::shared_ptr<MissionItem> >)> dronecode_sdk::Mission::mission_items_and_result_callback_t
```


Callback type for [download_mission_async()](classdronecode__sdk_1_1_mission.md#classdronecode__sdk_1_1_mission_1a786b73a354af0b45b75caa36d197c336) call to get mission items and result.


### typedef progress_callback_t {#classdronecode__sdk_1_1_mission_1ab2fefd005c7c1f420ddcc32cba046760}

```cpp
typedef std::function<void(int current, int total)> dronecode_sdk::Mission::progress_callback_t
```


Callback type to receive mission progress.

The mission is finished if current == total.

**Parameters**

* **current** - Current mission item index (0 based).
* **total** - Total number of mission items.

## Member Enumeration Documentation


### enum Result {#classdronecode__sdk_1_1_mission_1a819b8fdcf5a49f76e690c2c16adf572d}


Possible results returned for mission requests.


Value | Description
--- | ---
<span id="classdronecode__sdk_1_1_mission_1a819b8fdcf5a49f76e690c2c16adf572da696b031073e74bf2cb98e5ef201d4aa3"></span> `UNKNOWN` | Unknown error. 
<span id="classdronecode__sdk_1_1_mission_1a819b8fdcf5a49f76e690c2c16adf572dad0749aaba8b833466dfcbb0428e4f89c"></span> `SUCCESS` | Request succeeded. 
<span id="classdronecode__sdk_1_1_mission_1a819b8fdcf5a49f76e690c2c16adf572dabb1ca97ec761fc37101737ba0aa2e7c5"></span> `ERROR` | Error. 
<span id="classdronecode__sdk_1_1_mission_1a819b8fdcf5a49f76e690c2c16adf572dab6968a2ae2835d0d36126e1d12e5d1a1"></span> `TOO_MANY_MISSION_ITEMS` | Too many [MissionItem](classdronecode__sdk_1_1_mission_item.md) objects in the mission. 
<span id="classdronecode__sdk_1_1_mission_1a819b8fdcf5a49f76e690c2c16adf572da802706a9238e2928077f97736854bad4"></span> `BUSY` | Vehicle busy. 
<span id="classdronecode__sdk_1_1_mission_1a819b8fdcf5a49f76e690c2c16adf572da070a0fb40f6c308ab544b227660aadff"></span> `TIMEOUT` | Request timed out. 
<span id="classdronecode__sdk_1_1_mission_1a819b8fdcf5a49f76e690c2c16adf572daf295a0c3e37c94f078e1c5476479132d"></span> `INVALID_ARGUMENT` | Invalid argument. 
<span id="classdronecode__sdk_1_1_mission_1a819b8fdcf5a49f76e690c2c16adf572da40aa75f8e8cfdf7b660c5620e953229f"></span> `UNSUPPORTED` | The mission downloaded from the system is not supported. 
<span id="classdronecode__sdk_1_1_mission_1a819b8fdcf5a49f76e690c2c16adf572da1d25c4b5260709868a0c57ae60ae815e"></span> `NO_MISSION_AVAILABLE` | No mission available on system. 
<span id="classdronecode__sdk_1_1_mission_1a819b8fdcf5a49f76e690c2c16adf572da44090b5626a9be3103d4e3624470635c"></span> `FAILED_TO_OPEN_QGC_PLAN` | Failed to open QGroundControl plan. 
<span id="classdronecode__sdk_1_1_mission_1a819b8fdcf5a49f76e690c2c16adf572da503c552313ebdaf4cd93b1e5b5525a4f"></span> `FAILED_TO_PARSE_QGC_PLAN` | Failed to parse QGroundControl plan. 
<span id="classdronecode__sdk_1_1_mission_1a819b8fdcf5a49f76e690c2c16adf572da0118056c7c9e890a242c9bdb961dac82"></span> `UNSUPPORTED_MISSION_CMD` | Unsupported mission command. 

## Member Function Documentation


### upload_mission_async() {#classdronecode__sdk_1_1_mission_1abe18ceecd0afba9c109ed216c77212f0}
```cpp
void dronecode_sdk::Mission::upload_mission_async(const std::vector< std::shared_ptr< MissionItem >> &mission_items, result_callback_t callback)
```


Uploads a vector of mission items to the system (asynchronous).

The mission items are uploaded to a drone. Once uploaded the mission can be started and executed even if a connection is lost.

**Parameters**

* const std::vector< std::shared_ptr< [MissionItem](classdronecode__sdk_1_1_mission_item.md) >>& **mission_items** - Reference to vector of mission items.
* [result_callback_t](classdronecode__sdk_1_1_mission.md#classdronecode__sdk_1_1_mission_1adab3125b28a8d7b7ed90a81ea56b0115) **callback** - Callback to receive result of this request.

### download_mission_async() {#classdronecode__sdk_1_1_mission_1a786b73a354af0b45b75caa36d197c336}
```cpp
void dronecode_sdk::Mission::download_mission_async(mission_items_and_result_callback_t callback)
```


Downloads a vector of mission items from the system (asynchronous).

The method will fail if any of the downloaded mission items are not supported by the Dronecode SDK API.

**Parameters**

* [mission_items_and_result_callback_t](classdronecode__sdk_1_1_mission.md#classdronecode__sdk_1_1_mission_1a319a5311e997cf351557e8663abc7d84) **callback** - Callback to receive mission items and result of this request.

### start_mission_async() {#classdronecode__sdk_1_1_mission_1aa4bfbd0e5e06692a96f0301fbe7bbbc3}
```cpp
void dronecode_sdk::Mission::start_mission_async(result_callback_t callback)
```


Starts the mission (asynchronous).

Note that the mission must be uploaded to the vehicle using [upload_mission_async()](classdronecode__sdk_1_1_mission.md#classdronecode__sdk_1_1_mission_1abe18ceecd0afba9c109ed216c77212f0) before this method is called.

**Parameters**

* [result_callback_t](classdronecode__sdk_1_1_mission.md#classdronecode__sdk_1_1_mission_1adab3125b28a8d7b7ed90a81ea56b0115) **callback** - callback to receive result of this request.

### pause_mission_async() {#classdronecode__sdk_1_1_mission_1a720993b72dcea4634aab3ed206124101}
```cpp
void dronecode_sdk::Mission::pause_mission_async(result_callback_t callback)
```


Pauses the mission (asynchronous).

Pausing the mission puts the vehicle into [HOLD mode](https://docs.px4.io/en/flight_modes/hold.html). A multicopter should just hover at the spot while a fixedwing vehicle should loiter around the location where it paused.

**Parameters**

* [result_callback_t](classdronecode__sdk_1_1_mission.md#classdronecode__sdk_1_1_mission_1adab3125b28a8d7b7ed90a81ea56b0115) **callback** - Callback to receive result of this request.

### set_current_mission_item_async() {#classdronecode__sdk_1_1_mission_1a48410e3f4e104d9db139418d9200c560}
```cpp
void dronecode_sdk::Mission::set_current_mission_item_async(int current, result_callback_t callback)
```


Sets the mission item index to go to (asynchronous).

By setting the current index to 0, the mission is restarted from the beginning. If it is set to a specific index of a mission item, the mission will be set to this item.


Note that this is not necessarily true for general missions using MAVLink if loop counters are used.

**Parameters**

* int **current** - Index for mission index to go to next (0 based).
* [result_callback_t](classdronecode__sdk_1_1_mission.md#classdronecode__sdk_1_1_mission_1adab3125b28a8d7b7ed90a81ea56b0115) **callback** - Callback to receive result of this request.

### mission_finished() {#classdronecode__sdk_1_1_mission_1a0ee8f797121687152529a7ebf054e3f0}
```cpp
bool dronecode_sdk::Mission::mission_finished() const
```


Checks if mission has been finished (synchronous).


**Returns**

&emsp;bool - true if mission is finished and the last mission item has been reached.

### current_mission_item() {#classdronecode__sdk_1_1_mission_1a1a58040494426a318828621177c455d2}
```cpp
int dronecode_sdk::Mission::current_mission_item() const
```


Returns the current mission item index (synchronous).

If the mission is finished, the current mission item will be the total number of mission items (so the last mission item index + 1).

**Returns**

&emsp;int - current mission item index (0 based).

### total_mission_items() {#classdronecode__sdk_1_1_mission_1a5ff976af79aa39a0d388b535bc508e20}
```cpp
int dronecode_sdk::Mission::total_mission_items() const
```


Returns the total number of mission items (synchronous).


**Returns**

&emsp;int - total number of mission items

### subscribe_progress() {#classdronecode__sdk_1_1_mission_1a319eeb2918a24e2f0dcb8ffbf0f84685}
```cpp
void dronecode_sdk::Mission::subscribe_progress(progress_callback_t callback)
```


Subscribes to mission progress (asynchronous).


**Parameters**

* [progress_callback_t](classdronecode__sdk_1_1_mission.md#classdronecode__sdk_1_1_mission_1ab2fefd005c7c1f420ddcc32cba046760) **callback** - Callback to receive mission progress.

### operator=() {#classdronecode__sdk_1_1_mission_1a01b702ceeeb9c4673c763fcf7d2a2c36}
```cpp
const Mission& dronecode_sdk::Mission::operator=(const Mission &)=delete
```


Equality operator (object is not copyable).


**Parameters**

* const [Mission](classdronecode__sdk_1_1_mission.md)&  - 

**Returns**

&emsp;const [Mission](classdronecode__sdk_1_1_mission.md) & - 

### result_str() {#classdronecode__sdk_1_1_mission_1ae8a4e4af6ae0d2485837afb88f2e66b1}
```cpp
static const char* dronecode_sdk::Mission::result_str(Result result)
```


Gets a human-readable English string for an [Mission::Result](classdronecode__sdk_1_1_mission.md#classdronecode__sdk_1_1_mission_1a819b8fdcf5a49f76e690c2c16adf572d).


**Parameters**

* [Result](classdronecode__sdk_1_1_mission.md#classdronecode__sdk_1_1_mission_1a819b8fdcf5a49f76e690c2c16adf572d) **result** - Enum for which string is required.

**Returns**

&emsp;const char * - Human readable string for the [Mission::Result](classdronecode__sdk_1_1_mission.md#classdronecode__sdk_1_1_mission_1a819b8fdcf5a49f76e690c2c16adf572d).

### import_qgroundcontrol_mission() {#classdronecode__sdk_1_1_mission_1a326d3ef45f0080e543ef5f1832246c5f}
```cpp
static Result dronecode_sdk::Mission::import_qgroundcontrol_mission(mission_items_t &mission_items, const std::string &qgc_plan_file)
```


Imports a **QGroundControl** (QGC) mission plan.

The method composes the plan into a vector of [MissionItem](classdronecode__sdk_1_1_mission_item.md) shared pointers that can then be uploaded to a vehicle. The method will fail if any of the imported mission items are not supported by the Dronecode SDK API.

**Parameters**

* [mission_items_t](classdronecode__sdk_1_1_mission.md#classdronecode__sdk_1_1_mission_1a4ceae9b6eda5553b91c47e0c5b94f1ec)& **mission_items** - Vector of mission items imported from QGC plan.
* const std::string& **qgc_plan_file** - File path of the QGC plan.

**Returns**

&emsp;[Result](classdronecode__sdk_1_1_mission.md#classdronecode__sdk_1_1_mission_1a819b8fdcf5a49f76e690c2c16adf572d) - [Result::SUCCESS](classdronecode__sdk_1_1_mission.md#classdronecode__sdk_1_1_mission_1a819b8fdcf5a49f76e690c2c16adf572dad0749aaba8b833466dfcbb0428e4f89c) if successful in importing QGC mission items. Otherwise one of the error codes: [Result::FAILED_TO_OPEN_QGC_PLAN](classdronecode__sdk_1_1_mission.md#classdronecode__sdk_1_1_mission_1a819b8fdcf5a49f76e690c2c16adf572da44090b5626a9be3103d4e3624470635c), [Result::FAILED_TO_PARSE_QGC_PLAN](classdronecode__sdk_1_1_mission.md#classdronecode__sdk_1_1_mission_1a819b8fdcf5a49f76e690c2c16adf572da503c552313ebdaf4cd93b1e5b5525a4f), [Result::UNSUPPORTED_MISSION_CMD](classdronecode__sdk_1_1_mission.md#classdronecode__sdk_1_1_mission_1a819b8fdcf5a49f76e690c2c16adf572da0118056c7c9e890a242c9bdb961dac82).

**See Also:**
- [QGroundControl Plan file format](https://dev.qgroundcontrol.com/en/file_formats/plan.html) (QGroundControl Dev Guide)

