# mavsdk::MissionRawServer Class Reference
`#include: mission_raw_server.h`

----


Acts as a vehicle and receives incoming missions from GCS (in raw MAVLINK format). Provides current mission item state, so the server can progress through missions. 


## Data Structures


struct [MissionItem](structmavsdk_1_1_mission_raw_server_1_1_mission_item.md)

struct [MissionPlan](structmavsdk_1_1_mission_raw_server_1_1_mission_plan.md)

struct [MissionProgress](structmavsdk_1_1_mission_raw_server_1_1_mission_progress.md)

## Public Types


Type | Description
--- | ---
enum [Result](#classmavsdk_1_1_mission_raw_server_1a14f2cae8b098b7221d8aae547b70f7bd) | Possible results returned for action requests.
std::function< void([Result](classmavsdk_1_1_mission_raw_server.md#classmavsdk_1_1_mission_raw_server_1a14f2cae8b098b7221d8aae547b70f7bd))> [ResultCallback](#classmavsdk_1_1_mission_raw_server_1a3bddb8adba3f8576ae102639601e576f) | Callback type for asynchronous [MissionRawServer](classmavsdk_1_1_mission_raw_server.md) calls.
std::function< void([Result](classmavsdk_1_1_mission_raw_server.md#classmavsdk_1_1_mission_raw_server_1a14f2cae8b098b7221d8aae547b70f7bd), [MissionPlan](structmavsdk_1_1_mission_raw_server_1_1_mission_plan.md))> [IncomingMissionCallback](#classmavsdk_1_1_mission_raw_server_1ac8bb83c581ff08945314e51973728693) | Callback type for subscribe_incoming_mission.
std::function< void([MissionItem](structmavsdk_1_1_mission_raw_server_1_1_mission_item.md))> [CurrentItemChangedCallback](#classmavsdk_1_1_mission_raw_server_1aca7ac64b6e39e612d05ff6497cd572b1) | Callback type for subscribe_current_item_changed.
std::function< void(uint32_t)> [ClearAllCallback](#classmavsdk_1_1_mission_raw_server_1ae9d7d9d863d1552274440d091e2ec869) | Callback type for subscribe_clear_all.

## Public Member Functions


Type | Name | Description
---: | --- | ---
&nbsp; | [MissionRawServer](#classmavsdk_1_1_mission_raw_server_1a409bf742aa4e227b83877476641e938e) ([System](classmavsdk_1_1_system.md) & system) | Constructor. Creates the plugin for a specific [System](classmavsdk_1_1_system.md).
&nbsp; | [MissionRawServer](#classmavsdk_1_1_mission_raw_server_1ac742e0088f8b72d349b2808f00bdf24b) (std::shared_ptr< [System](classmavsdk_1_1_system.md) > system) | Constructor. Creates the plugin for a specific [System](classmavsdk_1_1_system.md).
&nbsp; | [~MissionRawServer](#classmavsdk_1_1_mission_raw_server_1a547fd04a550429c4d395b528da554175) () | Destructor (internal use only).
&nbsp; | [MissionRawServer](#classmavsdk_1_1_mission_raw_server_1a14b11b78ba44bdda6fb718ed13e1ab77) (const [MissionRawServer](classmavsdk_1_1_mission_raw_server.md) & other) | Copy constructor.
void | [subscribe_incoming_mission](#classmavsdk_1_1_mission_raw_server_1a31b14a826e6bb8727c26105f05e53550) ([IncomingMissionCallback](classmavsdk_1_1_mission_raw_server.md#classmavsdk_1_1_mission_raw_server_1ac8bb83c581ff08945314e51973728693) callback) | Subscribe to when a new mission is uploaded (asynchronous).
[MissionPlan](structmavsdk_1_1_mission_raw_server_1_1_mission_plan.md) | [incoming_mission](#classmavsdk_1_1_mission_raw_server_1ae7c20d621170e5454953513526241577) () const | Poll for '[MissionPlan](structmavsdk_1_1_mission_raw_server_1_1_mission_plan.md)' (blocking).
void | [subscribe_current_item_changed](#classmavsdk_1_1_mission_raw_server_1a60ea84204d2679b41a607d87cd9a1082) ([CurrentItemChangedCallback](classmavsdk_1_1_mission_raw_server.md#classmavsdk_1_1_mission_raw_server_1aca7ac64b6e39e612d05ff6497cd572b1) callback) | Subscribe to when a new current item is set.
[MissionItem](structmavsdk_1_1_mission_raw_server_1_1_mission_item.md) | [current_item_changed](#classmavsdk_1_1_mission_raw_server_1af2bbab99a8a2e1dd1dfebceb439f2ad1) () const | Poll for '[MissionItem](structmavsdk_1_1_mission_raw_server_1_1_mission_item.md)' (blocking).
void | [set_current_item_complete](#classmavsdk_1_1_mission_raw_server_1a496791a14c2bdc1e9917f5d04622330a) () const | Set Current item as completed.
void | [subscribe_clear_all](#classmavsdk_1_1_mission_raw_server_1a990002711e49d62b854a608bd30126a9) ([ClearAllCallback](classmavsdk_1_1_mission_raw_server.md#classmavsdk_1_1_mission_raw_server_1ae9d7d9d863d1552274440d091e2ec869) callback) | Subscribe when a MISSION_CLEAR_ALL is received.
uint32_t | [clear_all](#classmavsdk_1_1_mission_raw_server_1a307e0f39d704ae9aeb227a27092bf435) () const | Poll for 'uint32_t' (blocking).
const [MissionRawServer](classmavsdk_1_1_mission_raw_server.md) & | [operator=](#classmavsdk_1_1_mission_raw_server_1a9d589d816286937b2c9c5d29451f0f91) (const [MissionRawServer](classmavsdk_1_1_mission_raw_server.md) &)=delete | Equality operator (object is not copyable).


## Constructor & Destructor Documentation


### MissionRawServer() {#classmavsdk_1_1_mission_raw_server_1a409bf742aa4e227b83877476641e938e}
```cpp
mavsdk::MissionRawServer::MissionRawServer(System &system)
```


Constructor. Creates the plugin for a specific [System](classmavsdk_1_1_system.md).

The plugin is typically created as shown below: 

```cpp
auto mission_raw_server = MissionRawServer(system);
```

**Parameters**

* [System](classmavsdk_1_1_system.md)& **system** - The specific system associated with this plugin.

### MissionRawServer() {#classmavsdk_1_1_mission_raw_server_1ac742e0088f8b72d349b2808f00bdf24b}
```cpp
mavsdk::MissionRawServer::MissionRawServer(std::shared_ptr< System > system)
```


Constructor. Creates the plugin for a specific [System](classmavsdk_1_1_system.md).

The plugin is typically created as shown below: 

```cpp
auto mission_raw_server = MissionRawServer(system);
```

**Parameters**

* std::shared_ptr< [System](classmavsdk_1_1_system.md) > **system** - The specific system associated with this plugin.

### ~MissionRawServer() {#classmavsdk_1_1_mission_raw_server_1a547fd04a550429c4d395b528da554175}
```cpp
mavsdk::MissionRawServer::~MissionRawServer()
```


Destructor (internal use only).


### MissionRawServer() {#classmavsdk_1_1_mission_raw_server_1a14b11b78ba44bdda6fb718ed13e1ab77}
```cpp
mavsdk::MissionRawServer::MissionRawServer(const MissionRawServer &other)
```


Copy constructor.


**Parameters**

* const [MissionRawServer](classmavsdk_1_1_mission_raw_server.md)& **other** - 

## Member Typdef Documentation


### typedef ResultCallback {#classmavsdk_1_1_mission_raw_server_1a3bddb8adba3f8576ae102639601e576f}

```cpp
using mavsdk::MissionRawServer::ResultCallback =  std::function<void(Result)>
```


Callback type for asynchronous [MissionRawServer](classmavsdk_1_1_mission_raw_server.md) calls.


### typedef IncomingMissionCallback {#classmavsdk_1_1_mission_raw_server_1ac8bb83c581ff08945314e51973728693}

```cpp
using mavsdk::MissionRawServer::IncomingMissionCallback =  std::function<void(Result, MissionPlan)>
```


Callback type for subscribe_incoming_mission.


### typedef CurrentItemChangedCallback {#classmavsdk_1_1_mission_raw_server_1aca7ac64b6e39e612d05ff6497cd572b1}

```cpp
using mavsdk::MissionRawServer::CurrentItemChangedCallback =  std::function<void(MissionItem)>
```


Callback type for subscribe_current_item_changed.


### typedef ClearAllCallback {#classmavsdk_1_1_mission_raw_server_1ae9d7d9d863d1552274440d091e2ec869}

```cpp
using mavsdk::MissionRawServer::ClearAllCallback =  std::function<void(uint32_t)>
```


Callback type for subscribe_clear_all.


## Member Enumeration Documentation


### enum Result {#classmavsdk_1_1_mission_raw_server_1a14f2cae8b098b7221d8aae547b70f7bd}


Possible results returned for action requests.


Value | Description
--- | ---
<span id="classmavsdk_1_1_mission_raw_server_1a14f2cae8b098b7221d8aae547b70f7bda88183b946cc5f0e8c96b2e66e1c74a7e"></span> `Unknown` | Unknown result. 
<span id="classmavsdk_1_1_mission_raw_server_1a14f2cae8b098b7221d8aae547b70f7bda505a83f220c02df2f85c3810cd9ceb38"></span> `Success` | Request succeeded. 
<span id="classmavsdk_1_1_mission_raw_server_1a14f2cae8b098b7221d8aae547b70f7bda902b0d55fddef6f8d651fe1035b7d4bd"></span> `Error` | Error. 
<span id="classmavsdk_1_1_mission_raw_server_1a14f2cae8b098b7221d8aae547b70f7bdaecc3de82f27e8e7f65807c69a114efbe"></span> `TooManyMissionItems` | Too many mission items in the mission. 
<span id="classmavsdk_1_1_mission_raw_server_1a14f2cae8b098b7221d8aae547b70f7bdad8a942ef2b04672adfafef0ad817a407"></span> `Busy` | Vehicle is busy. 
<span id="classmavsdk_1_1_mission_raw_server_1a14f2cae8b098b7221d8aae547b70f7bdac85a251cc457840f1e032f1b733e9398"></span> `Timeout` | Request timed out. 
<span id="classmavsdk_1_1_mission_raw_server_1a14f2cae8b098b7221d8aae547b70f7bda253ca7dd096ee0956cccee4d376cab8b"></span> `InvalidArgument` | Invalid argument. 
<span id="classmavsdk_1_1_mission_raw_server_1a14f2cae8b098b7221d8aae547b70f7bdab4080bdf74febf04d578ff105cce9d3f"></span> `Unsupported` | [Mission](classmavsdk_1_1_mission.md) downloaded from the system is not supported. 
<span id="classmavsdk_1_1_mission_raw_server_1a14f2cae8b098b7221d8aae547b70f7bda6b0ce476dfc17eed72967386f52ede78"></span> `NoMissionAvailable` | No mission available on the system. 
<span id="classmavsdk_1_1_mission_raw_server_1a14f2cae8b098b7221d8aae547b70f7bdaefcaef698baace312f79a53019bd9cf4"></span> `UnsupportedMissionCmd` | Unsupported mission command. 
<span id="classmavsdk_1_1_mission_raw_server_1a14f2cae8b098b7221d8aae547b70f7bda3465fd31285ebd60597cf59bff9db01a"></span> `TransferCancelled` | [Mission](classmavsdk_1_1_mission.md) transfer (upload or download) has been cancelled. 
<span id="classmavsdk_1_1_mission_raw_server_1a14f2cae8b098b7221d8aae547b70f7bda1119faf72ba0dfb23aeea644fed960ad"></span> `NoSystem` | No system connected. 
<span id="classmavsdk_1_1_mission_raw_server_1a14f2cae8b098b7221d8aae547b70f7bda10ac3d04253ef7e1ddc73e6091c0cd55"></span> `Next` | Intermediate message showing progress or instructions on the next steps. 

## Member Function Documentation


### subscribe_incoming_mission() {#classmavsdk_1_1_mission_raw_server_1a31b14a826e6bb8727c26105f05e53550}
```cpp
void mavsdk::MissionRawServer::subscribe_incoming_mission(IncomingMissionCallback callback)
```


Subscribe to when a new mission is uploaded (asynchronous).


**Parameters**

* [IncomingMissionCallback](classmavsdk_1_1_mission_raw_server.md#classmavsdk_1_1_mission_raw_server_1ac8bb83c581ff08945314e51973728693) **callback** - 

### incoming_mission() {#classmavsdk_1_1_mission_raw_server_1ae7c20d621170e5454953513526241577}
```cpp
MissionPlan mavsdk::MissionRawServer::incoming_mission() const
```


Poll for '[MissionPlan](structmavsdk_1_1_mission_raw_server_1_1_mission_plan.md)' (blocking).


**Returns**

&emsp;[MissionPlan](structmavsdk_1_1_mission_raw_server_1_1_mission_plan.md) - One [MissionPlan](structmavsdk_1_1_mission_raw_server_1_1_mission_plan.md) update.

### subscribe_current_item_changed() {#classmavsdk_1_1_mission_raw_server_1a60ea84204d2679b41a607d87cd9a1082}
```cpp
void mavsdk::MissionRawServer::subscribe_current_item_changed(CurrentItemChangedCallback callback)
```


Subscribe to when a new current item is set.


**Parameters**

* [CurrentItemChangedCallback](classmavsdk_1_1_mission_raw_server.md#classmavsdk_1_1_mission_raw_server_1aca7ac64b6e39e612d05ff6497cd572b1) **callback** - 

### current_item_changed() {#classmavsdk_1_1_mission_raw_server_1af2bbab99a8a2e1dd1dfebceb439f2ad1}
```cpp
MissionItem mavsdk::MissionRawServer::current_item_changed() const
```


Poll for '[MissionItem](structmavsdk_1_1_mission_raw_server_1_1_mission_item.md)' (blocking).


**Returns**

&emsp;[MissionItem](structmavsdk_1_1_mission_raw_server_1_1_mission_item.md) - One [MissionItem](structmavsdk_1_1_mission_raw_server_1_1_mission_item.md) update.

### set_current_item_complete() {#classmavsdk_1_1_mission_raw_server_1a496791a14c2bdc1e9917f5d04622330a}
```cpp
void mavsdk::MissionRawServer::set_current_item_complete() const
```


Set Current item as completed.

This function is blocking.

### subscribe_clear_all() {#classmavsdk_1_1_mission_raw_server_1a990002711e49d62b854a608bd30126a9}
```cpp
void mavsdk::MissionRawServer::subscribe_clear_all(ClearAllCallback callback)
```


Subscribe when a MISSION_CLEAR_ALL is received.


**Parameters**

* [ClearAllCallback](classmavsdk_1_1_mission_raw_server.md#classmavsdk_1_1_mission_raw_server_1ae9d7d9d863d1552274440d091e2ec869) **callback** - 

### clear_all() {#classmavsdk_1_1_mission_raw_server_1a307e0f39d704ae9aeb227a27092bf435}
```cpp
uint32_t mavsdk::MissionRawServer::clear_all() const
```


Poll for 'uint32_t' (blocking).


**Returns**

&emsp;uint32_t - One uint32_t update.

### operator=() {#classmavsdk_1_1_mission_raw_server_1a9d589d816286937b2c9c5d29451f0f91}
```cpp
const MissionRawServer & mavsdk::MissionRawServer::operator=(const MissionRawServer &)=delete
```


Equality operator (object is not copyable).


**Parameters**

* const [MissionRawServer](classmavsdk_1_1_mission_raw_server.md)&  - 

**Returns**

&emsp;const [MissionRawServer](classmavsdk_1_1_mission_raw_server.md) & - 