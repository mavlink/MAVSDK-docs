# dronecode_sdk::MissionRaw Class Reference
`#include: mission_raw.h`

----


The [MissionRaw](classdronecode__sdk_1_1_mission_raw.md) class enables direct direct access to MAVLink mission items. 


## Data Structures


struct [MavlinkMissionItemInt](structdronecode__sdk_1_1_mission_raw_1_1_mavlink_mission_item_int.md)

## Public Types


Type | Description
--- | ---
enum [Result](#classdronecode__sdk_1_1_mission_raw_1a82e84d835ef6d2436ddf3ae735edcd07) | Possible results returned for mission requests.
std::function< void([Result](classdronecode__sdk_1_1_mission_raw.md#classdronecode__sdk_1_1_mission_raw_1a82e84d835ef6d2436ddf3ae735edcd07), std::vector< std::shared_ptr< [MavlinkMissionItemInt](structdronecode__sdk_1_1_mission_raw_1_1_mavlink_mission_item_int.md) > >)> [mission_items_and_result_callback_t](#classdronecode__sdk_1_1_mission_raw_1ad56cffb012161723b38a9ccffa812382) | Type for vector of mission items.
std::function< void()> [mission_changed_callback_t](#classdronecode__sdk_1_1_mission_raw_1ab882f6b08cc17126afbbb3a865b1cbde) | Callback type to signal if the mission has changed.

## Public Member Functions


Type | Name | Description
---: | --- | ---
&nbsp; | [MissionRaw](#classdronecode__sdk_1_1_mission_raw_1ae11f0a22c9153322bc114d753f3ae5b3) ([System](classdronecode__sdk_1_1_system.md) & system) | Constructor. Creates the plugin for a specific [System](classdronecode__sdk_1_1_system.md).
&nbsp; | [~MissionRaw](#classdronecode__sdk_1_1_mission_raw_1a17d17d117b998c55310d3b60e502a410) () | Destructor (internal use only).
&nbsp; | [MissionRaw](#classdronecode__sdk_1_1_mission_raw_1af2642e44f344990d1d08575ad9321332) (const [MissionRaw](classdronecode__sdk_1_1_mission_raw.md) &)=delete | Copy constructor (object is not copyable).
void | [download_mission_async](#classdronecode__sdk_1_1_mission_raw_1a3878846b6ee0fa55068d77850e446d45) ([mission_items_and_result_callback_t](classdronecode__sdk_1_1_mission_raw.md#classdronecode__sdk_1_1_mission_raw_1ad56cffb012161723b38a9ccffa812382) callback) | Downloads a vector of mission items from the system (asynchronous).
void | [download_mission_cancel](#classdronecode__sdk_1_1_mission_raw_1a3db03bbf14b8066005b85ac2deb0decf) () | Cancel a mission download (asynchronous).
void | [subscribe_mission_changed](#classdronecode__sdk_1_1_mission_raw_1aa0b3f0c4c82a3a045351b7f1819ad630) ([mission_changed_callback_t](classdronecode__sdk_1_1_mission_raw.md#classdronecode__sdk_1_1_mission_raw_1ab882f6b08cc17126afbbb3a865b1cbde) callback) | Subscribes to mission progress (asynchronous).
const [MissionRaw](classdronecode__sdk_1_1_mission_raw.md) & | [operator=](#classdronecode__sdk_1_1_mission_raw_1a1747ff89013691cb608ae287704e0e67) (const [MissionRaw](classdronecode__sdk_1_1_mission_raw.md) &)=delete | Equality operator (object is not copyable).

## Static Public Member Functions


Type | Name | Description
---: | --- | ---
const char * | [result_str](#classdronecode__sdk_1_1_mission_raw_1a305825a4853ebc662120f54f23393f06) ([Result](classdronecode__sdk_1_1_mission_raw.md#classdronecode__sdk_1_1_mission_raw_1a82e84d835ef6d2436ddf3ae735edcd07) result) | Gets a human-readable English string for an [MissionRaw::Result](classdronecode__sdk_1_1_mission_raw.md#classdronecode__sdk_1_1_mission_raw_1a82e84d835ef6d2436ddf3ae735edcd07).


## Constructor & Destructor Documentation


### MissionRaw() {#classdronecode__sdk_1_1_mission_raw_1ae11f0a22c9153322bc114d753f3ae5b3}
```cpp
dronecode_sdk::MissionRaw::MissionRaw(System &system)
```


Constructor. Creates the plugin for a specific [System](classdronecode__sdk_1_1_system.md).

The plugin is typically created as shown below: 

```cpp
auto mission_raw = std::make_shared<MissionRaw>(system);
```

**Parameters**

* [System](classdronecode__sdk_1_1_system.md)& **system** - The specific system associated with this plugin.

### ~MissionRaw() {#classdronecode__sdk_1_1_mission_raw_1a17d17d117b998c55310d3b60e502a410}
```cpp
dronecode_sdk::MissionRaw::~MissionRaw()
```


Destructor (internal use only).


### MissionRaw() {#classdronecode__sdk_1_1_mission_raw_1af2642e44f344990d1d08575ad9321332}
```cpp
dronecode_sdk::MissionRaw::MissionRaw(const MissionRaw &)=delete
```


Copy constructor (object is not copyable).


**Parameters**

* const [MissionRaw](classdronecode__sdk_1_1_mission_raw.md)&  - 

## Member Typdef Documentation


### typedef mission_items_and_result_callback_t {#classdronecode__sdk_1_1_mission_raw_1ad56cffb012161723b38a9ccffa812382}

```cpp
typedef std::function<void(Result, std::vector<std::shared_ptr<MavlinkMissionItemInt> >)> dronecode_sdk::MissionRaw::mission_items_and_result_callback_t
```


Type for vector of mission items.


### typedef mission_changed_callback_t {#classdronecode__sdk_1_1_mission_raw_1ab882f6b08cc17126afbbb3a865b1cbde}

```cpp
typedef std::function<void()> dronecode_sdk::MissionRaw::mission_changed_callback_t
```


Callback type to signal if the mission has changed.


## Member Enumeration Documentation


### enum Result {#classdronecode__sdk_1_1_mission_raw_1a82e84d835ef6d2436ddf3ae735edcd07}


Possible results returned for mission requests.


Value | Description
--- | ---
<span id="classdronecode__sdk_1_1_mission_raw_1a82e84d835ef6d2436ddf3ae735edcd07a696b031073e74bf2cb98e5ef201d4aa3"></span> `UNKNOWN` | Unknown error. 
<span id="classdronecode__sdk_1_1_mission_raw_1a82e84d835ef6d2436ddf3ae735edcd07ad0749aaba8b833466dfcbb0428e4f89c"></span> `SUCCESS` | Request succeeded. 
<span id="classdronecode__sdk_1_1_mission_raw_1a82e84d835ef6d2436ddf3ae735edcd07abb1ca97ec761fc37101737ba0aa2e7c5"></span> `ERROR` | Error. 
<span id="classdronecode__sdk_1_1_mission_raw_1a82e84d835ef6d2436ddf3ae735edcd07a802706a9238e2928077f97736854bad4"></span> `BUSY` | Vehicle busy. 
<span id="classdronecode__sdk_1_1_mission_raw_1a82e84d835ef6d2436ddf3ae735edcd07a070a0fb40f6c308ab544b227660aadff"></span> `TIMEOUT` | Request timed out. 
<span id="classdronecode__sdk_1_1_mission_raw_1a82e84d835ef6d2436ddf3ae735edcd07af295a0c3e37c94f078e1c5476479132d"></span> `INVALID_ARGUMENT` | Invalid argument. 
<span id="classdronecode__sdk_1_1_mission_raw_1a82e84d835ef6d2436ddf3ae735edcd07a1d25c4b5260709868a0c57ae60ae815e"></span> `NO_MISSION_AVAILABLE` | No mission available on system. 
<span id="classdronecode__sdk_1_1_mission_raw_1a82e84d835ef6d2436ddf3ae735edcd07a9f935beb31030ad0d4d26126c0f39bf2"></span> `CANCELLED` | [Mission](classdronecode__sdk_1_1_mission.md) upload or download has been cancelled. 

## Member Function Documentation


### download_mission_async() {#classdronecode__sdk_1_1_mission_raw_1a3878846b6ee0fa55068d77850e446d45}
```cpp
void dronecode_sdk::MissionRaw::download_mission_async(mission_items_and_result_callback_t callback)
```


Downloads a vector of mission items from the system (asynchronous).

The method will fail if any of the downloaded mission items are not supported by the Dronecode SDK API.

**Parameters**

* [mission_items_and_result_callback_t](classdronecode__sdk_1_1_mission_raw.md#classdronecode__sdk_1_1_mission_raw_1ad56cffb012161723b38a9ccffa812382) **callback** - Callback to receive mission items and result of this request.

### download_mission_cancel() {#classdronecode__sdk_1_1_mission_raw_1a3db03bbf14b8066005b85ac2deb0decf}
```cpp
void dronecode_sdk::MissionRaw::download_mission_cancel()
```


Cancel a mission download (asynchronous).

This cancels an ongoing mission download. The mission download will fail with the result [Result::CANCELLED](classdronecode__sdk_1_1_mission_raw.md#classdronecode__sdk_1_1_mission_raw_1a82e84d835ef6d2436ddf3ae735edcd07a9f935beb31030ad0d4d26126c0f39bf2).

### subscribe_mission_changed() {#classdronecode__sdk_1_1_mission_raw_1aa0b3f0c4c82a3a045351b7f1819ad630}
```cpp
void dronecode_sdk::MissionRaw::subscribe_mission_changed(mission_changed_callback_t callback)
```


Subscribes to mission progress (asynchronous).


**Parameters**

* [mission_changed_callback_t](classdronecode__sdk_1_1_mission_raw.md#classdronecode__sdk_1_1_mission_raw_1ab882f6b08cc17126afbbb3a865b1cbde) **callback** - Callback to receive mission progress.

### operator=() {#classdronecode__sdk_1_1_mission_raw_1a1747ff89013691cb608ae287704e0e67}
```cpp
const MissionRaw& dronecode_sdk::MissionRaw::operator=(const MissionRaw &)=delete
```


Equality operator (object is not copyable).


**Parameters**

* const [MissionRaw](classdronecode__sdk_1_1_mission_raw.md)&  - 

**Returns**

&emsp;const [MissionRaw](classdronecode__sdk_1_1_mission_raw.md) & - 

### result_str() {#classdronecode__sdk_1_1_mission_raw_1a305825a4853ebc662120f54f23393f06}
```cpp
static const char* dronecode_sdk::MissionRaw::result_str(Result result)
```


Gets a human-readable English string for an [MissionRaw::Result](classdronecode__sdk_1_1_mission_raw.md#classdronecode__sdk_1_1_mission_raw_1a82e84d835ef6d2436ddf3ae735edcd07).


**Parameters**

* [Result](classdronecode__sdk_1_1_mission_raw.md#classdronecode__sdk_1_1_mission_raw_1a82e84d835ef6d2436ddf3ae735edcd07) **result** - Enum for which string is required.

**Returns**

&emsp;const char * - Human readable string for the [MissionRaw::Result](classdronecode__sdk_1_1_mission_raw.md#classdronecode__sdk_1_1_mission_raw_1a82e84d835ef6d2436ddf3ae735edcd07).