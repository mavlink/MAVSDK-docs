# SDK Paradigms/Usage

This topic provides general/overview information about how the MAVSDK is used, designed and some limitations. 

## Object Management

[Mavsdk](../api_reference/classmavsdk_1_1_mavsdk.md) is the main library class. 
Applications must create a `Mavsdk` object and destroy it during application shut down. 
The object is usually created as an automatic variable that is cleaned up when it goes out of scope (you can also dynamically create/destroy the object using `new`/`delete`).

API consumers use [Mavsdk](../api_reference/classmavsdk_1_1_mavsdk.md) to discover and connect to [System](../api_reference/classmavsdk_1_1_system.md) objects (vehicles/cameras etc.). 

Access to drone information and control objects are provided [by plugins](../guide/using_plugins.md) (e.g. Telemetry, Action, Mission etc.). 
Plugin objects are instantiated with a *specific* `System` object (a plugin instance must be created for every system that needs it). 

Plugin objects are created as shared pointers that will be destroyed when all associated handles are out of scope. 
All objects are automatically cleaned up when the parent `Mavsdk` object is destroyed.


## Error Handling

MAVSDK APIs do not raise exceptions! Instead, methods that can fail return success or an error reason as `enum` values.

> **Tip** The error code usually reflects acknowledgment from the vehicle that it will perform the requested action (or not). 
  The operation itself may not yet have completed (e.g. taking off).

The various classes also all provide methods getting human readable strings from their associated enum (e.g. [connection_result_str()](../api_reference/namespacemavsdk.md#namespacemavsdk_1a59e8a165c1edafab6ab0c04df2c83679), [Telemetry::result_str()](../api_reference/classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a046457e28886493a677fe7d35627bacc)). You can see how these are used in the example code.


## Shared Vehicle Control

A vehicle can receive commands from multiple sources, including a Ground Control Station, or other MAVLink applications.

SDK applications, which are running in environments where it is possible, can explicitly monitor for changes in flight mode 
(outside application control) and change behaviour appropriately (e.g. using [Telemetry::flight_mode_async()](../api_reference/classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a29494b6f0ed34be913e3f5c4bbfdf4cd)). 


## API Limitations/Behaviour

### Supported Vehicles

The SDK has been designed to manage *aircraft* that use the PX4 autopilot. 
It has primarily been tested for use with multicopters, but also has basic support for fixed wing and [VTOL](../guide/vtol.md).

The APIs include methods that do not make sense for other vehicle types - including "takeoff" and "land". 
While ground vehicles may work, they are not supported and are untested.
Similarly, other autopilots may well work, but, they are not explicitly supported and are untested.


### Telemetry/Information

The SDK gets and stores vehicle state/telemetry information from received MAVLink messages. 
The information is supplied to callback subscribers as soon as message updates are received. 
Clients can also query the API synchronously, and will get the information from the last received message (depending on channel latency, this information will become increasingly "stale" between messages).

The rate at which update messages are sent by the vehicle can be specified using the API (but will be limited by the bandwidth of the channel). 
Developers need to use a channel and a message update rate that allows their desired control algorithm to be effective - there is no point trying to use computer vision over an unreliable high-latency link.

`Info` information does not change for a particular vehicle, so will be accurate whenever read.


### Actions/Offboard

`Action` methods (and any other "vehicle instructions") return when the vehicle has confirmed that the message was received and will be acted on (or not). 
The methods do not wait for the commanded action to complete.

So, for example, the [Action::land()](../api_reference/classmavsdk_1_1_action.md#classmavsdk_1_1_action_1a25490d09fd2905b96de2c2c6e52e5f7b) method returns as soon as the vehicle confirms it will land, but will actually land at some later point. 

The implication is that developers will need to separately monitor the completion of the requested actions, if this is important to the application.


### Missions

The `Mission` and `MissionItem` APIs provide a the most useful *subset* of MAVLink mission commands as a developer-friendly API. 

Not every mission command behaviour supported by the protocol and PX4 will be supported by the SDK. 
For example, at time of writing the API does not allow you to specify commands that jump back to previous mission items.

The API allows you to download/import missions. 
Note however that this will fail if the mission contains a command that is not supported by the API.


### Connection Status

A system is considered to be disconnected (timed-out) if its heartbeat message is not detected within 3 seconds.
