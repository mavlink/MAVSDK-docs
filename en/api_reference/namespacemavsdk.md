# mavsdk Namespace Reference

----

Namespace for all mavsdk types.


## Data Structures

* [mavsdk::Action](classmavsdk_1_1_action.md)
* [mavsdk::Calibration](classmavsdk_1_1_calibration.md)
* [mavsdk::Camera](classmavsdk_1_1_camera.md)
* [mavsdk::FollowMe](classmavsdk_1_1_follow_me.md)
* [mavsdk::Ftp](classmavsdk_1_1_ftp.md)
* [mavsdk::Geofence](classmavsdk_1_1_geofence.md)
* [mavsdk::Gimbal](classmavsdk_1_1_gimbal.md)
* [mavsdk::Info](classmavsdk_1_1_info.md)
* [mavsdk::LogFiles](classmavsdk_1_1_log_files.md)
* [mavsdk::MavlinkPassthrough](classmavsdk_1_1_mavlink_passthrough.md)
* [mavsdk::Mavsdk](classmavsdk_1_1_mavsdk.md)
* [mavsdk::Mission](classmavsdk_1_1_mission.md)
* [mavsdk::MissionRaw](classmavsdk_1_1_mission_raw.md)
* [mavsdk::Mocap](classmavsdk_1_1_mocap.md)
* [mavsdk::Offboard](classmavsdk_1_1_offboard.md)
* [mavsdk::Param](classmavsdk_1_1_param.md)
* [mavsdk::PluginBase](classmavsdk_1_1_plugin_base.md)
* [mavsdk::Shell](classmavsdk_1_1_shell.md)
* [mavsdk::System](classmavsdk_1_1_system.md)
* [mavsdk::Telemetry](classmavsdk_1_1_telemetry.md)
* [mavsdk::Tune](classmavsdk_1_1_tune.md)

## Enumerations

Type | Description
--- | ---
enum [ConnectionResult](#namespacemavsdk_1a0bad93f6d037051ac3906a0bcc09f992) | Result type returned when adding a connection.
enum [ComponentType](#namespacemavsdk_1a20fe7f7c8312779a187017111bf33d12) | Component Types.

## Functions

Type | Name | Description
--- | --- | ---
std::ostream & | [operator<<](#namespacemavsdk_1a3307e6cbeb3dba8551dcde4b873691d3) (std::ostream & str, const [ConnectionResult](namespacemavsdk.md#namespacemavsdk_1a0bad93f6d037051ac3906a0bcc09f992) & result) | Stream operator to print information about a `ConnectionResult`.

## Enumeration Type Documentation


### enum ConnectionResult {#namespacemavsdk_1a0bad93f6d037051ac3906a0bcc09f992}

```
#include: connection_result.h
```


Result type returned when adding a connection.

**Note**: [Mavsdk](classmavsdk_1_1_mavsdk.md) does not throw exceptions. Instead a result of this type will be returned when you add a connection: add_udp_connection().

Value | Description
--- | ---
<span id="namespacemavsdk_1a0bad93f6d037051ac3906a0bcc09f992a505a83f220c02df2f85c3810cd9ceb38"></span> `Success` | Connection succeeded. 
<span id="namespacemavsdk_1a0bad93f6d037051ac3906a0bcc09f992ac85a251cc457840f1e032f1b733e9398"></span> `Timeout` | Connection timed out. 
<span id="namespacemavsdk_1a0bad93f6d037051ac3906a0bcc09f992ad4a2b05c3c61121e1ce151feb647a0c6"></span> `SocketError` | Socket error. 
<span id="namespacemavsdk_1a0bad93f6d037051ac3906a0bcc09f992a0e4f8eb16eec43ffd4fa88d49195664a"></span> `BindError` | Bind error. 
<span id="namespacemavsdk_1a0bad93f6d037051ac3906a0bcc09f992a0e6a105b658bcf46443616f4ca8f51ee"></span> `SocketConnectionError` | Socket connection error. 
<span id="namespacemavsdk_1a0bad93f6d037051ac3906a0bcc09f992a094a6f6b0868122a9dd008cb91c083e4"></span> `ConnectionError` | Connection error. 
<span id="namespacemavsdk_1a0bad93f6d037051ac3906a0bcc09f992a997ca4ce119685f40f03a9a8a6c5346e"></span> `NotImplemented` | Connection type not implemented. 
<span id="namespacemavsdk_1a0bad93f6d037051ac3906a0bcc09f992a581519b813a8e38c88e0aeb9edcf4535"></span> `SystemNotConnected` | No system is connected. 
<span id="namespacemavsdk_1a0bad93f6d037051ac3906a0bcc09f992a1c18a1a383bcd5a039b68b3751ac6d71"></span> `SystemBusy` | System is busy. 
<span id="namespacemavsdk_1a0bad93f6d037051ac3906a0bcc09f992a3398e12855176d55f43d53e04f472c8a"></span> `CommandDenied` | Command is denied. 
<span id="namespacemavsdk_1a0bad93f6d037051ac3906a0bcc09f992a5a36b75b17476943413af4c3f5b75ce3"></span> `DestinationIpUnknown` | Connection IP is unknown. 
<span id="namespacemavsdk_1a0bad93f6d037051ac3906a0bcc09f992a63e76f04ccb26b3da08fc20176c8577c"></span> `ConnectionsExhausted` | Connections exhausted. 
<span id="namespacemavsdk_1a0bad93f6d037051ac3906a0bcc09f992a4ffb87ccb1fd17d4d54d882a06885f49"></span> `ConnectionUrlInvalid` | URL invalid. 
<span id="namespacemavsdk_1a0bad93f6d037051ac3906a0bcc09f992a94a6b3fbdd01834703b52a5493535b1d"></span> `BaudrateUnknown` | Baudrate unknown. 

### enum ComponentType {#namespacemavsdk_1a20fe7f7c8312779a187017111bf33d12}

```
#include: system.h
```


Component Types.


Value | Description
--- | ---
<span id="namespacemavsdk_1a20fe7f7c8312779a187017111bf33d12a7b0b07ec8293a25730d05980f5bf1946"></span> `UNKNOWN` |  
<span id="namespacemavsdk_1a20fe7f7c8312779a187017111bf33d12a092366b39e29ed2f2a5429b0bf82023f"></span> `AUTOPILOT` |  
<span id="namespacemavsdk_1a20fe7f7c8312779a187017111bf33d12a2950492ed394e5c5bdf9b0eed9f5737b"></span> `CAMERA` |  
<span id="namespacemavsdk_1a20fe7f7c8312779a187017111bf33d12a9683a40d8c6ef6e539a71a3c12f7aee3"></span> `GIMBAL` |  

## Function Documentation


### operator<<() {#namespacemavsdk_1a3307e6cbeb3dba8551dcde4b873691d3}

```
#include: connection_result.h
```
```cpp
std::ostream& mavsdk::operator<<(std::ostream &str, const ConnectionResult &result)
```


Stream operator to print information about a `ConnectionResult`.


**Parameters**

* std::ostream& **str** - 
* const [ConnectionResult](namespacemavsdk.md#namespacemavsdk_1a0bad93f6d037051ac3906a0bcc09f992)& **result** - 

**Returns**

&emsp;std::ostream & - A reference to the stream.