# dronecore::MissionItem Class Reference
`#include: mission_item.h`

----


A mission is a vector of [MissionItem](classdronecore_1_1_mission_item.md)s. 


Each [MissionItem](classdronecore_1_1_mission_item.md) can contain a position and/or actions. [Mission](classdronecore_1_1_mission.md) items are just building blocks to assemble a mission, which can be sent to (or received from) a device. They cannot be used independently. 


## Public Types


Type | Description
--- | ---
enum [CameraAction](#classdronecore_1_1_mission_item_1a0cdd25121e5ed6930080ac022857887a) | Possible camera actions at a mission item.

## Public Member Functions


Type | Name | Description
---: | --- | ---
| [MissionItem](#classdronecore_1_1_mission_item_1aca4d7fd82ae0f623cd162730140a5a68) () | Constructor (internal use only).
| [~MissionItem](#classdronecore_1_1_mission_item_1abfcfaeb576e969d6da33a4d16013dd9f) () | Destructor (internal use only).
| [MissionItem](#classdronecore_1_1_mission_item_1ac6e6d75b38193db07eaa05b21fc229e2) (const MissionItem &)=delete | Copy constructor (object is not copyable).
void | [set_position](#classdronecore_1_1_mission_item_1ab5897670c8830fc3514036d6ee99b582) (double latitude_deg, double longitude_deg) | Set the position of a mission item.
void | [set_relative_altitude](#classdronecore_1_1_mission_item_1afef21f3028edad2ba2a0e966404fa33a) (float altitude_m) | Set the relative altitude of a mission item.
void | [set_fly_through](#classdronecore_1_1_mission_item_1a63d73896635dc0af136a521cd35bf352) (bool fly_through) | Set the fly-through property of a mission item.
void | [set_speed](#classdronecore_1_1_mission_item_1a37e43f748da4136c659419a4a2d84b0e) (float speed_m_s) | Set the speed to use after a mission item.
void | [set_gimbal_pitch_and_yaw](#classdronecore_1_1_mission_item_1a10adfcff1e99ae937654786b767e5558) (float pitch_deg, float yaw_deg) | Set the pitch and yaw angle of a gimbal at that mission item.
void | [set_camera_action](#classdronecore_1_1_mission_item_1a8d0d8a5519783aaa272befd73e851896) (CameraAction action) | Set the camera action for a mission item.
void | [set_camera_photo_interval](#classdronecore_1_1_mission_item_1a4ffe698b47c659aa8857725e94ad1f7c) (double interval_s) | Set the camera photo interval.
double | [get_latitude_deg](#classdronecore_1_1_mission_item_1ad95d5d10d69bdb43321231c51dda1175) () const | Get the latitude of a mission item.
double | [get_longitude_deg](#classdronecore_1_1_mission_item_1a9f76de6dbbcec3269207867794a2d099) () const | Get the longitude of a mission item.
float | [get_relative_altitude_m](#classdronecore_1_1_mission_item_1a22481d92a61136d42b5133b208e6cf0d) () const | Get the relative altitude of a mission item.
bool | [get_fly_through](#classdronecore_1_1_mission_item_1afd92f9ab01d25c0d721b4249821b6da2) () const | Get the fly-through property of a mission item.
float | [get_speed_m_s](#classdronecore_1_1_mission_item_1adc737b7be9b49cd0fe188763203aeae5) () const | Get the speed to be used after this mission item.
[CameraAction](classdronecore_1_1_mission_item.md#classdronecore_1_1_mission_item_1a0cdd25121e5ed6930080ac022857887a) | [get_camera_action](#classdronecore_1_1_mission_item_1ae42a857f79b63c611f5a21fed2ea18fc) () const | Get the camera action set for this mission item.
double | [get_camera_photo_interval_s](#classdronecore_1_1_mission_item_1adf38956d9ed1ef4e98a4d5a6b61eccd7) () const | Get the camera photo interval that was set for this mission item.
const [MissionItem](classdronecore_1_1_mission_item.md) & | [operator=](#classdronecore_1_1_mission_item_1a8582ad72a3a8c20c87e8224ab10970c0) (const MissionItem &)=delete | Equality operator (object is not copyable).


## Constructor & Destructor Documentation


### MissionItem() {#classdronecore_1_1_mission_item_1aca4d7fd82ae0f623cd162730140a5a68}
```cpp
dronecore::MissionItem::MissionItem()
```


Constructor (internal use only).


### ~MissionItem() {#classdronecore_1_1_mission_item_1abfcfaeb576e969d6da33a4d16013dd9f}
```cpp
dronecore::MissionItem::~MissionItem()
```


Destructor (internal use only).


### MissionItem() {#classdronecore_1_1_mission_item_1ac6e6d75b38193db07eaa05b21fc229e2}
```cpp
dronecore::MissionItem::MissionItem(const MissionItem &)=delete
```


Copy constructor (object is not copyable).


**Parameters**

* const [MissionItem](classdronecore_1_1_mission_item.md) & **** - 

## Member Enumeration Documentation


### enum CameraAction {#classdronecore_1_1_mission_item_1a0cdd25121e5ed6930080ac022857887a}


Possible camera actions at a mission item.


 Value | Description
--- | ---
<span id="classdronecore_1_1_mission_item_1a0cdd25121e5ed6930080ac022857887aa4130de26d3895fa5de9f46ddd558315c"></span> `TAKE_PHOTO` | Take single photo. 
<span id="classdronecore_1_1_mission_item_1a0cdd25121e5ed6930080ac022857887aa27eb71e5403792ee9072932ec93c113c"></span> `START_PHOTO_INTERVAL` | Start capturing photos at regular intervals - see [set_camera_photo_interval()](classdronecore_1_1_mission_item.md#classdronecore_1_1_mission_item_1a4ffe698b47c659aa8857725e94ad1f7c). 
<span id="classdronecore_1_1_mission_item_1a0cdd25121e5ed6930080ac022857887aa7554aaea445f14cf06a0757ff8204b0a"></span> `STOP_PHOTO_INTERVAL` | Stop capturing photos at regular intervals. 
<span id="classdronecore_1_1_mission_item_1a0cdd25121e5ed6930080ac022857887aa2830bdcebb2b8bb17e19bef72a7255bc"></span> `START_VIDEO` | Start capturing video. 
<span id="classdronecore_1_1_mission_item_1a0cdd25121e5ed6930080ac022857887aac7dbedd5fead832bc23d7caaf4cfb8cf"></span> `STOP_VIDEO` | Stop capturing video. 
<span id="classdronecore_1_1_mission_item_1a0cdd25121e5ed6930080ac022857887aab50339a10e1de285ac99d4c3990b8693"></span> `NONE` | No action. 

## Member Function Documentation


### set_position() {#classdronecore_1_1_mission_item_1ab5897670c8830fc3514036d6ee99b582}
```cpp
void dronecore::MissionItem::set_position(double latitude_deg, double longitude_deg)
```


Set the position of a mission item.


**Parameters**

* double **latitude_deg** - Latitude of the waypoint in degrees.
* double **longitude_deg** - Longitude of the waypoint in degrees.

### set_relative_altitude() {#classdronecore_1_1_mission_item_1afef21f3028edad2ba2a0e966404fa33a}
```cpp
void dronecore::MissionItem::set_relative_altitude(float altitude_m)
```


Set the relative altitude of a mission item.


**Parameters**

* float **altitude_m** - Altitude relative to takeoff position in metres.

### set_fly_through() {#classdronecore_1_1_mission_item_1a63d73896635dc0af136a521cd35bf352}
```cpp
void dronecore::MissionItem::set_fly_through(bool fly_through)
```


Set the fly-through property of a mission item.


**Parameters**

* bool **fly_through** - If true the drone will fly through the waypoint without stopping. If false the drone will come to a stop at the waypoint before continuing.

### set_speed() {#classdronecore_1_1_mission_item_1a37e43f748da4136c659419a4a2d84b0e}
```cpp
void dronecore::MissionItem::set_speed(float speed_m_s)
```


Set the speed to use after a mission item.


**Parameters**

* float **speed_m_s** - Speed to use after this mission item in metres/second.

### set_gimbal_pitch_and_yaw() {#classdronecore_1_1_mission_item_1a10adfcff1e99ae937654786b767e5558}
```cpp
void dronecore::MissionItem::set_gimbal_pitch_and_yaw(float pitch_deg, float yaw_deg)
```


Set the pitch and yaw angle of a gimbal at that mission item.


**Parameters**

* float **pitch_deg** - The new pitch angle of the gimbal in degrees (0: horizontal, positive up, -90: vertical downward facing).
* float **yaw_deg** - The new yaw angle of the gimbal in degrees (0: forward, positive clock-wise, 90: to the right).

### set_camera_action() {#classdronecore_1_1_mission_item_1a8d0d8a5519783aaa272befd73e851896}
```cpp
void dronecore::MissionItem::set_camera_action(CameraAction action)
```


Set the camera action for a mission item.


**Parameters**

* [CameraAction](classdronecore_1_1_mission_item.md#classdronecore_1_1_mission_item_1a0cdd25121e5ed6930080ac022857887a) **action** - The camera action.

### set_camera_photo_interval() {#classdronecore_1_1_mission_item_1a4ffe698b47c659aa8857725e94ad1f7c}
```cpp
void dronecore::MissionItem::set_camera_photo_interval(double interval_s)
```


Set the camera photo interval.

This only has an effect if used together with [CameraAction::START_PHOTO_INTERVAL](classdronecore_1_1_mission_item.md#classdronecore_1_1_mission_item_1a0cdd25121e5ed6930080ac022857887aa27eb71e5403792ee9072932ec93c113c).

**Parameters**

* double **interval_s** - Interval between photo captures in seconds.

### get_latitude_deg() {#classdronecore_1_1_mission_item_1ad95d5d10d69bdb43321231c51dda1175}
```cpp
double dronecore::MissionItem::get_latitude_deg() const
```


Get the latitude of a mission item.


**Returns**

&emsp;double - Latitude in degrees.

### get_longitude_deg() {#classdronecore_1_1_mission_item_1a9f76de6dbbcec3269207867794a2d099}
```cpp
double dronecore::MissionItem::get_longitude_deg() const
```


Get the longitude of a mission item.


**Returns**

&emsp;double - Longitude in degrees.

### get_relative_altitude_m() {#classdronecore_1_1_mission_item_1a22481d92a61136d42b5133b208e6cf0d}
```cpp
float dronecore::MissionItem::get_relative_altitude_m() const
```


Get the relative altitude of a mission item.


**Returns**

&emsp;float - The altitude relative to the takeoff position in metres.

### get_fly_through() {#classdronecore_1_1_mission_item_1afd92f9ab01d25c0d721b4249821b6da2}
```cpp
bool dronecore::MissionItem::get_fly_through() const
```


Get the fly-through property of a mission item.


**Returns**

&emsp;bool - true if the drone will fly through the waypoint without stopping. false if the drone will come to a stop at the waypoint before continuing.

### get_speed_m_s() {#classdronecore_1_1_mission_item_1adc737b7be9b49cd0fe188763203aeae5}
```cpp
float dronecore::MissionItem::get_speed_m_s() const
```


Get the speed to be used after this mission item.


**Returns**

&emsp;float - Speed in metres/second.

### get_camera_action() {#classdronecore_1_1_mission_item_1ae42a857f79b63c611f5a21fed2ea18fc}
```cpp
CameraAction dronecore::MissionItem::get_camera_action() const
```


Get the camera action set for this mission item.


**Returns**

&emsp;[CameraAction](classdronecore_1_1_mission_item.md#classdronecore_1_1_mission_item_1a0cdd25121e5ed6930080ac022857887a) - Camera action enum value.

### get_camera_photo_interval_s() {#classdronecore_1_1_mission_item_1adf38956d9ed1ef4e98a4d5a6b61eccd7}
```cpp
double dronecore::MissionItem::get_camera_photo_interval_s() const
```


Get the camera photo interval that was set for this mission item.

This only has an effect if used together with [CameraAction::START_PHOTO_INTERVAL](classdronecore_1_1_mission_item.md#classdronecore_1_1_mission_item_1a0cdd25121e5ed6930080ac022857887aa27eb71e5403792ee9072932ec93c113c).

**Returns**

&emsp;double - Camera photo interval in seconds.

### operator=() {#classdronecore_1_1_mission_item_1a8582ad72a3a8c20c87e8224ab10970c0}
```cpp
const MissionItem& dronecore::MissionItem::operator=(const MissionItem &)=delete
```


Equality operator (object is not copyable).


**Parameters**

* const [MissionItem](classdronecore_1_1_mission_item.md) & **** - 

**Returns**

&emsp;const [MissionItem](classdronecore_1_1_mission_item.md) & - 