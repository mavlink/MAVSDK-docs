# dronecode_sdk::System Class Reference
`#include: system.h`

----


This class represents a system, made up of one or more components (e.g. autopilot, cameras, servos, gimbals, etc). 


[System](classdronecode__sdk_1_1_system.md) objects are used to interact with UAVs (including their components) and standalone cameras. They are not created directly by application code, but are returned by the [DronecodeSDK](classdronecode__sdk_1_1_dronecode_s_d_k.md) class. 


## Public Member Functions


Type | Name | Description
---: | --- | ---
&nbsp; | [~System](#classdronecode__sdk_1_1_system_1ad11b6b5f4a9dc1e09e8225bc90764e3b) () | Destructor.
&nbsp; | [System](#classdronecode__sdk_1_1_system_1a35ffd64ebfea1642a2b3838213c8ae55) (const [System](classdronecode__sdk_1_1_system.md) &)=delete | Copy constructor (object is not copyable).
bool | [has_autopilot](#classdronecode__sdk_1_1_system_1ae8ce1c257b0491e33a7e6818af70649d) () const | Checks whether the system has an autopilot.
bool | [is_standalone](#classdronecode__sdk_1_1_system_1a5ab8f437b9da2a9cd5cb32f6ea61f04a) () const | Checks whether the system is a standalone (non-autopilot).
bool | [has_camera](#classdronecode__sdk_1_1_system_1aeb1b529b51317bc5d34672013901b04b) (int camera_id=-1)const | Checks whether the system has a camera with the given camera ID.
bool | [has_gimbal](#classdronecode__sdk_1_1_system_1ab540753165cc0e65094e107822675fe0) () const | Checks whether the system has a gimbal.
bool | [is_connected](#classdronecode__sdk_1_1_system_1aed68c810fa02f73ab089fe7f6605e0ae) () const | Checks if the system is connected.
uint64_t | [get_uuid](#classdronecode__sdk_1_1_system_1a195a32bba02b8e0d7e8dce3fa98cc440) () const | Get the UUID of the system.
const [System](classdronecode__sdk_1_1_system.md) & | [operator=](#classdronecode__sdk_1_1_system_1af49f5528da27c3fd1e6d8559a80f55e4) (const [System](classdronecode__sdk_1_1_system.md) &)=delete | Equality operator (object is not copyable).


## Constructor & Destructor Documentation


### ~System() {#classdronecode__sdk_1_1_system_1ad11b6b5f4a9dc1e09e8225bc90764e3b}
```cpp
dronecode_sdk::System::~System()
```


Destructor.


### System() {#classdronecode__sdk_1_1_system_1a35ffd64ebfea1642a2b3838213c8ae55}
```cpp
dronecode_sdk::System::System(const System &)=delete
```


Copy constructor (object is not copyable).


**Parameters**

* const [System](classdronecode__sdk_1_1_system.md)&  - 

## Member Function Documentation


### has_autopilot() {#classdronecode__sdk_1_1_system_1ae8ce1c257b0491e33a7e6818af70649d}
```cpp
bool dronecode_sdk::System::has_autopilot() const
```


Checks whether the system has an autopilot.


**Returns**

&emsp;bool - `true` if it has an autopilot, `false` otherwise.

### is_standalone() {#classdronecode__sdk_1_1_system_1a5ab8f437b9da2a9cd5cb32f6ea61f04a}
```cpp
bool dronecode_sdk::System::is_standalone() const
```


Checks whether the system is a standalone (non-autopilot).


**Returns**

&emsp;bool - `true` if stand alone, `false` otherwise.

### has_camera() {#classdronecode__sdk_1_1_system_1aeb1b529b51317bc5d34672013901b04b}
```cpp
bool dronecode_sdk::System::has_camera(int camera_id=-1) const
```


Checks whether the system has a camera with the given camera ID.

A [System](classdronecode__sdk_1_1_system.md) may have several cameras, with IDs starting from 0. When called without passing a camera ID, it checks whether the system has any camera.

**Parameters**

* int **camera_id** - ID of the camera starting from 0 onwards.

**Returns**

&emsp;bool - `true` if camera with the given camera ID is found, `false` otherwise.

### has_gimbal() {#classdronecode__sdk_1_1_system_1ab540753165cc0e65094e107822675fe0}
```cpp
bool dronecode_sdk::System::has_gimbal() const
```


Checks whether the system has a gimbal.


**Returns**

&emsp;bool - `true` if the system has a gimbal, false otherwise.

### is_connected() {#classdronecode__sdk_1_1_system_1aed68c810fa02f73ab089fe7f6605e0ae}
```cpp
bool dronecode_sdk::System::is_connected() const
```


Checks if the system is connected.

A system is connected when heartbeats are arriving (discovered and not timed out).

**Returns**

&emsp;bool - `true` if the system is connected.

### get_uuid() {#classdronecode__sdk_1_1_system_1a195a32bba02b8e0d7e8dce3fa98cc440}
```cpp
uint64_t dronecode_sdk::System::get_uuid() const
```


Get the UUID of the system.


**Returns**

&emsp;uint64_t - UUID of system.

### operator=() {#classdronecode__sdk_1_1_system_1af49f5528da27c3fd1e6d8559a80f55e4}
```cpp
const System& dronecode_sdk::System::operator=(const System &)=delete
```


Equality operator (object is not copyable).


**Parameters**

* const [System](classdronecode__sdk_1_1_system.md)&  - 

**Returns**

&emsp;const [System](classdronecode__sdk_1_1_system.md) & - 