# dronecore Namespace Reference

----

Namespace for all dronecore types.


## Data Structures

* [dronecore::Action](classdronecore_1_1_action.md)
* [dronecore::Camera](classdronecore_1_1_camera.md)
* [dronecore::DroneCore](classdronecore_1_1_drone_core.md)
* [dronecore::FollowMe](classdronecore_1_1_follow_me.md)
* [dronecore::Gimbal](classdronecore_1_1_gimbal.md)
* [dronecore::Info](classdronecore_1_1_info.md)
* [dronecore::Logging](classdronecore_1_1_logging.md)
* [dronecore::Mission](classdronecore_1_1_mission.md)
* [dronecore::MissionItem](classdronecore_1_1_mission_item.md)
* [dronecore::Offboard](classdronecore_1_1_offboard.md)
* [dronecore::PluginBase](classdronecore_1_1_plugin_base.md)
* [dronecore::System](classdronecore_1_1_system.md)
* [dronecore::Telemetry](classdronecore_1_1_telemetry.md)

## Enumerations

Type | Description
--- | ---
enum [ActionResult](#namespacedronecore_1aedb56a8f642ce3cb7bc4b940c67033c5) | Possible results returned for commanded actions.
enum [ConnectionResult](#namespacedronecore_1a42d7afdc816d7f750e1a8d4282da0ddc) | Result type returned when adding a connection.

## Functions

Type | Name | Description
--- | --- | ---
const char * | [action_result_str](#namespacedronecore_1aa3b1897424479e1e7d5d079a5037957d) ([ActionResult](namespacedronecore.md#namespacedronecore_1aedb56a8f642ce3cb7bc4b940c67033c5) result) | Returns a human-readable English string for an ActionResult.
const char * | [connection_result_str](#namespacedronecore_1a71899c532d8bedfa9654160fc175cce8) (const [ConnectionResult](namespacedronecore.md#namespacedronecore_1a42d7afdc816d7f750e1a8d4282da0ddc) result) | Returns a human-readable English string for a ConnectionResult.
bool | [operator==](#namespacedronecore_1a7c3473f77d60654f451d6e48f4e3d386) (const [MissionItem](classdronecore_1_1_mission_item.md) & lhs, const [MissionItem](classdronecore_1_1_mission_item.md) & rhs) |
std::ostream & | [operator<<](#namespacedronecore_1a062cf568f140581dba03c6b97c65077e) (std::ostream & str, [MissionItem](classdronecore_1_1_mission_item.md) const & mission_item) |
std::ostream & | [operator<<](#namespacedronecore_1a2ca7e28c68f825c8a181761533745c19) (std::ostream & str, [MissionItem::CameraAction](classdronecore_1_1_mission_item.md#classdronecore_1_1_mission_item_1a0cdd25121e5ed6930080ac022857887a) const & camera_action) |
bool | [operator==](#namespacedronecore_1a0363203162fba53fefe7d4d60cd3b1c9) (const [Telemetry::Position](structdronecore_1_1_telemetry_1_1_position.md) & lhs, const [Telemetry::Position](structdronecore_1_1_telemetry_1_1_position.md) & rhs) |
std::ostream & | [operator<<](#namespacedronecore_1a9bc5f60e2e310023bbd0ed436250b217) (std::ostream & str, [Telemetry::Position](structdronecore_1_1_telemetry_1_1_position.md) const & position) |
bool | [operator==](#namespacedronecore_1ab044bfb4b8bceac15f4ef1f7959775d8) (const [Telemetry::Health](structdronecore_1_1_telemetry_1_1_health.md) & lhs, const [Telemetry::Health](structdronecore_1_1_telemetry_1_1_health.md) & rhs) |
std::ostream & | [operator<<](#namespacedronecore_1a33d736c83c404d96c46ff9a7f4750fb1) (std::ostream & str, [Telemetry::Health](structdronecore_1_1_telemetry_1_1_health.md) const & health) |
bool | [operator==](#namespacedronecore_1a65e8014734a31eaf756b98b672dd6466) (const [Telemetry::GPSInfo](structdronecore_1_1_telemetry_1_1_g_p_s_info.md) & lhs, const [Telemetry::GPSInfo](structdronecore_1_1_telemetry_1_1_g_p_s_info.md) & rhs) |
std::ostream & | [operator<<](#namespacedronecore_1a80860746c1bda3cc94fb5ab3962cd6f6) (std::ostream & str, [Telemetry::GPSInfo](structdronecore_1_1_telemetry_1_1_g_p_s_info.md) const & gps_info) |
bool | [operator==](#namespacedronecore_1ae113d4a3da31a7baa40029e3a1833e86) (const [Telemetry::Battery](structdronecore_1_1_telemetry_1_1_battery.md) & lhs, const [Telemetry::Battery](structdronecore_1_1_telemetry_1_1_battery.md) & rhs) |
std::ostream & | [operator<<](#namespacedronecore_1a5e9f9c205d03cca66694584afb649155) (std::ostream & str, [Telemetry::Battery](structdronecore_1_1_telemetry_1_1_battery.md) const & battery) |
bool | [operator==](#namespacedronecore_1a76393963fd7c444510369aa84f75a510) (const [Telemetry::Quaternion](structdronecore_1_1_telemetry_1_1_quaternion.md) & lhs, const [Telemetry::Quaternion](structdronecore_1_1_telemetry_1_1_quaternion.md) & rhs) |
std::ostream & | [operator<<](#namespacedronecore_1a64ba6a17f16435543665842c77978b7f) (std::ostream & str, [Telemetry::Quaternion](structdronecore_1_1_telemetry_1_1_quaternion.md) const & quaternion) |
bool | [operator==](#namespacedronecore_1ab79eb5727113df246d7a9831bd6d411e) (const [Telemetry::EulerAngle](structdronecore_1_1_telemetry_1_1_euler_angle.md) & lhs, const [Telemetry::EulerAngle](structdronecore_1_1_telemetry_1_1_euler_angle.md) & rhs) |
std::ostream & | [operator<<](#namespacedronecore_1a74ec1af5c36cf3c5709655b28079c041) (std::ostream & str, [Telemetry::EulerAngle](structdronecore_1_1_telemetry_1_1_euler_angle.md) const & euler_angle) |
bool | [operator==](#namespacedronecore_1aedab25310e4642ea7bc35c2dd04040a3) (const [Telemetry::GroundSpeedNED](structdronecore_1_1_telemetry_1_1_ground_speed_n_e_d.md) & lhs, const [Telemetry::GroundSpeedNED](structdronecore_1_1_telemetry_1_1_ground_speed_n_e_d.md) & rhs) |
std::ostream & | [operator<<](#namespacedronecore_1a30d9e948976cd9da8692f0e68fab9241) (std::ostream & str, [Telemetry::GroundSpeedNED](structdronecore_1_1_telemetry_1_1_ground_speed_n_e_d.md) const & ground_speed) |
bool | [operator==](#namespacedronecore_1a6b84d191db124cabb9115a37fb01958a) (const [Telemetry::RCStatus](structdronecore_1_1_telemetry_1_1_r_c_status.md) & lhs, const [Telemetry::RCStatus](structdronecore_1_1_telemetry_1_1_r_c_status.md) & rhs) |
std::ostream & | [operator<<](#namespacedronecore_1abd2ed9cab741fc0c46d270a6df643d94) (std::ostream & str, [Telemetry::RCStatus](structdronecore_1_1_telemetry_1_1_r_c_status.md) const & rc_status) |

## Enumeration Type Documentation


### enum ActionResult {#namespacedronecore_1aedb56a8f642ce3cb7bc4b940c67033c5}

```
#include: action_result.h
```


Possible results returned for commanded actions.

> **Note** [DroneCore](classdronecore_1_1_drone_core.md) does not throw exceptions. Instead a result of this type will be returned when you execute actions.

Value | Description
--- | ---
<span id="namespacedronecore_1aedb56a8f642ce3cb7bc4b940c67033c5a696b031073e74bf2cb98e5ef201d4aa3"></span> `UNKNOWN` | Unspecified error. 
<span id="namespacedronecore_1aedb56a8f642ce3cb7bc4b940c67033c5ad0749aaba8b833466dfcbb0428e4f89c"></span> `SUCCESS` | Success. The action command was accepted by the vehicle. 
<span id="namespacedronecore_1aedb56a8f642ce3cb7bc4b940c67033c5afeae72a3a2feec3c92c2a79a30d31186"></span> `NO_SYSTEM` | No system is connected error. 
<span id="namespacedronecore_1aedb56a8f642ce3cb7bc4b940c67033c5ac77f1f09dab2c0c9980fca7cfae02518"></span> `CONNECTION_ERROR` | Connection error. 
<span id="namespacedronecore_1aedb56a8f642ce3cb7bc4b940c67033c5a802706a9238e2928077f97736854bad4"></span> `BUSY` | Vehicle busy error. 
<span id="namespacedronecore_1aedb56a8f642ce3cb7bc4b940c67033c5a6fa4dbf368cea972db8d9156799d5dbe"></span> `COMMAND_DENIED` | Command refused by vehicle. 
<span id="namespacedronecore_1aedb56a8f642ce3cb7bc4b940c67033c5a939d986bd1af6a2e1db07a61a60f7ae2"></span> `COMMAND_DENIED_LANDED_STATE_UNKNOWN` | Command refused because landed state is unknown. 
<span id="namespacedronecore_1aedb56a8f642ce3cb7bc4b940c67033c5ad7e95e2842caf0baff502fbd1290fd69"></span> `COMMAND_DENIED_NOT_LANDED` | Command refused because vehicle not landed. 
<span id="namespacedronecore_1aedb56a8f642ce3cb7bc4b940c67033c5a070a0fb40f6c308ab544b227660aadff"></span> `TIMEOUT` | Timeout waiting for command acknowledgement from vehicle. 
<span id="namespacedronecore_1aedb56a8f642ce3cb7bc4b940c67033c5a59e19d623bfb3a7a60195410afcbe31f"></span> `VTOL_TRANSITION_SUPPORT_UNKNOWN` | hybrid/VTOL transition refused because VTOL support is unknown. 
<span id="namespacedronecore_1aedb56a8f642ce3cb7bc4b940c67033c5af3712e88cb2a09f0d5b72e8e493b53be"></span> `NO_VTOL_TRANSITION_SUPPORT` | Vehicle does not support hybrid/VTOL transitions. 

### enum ConnectionResult {#namespacedronecore_1a42d7afdc816d7f750e1a8d4282da0ddc}

```
#include: connection_result.h
```


Result type returned when adding a connection.

**Note**: [DroneCore](classdronecore_1_1_drone_core.md) does not throw exceptions. Instead a result of this type will be returned when you add a connection: add_udp_connection().

Value | Description
--- | ---
<span id="namespacedronecore_1a42d7afdc816d7f750e1a8d4282da0ddcad0749aaba8b833466dfcbb0428e4f89c"></span> `SUCCESS` | Connection succeeded. 
<span id="namespacedronecore_1a42d7afdc816d7f750e1a8d4282da0ddca070a0fb40f6c308ab544b227660aadff"></span> `TIMEOUT` | Connection timed out. 
<span id="namespacedronecore_1a42d7afdc816d7f750e1a8d4282da0ddcaac87548d79aa92c60dcfac06ae83e5ad"></span> `SOCKET_ERROR` | Socket error. 
<span id="namespacedronecore_1a42d7afdc816d7f750e1a8d4282da0ddcaf69a41125696a14c45a8182ce7ba83a7"></span> `BIND_ERROR` | Bind error. 
<span id="namespacedronecore_1a42d7afdc816d7f750e1a8d4282da0ddca20766ec998922f65e7ac718b7a9b7a22"></span> `SOCKET_CONNECTION_ERROR` | Socket connection error. 
<span id="namespacedronecore_1a42d7afdc816d7f750e1a8d4282da0ddcac77f1f09dab2c0c9980fca7cfae02518"></span> `CONNECTION_ERROR` | Connection error. 
<span id="namespacedronecore_1a42d7afdc816d7f750e1a8d4282da0ddca3e860a081575fc82cc7b6ed2ca602947"></span> `NOT_IMPLEMENTED` | Connection type not implemented. 
<span id="namespacedronecore_1a42d7afdc816d7f750e1a8d4282da0ddca222a5d8795464ca9a47b49daf1357538"></span> `SYSTEM_NOT_CONNECTED` | No system is connected. 
<span id="namespacedronecore_1a42d7afdc816d7f750e1a8d4282da0ddca5a426189f0eb9043da73058f959c2ba1"></span> `SYSTEM_BUSY` | System is busy. 
<span id="namespacedronecore_1a42d7afdc816d7f750e1a8d4282da0ddca6fa4dbf368cea972db8d9156799d5dbe"></span> `COMMAND_DENIED` | Command is denied. 
<span id="namespacedronecore_1a42d7afdc816d7f750e1a8d4282da0ddca588cf56f08269878b055227a8490de67"></span> `DESTINATION_IP_UNKNOWN` | Connection IP is unknown. 
<span id="namespacedronecore_1a42d7afdc816d7f750e1a8d4282da0ddca9532aa7fe8e205a02479a2e43d05f6b1"></span> `CONNECTIONS_EXHAUSTED` | Connections exhausted. 
<span id="namespacedronecore_1a42d7afdc816d7f750e1a8d4282da0ddca269972fd1df83e8f423abead920f8780"></span> `CONNECTION_URL_INVALID` | URL invalid. 

## Function Documentation


### action_result_str() {#namespacedronecore_1aa3b1897424479e1e7d5d079a5037957d}

```
#include: action_result.h
```
```cpp
const char* dronecore::action_result_str(ActionResult result)
```


Returns a human-readable English string for an ActionResult.


**Parameters**

* [ActionResult](namespacedronecore.md#namespacedronecore_1aedb56a8f642ce3cb7bc4b940c67033c5) **result** - The enum value for which a human readable string is required.

**Returns**

&emsp;const char * - Human readable string for the ActionResult.

### connection_result_str() {#namespacedronecore_1a71899c532d8bedfa9654160fc175cce8}

```
#include: connection_result.h
```
```cpp
const char* dronecore::connection_result_str(const ConnectionResult result)
```


Returns a human-readable English string for a ConnectionResult.


**Parameters**

* const [ConnectionResult](namespacedronecore.md#namespacedronecore_1a42d7afdc816d7f750e1a8d4282da0ddc) **result** - The enum value for which a human readable string is required.

**Returns**

&emsp;const char * - Human readable string for the ConnectionResult.

### operator==() {#namespacedronecore_1a7c3473f77d60654f451d6e48f4e3d386}

```
#include: mission_item.h
```
```cpp
bool dronecore::operator==(const MissionItem &lhs, const MissionItem &rhs)
```


**Parameters**

* const [MissionItem](classdronecore_1_1_mission_item.md)& **lhs** - 
* const [MissionItem](classdronecore_1_1_mission_item.md)& **rhs** - 

**Returns**

&emsp;bool - 

### operator<<() {#namespacedronecore_1a062cf568f140581dba03c6b97c65077e}

```
#include: mission_item.h
```
```cpp
std::ostream& dronecore::operator<<(std::ostream &str, MissionItem const &mission_item)
```


**Parameters**

* std::ostream& **str** - 
* [MissionItem](classdronecore_1_1_mission_item.md) const& **mission_item** - 

**Returns**

&emsp;std::ostream & - 

### operator<<() {#namespacedronecore_1a2ca7e28c68f825c8a181761533745c19}

```
#include: mission_item.h
```
```cpp
std::ostream& dronecore::operator<<(std::ostream &str, MissionItem::CameraAction const &camera_action)
```


**Parameters**

* std::ostream& **str** - 
* [MissionItem::CameraAction](classdronecore_1_1_mission_item.md#classdronecore_1_1_mission_item_1a0cdd25121e5ed6930080ac022857887a) const& **camera_action** - 

**Returns**

&emsp;std::ostream & - 

### operator==() {#namespacedronecore_1a0363203162fba53fefe7d4d60cd3b1c9}

```
#include: telemetry.h
```
```cpp
bool dronecore::operator==(const Telemetry::Position &lhs, const Telemetry::Position &rhs)
```


**Parameters**

* const [Telemetry::Position](structdronecore_1_1_telemetry_1_1_position.md)& **lhs** - 
* const [Telemetry::Position](structdronecore_1_1_telemetry_1_1_position.md)& **rhs** - 

**Returns**

&emsp;bool - 

### operator<<() {#namespacedronecore_1a9bc5f60e2e310023bbd0ed436250b217}

```
#include: telemetry.h
```
```cpp
std::ostream& dronecore::operator<<(std::ostream &str, Telemetry::Position const &position)
```


**Parameters**

* std::ostream& **str** - 
* [Telemetry::Position](structdronecore_1_1_telemetry_1_1_position.md) const& **position** - 

**Returns**

&emsp;std::ostream & - 

### operator==() {#namespacedronecore_1ab044bfb4b8bceac15f4ef1f7959775d8}

```
#include: telemetry.h
```
```cpp
bool dronecore::operator==(const Telemetry::Health &lhs, const Telemetry::Health &rhs)
```


**Parameters**

* const [Telemetry::Health](structdronecore_1_1_telemetry_1_1_health.md)& **lhs** - 
* const [Telemetry::Health](structdronecore_1_1_telemetry_1_1_health.md)& **rhs** - 

**Returns**

&emsp;bool - 

### operator<<() {#namespacedronecore_1a33d736c83c404d96c46ff9a7f4750fb1}

```
#include: telemetry.h
```
```cpp
std::ostream& dronecore::operator<<(std::ostream &str, Telemetry::Health const &health)
```


**Parameters**

* std::ostream& **str** - 
* [Telemetry::Health](structdronecore_1_1_telemetry_1_1_health.md) const& **health** - 

**Returns**

&emsp;std::ostream & - 

### operator==() {#namespacedronecore_1a65e8014734a31eaf756b98b672dd6466}

```
#include: telemetry.h
```
```cpp
bool dronecore::operator==(const Telemetry::GPSInfo &lhs, const Telemetry::GPSInfo &rhs)
```


**Parameters**

* const [Telemetry::GPSInfo](structdronecore_1_1_telemetry_1_1_g_p_s_info.md)& **lhs** - 
* const [Telemetry::GPSInfo](structdronecore_1_1_telemetry_1_1_g_p_s_info.md)& **rhs** - 

**Returns**

&emsp;bool - 

### operator<<() {#namespacedronecore_1a80860746c1bda3cc94fb5ab3962cd6f6}

```
#include: telemetry.h
```
```cpp
std::ostream& dronecore::operator<<(std::ostream &str, Telemetry::GPSInfo const &gps_info)
```


**Parameters**

* std::ostream& **str** - 
* [Telemetry::GPSInfo](structdronecore_1_1_telemetry_1_1_g_p_s_info.md) const& **gps_info** - 

**Returns**

&emsp;std::ostream & - 

### operator==() {#namespacedronecore_1ae113d4a3da31a7baa40029e3a1833e86}

```
#include: telemetry.h
```
```cpp
bool dronecore::operator==(const Telemetry::Battery &lhs, const Telemetry::Battery &rhs)
```


**Parameters**

* const [Telemetry::Battery](structdronecore_1_1_telemetry_1_1_battery.md)& **lhs** - 
* const [Telemetry::Battery](structdronecore_1_1_telemetry_1_1_battery.md)& **rhs** - 

**Returns**

&emsp;bool - 

### operator<<() {#namespacedronecore_1a5e9f9c205d03cca66694584afb649155}

```
#include: telemetry.h
```
```cpp
std::ostream& dronecore::operator<<(std::ostream &str, Telemetry::Battery const &battery)
```


**Parameters**

* std::ostream& **str** - 
* [Telemetry::Battery](structdronecore_1_1_telemetry_1_1_battery.md) const& **battery** - 

**Returns**

&emsp;std::ostream & - 

### operator==() {#namespacedronecore_1a76393963fd7c444510369aa84f75a510}

```
#include: telemetry.h
```
```cpp
bool dronecore::operator==(const Telemetry::Quaternion &lhs, const Telemetry::Quaternion &rhs)
```


**Parameters**

* const [Telemetry::Quaternion](structdronecore_1_1_telemetry_1_1_quaternion.md)& **lhs** - 
* const [Telemetry::Quaternion](structdronecore_1_1_telemetry_1_1_quaternion.md)& **rhs** - 

**Returns**

&emsp;bool - 

### operator<<() {#namespacedronecore_1a64ba6a17f16435543665842c77978b7f}

```
#include: telemetry.h
```
```cpp
std::ostream& dronecore::operator<<(std::ostream &str, Telemetry::Quaternion const &quaternion)
```


**Parameters**

* std::ostream& **str** - 
* [Telemetry::Quaternion](structdronecore_1_1_telemetry_1_1_quaternion.md) const& **quaternion** - 

**Returns**

&emsp;std::ostream & - 

### operator==() {#namespacedronecore_1ab79eb5727113df246d7a9831bd6d411e}

```
#include: telemetry.h
```
```cpp
bool dronecore::operator==(const Telemetry::EulerAngle &lhs, const Telemetry::EulerAngle &rhs)
```


**Parameters**

* const [Telemetry::EulerAngle](structdronecore_1_1_telemetry_1_1_euler_angle.md)& **lhs** - 
* const [Telemetry::EulerAngle](structdronecore_1_1_telemetry_1_1_euler_angle.md)& **rhs** - 

**Returns**

&emsp;bool - 

### operator<<() {#namespacedronecore_1a74ec1af5c36cf3c5709655b28079c041}

```
#include: telemetry.h
```
```cpp
std::ostream& dronecore::operator<<(std::ostream &str, Telemetry::EulerAngle const &euler_angle)
```


**Parameters**

* std::ostream& **str** - 
* [Telemetry::EulerAngle](structdronecore_1_1_telemetry_1_1_euler_angle.md) const& **euler_angle** - 

**Returns**

&emsp;std::ostream & - 

### operator==() {#namespacedronecore_1aedab25310e4642ea7bc35c2dd04040a3}

```
#include: telemetry.h
```
```cpp
bool dronecore::operator==(const Telemetry::GroundSpeedNED &lhs, const Telemetry::GroundSpeedNED &rhs)
```


**Parameters**

* const [Telemetry::GroundSpeedNED](structdronecore_1_1_telemetry_1_1_ground_speed_n_e_d.md)& **lhs** - 
* const [Telemetry::GroundSpeedNED](structdronecore_1_1_telemetry_1_1_ground_speed_n_e_d.md)& **rhs** - 

**Returns**

&emsp;bool - 

### operator<<() {#namespacedronecore_1a30d9e948976cd9da8692f0e68fab9241}

```
#include: telemetry.h
```
```cpp
std::ostream& dronecore::operator<<(std::ostream &str, Telemetry::GroundSpeedNED const &ground_speed)
```


**Parameters**

* std::ostream& **str** - 
* [Telemetry::GroundSpeedNED](structdronecore_1_1_telemetry_1_1_ground_speed_n_e_d.md) const& **ground_speed** - 

**Returns**

&emsp;std::ostream & - 

### operator==() {#namespacedronecore_1a6b84d191db124cabb9115a37fb01958a}

```
#include: telemetry.h
```
```cpp
bool dronecore::operator==(const Telemetry::RCStatus &lhs, const Telemetry::RCStatus &rhs)
```


**Parameters**

* const [Telemetry::RCStatus](structdronecore_1_1_telemetry_1_1_r_c_status.md)& **lhs** - 
* const [Telemetry::RCStatus](structdronecore_1_1_telemetry_1_1_r_c_status.md)& **rhs** - 

**Returns**

&emsp;bool - 

### operator<<() {#namespacedronecore_1abd2ed9cab741fc0c46d270a6df643d94}

```
#include: telemetry.h
```
```cpp
std::ostream& dronecore::operator<<(std::ostream &str, Telemetry::RCStatus const &rc_status)
```


**Parameters**

* std::ostream& **str** - 
* [Telemetry::RCStatus](structdronecore_1_1_telemetry_1_1_r_c_status.md) const& **rc_status** - 

**Returns**

&emsp;std::ostream & - 