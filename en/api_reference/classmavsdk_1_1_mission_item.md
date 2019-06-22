# mavsdk::MissionItem Class Reference
`#include: mission_item.h`

----


A mission is a vector of [MissionItem](classmavsdk_1_1_mission_item.md)s. 


Each [MissionItem](classmavsdk_1_1_mission_item.md) can contain a position and/or actions. [Mission](classmavsdk_1_1_mission.md) items are just building blocks to assemble a mission, which can be sent to (or received from) a system. They cannot be used independently. 


## Public Types


Type | Description
--- | ---
enum [CameraAction](#classmavsdk_1_1_mission_item_1a132fb8fb01a95f7da406d6691a699b33) | Possible camera actions at a mission item.

## Public Member Functions


Type | Name | Description
---: | --- | ---
&nbsp; | [MissionItem](#classmavsdk_1_1_mission_item_1a5139434174fe4f03c9a9cb64dd934faf) () | Constructor (internal use only).
&nbsp; | [~MissionItem](#classmavsdk_1_1_mission_item_1a47e96b832c0fb6b61f48d28a87d19e14) () | Destructor (internal use only).
&nbsp; | [MissionItem](#classmavsdk_1_1_mission_item_1aca937c757d8ba74d2bd94b160e22eeb9) (const [MissionItem](classmavsdk_1_1_mission_item.md) &)=delete | Copy constructor (object is not copyable).
void | [set_position](#classmavsdk_1_1_mission_item_1abe17a24cf27fa0b6d632f39f8d7d15f3) (double latitude_deg, double longitude_deg) | Set the position of a mission item.
void | [set_relative_altitude](#classmavsdk_1_1_mission_item_1a4f2a78e4b299fc1aac67067e9ab672c1) (float altitude_m) | Set the relative altitude of a mission item.
void | [set_fly_through](#classmavsdk_1_1_mission_item_1a8136dc303b58ee2306d997e437f783d4) (bool fly_through) | Set the fly-through property of a mission item.
void | [set_acceptance_radius](#classmavsdk_1_1_mission_item_1a875a56ed851b4a48de2f1decac77fe1c) (float radius_m) | Set the acceptance radius property of a mission item.
void | [set_speed](#classmavsdk_1_1_mission_item_1a7cd1845321421330988dea441d0f980b) (float speed_m_s) | Set the speed to use after a mission item.
void | [set_gimbal_pitch_and_yaw](#classmavsdk_1_1_mission_item_1aee42aca98990f8924bddf2f7b0c37485) (float pitch_deg, float yaw_deg) | Set the pitch and yaw angle of a gimbal at that mission item.
void | [set_loiter_time](#classmavsdk_1_1_mission_item_1ad458170b2b6f282c1052cfcb7495586c) (float loiter_time_s) | Set loiter time in seconds.
void | [set_camera_action](#classmavsdk_1_1_mission_item_1aecf47062d8254bbb89f8cfe390100217) ([CameraAction](classmavsdk_1_1_mission_item.md#classmavsdk_1_1_mission_item_1a132fb8fb01a95f7da406d6691a699b33) action) | Set the camera action for a mission item.
void | [set_camera_photo_interval](#classmavsdk_1_1_mission_item_1a7eaeb877658d23d7df0b97592eace7e5) (double interval_s) | Set the camera photo interval.
double | [get_latitude_deg](#classmavsdk_1_1_mission_item_1a3001afa82fa2ec6eb7868b6b745be1d5) () const | Get the latitude of a mission item.
double | [get_longitude_deg](#classmavsdk_1_1_mission_item_1ad30b13797fa2f57af2de01c90e326cea) () const | Get the longitude of a mission item.
bool | [has_position_set](#classmavsdk_1_1_mission_item_1a5735e0382f41aa445726c91ee1faa56b) () const | Reports whether position info (Lat, Lon) was set for this mission item.
float | [get_relative_altitude_m](#classmavsdk_1_1_mission_item_1aa5be6daffe833e0695df566459c878f7) () const | Get the relative altitude of a mission item.
bool | [get_fly_through](#classmavsdk_1_1_mission_item_1a595c0e9b76858155cf2f6637b802f453) () const | Get the fly-through property of a mission item.
float | [get_acceptance_radius_m](#classmavsdk_1_1_mission_item_1a9d057dc8cb892a3dc4fbfdfb5db8dee5) () const | Get the acceptance radius of a mission item.
float | [get_speed_m_s](#classmavsdk_1_1_mission_item_1a8ec7abb2efb0c7613c24e019a4c3045c) () const | Get the speed to be used after this mission item.
float | [get_gimbal_pitch_deg](#classmavsdk_1_1_mission_item_1a7f4cb4f8c5c758a1d0ffec3367197fa0) () const | Get the gimbal pitch of a mission item.
float | [get_gimbal_yaw_deg](#classmavsdk_1_1_mission_item_1a7d923a49f5c74c75436a60e1e0c6fdfe) () const | Get the gimbal yaw of a mission item.
float | [get_loiter_time_s](#classmavsdk_1_1_mission_item_1a2d5d345406de899943102269a8e32360) () const | Get loiter time in seconds.
[CameraAction](classmavsdk_1_1_mission_item.md#classmavsdk_1_1_mission_item_1a132fb8fb01a95f7da406d6691a699b33) | [get_camera_action](#classmavsdk_1_1_mission_item_1a8708b9f8684f301ad180577a7abcfb64) () const | Get the camera action set for this mission item.
double | [get_camera_photo_interval_s](#classmavsdk_1_1_mission_item_1a873f750d6b19760a31d492d57775ea62) () const | Get the camera photo interval that was set for this mission item.
const [MissionItem](classmavsdk_1_1_mission_item.md) & | [operator=](#classmavsdk_1_1_mission_item_1af3737e3129abd684724b75a6b3690436) (const [MissionItem](classmavsdk_1_1_mission_item.md) &)=delete | Equality operator (object is not copyable).

## Static Public Member Functions


Type | Name | Description
---: | --- | ---
std::string | [to_str](#classmavsdk_1_1_mission_item_1a6d605f2411d9cf3c4dd57ccc94efc009) ([CameraAction](classmavsdk_1_1_mission_item.md#classmavsdk_1_1_mission_item_1a132fb8fb01a95f7da406d6691a699b33) camera_action) | Converts [CameraAction](classmavsdk_1_1_mission_item.md#classmavsdk_1_1_mission_item_1a132fb8fb01a95f7da406d6691a699b33) to English strings.


## Constructor & Destructor Documentation


### MissionItem() {#classmavsdk_1_1_mission_item_1a5139434174fe4f03c9a9cb64dd934faf}
```cpp
mavsdk::MissionItem::MissionItem()
```


Constructor (internal use only).


### ~MissionItem() {#classmavsdk_1_1_mission_item_1a47e96b832c0fb6b61f48d28a87d19e14}
```cpp
mavsdk::MissionItem::~MissionItem()
```


Destructor (internal use only).


### MissionItem() {#classmavsdk_1_1_mission_item_1aca937c757d8ba74d2bd94b160e22eeb9}
```cpp
mavsdk::MissionItem::MissionItem(const MissionItem &)=delete
```


Copy constructor (object is not copyable).


**Parameters**

* const [MissionItem](classmavsdk_1_1_mission_item.md)&  - 

## Member Enumeration Documentation


### enum CameraAction {#classmavsdk_1_1_mission_item_1a132fb8fb01a95f7da406d6691a699b33}


Possible camera actions at a mission item.


Value | Description
--- | ---
<span id="classmavsdk_1_1_mission_item_1a132fb8fb01a95f7da406d6691a699b33a4130de26d3895fa5de9f46ddd558315c"></span> `TAKE_PHOTO` | Take single photo. 
<span id="classmavsdk_1_1_mission_item_1a132fb8fb01a95f7da406d6691a699b33a27eb71e5403792ee9072932ec93c113c"></span> `START_PHOTO_INTERVAL` | Start capturing photos at regular intervals - see [set_camera_photo_interval()](classmavsdk_1_1_mission_item.md#classmavsdk_1_1_mission_item_1a7eaeb877658d23d7df0b97592eace7e5). 
<span id="classmavsdk_1_1_mission_item_1a132fb8fb01a95f7da406d6691a699b33a7554aaea445f14cf06a0757ff8204b0a"></span> `STOP_PHOTO_INTERVAL` | Stop capturing photos at regular intervals. 
<span id="classmavsdk_1_1_mission_item_1a132fb8fb01a95f7da406d6691a699b33a2830bdcebb2b8bb17e19bef72a7255bc"></span> `START_VIDEO` | Start capturing video. 
<span id="classmavsdk_1_1_mission_item_1a132fb8fb01a95f7da406d6691a699b33ac7dbedd5fead832bc23d7caaf4cfb8cf"></span> `STOP_VIDEO` | Stop capturing video. 
<span id="classmavsdk_1_1_mission_item_1a132fb8fb01a95f7da406d6691a699b33ab50339a10e1de285ac99d4c3990b8693"></span> `NONE` | No action. 

**See Also:**
- [to_str()](classmavsdk_1_1_mission_item.md#classmavsdk_1_1_mission_item_1a6d605f2411d9cf3c4dd57ccc94efc009)


## Member Function Documentation


### set_position() {#classmavsdk_1_1_mission_item_1abe17a24cf27fa0b6d632f39f8d7d15f3}
```cpp
void mavsdk::MissionItem::set_position(double latitude_deg, double longitude_deg)
```


Set the position of a mission item.


**Parameters**

* double **latitude_deg** - Latitude of the waypoint in degrees.
* double **longitude_deg** - Longitude of the waypoint in degrees.

### set_relative_altitude() {#classmavsdk_1_1_mission_item_1a4f2a78e4b299fc1aac67067e9ab672c1}
```cpp
void mavsdk::MissionItem::set_relative_altitude(float altitude_m)
```


Set the relative altitude of a mission item.


**Parameters**

* float **altitude_m** - Altitude relative to takeoff position in metres.

### set_fly_through() {#classmavsdk_1_1_mission_item_1a8136dc303b58ee2306d997e437f783d4}
```cpp
void mavsdk::MissionItem::set_fly_through(bool fly_through)
```


Set the fly-through property of a mission item.


**Parameters**

* bool **fly_through** - If `true` the drone will fly through the waypoint without stopping. If `false` the drone will come to a stop at the waypoint before continuing.

### set_acceptance_radius() {#classmavsdk_1_1_mission_item_1a875a56ed851b4a48de2f1decac77fe1c}
```cpp
void mavsdk::MissionItem::set_acceptance_radius(float radius_m)
```


Set the acceptance radius property of a mission item.


**Parameters**

* float **radius_m** - Radius in meters around the mission_item where it will be considered as reached.

### set_speed() {#classmavsdk_1_1_mission_item_1a7cd1845321421330988dea441d0f980b}
```cpp
void mavsdk::MissionItem::set_speed(float speed_m_s)
```


Set the speed to use after a mission item.


**Parameters**

* float **speed_m_s** - Speed to use after this mission item in metres/second.

### set_gimbal_pitch_and_yaw() {#classmavsdk_1_1_mission_item_1aee42aca98990f8924bddf2f7b0c37485}
```cpp
void mavsdk::MissionItem::set_gimbal_pitch_and_yaw(float pitch_deg, float yaw_deg)
```


Set the pitch and yaw angle of a gimbal at that mission item.


**Parameters**

* float **pitch_deg** - The new pitch angle of the gimbal in degrees (0: horizontal, positive up, -90: vertical downward facing).
* float **yaw_deg** - The new yaw angle of the gimbal in degrees (0: forward, positive clock-wise, 90: to the right).

### set_loiter_time() {#classmavsdk_1_1_mission_item_1ad458170b2b6f282c1052cfcb7495586c}
```cpp
void mavsdk::MissionItem::set_loiter_time(float loiter_time_s)
```


Set loiter time in seconds.

This specifies the delay at a waypoint before executing next mission item. It can be used to wait for vehicle to slow down or a gimbal to arrive at the set orientation.

**Parameters**

* float **loiter_time_s** - The time to wait (loiter), in seconds.

### set_camera_action() {#classmavsdk_1_1_mission_item_1aecf47062d8254bbb89f8cfe390100217}
```cpp
void mavsdk::MissionItem::set_camera_action(CameraAction action)
```


Set the camera action for a mission item.


**Parameters**

* [CameraAction](classmavsdk_1_1_mission_item.md#classmavsdk_1_1_mission_item_1a132fb8fb01a95f7da406d6691a699b33) **action** - The camera action.

### set_camera_photo_interval() {#classmavsdk_1_1_mission_item_1a7eaeb877658d23d7df0b97592eace7e5}
```cpp
void mavsdk::MissionItem::set_camera_photo_interval(double interval_s)
```


Set the camera photo interval.

This only has an effect if used together with [CameraAction::START_PHOTO_INTERVAL](classmavsdk_1_1_mission_item.md#classmavsdk_1_1_mission_item_1a132fb8fb01a95f7da406d6691a699b33a27eb71e5403792ee9072932ec93c113c).

**Parameters**

* double **interval_s** - Interval between photo captures in seconds.

### get_latitude_deg() {#classmavsdk_1_1_mission_item_1a3001afa82fa2ec6eb7868b6b745be1d5}
```cpp
double mavsdk::MissionItem::get_latitude_deg() const
```


Get the latitude of a mission item.


**Returns**

&emsp;double - Latitude in degrees.

### get_longitude_deg() {#classmavsdk_1_1_mission_item_1ad30b13797fa2f57af2de01c90e326cea}
```cpp
double mavsdk::MissionItem::get_longitude_deg() const
```


Get the longitude of a mission item.


**Returns**

&emsp;double - Longitude in degrees.

### has_position_set() {#classmavsdk_1_1_mission_item_1a5735e0382f41aa445726c91ee1faa56b}
```cpp
bool mavsdk::MissionItem::has_position_set() const
```


Reports whether position info (Lat, Lon) was set for this mission item.


**Returns**

&emsp;bool - true if Lat, Lon is set for this mission item.

### get_relative_altitude_m() {#classmavsdk_1_1_mission_item_1aa5be6daffe833e0695df566459c878f7}
```cpp
float mavsdk::MissionItem::get_relative_altitude_m() const
```


Get the relative altitude of a mission item.


**Returns**

&emsp;float - The altitude relative to the takeoff position in metres.

### get_fly_through() {#classmavsdk_1_1_mission_item_1a595c0e9b76858155cf2f6637b802f453}
```cpp
bool mavsdk::MissionItem::get_fly_through() const
```


Get the fly-through property of a mission item.


**Returns**

&emsp;bool - true if the drone will fly through the waypoint without stopping. false if the drone will come to a stop at the waypoint before continuing.

### get_acceptance_radius_m() {#classmavsdk_1_1_mission_item_1a9d057dc8cb892a3dc4fbfdfb5db8dee5}
```cpp
float mavsdk::MissionItem::get_acceptance_radius_m() const
```


Get the acceptance radius of a mission item.


**Returns**

&emsp;float - Acceptance radius in meters.

### get_speed_m_s() {#classmavsdk_1_1_mission_item_1a8ec7abb2efb0c7613c24e019a4c3045c}
```cpp
float mavsdk::MissionItem::get_speed_m_s() const
```


Get the speed to be used after this mission item.


**Returns**

&emsp;float - Speed in metres/second.

### get_gimbal_pitch_deg() {#classmavsdk_1_1_mission_item_1a7f4cb4f8c5c758a1d0ffec3367197fa0}
```cpp
float mavsdk::MissionItem::get_gimbal_pitch_deg() const
```


Get the gimbal pitch of a mission item.


**Returns**

&emsp;float - [Gimbal](classmavsdk_1_1_gimbal.md) pitch in degrees.

### get_gimbal_yaw_deg() {#classmavsdk_1_1_mission_item_1a7d923a49f5c74c75436a60e1e0c6fdfe}
```cpp
float mavsdk::MissionItem::get_gimbal_yaw_deg() const
```


Get the gimbal yaw of a mission item.


**Returns**

&emsp;float - [Gimbal](classmavsdk_1_1_gimbal.md) yaw in degrees.

### get_loiter_time_s() {#classmavsdk_1_1_mission_item_1a2d5d345406de899943102269a8e32360}
```cpp
float mavsdk::MissionItem::get_loiter_time_s() const
```


Get loiter time in seconds.


**Returns**

&emsp;float - Loiter time in seconds.

### get_camera_action() {#classmavsdk_1_1_mission_item_1a8708b9f8684f301ad180577a7abcfb64}
```cpp
CameraAction mavsdk::MissionItem::get_camera_action() const
```


Get the camera action set for this mission item.


**Returns**

&emsp;[CameraAction](classmavsdk_1_1_mission_item.md#classmavsdk_1_1_mission_item_1a132fb8fb01a95f7da406d6691a699b33) - [Camera](classmavsdk_1_1_camera.md) action enum value.

### get_camera_photo_interval_s() {#classmavsdk_1_1_mission_item_1a873f750d6b19760a31d492d57775ea62}
```cpp
double mavsdk::MissionItem::get_camera_photo_interval_s() const
```


Get the camera photo interval that was set for this mission item.

This only has an effect if used together with [CameraAction::START_PHOTO_INTERVAL](classmavsdk_1_1_mission_item.md#classmavsdk_1_1_mission_item_1a132fb8fb01a95f7da406d6691a699b33a27eb71e5403792ee9072932ec93c113c).

**Returns**

&emsp;double - [Camera](classmavsdk_1_1_camera.md) photo interval in seconds.

### operator=() {#classmavsdk_1_1_mission_item_1af3737e3129abd684724b75a6b3690436}
```cpp
const MissionItem& mavsdk::MissionItem::operator=(const MissionItem &)=delete
```


Equality operator (object is not copyable).


**Parameters**

* const [MissionItem](classmavsdk_1_1_mission_item.md)&  - 

**Returns**

&emsp;const [MissionItem](classmavsdk_1_1_mission_item.md) & - 

### to_str() {#classmavsdk_1_1_mission_item_1a6d605f2411d9cf3c4dd57ccc94efc009}
```cpp
static std::string mavsdk::MissionItem::to_str(CameraAction camera_action)
```


Converts [CameraAction](classmavsdk_1_1_mission_item.md#classmavsdk_1_1_mission_item_1a132fb8fb01a95f7da406d6691a699b33) to English strings.


**Parameters**

* [CameraAction](classmavsdk_1_1_mission_item.md#classmavsdk_1_1_mission_item_1a132fb8fb01a95f7da406d6691a699b33) **camera_action** - Enum [CameraAction](classmavsdk_1_1_mission_item.md#classmavsdk_1_1_mission_item_1a132fb8fb01a95f7da406d6691a699b33).

**Returns**

&emsp;std::string - Human readable english string for [CameraAction](classmavsdk_1_1_mission_item.md#classmavsdk_1_1_mission_item_1a132fb8fb01a95f7da406d6691a699b33).