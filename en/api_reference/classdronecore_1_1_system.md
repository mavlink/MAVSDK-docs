# dronecore::System Class Reference
`#include: system.h`

----


This class represents a system, made up of one or more components (e.g. autopilot, cameras, servos, gimbals, etc). Commonly [System](classdronecore_1_1_system.md) objects are used to interact with UAVs (including their components) and standalone cameras. 


## Public Member Functions


Type | Name | Description
---: | --- | ---
&nbsp; | [System](#classdronecore_1_1_system_1a04b6c349f03f7e733f36cbbdd2db49b6) (DroneCoreImpl & parent, uint8_t system_id, uint8_t comp_id) | Constructor.
&nbsp; | [~System](#classdronecore_1_1_system_1abeed98bdc18e63fc3632a3a0d1c9c097) () | Destructor.
&nbsp; | [System](#classdronecore_1_1_system_1a61860ab94c3fdcab5c2321aedd69faf1) (const [System](classdronecore_1_1_system.md) &)=delete | Copy constructor (object is not copyable).
bool | [has_autopilot](#classdronecore_1_1_system_1ab8b0fca82ac033d36d602231bee65a15) () const | Checks whether the system has an autopilot.
bool | [is_standalone](#classdronecore_1_1_system_1a07624a4ea1e4d22be85e9c4b635ea921) () const | Checks whether the system is a standalone (non-autopilot).
bool | [has_camera](#classdronecore_1_1_system_1a29398f091973a76b5631e37a71af0e43) (int camera_id=-1)const | Checks whether the system has a camera with the given camera ID.
bool | [has_gimbal](#classdronecore_1_1_system_1ae4e577b84fc7ff268935264e247a6668) () const | Checks whether the system has a gimbal.
const [System](classdronecore_1_1_system.md) & | [operator=](#classdronecore_1_1_system_1ab7e8e98e739dd153d775c4dec1f322a7) (const [System](classdronecore_1_1_system.md) &)=delete | Equality operator (object is not copyable).


## Constructor & Destructor Documentation


### System() {#classdronecore_1_1_system_1a04b6c349f03f7e733f36cbbdd2db49b6}
```cpp
dronecore::System::System(DroneCoreImpl &parent, uint8_t system_id, uint8_t comp_id)
```


Constructor.


**Parameters**

* DroneCoreImpl& **parent** - 
* uint8_t **system_id** - MAVLink system id.
* uint8_t **comp_id** - MAVLink component id.

### ~System() {#classdronecore_1_1_system_1abeed98bdc18e63fc3632a3a0d1c9c097}
```cpp
dronecore::System::~System()
```


Destructor.


### System() {#classdronecore_1_1_system_1a61860ab94c3fdcab5c2321aedd69faf1}
```cpp
dronecore::System::System(const System &)=delete
```


Copy constructor (object is not copyable).


**Parameters**

* const [System](classdronecore_1_1_system.md)&  - 

## Member Function Documentation


### has_autopilot() {#classdronecore_1_1_system_1ab8b0fca82ac033d36d602231bee65a15}
```cpp
bool dronecore::System::has_autopilot() const
```


Checks whether the system has an autopilot.


**Returns**

&emsp;bool - `true` if it has an autopilot, `false` otherwise.

### is_standalone() {#classdronecore_1_1_system_1a07624a4ea1e4d22be85e9c4b635ea921}
```cpp
bool dronecore::System::is_standalone() const
```


Checks whether the system is a standalone (non-autopilot).


**Returns**

&emsp;bool - `true` if stand alone, `false` otherwise.

### has_camera() {#classdronecore_1_1_system_1a29398f091973a76b5631e37a71af0e43}
```cpp
bool dronecore::System::has_camera(int camera_id=-1) const
```


Checks whether the system has a camera with the given camera ID.

A [System](classdronecore_1_1_system.md) may have several cameras, with IDs starting from 0. When called without passing a camera ID, it checks whether the system has any camera.

**Parameters**

* int **camera_id** - ID of the camera starting from 0 onwards.

**Returns**

&emsp;bool - `true` if camera with the given camera ID is found, `false` otherwise.

### has_gimbal() {#classdronecore_1_1_system_1ae4e577b84fc7ff268935264e247a6668}
```cpp
bool dronecore::System::has_gimbal() const
```


Checks whether the system has a gimbal.


**Returns**

&emsp;bool - `true` if the system has a gimbal, false otherwise.

### operator=() {#classdronecore_1_1_system_1ab7e8e98e739dd153d775c4dec1f322a7}
```cpp
const System& dronecore::System::operator=(const System &)=delete
```


Equality operator (object is not copyable).


**Parameters**

* const [System](classdronecore_1_1_system.md)&  - 

**Returns**

&emsp;const [System](classdronecore_1_1_system.md) & - 