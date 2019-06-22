# mavsdk::MissionRaw Class Reference
`#include: mission_raw.h`

----


The [MissionRaw](classmavsdk_1_1_mission_raw.md) class enables direct access to MAVLink mission items. 


This plugin gives direct access to the MAVLink mission protocol which means full control over waypoints and waypoint actions/commands. However, this means that not all functionality provided is actually implemented or correctly supported by a flight controller.


For a tested, simpler subset in mission functionality, it is recommended to use the [Mission](classmavsdk_1_1_mission.md) plugin.


> **Note** Currently, only downloading the mission items is implemented, uploading could be added in the future if required.


## Data Structures


struct [MavlinkMissionItemInt](structmavsdk_1_1_mission_raw_1_1_mavlink_mission_item_int.md)

## Public Types


Type | Description
--- | ---
enum [Result](#classmavsdk_1_1_mission_raw_1a7ea2a624818ebb5a3e209cc275d58eaf) | Possible results returned for mission requests.
std::function< void([Result](classmavsdk_1_1_mission_raw.md#classmavsdk_1_1_mission_raw_1a7ea2a624818ebb5a3e209cc275d58eaf), std::vector< std::shared_ptr< [MavlinkMissionItemInt](structmavsdk_1_1_mission_raw_1_1_mavlink_mission_item_int.md) > >)> [mission_items_and_result_callback_t](#classmavsdk_1_1_mission_raw_1aaa9039b205df27b10ade1ea08de459f8) | Type for vector of mission items.
std::function< void()> [mission_changed_callback_t](#classmavsdk_1_1_mission_raw_1a73cd21daf1e6b365ef0f67c4a65300d5) | Callback type to signal if the mission has changed.

## Public Member Functions


Type | Name | Description
---: | --- | ---
&nbsp; | [MissionRaw](#classmavsdk_1_1_mission_raw_1ad03476f12988a12808a8c4385c7a7344) ([System](classmavsdk_1_1_system.md) & system) | Constructor. Creates the plugin for a specific [System](classmavsdk_1_1_system.md).
&nbsp; | [~MissionRaw](#classmavsdk_1_1_mission_raw_1a366afae5d3c7c2345e3ecec26ff9e307) () | Destructor (internal use only).
&nbsp; | [MissionRaw](#classmavsdk_1_1_mission_raw_1a6a98ba999d8fa548b45f031f372fdfe9) (const [MissionRaw](classmavsdk_1_1_mission_raw.md) &)=delete | Copy constructor (object is not copyable).
void | [download_mission_async](#classmavsdk_1_1_mission_raw_1a76d7710e3f84dea907a12425057f30cb) ([mission_items_and_result_callback_t](classmavsdk_1_1_mission_raw.md#classmavsdk_1_1_mission_raw_1aaa9039b205df27b10ade1ea08de459f8) callback) | Downloads a vector of mission items from the system (asynchronous).
void | [download_mission_cancel](#classmavsdk_1_1_mission_raw_1abc80a9b7e5066441110df803027381b9) () | Cancel a mission download (asynchronous).
void | [subscribe_mission_changed](#classmavsdk_1_1_mission_raw_1aade4b95d43b7acaee2bf1b66bb2e2c3a) ([mission_changed_callback_t](classmavsdk_1_1_mission_raw.md#classmavsdk_1_1_mission_raw_1a73cd21daf1e6b365ef0f67c4a65300d5) callback) | Subscribes to mission progress (asynchronous).
const [MissionRaw](classmavsdk_1_1_mission_raw.md) & | [operator=](#classmavsdk_1_1_mission_raw_1a0cfdf21bad5478c91cf18207b6a21ad3) (const [MissionRaw](classmavsdk_1_1_mission_raw.md) &)=delete | Equality operator (object is not copyable).

## Static Public Member Functions


Type | Name | Description
---: | --- | ---
const char * | [result_str](#classmavsdk_1_1_mission_raw_1a3e77569c665ced340dde2e675bce5140) ([Result](classmavsdk_1_1_mission_raw.md#classmavsdk_1_1_mission_raw_1a7ea2a624818ebb5a3e209cc275d58eaf) result) | Gets a human-readable English string for an [MissionRaw::Result](classmavsdk_1_1_mission_raw.md#classmavsdk_1_1_mission_raw_1a7ea2a624818ebb5a3e209cc275d58eaf).


## Constructor & Destructor Documentation


### MissionRaw() {#classmavsdk_1_1_mission_raw_1ad03476f12988a12808a8c4385c7a7344}
```cpp
mavsdk::MissionRaw::MissionRaw(System &system)
```


Constructor. Creates the plugin for a specific [System](classmavsdk_1_1_system.md).

The plugin is typically created as shown below: 

```cpp
auto mission_raw = std::make_shared<MissionRaw>(system);
```

**Parameters**

* [System](classmavsdk_1_1_system.md)& **system** - The specific system associated with this plugin.

### ~MissionRaw() {#classmavsdk_1_1_mission_raw_1a366afae5d3c7c2345e3ecec26ff9e307}
```cpp
mavsdk::MissionRaw::~MissionRaw()
```


Destructor (internal use only).


### MissionRaw() {#classmavsdk_1_1_mission_raw_1a6a98ba999d8fa548b45f031f372fdfe9}
```cpp
mavsdk::MissionRaw::MissionRaw(const MissionRaw &)=delete
```


Copy constructor (object is not copyable).


**Parameters**

* const [MissionRaw](classmavsdk_1_1_mission_raw.md)&  - 

## Member Typdef Documentation


### typedef mission_items_and_result_callback_t {#classmavsdk_1_1_mission_raw_1aaa9039b205df27b10ade1ea08de459f8}

```cpp
typedef std::function<void(Result, std::vector<std::shared_ptr<MavlinkMissionItemInt> >)> mavsdk::MissionRaw::mission_items_and_result_callback_t
```


Type for vector of mission items.


### typedef mission_changed_callback_t {#classmavsdk_1_1_mission_raw_1a73cd21daf1e6b365ef0f67c4a65300d5}

```cpp
typedef std::function<void()> mavsdk::MissionRaw::mission_changed_callback_t
```


Callback type to signal if the mission has changed.


## Member Enumeration Documentation


### enum Result {#classmavsdk_1_1_mission_raw_1a7ea2a624818ebb5a3e209cc275d58eaf}


Possible results returned for mission requests.


Value | Description
--- | ---
<span id="classmavsdk_1_1_mission_raw_1a7ea2a624818ebb5a3e209cc275d58eafa696b031073e74bf2cb98e5ef201d4aa3"></span> `UNKNOWN` | Unknown error. 
<span id="classmavsdk_1_1_mission_raw_1a7ea2a624818ebb5a3e209cc275d58eafad0749aaba8b833466dfcbb0428e4f89c"></span> `SUCCESS` | Request succeeded. 
<span id="classmavsdk_1_1_mission_raw_1a7ea2a624818ebb5a3e209cc275d58eafabb1ca97ec761fc37101737ba0aa2e7c5"></span> `ERROR` | Error. 
<span id="classmavsdk_1_1_mission_raw_1a7ea2a624818ebb5a3e209cc275d58eafa802706a9238e2928077f97736854bad4"></span> `BUSY` | Vehicle busy. 
<span id="classmavsdk_1_1_mission_raw_1a7ea2a624818ebb5a3e209cc275d58eafa070a0fb40f6c308ab544b227660aadff"></span> `TIMEOUT` | Request timed out. 
<span id="classmavsdk_1_1_mission_raw_1a7ea2a624818ebb5a3e209cc275d58eafaf295a0c3e37c94f078e1c5476479132d"></span> `INVALID_ARGUMENT` | Invalid argument. 
<span id="classmavsdk_1_1_mission_raw_1a7ea2a624818ebb5a3e209cc275d58eafa1d25c4b5260709868a0c57ae60ae815e"></span> `NO_MISSION_AVAILABLE` | No mission available on system. 
<span id="classmavsdk_1_1_mission_raw_1a7ea2a624818ebb5a3e209cc275d58eafa9f935beb31030ad0d4d26126c0f39bf2"></span> `CANCELLED` | [Mission](classmavsdk_1_1_mission.md) upload or download has been cancelled. 

## Member Function Documentation


### download_mission_async() {#classmavsdk_1_1_mission_raw_1a76d7710e3f84dea907a12425057f30cb}
```cpp
void mavsdk::MissionRaw::download_mission_async(mission_items_and_result_callback_t callback)
```


Downloads a vector of mission items from the system (asynchronous).

The method will fail if any of the downloaded mission items are not supported by the Dronecode SDK API.

**Parameters**

* [mission_items_and_result_callback_t](classmavsdk_1_1_mission_raw.md#classmavsdk_1_1_mission_raw_1aaa9039b205df27b10ade1ea08de459f8) **callback** - Callback to receive mission items and result of this request.

### download_mission_cancel() {#classmavsdk_1_1_mission_raw_1abc80a9b7e5066441110df803027381b9}
```cpp
void mavsdk::MissionRaw::download_mission_cancel()
```


Cancel a mission download (asynchronous).

This cancels an ongoing mission download. The mission download will fail with the result [Result::CANCELLED](classmavsdk_1_1_mission_raw.md#classmavsdk_1_1_mission_raw_1a7ea2a624818ebb5a3e209cc275d58eafa9f935beb31030ad0d4d26126c0f39bf2).

### subscribe_mission_changed() {#classmavsdk_1_1_mission_raw_1aade4b95d43b7acaee2bf1b66bb2e2c3a}
```cpp
void mavsdk::MissionRaw::subscribe_mission_changed(mission_changed_callback_t callback)
```


Subscribes to mission progress (asynchronous).


**Parameters**

* [mission_changed_callback_t](classmavsdk_1_1_mission_raw.md#classmavsdk_1_1_mission_raw_1a73cd21daf1e6b365ef0f67c4a65300d5) **callback** - Callback to receive mission progress.

### operator=() {#classmavsdk_1_1_mission_raw_1a0cfdf21bad5478c91cf18207b6a21ad3}
```cpp
const MissionRaw& mavsdk::MissionRaw::operator=(const MissionRaw &)=delete
```


Equality operator (object is not copyable).


**Parameters**

* const [MissionRaw](classmavsdk_1_1_mission_raw.md)&  - 

**Returns**

&emsp;const [MissionRaw](classmavsdk_1_1_mission_raw.md) & - 

### result_str() {#classmavsdk_1_1_mission_raw_1a3e77569c665ced340dde2e675bce5140}
```cpp
static const char* mavsdk::MissionRaw::result_str(Result result)
```


Gets a human-readable English string for an [MissionRaw::Result](classmavsdk_1_1_mission_raw.md#classmavsdk_1_1_mission_raw_1a7ea2a624818ebb5a3e209cc275d58eaf).


**Parameters**

* [Result](classmavsdk_1_1_mission_raw.md#classmavsdk_1_1_mission_raw_1a7ea2a624818ebb5a3e209cc275d58eaf) **result** - Enum for which string is required.

**Returns**

&emsp;const char * - Human readable string for the [MissionRaw::Result](classmavsdk_1_1_mission_raw.md#classmavsdk_1_1_mission_raw_1a7ea2a624818ebb5a3e209cc275d58eaf).