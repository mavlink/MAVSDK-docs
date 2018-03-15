# dronecore::Mission Class Reference
`#include: mission.h`

----


The [Mission](classdronecore_1_1_mission.md) class enables waypoint missions. 


## Public Types


Type | Description
--- | ---
enum [Result](#classdronecore_1_1_mission_1a529b17f5b63508494ca22fc247598cda) | Possible results returned for mission requests.
std::function< void([Result](classdronecore_1_1_mission.md#classdronecore_1_1_mission_1a529b17f5b63508494ca22fc247598cda))> [result_callback_t](#classdronecore_1_1_mission_1a239f8d5853785d6ccf90c8c48b5ccf06) | Callback type for async mission calls.
std::vector< std::shared_ptr< [MissionItem](classdronecore_1_1_mission_item.md) > > [mission_items_t](#classdronecore_1_1_mission_1aeedbc1d50fec7304f0d140ce9748a5e2) | Type for vector of mission items.
std::function< void([Result](classdronecore_1_1_mission.md#classdronecore_1_1_mission_1a529b17f5b63508494ca22fc247598cda), std::vector< std::shared_ptr< [MissionItem](classdronecore_1_1_mission_item.md) > >)> [mission_items_and_result_callback_t](#classdronecore_1_1_mission_1a7cb36c0356a867e90f3c4c764d424d32) | Callback type for [download_mission_async()](classdronecore_1_1_mission.md#classdronecore_1_1_mission_1a1bd15f508fe7da39b587a8e4d5e59ae2) call to get mission items and result.
std::function< void(int current, int total)> [progress_callback_t](#classdronecore_1_1_mission_1aeda7795cd898008afc05b779f99b704b) | Callback type to receive mission progress.

## Public Member Functions


Type | Name | Description
---: | --- | ---
&nbsp; | [Mission](#classdronecore_1_1_mission_1a8af8e71979b15c73ced7fa2d5a6f6894) ([Device](classdronecore_1_1_device.md) & device) | Constructor. Creates the plugin for a specific [Device](classdronecore_1_1_device.md).
&nbsp; | [~Mission](#classdronecore_1_1_mission_1a395b8c121630aa8a5dd3d48f95290659) () | Destructor (internal use only).
&nbsp; | [Mission](#classdronecore_1_1_mission_1a4947f79b7dd71e66bca64e5bbb0b3377) (const [Mission](classdronecore_1_1_mission.md) &)=delete | Copy constructor (object is not copyable).
void | [upload_mission_async](#classdronecore_1_1_mission_1a414b5b6d0c66af695a725e92003872b5) (const std::vector< std::shared_ptr< [MissionItem](classdronecore_1_1_mission_item.md) >> & mission_items, [result_callback_t](classdronecore_1_1_mission.md#classdronecore_1_1_mission_1a239f8d5853785d6ccf90c8c48b5ccf06) callback) | Uploads a vector of mission items to the device (asynchronous).
void | [download_mission_async](#classdronecore_1_1_mission_1a1bd15f508fe7da39b587a8e4d5e59ae2) ([mission_items_and_result_callback_t](classdronecore_1_1_mission.md#classdronecore_1_1_mission_1a7cb36c0356a867e90f3c4c764d424d32) callback) | Downloads a vector of mission items from the device (asynchronous).
void | [start_mission_async](#classdronecore_1_1_mission_1a9e032c6b2bc35cf6e7e19e07747fb0d3) ([result_callback_t](classdronecore_1_1_mission.md#classdronecore_1_1_mission_1a239f8d5853785d6ccf90c8c48b5ccf06) callback) | Starts the mission (asynchronous).
void | [pause_mission_async](#classdronecore_1_1_mission_1a65f729cf954586507ecd8dc07a510dd1) ([result_callback_t](classdronecore_1_1_mission.md#classdronecore_1_1_mission_1a239f8d5853785d6ccf90c8c48b5ccf06) callback) | Pauses the mission (asynchronous).
void | [set_current_mission_item_async](#classdronecore_1_1_mission_1af8d06941d424d57bcc2b55f8f9a2ea27) (int current, [result_callback_t](classdronecore_1_1_mission.md#classdronecore_1_1_mission_1a239f8d5853785d6ccf90c8c48b5ccf06) callback) | Sets the mission item index to go to (asynchronous).
bool | [mission_finished](#classdronecore_1_1_mission_1abf3463efaa18147a1c179e7449503829) () const | Checks if mission has been finished (synchronous).
int | [current_mission_item](#classdronecore_1_1_mission_1a1faa448b32cd0028923b22de0cc78e9c) () const | Returns the current mission item index (synchronous).
int | [total_mission_items](#classdronecore_1_1_mission_1a9d2195ec1af301c51002f8cb99aa22e9) () const | Returns the total number of mission items (synchronous).
void | [subscribe_progress](#classdronecore_1_1_mission_1a3290fc79eb22f899528328adfca48a61) ([progress_callback_t](classdronecore_1_1_mission.md#classdronecore_1_1_mission_1aeda7795cd898008afc05b779f99b704b) callback) | Subscribes to mission progress (asynchronous).
const [Mission](classdronecore_1_1_mission.md) & | [operator=](#classdronecore_1_1_mission_1ae946abaf32a30cb0b803a145f095217d) (const [Mission](classdronecore_1_1_mission.md) &)=delete | Equality operator (object is not copyable).

## Static Public Member Functions


Type | Name | Description
---: | --- | ---
const char * | [result_str](#classdronecore_1_1_mission_1a0eabb2fe4db664c552d28161678c593f) ([Result](classdronecore_1_1_mission.md#classdronecore_1_1_mission_1a529b17f5b63508494ca22fc247598cda) result) | Gets a human-readable English string for an [Mission::Result](classdronecore_1_1_mission.md#classdronecore_1_1_mission_1a529b17f5b63508494ca22fc247598cda).
[Result](classdronecore_1_1_mission.md#classdronecore_1_1_mission_1a529b17f5b63508494ca22fc247598cda) | [import_qgroundcontrol_mission](#classdronecore_1_1_mission_1a7c73e97e5c1395a7451bb659d03e5f57) ([mission_items_t](classdronecore_1_1_mission.md#classdronecore_1_1_mission_1aeedbc1d50fec7304f0d140ce9748a5e2) & mission_items, const std::string & qgc_plan_file) | Imports a **QGroundControl** (QGC) mission plan.


## Constructor & Destructor Documentation


### Mission() {#classdronecore_1_1_mission_1a8af8e71979b15c73ced7fa2d5a6f6894}
```cpp
dronecore::Mission::Mission(Device &device)
```


Constructor. Creates the plugin for a specific [Device](classdronecore_1_1_device.md).

The plugin is typically created as shown below: 

```cpp
auto mission = std::make_shared<Mission>(device);
```

**Parameters**

* [Device](classdronecore_1_1_device.md) & **device** - The specific device associated with this plugin.

### ~Mission() {#classdronecore_1_1_mission_1a395b8c121630aa8a5dd3d48f95290659}
```cpp
dronecore::Mission::~Mission()
```


Destructor (internal use only).


### Mission() {#classdronecore_1_1_mission_1a4947f79b7dd71e66bca64e5bbb0b3377}
```cpp
dronecore::Mission::Mission(const Mission &)=delete
```


Copy constructor (object is not copyable).


**Parameters**

* const [Mission](classdronecore_1_1_mission.md) & - 

## Member Typdef Documentation


### typedef result_callback_t {#classdronecore_1_1_mission_1a239f8d5853785d6ccf90c8c48b5ccf06}

```cpp
typedef std::function<void(Result)> dronecore::Mission::result_callback_t
```


Callback type for async mission calls.


### typedef mission_items_t {#classdronecore_1_1_mission_1aeedbc1d50fec7304f0d140ce9748a5e2}

```cpp
typedef std::vector<std::shared_ptr<MissionItem> > dronecore::Mission::mission_items_t
```


Type for vector of mission items.


### typedef mission_items_and_result_callback_t {#classdronecore_1_1_mission_1a7cb36c0356a867e90f3c4c764d424d32}

```cpp
typedef std::function<void(Result, std::vector<std::shared_ptr<MissionItem> >)> dronecore::Mission::mission_items_and_result_callback_t
```


Callback type for [download_mission_async()](classdronecore_1_1_mission.md#classdronecore_1_1_mission_1a1bd15f508fe7da39b587a8e4d5e59ae2) call to get mission items and result.


### typedef progress_callback_t {#classdronecore_1_1_mission_1aeda7795cd898008afc05b779f99b704b}

```cpp
typedef std::function<void(int current, int total)> dronecore::Mission::progress_callback_t
```


Callback type to receive mission progress.

The mission is finished if current == total.

**Parameters**

* **current** - Current mission item index (0 based).
* **total** - Total number of mission items.

## Member Enumeration Documentation


### enum Result {#classdronecore_1_1_mission_1a529b17f5b63508494ca22fc247598cda}


Possible results returned for mission requests.


Value | Description
--- | ---
<span id="classdronecore_1_1_mission_1a529b17f5b63508494ca22fc247598cdaad0749aaba8b833466dfcbb0428e4f89c"></span> `SUCCESS` | Request succeeded. 
<span id="classdronecore_1_1_mission_1a529b17f5b63508494ca22fc247598cdaabb1ca97ec761fc37101737ba0aa2e7c5"></span> `ERROR` | Error. 
<span id="classdronecore_1_1_mission_1a529b17f5b63508494ca22fc247598cdaab6968a2ae2835d0d36126e1d12e5d1a1"></span> `TOO_MANY_MISSION_ITEMS` | Too many [MissionItem](classdronecore_1_1_mission_item.md) objects in the mission. 
<span id="classdronecore_1_1_mission_1a529b17f5b63508494ca22fc247598cdaa802706a9238e2928077f97736854bad4"></span> `BUSY` | Vehicle busy. 
<span id="classdronecore_1_1_mission_1a529b17f5b63508494ca22fc247598cdaa070a0fb40f6c308ab544b227660aadff"></span> `TIMEOUT` | Request timed out. 
<span id="classdronecore_1_1_mission_1a529b17f5b63508494ca22fc247598cdaaf295a0c3e37c94f078e1c5476479132d"></span> `INVALID_ARGUMENT` | Invalid argument. 
<span id="classdronecore_1_1_mission_1a529b17f5b63508494ca22fc247598cdaa40aa75f8e8cfdf7b660c5620e953229f"></span> `UNSUPPORTED` | The mission downloaded from the device is not supported. 
<span id="classdronecore_1_1_mission_1a529b17f5b63508494ca22fc247598cdaa1d25c4b5260709868a0c57ae60ae815e"></span> `NO_MISSION_AVAILABLE` | No mission available on device. 
<span id="classdronecore_1_1_mission_1a529b17f5b63508494ca22fc247598cdaa44090b5626a9be3103d4e3624470635c"></span> `FAILED_TO_OPEN_QGC_PLAN` | Failed to open QGroundControl plan. 
<span id="classdronecore_1_1_mission_1a529b17f5b63508494ca22fc247598cdaa503c552313ebdaf4cd93b1e5b5525a4f"></span> `FAILED_TO_PARSE_QGC_PLAN` | Failed to parse QGroundControl plan. 
<span id="classdronecore_1_1_mission_1a529b17f5b63508494ca22fc247598cdaa0118056c7c9e890a242c9bdb961dac82"></span> `UNSUPPORTED_MISSION_CMD` | Unsupported mission command. 
<span id="classdronecore_1_1_mission_1a529b17f5b63508494ca22fc247598cdaa696b031073e74bf2cb98e5ef201d4aa3"></span> `UNKNOWN` | Unknown error. 

## Member Function Documentation


### upload_mission_async() {#classdronecore_1_1_mission_1a414b5b6d0c66af695a725e92003872b5}
```cpp
void dronecore::Mission::upload_mission_async(const std::vector< std::shared_ptr< MissionItem >> &mission_items, result_callback_t callback)
```


Uploads a vector of mission items to the device (asynchronous).

The mission items are uploaded to a drone. Once uploaded the mission can be started and executed even if a connection is lost.

**Parameters**

* const std::vector< std::shared_ptr< [MissionItem](classdronecore_1_1_mission_item.md) >> & **mission_items** - Reference to vector of mission items.
* [result_callback_t](classdronecore_1_1_mission.md#classdronecore_1_1_mission_1a239f8d5853785d6ccf90c8c48b5ccf06) **callback** - Callback to receive result of this request.

### download_mission_async() {#classdronecore_1_1_mission_1a1bd15f508fe7da39b587a8e4d5e59ae2}
```cpp
void dronecore::Mission::download_mission_async(mission_items_and_result_callback_t callback)
```


Downloads a vector of mission items from the device (asynchronous).

The method will fail if any of the downloaded mission items are not supported by the [DroneCore](classdronecore_1_1_drone_core.md) API.

**Parameters**

* [mission_items_and_result_callback_t](classdronecore_1_1_mission.md#classdronecore_1_1_mission_1a7cb36c0356a867e90f3c4c764d424d32) **callback** - Callback to receive mission items and result of this request.

### start_mission_async() {#classdronecore_1_1_mission_1a9e032c6b2bc35cf6e7e19e07747fb0d3}
```cpp
void dronecore::Mission::start_mission_async(result_callback_t callback)
```


Starts the mission (asynchronous).

Note that the mission must be uploaded to the vehicle using [upload_mission_async()](classdronecore_1_1_mission.md#classdronecore_1_1_mission_1a414b5b6d0c66af695a725e92003872b5) before this method is called.

**Parameters**

* [result_callback_t](classdronecore_1_1_mission.md#classdronecore_1_1_mission_1a239f8d5853785d6ccf90c8c48b5ccf06) **callback** - callback to receive result of this request.

### pause_mission_async() {#classdronecore_1_1_mission_1a65f729cf954586507ecd8dc07a510dd1}
```cpp
void dronecore::Mission::pause_mission_async(result_callback_t callback)
```


Pauses the mission (asynchronous).

Pausing the mission puts the vehicle into [HOLD mode](https://docs.px4.io/en/flight_modes/hold.html). A multicopter should just hover at the spot while a fixedwing vehicle should loiter around the location where it paused.

**Parameters**

* [result_callback_t](classdronecore_1_1_mission.md#classdronecore_1_1_mission_1a239f8d5853785d6ccf90c8c48b5ccf06) **callback** - Callback to receive result of this request.

### set_current_mission_item_async() {#classdronecore_1_1_mission_1af8d06941d424d57bcc2b55f8f9a2ea27}
```cpp
void dronecore::Mission::set_current_mission_item_async(int current, result_callback_t callback)
```


Sets the mission item index to go to (asynchronous).

By setting the current index to 0, the mission is restarted from the beginning. If it is set to a specific index of a mission item, the mission will be set to this item.


Note that this is not necessarily true for general missions using MAVLink if loop counters are used.

**Parameters**

* int **current** - Index for mission index to go to next (0 based).
* [result_callback_t](classdronecore_1_1_mission.md#classdronecore_1_1_mission_1a239f8d5853785d6ccf90c8c48b5ccf06) **callback** - Callback to receive result of this request.

### mission_finished() {#classdronecore_1_1_mission_1abf3463efaa18147a1c179e7449503829}
```cpp
bool dronecore::Mission::mission_finished() const
```


Checks if mission has been finished (synchronous).


**Returns**

&emsp;bool - true if mission is finished and the last mission item has been reached.

### current_mission_item() {#classdronecore_1_1_mission_1a1faa448b32cd0028923b22de0cc78e9c}
```cpp
int dronecore::Mission::current_mission_item() const
```


Returns the current mission item index (synchronous).

If the mission is finished, the current mission item will be the total number of mission items (so the last mission item index + 1).

**Returns**

&emsp;int - current mission item index (0 based).

### total_mission_items() {#classdronecore_1_1_mission_1a9d2195ec1af301c51002f8cb99aa22e9}
```cpp
int dronecore::Mission::total_mission_items() const
```


Returns the total number of mission items (synchronous).


**Returns**

&emsp;int - total number of mission items

### subscribe_progress() {#classdronecore_1_1_mission_1a3290fc79eb22f899528328adfca48a61}
```cpp
void dronecore::Mission::subscribe_progress(progress_callback_t callback)
```


Subscribes to mission progress (asynchronous).


**Parameters**

* [progress_callback_t](classdronecore_1_1_mission.md#classdronecore_1_1_mission_1aeda7795cd898008afc05b779f99b704b) **callback** - Callback to receive mission progress.

### operator=() {#classdronecore_1_1_mission_1ae946abaf32a30cb0b803a145f095217d}
```cpp
const Mission& dronecore::Mission::operator=(const Mission &)=delete
```


Equality operator (object is not copyable).


**Parameters**

* const [Mission](classdronecore_1_1_mission.md) & - 

**Returns**

&emsp;const [Mission](classdronecore_1_1_mission.md) & - 

### result_str() {#classdronecore_1_1_mission_1a0eabb2fe4db664c552d28161678c593f}
```cpp
static const char* dronecore::Mission::result_str(Result result)
```


Gets a human-readable English string for an [Mission::Result](classdronecore_1_1_mission.md#classdronecore_1_1_mission_1a529b17f5b63508494ca22fc247598cda).


**Parameters**

* [Result](classdronecore_1_1_mission.md#classdronecore_1_1_mission_1a529b17f5b63508494ca22fc247598cda) **result** - Enum for which string is required.

**Returns**

&emsp;const char * - Human readable string for the [Mission::Result](classdronecore_1_1_mission.md#classdronecore_1_1_mission_1a529b17f5b63508494ca22fc247598cda).

### import_qgroundcontrol_mission() {#classdronecore_1_1_mission_1a7c73e97e5c1395a7451bb659d03e5f57}
```cpp
static Result dronecore::Mission::import_qgroundcontrol_mission(mission_items_t &mission_items, const std::string &qgc_plan_file)
```


Imports a **QGroundControl** (QGC) mission plan.

The method composes the plan into a vector of [MissionItem](classdronecore_1_1_mission_item.md) shared pointers that can then be uploaded to a vehicle. The method will fail if any of the imported mission items are not supported by the DroneCore API.

**Parameters**

* [mission_items_t](classdronecore_1_1_mission.md#classdronecore_1_1_mission_1aeedbc1d50fec7304f0d140ce9748a5e2) & **mission_items** - Vector of mission items imported from QGC plan.
* const std::string & **qgc_plan_file** - File path of the QGC plan.

**Returns**

&emsp;[Result](classdronecore_1_1_mission.md#classdronecore_1_1_mission_1a529b17f5b63508494ca22fc247598cda) - [Result::SUCCESS](classdronecore_1_1_mission.md#classdronecore_1_1_mission_1a529b17f5b63508494ca22fc247598cdaad0749aaba8b833466dfcbb0428e4f89c) if successful in importing QGC mission items. Otherwise one of the error codes: [Result::FAILED_TO_OPEN_QGC_PLAN](classdronecore_1_1_mission.md#classdronecore_1_1_mission_1a529b17f5b63508494ca22fc247598cdaa44090b5626a9be3103d4e3624470635c), [Result::FAILED_TO_PARSE_QGC_PLAN](classdronecore_1_1_mission.md#classdronecore_1_1_mission_1a529b17f5b63508494ca22fc247598cdaa503c552313ebdaf4cd93b1e5b5525a4f), [Result::UNSUPPORTED_MISSION_CMD](classdronecore_1_1_mission.md#classdronecore_1_1_mission_1a529b17f5b63508494ca22fc247598cdaa0118056c7c9e890a242c9bdb961dac82).

**See Also:**
- [QGroundControl Plan file format](https://dev.qgroundcontrol.com/en/file_formats/plan.html) (QGroundControl Dev Guide)

