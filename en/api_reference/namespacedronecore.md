# dronecore Namespace Reference

----

Namespace for all dronecore types.


## Data Structures

* [dronecore::Action](classdronecore_1_1_action.md)
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
bool | [operator==](#namespacedronecore_1a0363203162fba53fefe7d4d60cd3b1c9) (const [Telemetry::Position](structdronecore_1_1_telemetry_1_1_position.md) & lhs, const [Telemetry::Position](structdronecore_1_1_telemetry_1_1_position.md) & rhs) |
std::ostream & | [operator<<](#namespacedronecore_1a9bc5f60e2e310023bbd0ed436250b217) (std::ostream & str, [Telemetry::Position](structdronecore_1_1_telemetry_1_1_position.md) const & position) |

## Enumeration Type Documentation


### enum ActionResult {#namespacedronecore_1aedb56a8f642ce3cb7bc4b940c67033c5}

```
#include: action_result.h
```


Possible results returned for commanded actions.

**Note**: [DroneCore](classdronecore_1_1_drone_core.md) does not throw exceptions. Instead a result of this type will be returned when you execute actions.

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