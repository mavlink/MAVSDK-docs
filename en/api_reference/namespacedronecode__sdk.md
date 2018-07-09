# dronecode_sdk Namespace Reference

----

Namespace for all [dronecode_sdk](namespacedronecode__sdk.md) types.


## Data Structures

* [dronecode_sdk::Action](classdronecode__sdk_1_1_action.md)
* [dronecode_sdk::Calibration](classdronecode__sdk_1_1_calibration.md)
* [dronecode_sdk::Camera](classdronecode__sdk_1_1_camera.md)
* [dronecode_sdk::DronecodeSDK](classdronecode__sdk_1_1_dronecode_s_d_k.md)
* [dronecode_sdk::FollowMe](classdronecode__sdk_1_1_follow_me.md)
* [dronecode_sdk::Gimbal](classdronecode__sdk_1_1_gimbal.md)
* [dronecode_sdk::Info](classdronecode__sdk_1_1_info.md)
* [dronecode_sdk::Logging](classdronecode__sdk_1_1_logging.md)
* [dronecode_sdk::Mission](classdronecode__sdk_1_1_mission.md)
* [dronecode_sdk::MissionItem](classdronecode__sdk_1_1_mission_item.md)
* [dronecode_sdk::Offboard](classdronecode__sdk_1_1_offboard.md)
* [dronecode_sdk::PluginBase](classdronecode__sdk_1_1_plugin_base.md)
* [dronecode_sdk::System](classdronecode__sdk_1_1_system.md)
* [dronecode_sdk::Telemetry](classdronecode__sdk_1_1_telemetry.md)

## Enumerations

Type | Description
--- | ---
enum [ActionResult](#namespacedronecode__sdk_1a03f15ca37e363d61087d14b709b1861e) | Possible results returned for commanded actions.
enum [ConnectionResult](#namespacedronecode__sdk_1a8ba260cb5fc0837533a86e236d205c96) | Result type returned when adding a connection.

## Functions

Type | Name | Description
--- | --- | ---
const char * | [action_result_str](#namespacedronecode__sdk_1a317e77ee37b9d47c863d1ee1cf3d20e0) ([ActionResult](namespacedronecode__sdk.md#namespacedronecode__sdk_1a03f15ca37e363d61087d14b709b1861e) result) | Returns a human-readable English string for an ActionResult.
const char * | [connection_result_str](#namespacedronecode__sdk_1a4f99d135d291363375982e84b6928f38) (const [ConnectionResult](namespacedronecode__sdk.md#namespacedronecode__sdk_1a8ba260cb5fc0837533a86e236d205c96) result) | Returns a human-readable English string for a ConnectionResult.
bool | [operator==](#namespacedronecode__sdk_1add402a7e54e431c79040066cf0eb009a) (const [MissionItem](classdronecode__sdk_1_1_mission_item.md) & lhs, const [MissionItem](classdronecode__sdk_1_1_mission_item.md) & rhs) | Equal operator to compare two [MissionItem](classdronecode__sdk_1_1_mission_item.md) objects.
std::ostream & | [operator<<](#namespacedronecode__sdk_1a099ffe3cf3144ce815d31b2d1798ee1f) (std::ostream & str, [MissionItem](classdronecode__sdk_1_1_mission_item.md) const & mission_item) | Stream operator to print infos about a [MissionItem](classdronecode__sdk_1_1_mission_item.md).
std::ostream & | [operator<<](#namespacedronecode__sdk_1aba2a59ff24c643d38cd2f8f953d12aa0) (std::ostream & str, [MissionItem::CameraAction](classdronecode__sdk_1_1_mission_item.md#classdronecode__sdk_1_1_mission_item_1a636a841437572871ab82e01e1c41f447) const & camera_action) | Stream operator to print infos about a [MissionItem::CameraAction](classdronecode__sdk_1_1_mission_item.md#classdronecode__sdk_1_1_mission_item_1a636a841437572871ab82e01e1c41f447).
bool | [operator==](#namespacedronecode__sdk_1a70e13ff33048ec0b6a8d100dc813a84a) (const [Telemetry::PositionVelocityNED](structdronecode__sdk_1_1_telemetry_1_1_position_velocity_n_e_d.md) & lhs, const [Telemetry::PositionVelocityNED](structdronecode__sdk_1_1_telemetry_1_1_position_velocity_n_e_d.md) & rhs) | Equal operator to compare two [Telemetry::PositionVelocityNED](structdronecode__sdk_1_1_telemetry_1_1_position_velocity_n_e_d.md) objects.
bool | [operator==](#namespacedronecode__sdk_1aeee7bba4738b277d079f347b8f48a1e7) (const [Telemetry::Position](structdronecode__sdk_1_1_telemetry_1_1_position.md) & lhs, const [Telemetry::Position](structdronecode__sdk_1_1_telemetry_1_1_position.md) & rhs) | Equal operator to compare two [Telemetry::Position](structdronecode__sdk_1_1_telemetry_1_1_position.md) objects.
std::ostream & | [operator<<](#namespacedronecode__sdk_1a1d3838c8844e1dc4a784c789f29f5267) (std::ostream & str, [Telemetry::Position](structdronecode__sdk_1_1_telemetry_1_1_position.md) const & position) | Stream operator to print information about a [Telemetry::Position](structdronecode__sdk_1_1_telemetry_1_1_position.md).
bool | [operator==](#namespacedronecode__sdk_1a023eddb27d7cee0950801ce1e1445ada) (const [Telemetry::Health](structdronecode__sdk_1_1_telemetry_1_1_health.md) & lhs, const [Telemetry::Health](structdronecode__sdk_1_1_telemetry_1_1_health.md) & rhs) | Equal operator to compare two [Telemetry::Health](structdronecode__sdk_1_1_telemetry_1_1_health.md) objects.
std::ostream & | [operator<<](#namespacedronecode__sdk_1a28f6d4519e116bed2fb0457455742ee1) (std::ostream & str, [Telemetry::Health](structdronecode__sdk_1_1_telemetry_1_1_health.md) const & health) | Stream operator to print information about a [Telemetry::Health](structdronecode__sdk_1_1_telemetry_1_1_health.md).
bool | [operator==](#namespacedronecode__sdk_1ab03745281710b020b9ac76daf16140ed) (const [Telemetry::GPSInfo](structdronecode__sdk_1_1_telemetry_1_1_g_p_s_info.md) & lhs, const [Telemetry::GPSInfo](structdronecode__sdk_1_1_telemetry_1_1_g_p_s_info.md) & rhs) | Equal operator to compare two [Telemetry::GPSInfo](structdronecode__sdk_1_1_telemetry_1_1_g_p_s_info.md) objects.
std::ostream & | [operator<<](#namespacedronecode__sdk_1ae92c2a91b6fa86a56494a6086299d60d) (std::ostream & str, [Telemetry::GPSInfo](structdronecode__sdk_1_1_telemetry_1_1_g_p_s_info.md) const & gps_info) | Stream operator to print information about a [Telemetry::GPSInfo](structdronecode__sdk_1_1_telemetry_1_1_g_p_s_info.md).
bool | [operator==](#namespacedronecode__sdk_1a5cb7b16c1ebe37da78b81a40da3137da) (const [Telemetry::Battery](structdronecode__sdk_1_1_telemetry_1_1_battery.md) & lhs, const [Telemetry::Battery](structdronecode__sdk_1_1_telemetry_1_1_battery.md) & rhs) | Equal operator to compare two [Telemetry::Battery](structdronecode__sdk_1_1_telemetry_1_1_battery.md) objects.
std::ostream & | [operator<<](#namespacedronecode__sdk_1a6299693fefce3144cf2ba0a27c4dd955) (std::ostream & str, [Telemetry::Battery](structdronecode__sdk_1_1_telemetry_1_1_battery.md) const & battery) | Stream operator to print information about a [Telemetry::Battery](structdronecode__sdk_1_1_telemetry_1_1_battery.md).
bool | [operator==](#namespacedronecode__sdk_1aa65226e58f9b3c7f134d9c195ece6424) (const [Telemetry::Quaternion](structdronecode__sdk_1_1_telemetry_1_1_quaternion.md) & lhs, const [Telemetry::Quaternion](structdronecode__sdk_1_1_telemetry_1_1_quaternion.md) & rhs) | Equal operator to compare two [Telemetry::Quaternion](structdronecode__sdk_1_1_telemetry_1_1_quaternion.md) objects.
std::ostream & | [operator<<](#namespacedronecode__sdk_1a082304afec256131fcc09564cbc805e5) (std::ostream & str, [Telemetry::Quaternion](structdronecode__sdk_1_1_telemetry_1_1_quaternion.md) const & quaternion) | Stream operator to print information about a [Telemetry::Quaternion](structdronecode__sdk_1_1_telemetry_1_1_quaternion.md).
bool | [operator==](#namespacedronecode__sdk_1aa6e3534d0274ff548533fe554938c46c) (const [Telemetry::EulerAngle](structdronecode__sdk_1_1_telemetry_1_1_euler_angle.md) & lhs, const [Telemetry::EulerAngle](structdronecode__sdk_1_1_telemetry_1_1_euler_angle.md) & rhs) | Equal operator to compare two [Telemetry::EulerAngle](structdronecode__sdk_1_1_telemetry_1_1_euler_angle.md) objects.
std::ostream & | [operator<<](#namespacedronecode__sdk_1a5ffcb10a86abe49a909a3641689974de) (std::ostream & str, [Telemetry::EulerAngle](structdronecode__sdk_1_1_telemetry_1_1_euler_angle.md) const & euler_angle) | Stream operator to print information about a [Telemetry::EulerAngle](structdronecode__sdk_1_1_telemetry_1_1_euler_angle.md).
bool | [operator==](#namespacedronecode__sdk_1aaf687fbbe3cfe22bc3f5af30595d4b2e) (const [Telemetry::GroundSpeedNED](structdronecode__sdk_1_1_telemetry_1_1_ground_speed_n_e_d.md) & lhs, const [Telemetry::GroundSpeedNED](structdronecode__sdk_1_1_telemetry_1_1_ground_speed_n_e_d.md) & rhs) | Equal operator to compare two [Telemetry::GroundSpeedNED](structdronecode__sdk_1_1_telemetry_1_1_ground_speed_n_e_d.md) objects.
std::ostream & | [operator<<](#namespacedronecode__sdk_1ab1411c69c211b5eb231f1ad4ff893679) (std::ostream & str, [Telemetry::GroundSpeedNED](structdronecode__sdk_1_1_telemetry_1_1_ground_speed_n_e_d.md) const & ground_speed) | Stream operator to print information about a [Telemetry::GroundSpeedNED](structdronecode__sdk_1_1_telemetry_1_1_ground_speed_n_e_d.md).
bool | [operator==](#namespacedronecode__sdk_1a2146a33adf4b5d158aff9b6e53fd06ab) (const [Telemetry::RCStatus](structdronecode__sdk_1_1_telemetry_1_1_r_c_status.md) & lhs, const [Telemetry::RCStatus](structdronecode__sdk_1_1_telemetry_1_1_r_c_status.md) & rhs) | Equal operator to compare two [Telemetry::RCStatus](structdronecode__sdk_1_1_telemetry_1_1_r_c_status.md) objects.
std::ostream & | [operator<<](#namespacedronecode__sdk_1a4acb99b3d173ad128a4083096dac1995) (std::ostream & str, [Telemetry::RCStatus](structdronecode__sdk_1_1_telemetry_1_1_r_c_status.md) const & rc_status) | Stream operator to print information about a [Telemetry::RCStatus](structdronecode__sdk_1_1_telemetry_1_1_r_c_status.md).

## Enumeration Type Documentation


### enum ActionResult {#namespacedronecode__sdk_1a03f15ca37e363d61087d14b709b1861e}

```
#include: action_result.h
```


Possible results returned for commanded actions.

> **Note** [DronecodeSDK](classdronecode__sdk_1_1_dronecode_s_d_k.md) does not throw exceptions. Instead a result of this type will be returned when you execute actions.

Value | Description
--- | ---
<span id="namespacedronecode__sdk_1a03f15ca37e363d61087d14b709b1861ea696b031073e74bf2cb98e5ef201d4aa3"></span> `UNKNOWN` | Unspecified error. 
<span id="namespacedronecode__sdk_1a03f15ca37e363d61087d14b709b1861ead0749aaba8b833466dfcbb0428e4f89c"></span> `SUCCESS` | Success. The action command was accepted by the vehicle. 
<span id="namespacedronecode__sdk_1a03f15ca37e363d61087d14b709b1861eafeae72a3a2feec3c92c2a79a30d31186"></span> `NO_SYSTEM` | No system is connected error. 
<span id="namespacedronecode__sdk_1a03f15ca37e363d61087d14b709b1861eac77f1f09dab2c0c9980fca7cfae02518"></span> `CONNECTION_ERROR` | Connection error. 
<span id="namespacedronecode__sdk_1a03f15ca37e363d61087d14b709b1861ea802706a9238e2928077f97736854bad4"></span> `BUSY` | Vehicle busy error. 
<span id="namespacedronecode__sdk_1a03f15ca37e363d61087d14b709b1861ea6fa4dbf368cea972db8d9156799d5dbe"></span> `COMMAND_DENIED` | Command refused by vehicle. 
<span id="namespacedronecode__sdk_1a03f15ca37e363d61087d14b709b1861ea939d986bd1af6a2e1db07a61a60f7ae2"></span> `COMMAND_DENIED_LANDED_STATE_UNKNOWN` | Command refused because landed state is unknown. 
<span id="namespacedronecode__sdk_1a03f15ca37e363d61087d14b709b1861ead7e95e2842caf0baff502fbd1290fd69"></span> `COMMAND_DENIED_NOT_LANDED` | Command refused because vehicle not landed. 
<span id="namespacedronecode__sdk_1a03f15ca37e363d61087d14b709b1861ea070a0fb40f6c308ab544b227660aadff"></span> `TIMEOUT` | Timeout waiting for command acknowledgement from vehicle. 
<span id="namespacedronecode__sdk_1a03f15ca37e363d61087d14b709b1861ea59e19d623bfb3a7a60195410afcbe31f"></span> `VTOL_TRANSITION_SUPPORT_UNKNOWN` | hybrid/VTOL transition refused because VTOL support is unknown. 
<span id="namespacedronecode__sdk_1a03f15ca37e363d61087d14b709b1861eaf3712e88cb2a09f0d5b72e8e493b53be"></span> `NO_VTOL_TRANSITION_SUPPORT` | Vehicle does not support hybrid/VTOL transitions. 

### enum ConnectionResult {#namespacedronecode__sdk_1a8ba260cb5fc0837533a86e236d205c96}

```
#include: connection_result.h
```


Result type returned when adding a connection.

**Note**: [DronecodeSDK](classdronecode__sdk_1_1_dronecode_s_d_k.md) does not throw exceptions. Instead a result of this type will be returned when you add a connection: add_udp_connection().

Value | Description
--- | ---
<span id="namespacedronecode__sdk_1a8ba260cb5fc0837533a86e236d205c96ad0749aaba8b833466dfcbb0428e4f89c"></span> `SUCCESS` | Connection succeeded. 
<span id="namespacedronecode__sdk_1a8ba260cb5fc0837533a86e236d205c96a070a0fb40f6c308ab544b227660aadff"></span> `TIMEOUT` | Connection timed out. 
<span id="namespacedronecode__sdk_1a8ba260cb5fc0837533a86e236d205c96aac87548d79aa92c60dcfac06ae83e5ad"></span> `SOCKET_ERROR` | Socket error. 
<span id="namespacedronecode__sdk_1a8ba260cb5fc0837533a86e236d205c96af69a41125696a14c45a8182ce7ba83a7"></span> `BIND_ERROR` | Bind error. 
<span id="namespacedronecode__sdk_1a8ba260cb5fc0837533a86e236d205c96a20766ec998922f65e7ac718b7a9b7a22"></span> `SOCKET_CONNECTION_ERROR` | Socket connection error. 
<span id="namespacedronecode__sdk_1a8ba260cb5fc0837533a86e236d205c96ac77f1f09dab2c0c9980fca7cfae02518"></span> `CONNECTION_ERROR` | Connection error. 
<span id="namespacedronecode__sdk_1a8ba260cb5fc0837533a86e236d205c96a3e860a081575fc82cc7b6ed2ca602947"></span> `NOT_IMPLEMENTED` | Connection type not implemented. 
<span id="namespacedronecode__sdk_1a8ba260cb5fc0837533a86e236d205c96a222a5d8795464ca9a47b49daf1357538"></span> `SYSTEM_NOT_CONNECTED` | No system is connected. 
<span id="namespacedronecode__sdk_1a8ba260cb5fc0837533a86e236d205c96a5a426189f0eb9043da73058f959c2ba1"></span> `SYSTEM_BUSY` | System is busy. 
<span id="namespacedronecode__sdk_1a8ba260cb5fc0837533a86e236d205c96a6fa4dbf368cea972db8d9156799d5dbe"></span> `COMMAND_DENIED` | Command is denied. 
<span id="namespacedronecode__sdk_1a8ba260cb5fc0837533a86e236d205c96a588cf56f08269878b055227a8490de67"></span> `DESTINATION_IP_UNKNOWN` | Connection IP is unknown. 
<span id="namespacedronecode__sdk_1a8ba260cb5fc0837533a86e236d205c96a9532aa7fe8e205a02479a2e43d05f6b1"></span> `CONNECTIONS_EXHAUSTED` | Connections exhausted. 
<span id="namespacedronecode__sdk_1a8ba260cb5fc0837533a86e236d205c96a269972fd1df83e8f423abead920f8780"></span> `CONNECTION_URL_INVALID` | URL invalid. 

## Function Documentation


### action_result_str() {#namespacedronecode__sdk_1a317e77ee37b9d47c863d1ee1cf3d20e0}

```
#include: action_result.h
```
```cpp
const char* dronecode_sdk::action_result_str(ActionResult result)
```


Returns a human-readable English string for an ActionResult.


**Parameters**

* [ActionResult](namespacedronecode__sdk.md#namespacedronecode__sdk_1a03f15ca37e363d61087d14b709b1861e) **result** - The enum value for which a human readable string is required.

**Returns**

&emsp;const char * - Human readable string for the ActionResult.

### connection_result_str() {#namespacedronecode__sdk_1a4f99d135d291363375982e84b6928f38}

```
#include: connection_result.h
```
```cpp
const char* dronecode_sdk::connection_result_str(const ConnectionResult result)
```


Returns a human-readable English string for a ConnectionResult.


**Parameters**

* const [ConnectionResult](namespacedronecode__sdk.md#namespacedronecode__sdk_1a8ba260cb5fc0837533a86e236d205c96) **result** - The enum value for which a human readable string is required.

**Returns**

&emsp;const char * - Human readable string for the ConnectionResult.

### operator==() {#namespacedronecode__sdk_1add402a7e54e431c79040066cf0eb009a}

```
#include: mission_item.h
```
```cpp
bool dronecode_sdk::operator==(const MissionItem &lhs, const MissionItem &rhs)
```


Equal operator to compare two [MissionItem](classdronecode__sdk_1_1_mission_item.md) objects.


**Parameters**

* const [MissionItem](classdronecode__sdk_1_1_mission_item.md)& **lhs** - 
* const [MissionItem](classdronecode__sdk_1_1_mission_item.md)& **rhs** - 

**Returns**

&emsp;bool - `true` if items are equal.

### operator<<() {#namespacedronecode__sdk_1a099ffe3cf3144ce815d31b2d1798ee1f}

```
#include: mission_item.h
```
```cpp
std::ostream& dronecode_sdk::operator<<(std::ostream &str, MissionItem const &mission_item)
```


Stream operator to print infos about a [MissionItem](classdronecode__sdk_1_1_mission_item.md).


**Parameters**

* std::ostream& **str** - 
* [MissionItem](classdronecode__sdk_1_1_mission_item.md) const& **mission_item** - 

**Returns**

&emsp;std::ostream & - A reference to the stream.

### operator<<() {#namespacedronecode__sdk_1aba2a59ff24c643d38cd2f8f953d12aa0}

```
#include: mission_item.h
```
```cpp
std::ostream& dronecode_sdk::operator<<(std::ostream &str, MissionItem::CameraAction const &camera_action)
```


Stream operator to print infos about a [MissionItem::CameraAction](classdronecode__sdk_1_1_mission_item.md#classdronecode__sdk_1_1_mission_item_1a636a841437572871ab82e01e1c41f447).


**Parameters**

* std::ostream& **str** - 
* [MissionItem::CameraAction](classdronecode__sdk_1_1_mission_item.md#classdronecode__sdk_1_1_mission_item_1a636a841437572871ab82e01e1c41f447) const& **camera_action** - 

**Returns**

&emsp;std::ostream & - A reference to the stream.

### operator==() {#namespacedronecode__sdk_1a70e13ff33048ec0b6a8d100dc813a84a}

```
#include: telemetry.h
```
```cpp
bool dronecode_sdk::operator==(const Telemetry::PositionVelocityNED &lhs, const Telemetry::PositionVelocityNED &rhs)
```


Equal operator to compare two [Telemetry::PositionVelocityNED](structdronecode__sdk_1_1_telemetry_1_1_position_velocity_n_e_d.md) objects.


**Parameters**

* const [Telemetry::PositionVelocityNED](structdronecode__sdk_1_1_telemetry_1_1_position_velocity_n_e_d.md)& **lhs** - 
* const [Telemetry::PositionVelocityNED](structdronecode__sdk_1_1_telemetry_1_1_position_velocity_n_e_d.md)& **rhs** - 

**Returns**

&emsp;bool - `true` if items are equal.

### operator==() {#namespacedronecode__sdk_1aeee7bba4738b277d079f347b8f48a1e7}

```
#include: telemetry.h
```
```cpp
bool dronecode_sdk::operator==(const Telemetry::Position &lhs, const Telemetry::Position &rhs)
```


Equal operator to compare two [Telemetry::Position](structdronecode__sdk_1_1_telemetry_1_1_position.md) objects.


**Parameters**

* const [Telemetry::Position](structdronecode__sdk_1_1_telemetry_1_1_position.md)& **lhs** - 
* const [Telemetry::Position](structdronecode__sdk_1_1_telemetry_1_1_position.md)& **rhs** - 

**Returns**

&emsp;bool - `true` if items are equal.

### operator<<() {#namespacedronecode__sdk_1a1d3838c8844e1dc4a784c789f29f5267}

```
#include: telemetry.h
```
```cpp
std::ostream& dronecode_sdk::operator<<(std::ostream &str, Telemetry::Position const &position)
```


Stream operator to print information about a [Telemetry::Position](structdronecode__sdk_1_1_telemetry_1_1_position.md).


**Parameters**

* std::ostream& **str** - 
* [Telemetry::Position](structdronecode__sdk_1_1_telemetry_1_1_position.md) const& **position** - 

**Returns**

&emsp;std::ostream & - A reference to the stream.

### operator==() {#namespacedronecode__sdk_1a023eddb27d7cee0950801ce1e1445ada}

```
#include: telemetry.h
```
```cpp
bool dronecode_sdk::operator==(const Telemetry::Health &lhs, const Telemetry::Health &rhs)
```


Equal operator to compare two [Telemetry::Health](structdronecode__sdk_1_1_telemetry_1_1_health.md) objects.


**Parameters**

* const [Telemetry::Health](structdronecode__sdk_1_1_telemetry_1_1_health.md)& **lhs** - 
* const [Telemetry::Health](structdronecode__sdk_1_1_telemetry_1_1_health.md)& **rhs** - 

**Returns**

&emsp;bool - `true` if items are equal.

### operator<<() {#namespacedronecode__sdk_1a28f6d4519e116bed2fb0457455742ee1}

```
#include: telemetry.h
```
```cpp
std::ostream& dronecode_sdk::operator<<(std::ostream &str, Telemetry::Health const &health)
```


Stream operator to print information about a [Telemetry::Health](structdronecode__sdk_1_1_telemetry_1_1_health.md).


**Parameters**

* std::ostream& **str** - 
* [Telemetry::Health](structdronecode__sdk_1_1_telemetry_1_1_health.md) const& **health** - 

**Returns**

&emsp;std::ostream & - A reference to the stream.

### operator==() {#namespacedronecode__sdk_1ab03745281710b020b9ac76daf16140ed}

```
#include: telemetry.h
```
```cpp
bool dronecode_sdk::operator==(const Telemetry::GPSInfo &lhs, const Telemetry::GPSInfo &rhs)
```


Equal operator to compare two [Telemetry::GPSInfo](structdronecode__sdk_1_1_telemetry_1_1_g_p_s_info.md) objects.


**Parameters**

* const [Telemetry::GPSInfo](structdronecode__sdk_1_1_telemetry_1_1_g_p_s_info.md)& **lhs** - 
* const [Telemetry::GPSInfo](structdronecode__sdk_1_1_telemetry_1_1_g_p_s_info.md)& **rhs** - 

**Returns**

&emsp;bool - `true` if items are equal.

### operator<<() {#namespacedronecode__sdk_1ae92c2a91b6fa86a56494a6086299d60d}

```
#include: telemetry.h
```
```cpp
std::ostream& dronecode_sdk::operator<<(std::ostream &str, Telemetry::GPSInfo const &gps_info)
```


Stream operator to print information about a [Telemetry::GPSInfo](structdronecode__sdk_1_1_telemetry_1_1_g_p_s_info.md).


**Parameters**

* std::ostream& **str** - 
* [Telemetry::GPSInfo](structdronecode__sdk_1_1_telemetry_1_1_g_p_s_info.md) const& **gps_info** - 

**Returns**

&emsp;std::ostream & - A reference to the stream.

### operator==() {#namespacedronecode__sdk_1a5cb7b16c1ebe37da78b81a40da3137da}

```
#include: telemetry.h
```
```cpp
bool dronecode_sdk::operator==(const Telemetry::Battery &lhs, const Telemetry::Battery &rhs)
```


Equal operator to compare two [Telemetry::Battery](structdronecode__sdk_1_1_telemetry_1_1_battery.md) objects.


**Parameters**

* const [Telemetry::Battery](structdronecode__sdk_1_1_telemetry_1_1_battery.md)& **lhs** - 
* const [Telemetry::Battery](structdronecode__sdk_1_1_telemetry_1_1_battery.md)& **rhs** - 

**Returns**

&emsp;bool - `true` if items are equal.

### operator<<() {#namespacedronecode__sdk_1a6299693fefce3144cf2ba0a27c4dd955}

```
#include: telemetry.h
```
```cpp
std::ostream& dronecode_sdk::operator<<(std::ostream &str, Telemetry::Battery const &battery)
```


Stream operator to print information about a [Telemetry::Battery](structdronecode__sdk_1_1_telemetry_1_1_battery.md).


**Parameters**

* std::ostream& **str** - 
* [Telemetry::Battery](structdronecode__sdk_1_1_telemetry_1_1_battery.md) const& **battery** - 

**Returns**

&emsp;std::ostream & - A reference to the stream.

### operator==() {#namespacedronecode__sdk_1aa65226e58f9b3c7f134d9c195ece6424}

```
#include: telemetry.h
```
```cpp
bool dronecode_sdk::operator==(const Telemetry::Quaternion &lhs, const Telemetry::Quaternion &rhs)
```


Equal operator to compare two [Telemetry::Quaternion](structdronecode__sdk_1_1_telemetry_1_1_quaternion.md) objects.


**Parameters**

* const [Telemetry::Quaternion](structdronecode__sdk_1_1_telemetry_1_1_quaternion.md)& **lhs** - 
* const [Telemetry::Quaternion](structdronecode__sdk_1_1_telemetry_1_1_quaternion.md)& **rhs** - 

**Returns**

&emsp;bool - `true` if items are equal.

### operator<<() {#namespacedronecode__sdk_1a082304afec256131fcc09564cbc805e5}

```
#include: telemetry.h
```
```cpp
std::ostream& dronecode_sdk::operator<<(std::ostream &str, Telemetry::Quaternion const &quaternion)
```


Stream operator to print information about a [Telemetry::Quaternion](structdronecode__sdk_1_1_telemetry_1_1_quaternion.md).


**Parameters**

* std::ostream& **str** - 
* [Telemetry::Quaternion](structdronecode__sdk_1_1_telemetry_1_1_quaternion.md) const& **quaternion** - 

**Returns**

&emsp;std::ostream & - A reference to the stream.

### operator==() {#namespacedronecode__sdk_1aa6e3534d0274ff548533fe554938c46c}

```
#include: telemetry.h
```
```cpp
bool dronecode_sdk::operator==(const Telemetry::EulerAngle &lhs, const Telemetry::EulerAngle &rhs)
```


Equal operator to compare two [Telemetry::EulerAngle](structdronecode__sdk_1_1_telemetry_1_1_euler_angle.md) objects.


**Parameters**

* const [Telemetry::EulerAngle](structdronecode__sdk_1_1_telemetry_1_1_euler_angle.md)& **lhs** - 
* const [Telemetry::EulerAngle](structdronecode__sdk_1_1_telemetry_1_1_euler_angle.md)& **rhs** - 

**Returns**

&emsp;bool - `true` if items are equal.

### operator<<() {#namespacedronecode__sdk_1a5ffcb10a86abe49a909a3641689974de}

```
#include: telemetry.h
```
```cpp
std::ostream& dronecode_sdk::operator<<(std::ostream &str, Telemetry::EulerAngle const &euler_angle)
```


Stream operator to print information about a [Telemetry::EulerAngle](structdronecode__sdk_1_1_telemetry_1_1_euler_angle.md).


**Parameters**

* std::ostream& **str** - 
* [Telemetry::EulerAngle](structdronecode__sdk_1_1_telemetry_1_1_euler_angle.md) const& **euler_angle** - 

**Returns**

&emsp;std::ostream & - A reference to the stream.

### operator==() {#namespacedronecode__sdk_1aaf687fbbe3cfe22bc3f5af30595d4b2e}

```
#include: telemetry.h
```
```cpp
bool dronecode_sdk::operator==(const Telemetry::GroundSpeedNED &lhs, const Telemetry::GroundSpeedNED &rhs)
```


Equal operator to compare two [Telemetry::GroundSpeedNED](structdronecode__sdk_1_1_telemetry_1_1_ground_speed_n_e_d.md) objects.


**Parameters**

* const [Telemetry::GroundSpeedNED](structdronecode__sdk_1_1_telemetry_1_1_ground_speed_n_e_d.md)& **lhs** - 
* const [Telemetry::GroundSpeedNED](structdronecode__sdk_1_1_telemetry_1_1_ground_speed_n_e_d.md)& **rhs** - 

**Returns**

&emsp;bool - `true` if items are equal.

### operator<<() {#namespacedronecode__sdk_1ab1411c69c211b5eb231f1ad4ff893679}

```
#include: telemetry.h
```
```cpp
std::ostream& dronecode_sdk::operator<<(std::ostream &str, Telemetry::GroundSpeedNED const &ground_speed)
```


Stream operator to print information about a [Telemetry::GroundSpeedNED](structdronecode__sdk_1_1_telemetry_1_1_ground_speed_n_e_d.md).


**Parameters**

* std::ostream& **str** - 
* [Telemetry::GroundSpeedNED](structdronecode__sdk_1_1_telemetry_1_1_ground_speed_n_e_d.md) const& **ground_speed** - 

**Returns**

&emsp;std::ostream & - A reference to the stream.

### operator==() {#namespacedronecode__sdk_1a2146a33adf4b5d158aff9b6e53fd06ab}

```
#include: telemetry.h
```
```cpp
bool dronecode_sdk::operator==(const Telemetry::RCStatus &lhs, const Telemetry::RCStatus &rhs)
```


Equal operator to compare two [Telemetry::RCStatus](structdronecode__sdk_1_1_telemetry_1_1_r_c_status.md) objects.


**Parameters**

* const [Telemetry::RCStatus](structdronecode__sdk_1_1_telemetry_1_1_r_c_status.md)& **lhs** - 
* const [Telemetry::RCStatus](structdronecode__sdk_1_1_telemetry_1_1_r_c_status.md)& **rhs** - 

**Returns**

&emsp;bool - `true` if items are equal.

### operator<<() {#namespacedronecode__sdk_1a4acb99b3d173ad128a4083096dac1995}

```
#include: telemetry.h
```
```cpp
std::ostream& dronecode_sdk::operator<<(std::ostream &str, Telemetry::RCStatus const &rc_status)
```


Stream operator to print information about a [Telemetry::RCStatus](structdronecode__sdk_1_1_telemetry_1_1_r_c_status.md).


**Parameters**

* std::ostream& **str** - 
* [Telemetry::RCStatus](structdronecode__sdk_1_1_telemetry_1_1_r_c_status.md) const& **rc_status** - 

**Returns**

&emsp;std::ostream & - A reference to the stream.