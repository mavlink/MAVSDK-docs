# mavsdk::MissionRaw Class Reference
`#include: mission_raw.h`

----


Enable raw missions as exposed by MAVLink. 


## Data Structures


struct [MissionItem](structmavsdk_1_1_mission_raw_1_1_mission_item.md)

struct [MissionProgress](structmavsdk_1_1_mission_raw_1_1_mission_progress.md)

## Public Types


Type | Description
--- | ---
enum [Result](#classmavsdk_1_1_mission_raw_1a7ea2a624818ebb5a3e209cc275d58eaf) | Possible results returned for action requests.
std::function< void([Result](classmavsdk_1_1_mission_raw.md#classmavsdk_1_1_mission_raw_1a7ea2a624818ebb5a3e209cc275d58eaf))> [ResultCallback](#classmavsdk_1_1_mission_raw_1a1a36a84f17dca07e1da49c13abbc9564) | Callback type for asynchronous [MissionRaw](classmavsdk_1_1_mission_raw.md) calls.
std::function< void([Result](classmavsdk_1_1_mission_raw.md#classmavsdk_1_1_mission_raw_1a7ea2a624818ebb5a3e209cc275d58eaf), std::vector< [MissionItem](structmavsdk_1_1_mission_raw_1_1_mission_item.md) >)> [DownloadMissionCallback](#classmavsdk_1_1_mission_raw_1a016633e6338744da02ac7cb6da28880a) | Callback type for download_mission_async.
std::function< void([MissionProgress](structmavsdk_1_1_mission_raw_1_1_mission_progress.md))> [MissionProgressCallback](#classmavsdk_1_1_mission_raw_1a9dd594878925da494b4add6acc3184fc) | Callback type for subscribe_mission_progress.
std::function< void(bool)> [MissionChangedCallback](#classmavsdk_1_1_mission_raw_1ac22d81eefc5e883cdb6baf792a7487e6) | Callback type for subscribe_mission_changed.

## Public Member Functions


Type | Name | Description
---: | --- | ---
&nbsp; | [MissionRaw](#classmavsdk_1_1_mission_raw_1ad03476f12988a12808a8c4385c7a7344) ([System](classmavsdk_1_1_system.md) & system) | Constructor. Creates the plugin for a specific [System](classmavsdk_1_1_system.md).
&nbsp; | [~MissionRaw](#classmavsdk_1_1_mission_raw_1a366afae5d3c7c2345e3ecec26ff9e307) () | Destructor (internal use only).
&nbsp; | [MissionRaw](#classmavsdk_1_1_mission_raw_1a6a98ba999d8fa548b45f031f372fdfe9) (const [MissionRaw](classmavsdk_1_1_mission_raw.md) &)=delete | Copy constructor (object is not copyable).
void | [upload_mission_async](#classmavsdk_1_1_mission_raw_1a77cc5df3362b7ab4cbc94e5bc9707609) (std::vector< [MissionItem](structmavsdk_1_1_mission_raw_1_1_mission_item.md) > mission_items, const [ResultCallback](classmavsdk_1_1_mission_raw.md#classmavsdk_1_1_mission_raw_1a1a36a84f17dca07e1da49c13abbc9564) callback) | Upload a list of raw mission items to the system.
[Result](classmavsdk_1_1_mission_raw.md#classmavsdk_1_1_mission_raw_1a7ea2a624818ebb5a3e209cc275d58eaf) | [upload_mission](#classmavsdk_1_1_mission_raw_1ad4f5c2ccfb2249f6e11c9533c263926a) (std::vector< [MissionItem](structmavsdk_1_1_mission_raw_1_1_mission_item.md) > mission_items)const | Upload a list of raw mission items to the system.
[Result](classmavsdk_1_1_mission_raw.md#classmavsdk_1_1_mission_raw_1a7ea2a624818ebb5a3e209cc275d58eaf) | [cancel_mission_upload](#classmavsdk_1_1_mission_raw_1aa353e3fa6e836305248be131dbe19273) () const | Cancel an ongoing mission upload.
void | [download_mission_async](#classmavsdk_1_1_mission_raw_1a7e27b0fb58889ca5cb1202276c0e0669) (const [DownloadMissionCallback](classmavsdk_1_1_mission_raw.md#classmavsdk_1_1_mission_raw_1a016633e6338744da02ac7cb6da28880a) callback) | Download a list of raw mission items from the system (asynchronous).
std::pair< [Result](classmavsdk_1_1_mission_raw.md#classmavsdk_1_1_mission_raw_1a7ea2a624818ebb5a3e209cc275d58eaf), std::vector< [MissionRaw::MissionItem](structmavsdk_1_1_mission_raw_1_1_mission_item.md) > > | [download_mission](#classmavsdk_1_1_mission_raw_1a2cc470785c486d1b7fdaaa2e3fbff809) () const | Download a list of raw mission items from the system (asynchronous).
[Result](classmavsdk_1_1_mission_raw.md#classmavsdk_1_1_mission_raw_1a7ea2a624818ebb5a3e209cc275d58eaf) | [cancel_mission_download](#classmavsdk_1_1_mission_raw_1a7c554999ca66c5434ef1fa334d949e5a) () const | Cancel an ongoing mission download.
void | [start_mission_async](#classmavsdk_1_1_mission_raw_1acca64e0a08978f5721be8fa955b1bb0f) (const [ResultCallback](classmavsdk_1_1_mission_raw.md#classmavsdk_1_1_mission_raw_1a1a36a84f17dca07e1da49c13abbc9564) callback) | Start the mission.
[Result](classmavsdk_1_1_mission_raw.md#classmavsdk_1_1_mission_raw_1a7ea2a624818ebb5a3e209cc275d58eaf) | [start_mission](#classmavsdk_1_1_mission_raw_1af1b010b0f28b284a94eba88198ee15f8) () const | Start the mission.
void | [pause_mission_async](#classmavsdk_1_1_mission_raw_1aae0eedbe4216266eb6e2115cd03c61a1) (const [ResultCallback](classmavsdk_1_1_mission_raw.md#classmavsdk_1_1_mission_raw_1a1a36a84f17dca07e1da49c13abbc9564) callback) | Pause the mission.
[Result](classmavsdk_1_1_mission_raw.md#classmavsdk_1_1_mission_raw_1a7ea2a624818ebb5a3e209cc275d58eaf) | [pause_mission](#classmavsdk_1_1_mission_raw_1abda483b0659a6c0397c588341688bb39) () const | Pause the mission.
void | [clear_mission_async](#classmavsdk_1_1_mission_raw_1acf6bf293facbd45fa1126e52e99248a2) (const [ResultCallback](classmavsdk_1_1_mission_raw.md#classmavsdk_1_1_mission_raw_1a1a36a84f17dca07e1da49c13abbc9564) callback) | Clear the mission saved on the vehicle.
[Result](classmavsdk_1_1_mission_raw.md#classmavsdk_1_1_mission_raw_1a7ea2a624818ebb5a3e209cc275d58eaf) | [clear_mission](#classmavsdk_1_1_mission_raw_1ab10f8fcaa0f6d3e0f844b7430d8d14c2) () const | Clear the mission saved on the vehicle.
void | [set_current_mission_item_async](#classmavsdk_1_1_mission_raw_1a5540d6ca691d60ef19b66e303bae7f87) (int32_t index, const [ResultCallback](classmavsdk_1_1_mission_raw.md#classmavsdk_1_1_mission_raw_1a1a36a84f17dca07e1da49c13abbc9564) callback) | Sets the raw mission item index to go to.
[Result](classmavsdk_1_1_mission_raw.md#classmavsdk_1_1_mission_raw_1a7ea2a624818ebb5a3e209cc275d58eaf) | [set_current_mission_item](#classmavsdk_1_1_mission_raw_1ada9aa2abf79ebfc8e1d10de8e85e91ae) (int32_t index)const | Sets the raw mission item index to go to.
void | [subscribe_mission_progress](#classmavsdk_1_1_mission_raw_1ac0428c520645cdf10430c6c0554a104e) ([MissionProgressCallback](classmavsdk_1_1_mission_raw.md#classmavsdk_1_1_mission_raw_1a9dd594878925da494b4add6acc3184fc) callback) | Subscribe to mission progress updates.
[MissionProgress](structmavsdk_1_1_mission_raw_1_1_mission_progress.md) | [mission_progress](#classmavsdk_1_1_mission_raw_1a3200dea1094926a4dd54f079f21b94e1) () const | Poll for '[MissionProgress](structmavsdk_1_1_mission_raw_1_1_mission_progress.md)' (blocking).
void | [subscribe_mission_changed](#classmavsdk_1_1_mission_raw_1a18019bf4f46b6f3719df55512575f500) ([MissionChangedCallback](classmavsdk_1_1_mission_raw.md#classmavsdk_1_1_mission_raw_1ac22d81eefc5e883cdb6baf792a7487e6) callback) | <ul>
<li><p>Subscribes to mission changed. </p></li>
</ul>
const [MissionRaw](classmavsdk_1_1_mission_raw.md) & | [operator=](#classmavsdk_1_1_mission_raw_1a0cfdf21bad5478c91cf18207b6a21ad3) (const [MissionRaw](classmavsdk_1_1_mission_raw.md) &)=delete | Equality operator (object is not copyable).


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


### typedef ResultCallback {#classmavsdk_1_1_mission_raw_1a1a36a84f17dca07e1da49c13abbc9564}

```cpp
using mavsdk::MissionRaw::ResultCallback =  std::function<void(Result)>
```


Callback type for asynchronous [MissionRaw](classmavsdk_1_1_mission_raw.md) calls.


### typedef DownloadMissionCallback {#classmavsdk_1_1_mission_raw_1a016633e6338744da02ac7cb6da28880a}

```cpp
using mavsdk::MissionRaw::DownloadMissionCallback =  std::function<void(Result, std::vector<MissionItem>)>
```


Callback type for download_mission_async.


### typedef MissionProgressCallback {#classmavsdk_1_1_mission_raw_1a9dd594878925da494b4add6acc3184fc}

```cpp
using mavsdk::MissionRaw::MissionProgressCallback =  std::function<void(MissionProgress)>
```


Callback type for subscribe_mission_progress.


### typedef MissionChangedCallback {#classmavsdk_1_1_mission_raw_1ac22d81eefc5e883cdb6baf792a7487e6}

```cpp
using mavsdk::MissionRaw::MissionChangedCallback =  std::function<void(bool)>
```


Callback type for subscribe_mission_changed.


## Member Enumeration Documentation


### enum Result {#classmavsdk_1_1_mission_raw_1a7ea2a624818ebb5a3e209cc275d58eaf}


Possible results returned for action requests.


Value | Description
--- | ---
<span id="classmavsdk_1_1_mission_raw_1a7ea2a624818ebb5a3e209cc275d58eafa88183b946cc5f0e8c96b2e66e1c74a7e"></span> `Unknown` | Unknown result. 
<span id="classmavsdk_1_1_mission_raw_1a7ea2a624818ebb5a3e209cc275d58eafa505a83f220c02df2f85c3810cd9ceb38"></span> `Success` | Request succeeded. 
<span id="classmavsdk_1_1_mission_raw_1a7ea2a624818ebb5a3e209cc275d58eafa902b0d55fddef6f8d651fe1035b7d4bd"></span> `Error` | Error. 
<span id="classmavsdk_1_1_mission_raw_1a7ea2a624818ebb5a3e209cc275d58eafaecc3de82f27e8e7f65807c69a114efbe"></span> `TooManyMissionItems` | Too many mission items in the mission. 
<span id="classmavsdk_1_1_mission_raw_1a7ea2a624818ebb5a3e209cc275d58eafad8a942ef2b04672adfafef0ad817a407"></span> `Busy` | Vehicle is busy. 
<span id="classmavsdk_1_1_mission_raw_1a7ea2a624818ebb5a3e209cc275d58eafac85a251cc457840f1e032f1b733e9398"></span> `Timeout` | Request timed out. 
<span id="classmavsdk_1_1_mission_raw_1a7ea2a624818ebb5a3e209cc275d58eafa253ca7dd096ee0956cccee4d376cab8b"></span> `InvalidArgument` | Invalid argument. 
<span id="classmavsdk_1_1_mission_raw_1a7ea2a624818ebb5a3e209cc275d58eafab4080bdf74febf04d578ff105cce9d3f"></span> `Unsupported` | [Mission](classmavsdk_1_1_mission.md) downloaded from the system is not supported. 
<span id="classmavsdk_1_1_mission_raw_1a7ea2a624818ebb5a3e209cc275d58eafa6b0ce476dfc17eed72967386f52ede78"></span> `NoMissionAvailable` | No mission available on the system. 
<span id="classmavsdk_1_1_mission_raw_1a7ea2a624818ebb5a3e209cc275d58eafa3465fd31285ebd60597cf59bff9db01a"></span> `TransferCancelled` | [Mission](classmavsdk_1_1_mission.md) transfer (upload or download) has been cancelled. 

## Member Function Documentation


### upload_mission_async() {#classmavsdk_1_1_mission_raw_1a77cc5df3362b7ab4cbc94e5bc9707609}
```cpp
void mavsdk::MissionRaw::upload_mission_async(std::vector< MissionItem > mission_items, const ResultCallback callback)
```


Upload a list of raw mission items to the system.

The raw mission items are uploaded to a drone. Once uploaded the mission can be started and executed even if the connection is lost.


This function is non-blocking. See 'upload_mission' for the blocking counterpart.

**Parameters**

* std::vector< [MissionItem](structmavsdk_1_1_mission_raw_1_1_mission_item.md) > **mission_items** - 
* const [ResultCallback](classmavsdk_1_1_mission_raw.md#classmavsdk_1_1_mission_raw_1a1a36a84f17dca07e1da49c13abbc9564) **callback** - 

### upload_mission() {#classmavsdk_1_1_mission_raw_1ad4f5c2ccfb2249f6e11c9533c263926a}
```cpp
Result mavsdk::MissionRaw::upload_mission(std::vector< MissionItem > mission_items) const
```


Upload a list of raw mission items to the system.

The raw mission items are uploaded to a drone. Once uploaded the mission can be started and executed even if the connection is lost.


This function is blocking. See 'upload_mission_async' for the non-blocking counterpart.

**Parameters**

* std::vector< [MissionItem](structmavsdk_1_1_mission_raw_1_1_mission_item.md) > **mission_items** - 

**Returns**

&emsp;[Result](classmavsdk_1_1_mission_raw.md#classmavsdk_1_1_mission_raw_1a7ea2a624818ebb5a3e209cc275d58eaf) - Result of request.

### cancel_mission_upload() {#classmavsdk_1_1_mission_raw_1aa353e3fa6e836305248be131dbe19273}
```cpp
Result mavsdk::MissionRaw::cancel_mission_upload() const
```


Cancel an ongoing mission upload.

This function is blocking.

**Returns**

&emsp;[Result](classmavsdk_1_1_mission_raw.md#classmavsdk_1_1_mission_raw_1a7ea2a624818ebb5a3e209cc275d58eaf) - Result of request.

### download_mission_async() {#classmavsdk_1_1_mission_raw_1a7e27b0fb58889ca5cb1202276c0e0669}
```cpp
void mavsdk::MissionRaw::download_mission_async(const DownloadMissionCallback callback)
```


Download a list of raw mission items from the system (asynchronous).

This function is non-blocking. See 'download_mission' for the blocking counterpart.

**Parameters**

* const [DownloadMissionCallback](classmavsdk_1_1_mission_raw.md#classmavsdk_1_1_mission_raw_1a016633e6338744da02ac7cb6da28880a) **callback** - 

### download_mission() {#classmavsdk_1_1_mission_raw_1a2cc470785c486d1b7fdaaa2e3fbff809}
```cpp
std::pair<Result, std::vector<MissionRaw::MissionItem> > mavsdk::MissionRaw::download_mission() const
```


Download a list of raw mission items from the system (asynchronous).

This function is blocking. See 'download_mission_async' for the non-blocking counterpart.

**Returns**

&emsp;std::pair< [Result](classmavsdk_1_1_mission_raw.md#classmavsdk_1_1_mission_raw_1a7ea2a624818ebb5a3e209cc275d58eaf), std::vector< [MissionRaw::MissionItem](structmavsdk_1_1_mission_raw_1_1_mission_item.md) > > - Result of request.

### cancel_mission_download() {#classmavsdk_1_1_mission_raw_1a7c554999ca66c5434ef1fa334d949e5a}
```cpp
Result mavsdk::MissionRaw::cancel_mission_download() const
```


Cancel an ongoing mission download.

This function is blocking.

**Returns**

&emsp;[Result](classmavsdk_1_1_mission_raw.md#classmavsdk_1_1_mission_raw_1a7ea2a624818ebb5a3e209cc275d58eaf) - Result of request.

### start_mission_async() {#classmavsdk_1_1_mission_raw_1acca64e0a08978f5721be8fa955b1bb0f}
```cpp
void mavsdk::MissionRaw::start_mission_async(const ResultCallback callback)
```


Start the mission.

A mission must be uploaded to the vehicle before this can be called.


This function is non-blocking. See 'start_mission' for the blocking counterpart.

**Parameters**

* const [ResultCallback](classmavsdk_1_1_mission_raw.md#classmavsdk_1_1_mission_raw_1a1a36a84f17dca07e1da49c13abbc9564) **callback** - 

### start_mission() {#classmavsdk_1_1_mission_raw_1af1b010b0f28b284a94eba88198ee15f8}
```cpp
Result mavsdk::MissionRaw::start_mission() const
```


Start the mission.

A mission must be uploaded to the vehicle before this can be called.


This function is blocking. See 'start_mission_async' for the non-blocking counterpart.

**Returns**

&emsp;[Result](classmavsdk_1_1_mission_raw.md#classmavsdk_1_1_mission_raw_1a7ea2a624818ebb5a3e209cc275d58eaf) - Result of request.

### pause_mission_async() {#classmavsdk_1_1_mission_raw_1aae0eedbe4216266eb6e2115cd03c61a1}
```cpp
void mavsdk::MissionRaw::pause_mission_async(const ResultCallback callback)
```


Pause the mission.

Pausing the mission puts the vehicle into [HOLD mode](https://docs.px4.io/en/flight_modes/hold.html). A multicopter should just hover at the spot while a fixedwing vehicle should loiter around the location where it paused.


This function is non-blocking. See 'pause_mission' for the blocking counterpart.

**Parameters**

* const [ResultCallback](classmavsdk_1_1_mission_raw.md#classmavsdk_1_1_mission_raw_1a1a36a84f17dca07e1da49c13abbc9564) **callback** - 

### pause_mission() {#classmavsdk_1_1_mission_raw_1abda483b0659a6c0397c588341688bb39}
```cpp
Result mavsdk::MissionRaw::pause_mission() const
```


Pause the mission.

Pausing the mission puts the vehicle into [HOLD mode](https://docs.px4.io/en/flight_modes/hold.html). A multicopter should just hover at the spot while a fixedwing vehicle should loiter around the location where it paused.


This function is blocking. See 'pause_mission_async' for the non-blocking counterpart.

**Returns**

&emsp;[Result](classmavsdk_1_1_mission_raw.md#classmavsdk_1_1_mission_raw_1a7ea2a624818ebb5a3e209cc275d58eaf) - Result of request.

### clear_mission_async() {#classmavsdk_1_1_mission_raw_1acf6bf293facbd45fa1126e52e99248a2}
```cpp
void mavsdk::MissionRaw::clear_mission_async(const ResultCallback callback)
```


Clear the mission saved on the vehicle.

This function is non-blocking. See 'clear_mission' for the blocking counterpart.

**Parameters**

* const [ResultCallback](classmavsdk_1_1_mission_raw.md#classmavsdk_1_1_mission_raw_1a1a36a84f17dca07e1da49c13abbc9564) **callback** - 

### clear_mission() {#classmavsdk_1_1_mission_raw_1ab10f8fcaa0f6d3e0f844b7430d8d14c2}
```cpp
Result mavsdk::MissionRaw::clear_mission() const
```


Clear the mission saved on the vehicle.

This function is blocking. See 'clear_mission_async' for the non-blocking counterpart.

**Returns**

&emsp;[Result](classmavsdk_1_1_mission_raw.md#classmavsdk_1_1_mission_raw_1a7ea2a624818ebb5a3e209cc275d58eaf) - Result of request.

### set_current_mission_item_async() {#classmavsdk_1_1_mission_raw_1a5540d6ca691d60ef19b66e303bae7f87}
```cpp
void mavsdk::MissionRaw::set_current_mission_item_async(int32_t index, const ResultCallback callback)
```


Sets the raw mission item index to go to.

By setting the current index to 0, the mission is restarted from the beginning. If it is set to a specific index of a raw mission item, the mission will be set to this item.


This function is non-blocking. See 'set_current_mission_item' for the blocking counterpart.

**Parameters**

* int32_t **index** - 
* const [ResultCallback](classmavsdk_1_1_mission_raw.md#classmavsdk_1_1_mission_raw_1a1a36a84f17dca07e1da49c13abbc9564) **callback** - 

### set_current_mission_item() {#classmavsdk_1_1_mission_raw_1ada9aa2abf79ebfc8e1d10de8e85e91ae}
```cpp
Result mavsdk::MissionRaw::set_current_mission_item(int32_t index) const
```


Sets the raw mission item index to go to.

By setting the current index to 0, the mission is restarted from the beginning. If it is set to a specific index of a raw mission item, the mission will be set to this item.


This function is blocking. See 'set_current_mission_item_async' for the non-blocking counterpart.

**Parameters**

* int32_t **index** - 

**Returns**

&emsp;[Result](classmavsdk_1_1_mission_raw.md#classmavsdk_1_1_mission_raw_1a7ea2a624818ebb5a3e209cc275d58eaf) - Result of request.

### subscribe_mission_progress() {#classmavsdk_1_1_mission_raw_1ac0428c520645cdf10430c6c0554a104e}
```cpp
void mavsdk::MissionRaw::subscribe_mission_progress(MissionProgressCallback callback)
```


Subscribe to mission progress updates.


**Parameters**

* [MissionProgressCallback](classmavsdk_1_1_mission_raw.md#classmavsdk_1_1_mission_raw_1a9dd594878925da494b4add6acc3184fc) **callback** - 

### mission_progress() {#classmavsdk_1_1_mission_raw_1a3200dea1094926a4dd54f079f21b94e1}
```cpp
MissionProgress mavsdk::MissionRaw::mission_progress() const
```


Poll for '[MissionProgress](structmavsdk_1_1_mission_raw_1_1_mission_progress.md)' (blocking).


**Returns**

&emsp;[MissionProgress](structmavsdk_1_1_mission_raw_1_1_mission_progress.md) - One [MissionProgress](structmavsdk_1_1_mission_raw_1_1_mission_progress.md) update.

### subscribe_mission_changed() {#classmavsdk_1_1_mission_raw_1a18019bf4f46b6f3719df55512575f500}
```cpp
void mavsdk::MissionRaw::subscribe_mission_changed(MissionChangedCallback callback)
```


<ul>
<li><p>Subscribes to mission changed. </p></li>
</ul>

This notification can be used to be informed if a ground station has been uploaded or changed by a ground station or companion computer.

**Parameters**

* [MissionChangedCallback](classmavsdk_1_1_mission_raw.md#classmavsdk_1_1_mission_raw_1ac22d81eefc5e883cdb6baf792a7487e6) **callback** - Callback to notify about change.

### operator=() {#classmavsdk_1_1_mission_raw_1a0cfdf21bad5478c91cf18207b6a21ad3}
```cpp
const MissionRaw& mavsdk::MissionRaw::operator=(const MissionRaw &)=delete
```


Equality operator (object is not copyable).


**Parameters**

* const [MissionRaw](classmavsdk_1_1_mission_raw.md)&  - 

**Returns**

&emsp;const [MissionRaw](classmavsdk_1_1_mission_raw.md) & - 