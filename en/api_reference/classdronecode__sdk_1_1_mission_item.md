# dronecode_sdk::MissionItem Class Reference
`#include: mission_item.h`

----


A mission is a vector of [MissionItem](classdronecode__sdk_1_1_mission_item.md)s. 


Each [MissionItem](classdronecode__sdk_1_1_mission_item.md) can contain a position and/or actions. [Mission](classdronecode__sdk_1_1_mission.md) items are just building blocks to assemble a mission, which can be sent to (or received from) a system. They cannot be used independently. 


## Public Types


Type | Description
--- | ---
enum [CameraAction](#classdronecode__sdk_1_1_mission_item_1a636a841437572871ab82e01e1c41f447) | Possible camera actions at a mission item.

## Public Member Functions


Type | Name | Description
---: | --- | ---
&nbsp; | [MissionItem](#classdronecode__sdk_1_1_mission_item_1a59a7c856d033f99b95fd819c2ac8c80b) () | Constructor (internal use only).
&nbsp; | [~MissionItem](#classdronecode__sdk_1_1_mission_item_1ac61addc663244251851400f1ec2a7808) () | Destructor (internal use only).
&nbsp; | [MissionItem](#classdronecode__sdk_1_1_mission_item_1a0ec1cbf77bdb925589209938a6ebf595) (const [MissionItem](classdronecode__sdk_1_1_mission_item.md) &)=delete | Copy constructor (object is not copyable).
void | [set_position](#classdronecode__sdk_1_1_mission_item_1a8469fed0b53e808d1929ef2fd58c79f9) (double latitude_deg, double longitude_deg) | Set the position of a mission item.
void | [set_relative_altitude](#classdronecode__sdk_1_1_mission_item_1a77e41fe9772b873b270dc8a214771e56) (float altitude_m) | Set the relative altitude of a mission item.
void | [set_fly_through](#classdronecode__sdk_1_1_mission_item_1a86478814f2f461274e0ac532390b0709) (bool fly_through) | Set the fly-through property of a mission item.
void | [set_acceptance_radius](#classdronecode__sdk_1_1_mission_item_1a0b2b8df0aebec2d7acdc31f114d669fc) (float radius_m) | Set the acceptance radius property of a mission item.
void | [set_speed](#classdronecode__sdk_1_1_mission_item_1a5404dd53832bc27d3d7a0a6bd94f6468) (float speed_m_s) | Set the speed to use after a mission item.
void | [set_gimbal_pitch_and_yaw](#classdronecode__sdk_1_1_mission_item_1a9603f1d1821a834b8347b932645a34dc) (float pitch_deg, float yaw_deg) | Set the pitch and yaw angle of a gimbal at that mission item.
void | [set_loiter_time](#classdronecode__sdk_1_1_mission_item_1abdae197c436236200026233ee55979d4) (float loiter_time_s) | Set loiter time in seconds.
void | [set_camera_action](#classdronecode__sdk_1_1_mission_item_1a777159de01fa71c4fef160bb9267a232) ([CameraAction](classdronecode__sdk_1_1_mission_item.md#classdronecode__sdk_1_1_mission_item_1a636a841437572871ab82e01e1c41f447) action) | Set the camera action for a mission item.
void | [set_camera_photo_interval](#classdronecode__sdk_1_1_mission_item_1a312672ef322270cc3b080fb2d1399b4d) (double interval_s) | Set the camera photo interval.
double | [get_latitude_deg](#classdronecode__sdk_1_1_mission_item_1a0cf77ea15a422df75c9cb4c3c4274d19) () const | Get the latitude of a mission item.
double | [get_longitude_deg](#classdronecode__sdk_1_1_mission_item_1a85743f19dda4f6c236d99f84a79b2d79) () const | Get the longitude of a mission item.
bool | [has_position_set](#classdronecode__sdk_1_1_mission_item_1a9cb97c6c0572f8036e85b7a2c0fbc5ca) () const | Reports whether position info (Lat, Lon) was set for this mission item.
float | [get_relative_altitude_m](#classdronecode__sdk_1_1_mission_item_1a55addd10b5dce0b425ad41f08e03cbea) () const | Get the relative altitude of a mission item.
bool | [get_fly_through](#classdronecode__sdk_1_1_mission_item_1a81ad2b651efff62ff9b7f522a27a21a9) () const | Get the fly-through property of a mission item.
float | [get_acceptance_radius_m](#classdronecode__sdk_1_1_mission_item_1a861064af7d8fb7ca672ade5d4a7736ac) () const | Get the acceptance radius of a mission item.
float | [get_speed_m_s](#classdronecode__sdk_1_1_mission_item_1a8072b6cec779c2fa21da586dcd27cacb) () const | Get the speed to be used after this mission item.
float | [get_gimbal_pitch_deg](#classdronecode__sdk_1_1_mission_item_1ac0d6e210ee5cc3f99adef9b67a4e02b8) () const | Get the gimbal pitch of a mission item.
float | [get_gimbal_yaw_deg](#classdronecode__sdk_1_1_mission_item_1abe4c8f82f997ccb19d07393d7bafea89) () const | Get the gimbal yaw of a mission item.
float | [get_loiter_time_s](#classdronecode__sdk_1_1_mission_item_1a9ba1fa302fb6e4e6d185e2820629389a) () const | Get loiter time in seconds.
[CameraAction](classdronecode__sdk_1_1_mission_item.md#classdronecode__sdk_1_1_mission_item_1a636a841437572871ab82e01e1c41f447) | [get_camera_action](#classdronecode__sdk_1_1_mission_item_1afd52a303be1dab36017d7fb7f88eee53) () const | Get the camera action set for this mission item.
double | [get_camera_photo_interval_s](#classdronecode__sdk_1_1_mission_item_1a6a749300fc4a0f106b9a7995b84fab3d) () const | Get the camera photo interval that was set for this mission item.
const [MissionItem](classdronecode__sdk_1_1_mission_item.md) & | [operator=](#classdronecode__sdk_1_1_mission_item_1a89aa92055f92eee11098dfb647222584) (const [MissionItem](classdronecode__sdk_1_1_mission_item.md) &)=delete | Equality operator (object is not copyable).

## Static Public Member Functions


Type | Name | Description
---: | --- | ---
std::string | [to_str](#classdronecode__sdk_1_1_mission_item_1adff5eebd214dd86246e3b65d7d4e6145) ([CameraAction](classdronecode__sdk_1_1_mission_item.md#classdronecode__sdk_1_1_mission_item_1a636a841437572871ab82e01e1c41f447) camera_action) | Converts [CameraAction](classdronecode__sdk_1_1_mission_item.md#classdronecode__sdk_1_1_mission_item_1a636a841437572871ab82e01e1c41f447) to English strings.


## Constructor & Destructor Documentation


### MissionItem() {#classdronecode__sdk_1_1_mission_item_1a59a7c856d033f99b95fd819c2ac8c80b}
```cpp
dronecode_sdk::MissionItem::MissionItem()
```


Constructor (internal use only).


### ~MissionItem() {#classdronecode__sdk_1_1_mission_item_1ac61addc663244251851400f1ec2a7808}
```cpp
dronecode_sdk::MissionItem::~MissionItem()
```


Destructor (internal use only).


### MissionItem() {#classdronecode__sdk_1_1_mission_item_1a0ec1cbf77bdb925589209938a6ebf595}
```cpp
dronecode_sdk::MissionItem::MissionItem(const MissionItem &)=delete
```


Copy constructor (object is not copyable).


**Parameters**

* const [MissionItem](classdronecode__sdk_1_1_mission_item.md)&  - 

## Member Enumeration Documentation


### enum CameraAction {#classdronecode__sdk_1_1_mission_item_1a636a841437572871ab82e01e1c41f447}


Possible camera actions at a mission item.


Value | Description
--- | ---
<span id="classdronecode__sdk_1_1_mission_item_1a636a841437572871ab82e01e1c41f447a4130de26d3895fa5de9f46ddd558315c"></span> `TAKE_PHOTO` | Take single photo. 
<span id="classdronecode__sdk_1_1_mission_item_1a636a841437572871ab82e01e1c41f447a27eb71e5403792ee9072932ec93c113c"></span> `START_PHOTO_INTERVAL` | Start capturing photos at regular intervals - see [set_camera_photo_interval()](classdronecode__sdk_1_1_mission_item.md#classdronecode__sdk_1_1_mission_item_1a312672ef322270cc3b080fb2d1399b4d). 
<span id="classdronecode__sdk_1_1_mission_item_1a636a841437572871ab82e01e1c41f447a7554aaea445f14cf06a0757ff8204b0a"></span> `STOP_PHOTO_INTERVAL` | Stop capturing photos at regular intervals. 
<span id="classdronecode__sdk_1_1_mission_item_1a636a841437572871ab82e01e1c41f447a2830bdcebb2b8bb17e19bef72a7255bc"></span> `START_VIDEO` | Start capturing video. 
<span id="classdronecode__sdk_1_1_mission_item_1a636a841437572871ab82e01e1c41f447ac7dbedd5fead832bc23d7caaf4cfb8cf"></span> `STOP_VIDEO` | Stop capturing video. 
<span id="classdronecode__sdk_1_1_mission_item_1a636a841437572871ab82e01e1c41f447ab50339a10e1de285ac99d4c3990b8693"></span> `NONE` | No action. 

**See Also:**
- [to_str()](classdronecode__sdk_1_1_mission_item.md#classdronecode__sdk_1_1_mission_item_1adff5eebd214dd86246e3b65d7d4e6145)


## Member Function Documentation


### set_position() {#classdronecode__sdk_1_1_mission_item_1a8469fed0b53e808d1929ef2fd58c79f9}
```cpp
void dronecode_sdk::MissionItem::set_position(double latitude_deg, double longitude_deg)
```


Set the position of a mission item.


**Parameters**

* double **latitude_deg** - Latitude of the waypoint in degrees.
* double **longitude_deg** - Longitude of the waypoint in degrees.

### set_relative_altitude() {#classdronecode__sdk_1_1_mission_item_1a77e41fe9772b873b270dc8a214771e56}
```cpp
void dronecode_sdk::MissionItem::set_relative_altitude(float altitude_m)
```


Set the relative altitude of a mission item.


**Parameters**

* float **altitude_m** - Altitude relative to takeoff position in metres.

### set_fly_through() {#classdronecode__sdk_1_1_mission_item_1a86478814f2f461274e0ac532390b0709}
```cpp
void dronecode_sdk::MissionItem::set_fly_through(bool fly_through)
```


Set the fly-through property of a mission item.


**Parameters**

* bool **fly_through** - If `true` the drone will fly through the waypoint without stopping. If `false` the drone will come to a stop at the waypoint before continuing.

### set_acceptance_radius() {#classdronecode__sdk_1_1_mission_item_1a0b2b8df0aebec2d7acdc31f114d669fc}
```cpp
void dronecode_sdk::MissionItem::set_acceptance_radius(float radius_m)
```


Set the acceptance radius property of a mission item.


**Parameters**

* float **radius_m** - Radius in meters around the mission_item where it will be considered as reached.

### set_speed() {#classdronecode__sdk_1_1_mission_item_1a5404dd53832bc27d3d7a0a6bd94f6468}
```cpp
void dronecode_sdk::MissionItem::set_speed(float speed_m_s)
```


Set the speed to use after a mission item.


**Parameters**

* float **speed_m_s** - Speed to use after this mission item in metres/second.

### set_gimbal_pitch_and_yaw() {#classdronecode__sdk_1_1_mission_item_1a9603f1d1821a834b8347b932645a34dc}
```cpp
void dronecode_sdk::MissionItem::set_gimbal_pitch_and_yaw(float pitch_deg, float yaw_deg)
```


Set the pitch and yaw angle of a gimbal at that mission item.


**Parameters**

* float **pitch_deg** - The new pitch angle of the gimbal in degrees (0: horizontal, positive up, -90: vertical downward facing).
* float **yaw_deg** - The new yaw angle of the gimbal in degrees (0: forward, positive clock-wise, 90: to the right).

### set_loiter_time() {#classdronecode__sdk_1_1_mission_item_1abdae197c436236200026233ee55979d4}
```cpp
void dronecode_sdk::MissionItem::set_loiter_time(float loiter_time_s)
```


Set loiter time in seconds.

This specifies the delay at a waypoint before executing next mission item. It can be used to wait for vehicle to slow down or a gimbal to arrive at the set orientation.

**Parameters**

* float **loiter_time_s** - The time to wait (loiter), in seconds.

### set_camera_action() {#classdronecode__sdk_1_1_mission_item_1a777159de01fa71c4fef160bb9267a232}
```cpp
void dronecode_sdk::MissionItem::set_camera_action(CameraAction action)
```


Set the camera action for a mission item.


**Parameters**

* [CameraAction](classdronecode__sdk_1_1_mission_item.md#classdronecode__sdk_1_1_mission_item_1a636a841437572871ab82e01e1c41f447) **action** - The camera action.

### set_camera_photo_interval() {#classdronecode__sdk_1_1_mission_item_1a312672ef322270cc3b080fb2d1399b4d}
```cpp
void dronecode_sdk::MissionItem::set_camera_photo_interval(double interval_s)
```


Set the camera photo interval.

This only has an effect if used together with [CameraAction::START_PHOTO_INTERVAL](classdronecode__sdk_1_1_mission_item.md#classdronecode__sdk_1_1_mission_item_1a636a841437572871ab82e01e1c41f447a27eb71e5403792ee9072932ec93c113c).

**Parameters**

* double **interval_s** - Interval between photo captures in seconds.

### get_latitude_deg() {#classdronecode__sdk_1_1_mission_item_1a0cf77ea15a422df75c9cb4c3c4274d19}
```cpp
double dronecode_sdk::MissionItem::get_latitude_deg() const
```


Get the latitude of a mission item.


**Returns**

&emsp;double - Latitude in degrees.

### get_longitude_deg() {#classdronecode__sdk_1_1_mission_item_1a85743f19dda4f6c236d99f84a79b2d79}
```cpp
double dronecode_sdk::MissionItem::get_longitude_deg() const
```


Get the longitude of a mission item.


**Returns**

&emsp;double - Longitude in degrees.

### has_position_set() {#classdronecode__sdk_1_1_mission_item_1a9cb97c6c0572f8036e85b7a2c0fbc5ca}
```cpp
bool dronecode_sdk::MissionItem::has_position_set() const
```


Reports whether position info (Lat, Lon) was set for this mission item.


**Returns**

&emsp;bool - true if Lat, Lon is set for this mission item.

### get_relative_altitude_m() {#classdronecode__sdk_1_1_mission_item_1a55addd10b5dce0b425ad41f08e03cbea}
```cpp
float dronecode_sdk::MissionItem::get_relative_altitude_m() const
```


Get the relative altitude of a mission item.


**Returns**

&emsp;float - The altitude relative to the takeoff position in metres.

### get_fly_through() {#classdronecode__sdk_1_1_mission_item_1a81ad2b651efff62ff9b7f522a27a21a9}
```cpp
bool dronecode_sdk::MissionItem::get_fly_through() const
```


Get the fly-through property of a mission item.


**Returns**

&emsp;bool - true if the drone will fly through the waypoint without stopping. false if the drone will come to a stop at the waypoint before continuing.

### get_acceptance_radius_m() {#classdronecode__sdk_1_1_mission_item_1a861064af7d8fb7ca672ade5d4a7736ac}
```cpp
float dronecode_sdk::MissionItem::get_acceptance_radius_m() const
```


Get the acceptance radius of a mission item.


**Returns**

&emsp;float - Acceptance radius in meters.

### get_speed_m_s() {#classdronecode__sdk_1_1_mission_item_1a8072b6cec779c2fa21da586dcd27cacb}
```cpp
float dronecode_sdk::MissionItem::get_speed_m_s() const
```


Get the speed to be used after this mission item.


**Returns**

&emsp;float - Speed in metres/second.

### get_gimbal_pitch_deg() {#classdronecode__sdk_1_1_mission_item_1ac0d6e210ee5cc3f99adef9b67a4e02b8}
```cpp
float dronecode_sdk::MissionItem::get_gimbal_pitch_deg() const
```


Get the gimbal pitch of a mission item.


**Returns**

&emsp;float - [Gimbal](classdronecode__sdk_1_1_gimbal.md) pitch in degrees.

### get_gimbal_yaw_deg() {#classdronecode__sdk_1_1_mission_item_1abe4c8f82f997ccb19d07393d7bafea89}
```cpp
float dronecode_sdk::MissionItem::get_gimbal_yaw_deg() const
```


Get the gimbal yaw of a mission item.


**Returns**

&emsp;float - [Gimbal](classdronecode__sdk_1_1_gimbal.md) yaw in degrees.

### get_loiter_time_s() {#classdronecode__sdk_1_1_mission_item_1a9ba1fa302fb6e4e6d185e2820629389a}
```cpp
float dronecode_sdk::MissionItem::get_loiter_time_s() const
```


Get loiter time in seconds.


**Returns**

&emsp;float - Loiter time in seconds.

### get_camera_action() {#classdronecode__sdk_1_1_mission_item_1afd52a303be1dab36017d7fb7f88eee53}
```cpp
CameraAction dronecode_sdk::MissionItem::get_camera_action() const
```


Get the camera action set for this mission item.


**Returns**

&emsp;[CameraAction](classdronecode__sdk_1_1_mission_item.md#classdronecode__sdk_1_1_mission_item_1a636a841437572871ab82e01e1c41f447) - [Camera](classdronecode__sdk_1_1_camera.md) action enum value.

### get_camera_photo_interval_s() {#classdronecode__sdk_1_1_mission_item_1a6a749300fc4a0f106b9a7995b84fab3d}
```cpp
double dronecode_sdk::MissionItem::get_camera_photo_interval_s() const
```


Get the camera photo interval that was set for this mission item.

This only has an effect if used together with [CameraAction::START_PHOTO_INTERVAL](classdronecode__sdk_1_1_mission_item.md#classdronecode__sdk_1_1_mission_item_1a636a841437572871ab82e01e1c41f447a27eb71e5403792ee9072932ec93c113c).

**Returns**

&emsp;double - [Camera](classdronecode__sdk_1_1_camera.md) photo interval in seconds.

### operator=() {#classdronecode__sdk_1_1_mission_item_1a89aa92055f92eee11098dfb647222584}
```cpp
const MissionItem& dronecode_sdk::MissionItem::operator=(const MissionItem &)=delete
```


Equality operator (object is not copyable).


**Parameters**

* const [MissionItem](classdronecode__sdk_1_1_mission_item.md)&  - 

**Returns**

&emsp;const [MissionItem](classdronecode__sdk_1_1_mission_item.md) & - 

### to_str() {#classdronecode__sdk_1_1_mission_item_1adff5eebd214dd86246e3b65d7d4e6145}
```cpp
static std::string dronecode_sdk::MissionItem::to_str(CameraAction camera_action)
```


Converts [CameraAction](classdronecode__sdk_1_1_mission_item.md#classdronecode__sdk_1_1_mission_item_1a636a841437572871ab82e01e1c41f447) to English strings.


**Parameters**

* [CameraAction](classdronecode__sdk_1_1_mission_item.md#classdronecode__sdk_1_1_mission_item_1a636a841437572871ab82e01e1c41f447) **camera_action** - Enum [CameraAction](classdronecode__sdk_1_1_mission_item.md#classdronecode__sdk_1_1_mission_item_1a636a841437572871ab82e01e1c41f447).

**Returns**

&emsp;std::string - Human readable english string for [CameraAction](classdronecode__sdk_1_1_mission_item.md#classdronecode__sdk_1_1_mission_item_1a636a841437572871ab82e01e1c41f447).