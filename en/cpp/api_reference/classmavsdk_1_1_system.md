# mavsdk::System Class Reference
`#include: system.h`

----


This class represents a system, made up of one or more components (e.g. autopilot, cameras, servos, gimbals, etc). 


[System](classmavsdk_1_1_system.md) objects are used to interact with UAVs (including their components) and standalone cameras. They are not created directly by application code, but are returned by the [Mavsdk](classmavsdk_1_1_mavsdk.md) class. 


## Data Structures


struct [AutopilotVersion](structmavsdk_1_1_system_1_1_autopilot_version.md)

## Public Types


Type | Description
--- | ---
enum [ComponentType](#classmavsdk_1_1_system_1af2a91929d9771ae0e59c98557027b1dc) | Component Types.
std::function< void(bool)> [IsConnectedCallback](#classmavsdk_1_1_system_1a0e56bb48498100fde0872a3ec376f282) | type for is connected callback.
std::function< void([ComponentType](classmavsdk_1_1_system.md#classmavsdk_1_1_system_1af2a91929d9771ae0e59c98557027b1dc))> [DiscoverCallback](#classmavsdk_1_1_system_1af5f75718750071579b507434cdcd4562) | type for component discovery callback

## Public Member Functions


Type | Name | Description
---: | --- | ---
&nbsp; | [~System](#classmavsdk_1_1_system_1abdc4208c07d776c628acdc037a881ea6) () | Destructor.
&nbsp; | [System](#classmavsdk_1_1_system_1ac0e97e92181683f6b31fe208165dc35c) (const [System](classmavsdk_1_1_system.md) &)=delete | Copy constructor (object is not copyable).
void | [init](#classmavsdk_1_1_system_1add025b5dc9081631ef6fd3680acceb89) (uint8_t system_id, uint8_t component_id, bool connected)const | Initialize the system.
bool | [has_autopilot](#classmavsdk_1_1_system_1a0c3d766baa73f5b35e2950a6f0a38c02) () const | Checks whether the system has an autopilot.
bool | [is_standalone](#classmavsdk_1_1_system_1a7fb7ed01204498dcaa2ab7d9cc31acf2) () const | Checks whether the system is a standalone (non-autopilot).
bool | [has_camera](#classmavsdk_1_1_system_1a440fd601ed2120e1e41d9eab536a7da8) (int camera_id=-1)const | Checks whether the system has a camera with the given camera ID.
bool | [has_gimbal](#classmavsdk_1_1_system_1ad66c3ecc096970d40c34610e49dba929) () const | Checks whether the system has a gimbal.
bool | [is_connected](#classmavsdk_1_1_system_1ad07991ae044bc367e27f544db40d065b) () const | Checks if the system is connected.
uint8_t | [get_system_id](#classmavsdk_1_1_system_1a091d793db29719f4996040886ad951a6) () const | MAVLink [System](classmavsdk_1_1_system.md) ID of connected system.
void | [subscribe_is_connected](#classmavsdk_1_1_system_1a4e0a0237d54285ac8b7690f6e42c35fd) ([IsConnectedCallback](classmavsdk_1_1_system.md#classmavsdk_1_1_system_1a0e56bb48498100fde0872a3ec376f282) callback) | Subscribe to callback to be called when system connection state changes.
void | [register_component_discovered_callback](#classmavsdk_1_1_system_1aab05799a3c85976590ddc7ae2800c5a6) ([DiscoverCallback](classmavsdk_1_1_system.md#classmavsdk_1_1_system_1af5f75718750071579b507434cdcd4562) callback)const | Register a callback to be called when a component is discovered.
void | [enable_timesync](#classmavsdk_1_1_system_1a7c7177fb0789aefbfb375f4bb12ce824) () | Enable time synchronization using the TIMESYNC messages.
const [System](classmavsdk_1_1_system.md) & | [operator=](#classmavsdk_1_1_system_1a21284c27829fda2391ee27f5732f916d) (const [System](classmavsdk_1_1_system.md) &)=delete | Equality operator (object is not copyable).
void | [add_capabilities](#classmavsdk_1_1_system_1a5d4418aa5d9dff55a8246d98633c643d) (uint64_t capabilities) | Register capabilities to the system (only used if MAVSDK is autopilot)
void | [set_flight_sw_version](#classmavsdk_1_1_system_1abff603407597661498c0ac8bede2ee4c) (uint32_t flight_sw_version) | Set flight sw version (only used if MAVSDK is autopilot)
void | [set_middleware_sw_version](#classmavsdk_1_1_system_1abbe7a180d8de90f1e20f1d7ba849ec4a) (uint32_t middleware_sw_version) | Set middleware sw version (only used if MAVSDK is autopilot)
void | [set_os_sw_version](#classmavsdk_1_1_system_1a7a1f2c4e6ea54fb20625a83c3abb7065) (uint32_t os_sw_version) | Set OS sw version (only used if MAVSDK is autopilot)
void | [set_board_version](#classmavsdk_1_1_system_1a3a28436b9638a28849b6523dcba25a04) (uint32_t board_version) | Set hardware board version (only used if MAVSDK is autopilot)
void | [set_vendor_id](#classmavsdk_1_1_system_1a8c69f7d479d9849d04d6c219d278595b) (uint16_t vendor_id) | Set vendor id (only used if MAVSDK is autopilot)
void | [set_product_id](#classmavsdk_1_1_system_1a2c5d0b068e2f69c3867ff14ab6524dcd) (uint16_t product_id) | Set product id (only used if MAVSDK is autopilot)
bool | [set_uid2](#classmavsdk_1_1_system_1a7d4c809fc44f33238868e3391fd06423) (std::string uid2) | Set uid2, 18 chars max (only used if MAVSDK is autopilot)
[AutopilotVersion](structmavsdk_1_1_system_1_1_autopilot_version.md) | [get_autopilot_version_data](#classmavsdk_1_1_system_1af532662ee3301c92170939b7ab829651) () | Get autopilot version data.


## Constructor & Destructor Documentation


### ~System() {#classmavsdk_1_1_system_1abdc4208c07d776c628acdc037a881ea6}
```cpp
mavsdk::System::~System()
```


Destructor.


### System() {#classmavsdk_1_1_system_1ac0e97e92181683f6b31fe208165dc35c}
```cpp
mavsdk::System::System(const System &)=delete
```


Copy constructor (object is not copyable).


**Parameters**

* const [System](classmavsdk_1_1_system.md)&  - 

## Member Typdef Documentation


### typedef IsConnectedCallback {#classmavsdk_1_1_system_1a0e56bb48498100fde0872a3ec376f282}

```cpp
using mavsdk::System::IsConnectedCallback =  std::function<void(bool)>
```


type for is connected callback.


### typedef DiscoverCallback {#classmavsdk_1_1_system_1af5f75718750071579b507434cdcd4562}

```cpp
using mavsdk::System::DiscoverCallback =  std::function<void(ComponentType)>
```


type for component discovery callback


## Member Enumeration Documentation


### enum ComponentType {#classmavsdk_1_1_system_1af2a91929d9771ae0e59c98557027b1dc}


Component Types.


Value | Description
--- | ---
<span id="classmavsdk_1_1_system_1af2a91929d9771ae0e59c98557027b1dca696b031073e74bf2cb98e5ef201d4aa3"></span> `UNKNOWN` |  
<span id="classmavsdk_1_1_system_1af2a91929d9771ae0e59c98557027b1dca8797273a75c761c3b925c165511d653c"></span> `AUTOPILOT` |  
<span id="classmavsdk_1_1_system_1af2a91929d9771ae0e59c98557027b1dcaddf0d6b21537d984fea6544f58101fa8"></span> `CAMERA` |  
<span id="classmavsdk_1_1_system_1af2a91929d9771ae0e59c98557027b1dca0bad549bc68e5c4adb2ed793b8dcf8e3"></span> `GIMBAL` |  

## Member Function Documentation


### init() {#classmavsdk_1_1_system_1add025b5dc9081631ef6fd3680acceb89}
```cpp
void mavsdk::System::init(uint8_t system_id, uint8_t component_id, bool connected) const
```


Initialize the system.

This is not (and should not be) directly called by application code.

**Parameters**

* uint8_t **system_id** - [System](classmavsdk_1_1_system.md) id.
* uint8_t **component_id** - Component id.
* bool **connected** - If true then the system doesn't wait for heartbeat to go into connected state

### has_autopilot() {#classmavsdk_1_1_system_1a0c3d766baa73f5b35e2950a6f0a38c02}
```cpp
bool mavsdk::System::has_autopilot() const
```


Checks whether the system has an autopilot.


**Returns**

&emsp;bool - `true` if it has an autopilot, `false` otherwise.

### is_standalone() {#classmavsdk_1_1_system_1a7fb7ed01204498dcaa2ab7d9cc31acf2}
```cpp
bool mavsdk::System::is_standalone() const
```


Checks whether the system is a standalone (non-autopilot).


**Returns**

&emsp;bool - `true` if stand alone, `false` otherwise.

### has_camera() {#classmavsdk_1_1_system_1a440fd601ed2120e1e41d9eab536a7da8}
```cpp
bool mavsdk::System::has_camera(int camera_id=-1) const
```


Checks whether the system has a camera with the given camera ID.

A [System](classmavsdk_1_1_system.md) may have several cameras, with IDs starting from 0. When called without passing a camera ID, it checks whether the system has any camera.

**Parameters**

* int **camera_id** - ID of the camera starting from 0 onwards.

**Returns**

&emsp;bool - `true` if camera with the given camera ID is found, `false` otherwise.

### has_gimbal() {#classmavsdk_1_1_system_1ad66c3ecc096970d40c34610e49dba929}
```cpp
bool mavsdk::System::has_gimbal() const
```


Checks whether the system has a gimbal.


**Returns**

&emsp;bool - `true` if the system has a gimbal, false otherwise.

### is_connected() {#classmavsdk_1_1_system_1ad07991ae044bc367e27f544db40d065b}
```cpp
bool mavsdk::System::is_connected() const
```


Checks if the system is connected.

A system is connected when heartbeats are arriving (discovered and not timed out).

**Returns**

&emsp;bool - `true` if the system is connected.

### get_system_id() {#classmavsdk_1_1_system_1a091d793db29719f4996040886ad951a6}
```cpp
uint8_t mavsdk::System::get_system_id() const
```


MAVLink [System](classmavsdk_1_1_system.md) ID of connected system.

> **Note** : this is 0 if nothing is connected yet.

**Returns**

&emsp;uint8_t - the system ID.

### subscribe_is_connected() {#classmavsdk_1_1_system_1a4e0a0237d54285ac8b7690f6e42c35fd}
```cpp
void mavsdk::System::subscribe_is_connected(IsConnectedCallback callback)
```


Subscribe to callback to be called when system connection state changes.


**Parameters**

* [IsConnectedCallback](classmavsdk_1_1_system.md#classmavsdk_1_1_system_1a0e56bb48498100fde0872a3ec376f282) **callback** - Callback which will be called.

### register_component_discovered_callback() {#classmavsdk_1_1_system_1aab05799a3c85976590ddc7ae2800c5a6}
```cpp
void mavsdk::System::register_component_discovered_callback(DiscoverCallback callback) const
```


Register a callback to be called when a component is discovered.


**Parameters**

* [DiscoverCallback](classmavsdk_1_1_system.md#classmavsdk_1_1_system_1af5f75718750071579b507434cdcd4562) **callback** - a function of type void(ComponentType) which will be called with the component type of the new component.

### enable_timesync() {#classmavsdk_1_1_system_1a7c7177fb0789aefbfb375f4bb12ce824}
```cpp
void mavsdk::System::enable_timesync()
```


Enable time synchronization using the TIMESYNC messages.


### operator=() {#classmavsdk_1_1_system_1a21284c27829fda2391ee27f5732f916d}
```cpp
const System& mavsdk::System::operator=(const System &)=delete
```


Equality operator (object is not copyable).


**Parameters**

* const [System](classmavsdk_1_1_system.md)&  - 

**Returns**

&emsp;const [System](classmavsdk_1_1_system.md) & - 

### add_capabilities() {#classmavsdk_1_1_system_1a5d4418aa5d9dff55a8246d98633c643d}
```cpp
void mavsdk::System::add_capabilities(uint64_t capabilities)
```


Register capabilities to the system (only used if MAVSDK is autopilot)

> **Note** Plugins should register additional capabilities they provide using this.

**Parameters**

* uint64_t **capabilities** - MAVLink capability flag to bitwise OR

### set_flight_sw_version() {#classmavsdk_1_1_system_1abff603407597661498c0ac8bede2ee4c}
```cpp
void mavsdk::System::set_flight_sw_version(uint32_t flight_sw_version)
```


Set flight sw version (only used if MAVSDK is autopilot)


**Parameters**

* uint32_t **flight_sw_version** - version number of flight control software

### set_middleware_sw_version() {#classmavsdk_1_1_system_1abbe7a180d8de90f1e20f1d7ba849ec4a}
```cpp
void mavsdk::System::set_middleware_sw_version(uint32_t middleware_sw_version)
```


Set middleware sw version (only used if MAVSDK is autopilot)


**Parameters**

* uint32_t **middleware_sw_version** - version number of middleware software

### set_os_sw_version() {#classmavsdk_1_1_system_1a7a1f2c4e6ea54fb20625a83c3abb7065}
```cpp
void mavsdk::System::set_os_sw_version(uint32_t os_sw_version)
```


Set OS sw version (only used if MAVSDK is autopilot)


**Parameters**

* uint32_t **os_sw_version** - version number of operating system

### set_board_version() {#classmavsdk_1_1_system_1a3a28436b9638a28849b6523dcba25a04}
```cpp
void mavsdk::System::set_board_version(uint32_t board_version)
```


Set hardware board version (only used if MAVSDK is autopilot)


**Parameters**

* uint32_t **board_version** - version number of hardware board

### set_vendor_id() {#classmavsdk_1_1_system_1a8c69f7d479d9849d04d6c219d278595b}
```cpp
void mavsdk::System::set_vendor_id(uint16_t vendor_id)
```


Set vendor id (only used if MAVSDK is autopilot)


**Parameters**

* uint16_t **vendor_id** - number of vendor id

### set_product_id() {#classmavsdk_1_1_system_1a2c5d0b068e2f69c3867ff14ab6524dcd}
```cpp
void mavsdk::System::set_product_id(uint16_t product_id)
```


Set product id (only used if MAVSDK is autopilot)


**Parameters**

* uint16_t **product_id** - number of product id

### set_uid2() {#classmavsdk_1_1_system_1a7d4c809fc44f33238868e3391fd06423}
```cpp
bool mavsdk::System::set_uid2(std::string uid2)
```


Set uid2, 18 chars max (only used if MAVSDK is autopilot)


**Parameters**

* std::string **uid2** - unique hardware id

**Returns**

&emsp;bool - true if valid size, false if too large,

### get_autopilot_version_data() {#classmavsdk_1_1_system_1af532662ee3301c92170939b7ab829651}
```cpp
AutopilotVersion mavsdk::System::get_autopilot_version_data()
```


Get autopilot version data.


**Returns**

&emsp;[AutopilotVersion](structmavsdk_1_1_system_1_1_autopilot_version.md) - [AutopilotVersion](structmavsdk_1_1_system_1_1_autopilot_version.md) struct containing autopilot version ids