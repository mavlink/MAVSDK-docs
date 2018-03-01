# dronecore Namespace Reference

----

Namespace for all dronecore types.


## Data Structures

* [dronecore::Action](classdronecore_1_1_action.md)
* [dronecore::Device](classdronecore_1_1_device.md)
* [dronecore::DroneCore](classdronecore_1_1_drone_core.md)
* [dronecore::FollowMe](classdronecore_1_1_follow_me.md)
* [dronecore::Gimbal](classdronecore_1_1_gimbal.md)
* [dronecore::Info](classdronecore_1_1_info.md)
* [dronecore::Logging](classdronecore_1_1_logging.md)
* [dronecore::Mission](classdronecore_1_1_mission.md)
* [dronecore::MissionItem](classdronecore_1_1_mission_item.md)
* [dronecore::Offboard](classdronecore_1_1_offboard.md)
* [dronecore::PluginBase](classdronecore_1_1_plugin_base.md)
* [dronecore::Telemetry](classdronecore_1_1_telemetry.md)

## Enumerations

Type | Description
--- | ---
enum [ConnectionResult](#namespacedronecore_1a42d7afdc816d7f750e1a8d4282da0ddc) | Result type returned when adding a connection.

## Functions

Type | Name | Description
--- | --- | ---
const char * | [connection_result_str](#namespacedronecore_1a71899c532d8bedfa9654160fc175cce8) (const [ConnectionResult](namespacedronecore.md#namespacedronecore_1a42d7afdc816d7f750e1a8d4282da0ddc) result) | Returns a human-readable English string for a ConnectionResult.

## Enumeration Type Documentation


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
<span id="namespacedronecore_1a42d7afdc816d7f750e1a8d4282da0ddcadb6de85627898aecebdcd28613df3164"></span> `DEVICE_NOT_CONNECTED` | No device is connected. 
<span id="namespacedronecore_1a42d7afdc816d7f750e1a8d4282da0ddca9b40004e356bbecf8c222684be0988c7"></span> `DEVICE_BUSY` | Device is busy. 
<span id="namespacedronecore_1a42d7afdc816d7f750e1a8d4282da0ddca6fa4dbf368cea972db8d9156799d5dbe"></span> `COMMAND_DENIED` | Command is denied. 
<span id="namespacedronecore_1a42d7afdc816d7f750e1a8d4282da0ddca588cf56f08269878b055227a8490de67"></span> `DESTINATION_IP_UNKNOWN` | Connection IP is unknown. 
<span id="namespacedronecore_1a42d7afdc816d7f750e1a8d4282da0ddca9532aa7fe8e205a02479a2e43d05f6b1"></span> `CONNECTIONS_EXHAUSTED` | Connections exhausted. 
<span id="namespacedronecore_1a42d7afdc816d7f750e1a8d4282da0ddca269972fd1df83e8f423abead920f8780"></span> `CONNECTION_URL_INVALID` | URL invalid. 

## Function Documentation


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