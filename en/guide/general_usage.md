# DroneCore Paradigms/Usage

This topic provides general/overview information about how DroneCore is used, designed and some limitations. 

## Object Management

[DroneCore](../api_reference/classdronecore_1_1_drone_core.md) is the main library class. Applications must create a `DroneCore` object and destroy it during application shut down. The object can be created as an automatic variable that is cleaned up when it goes out of scope, or you can dynamically create/destroy the object using `new`/`delete`.

API consumers use [DroneCore](../api_reference/classdronecore_1_1_drone_core.md) to discover and connect to [Device](../api_reference/classdronecore_1_1_device.md) objects (vehicles/cameras etc.). 

Access to drone information and control objects are provided [by plugins](../guide/using_plugins.md). Plugin objects are created and associated with a *specific* `Device` object (a plugin instance must be created for every device that needs it). 

Plugin objects are owned by their associated `Device`, which is in turned owned by `DroneCore`. All objects are automatically cleaned up when the parent `DroneCore` object is destroyed.


## Error Handling

DroneCore APIs do not raise exceptions! Instead, methods that can fail return success or an error reason as `enum` values.

> **Tip** The error code usually reflects acknowledgment from the vehicle that it will perform the requested action (or not). The operation itself may not yet have completed (e.g. taking off).

The various classes also all provide methods getting human readable strings from their associated enum (e.g. [DroneCore::connection_result_str()](../api_reference/classdronecore_1_1_drone_core.md#classdronecore_1_1_drone_core_1a84c40dcefcafe888c38a5ed8dd93b0af), [Telemetry::result_str()](../api_reference/classdronecore_1_1_telemetry.md#classdronecore_1_1_telemetry_1a05c6355b7f8743250b2a7a611ea5fb4a)). You can see how these are used in the example code.


## Shared Vehicle Control

A vehicle can receive commands from multiple sources, including a Ground Control Station, or other MAVLink applications.

DroneCore applications that are running in environments where this is possible can explicitly monitor for changes in flight mode 
(outside application control) and change behaviour appropriately (e.g. using [Telemetry::flight_mode_async()](../api_reference/classdronecore_1_1_telemetry.md#classdronecore_1_1_telemetry_1ac8842dec06db4bd54c8c2ba2deb0d34a)). 


## API Limitations/Behaviour

### Supported Vehicles

DroneCore has been designed to manage *aircraft* that use the PX4 autopilot. It has primarily been tested for use with copters, but also has basic support for fixed wing and [VTOL](../guide/vtol.md).

The APIs include methods that do not make sense for other vehicle types - including "takeoff" and "land". While ground vehicles may work, they are not supported and are untested.


### Telemetry/Information

DroneCore gets and stores vehicle state/telemetry information from received MAVLink messages. The information is supplied to callback subscribers as soon as message updates are received. Clients can also query the API synchronously, and will get the information from the last recieved message (depending on channel latency, this information will become increasingly "stale" between messages).

The rate at which update messages are sent by the vehicle can be specified using DroneCore (but will be limited by the bandwidth of the channel). Developers need to use a channel and a message update rate that allows their desired control algorithm to be effective - there is no point trying to use computer vision over an unreliable high-latency link.

`Info` information does not change for a particular vehicle, so will be accurate whenever read.


### Actions/Offboard

`Action` methods (and any other "vehicle instructions") return when the vehicle has confirmed that the message was received and will be acted on (or not). The methods do not wait for the commanded action to complete.

So, for example, the [Action::land()](../api_reference/classdronecore_1_1_action.md#classdronecore_1_1_action_1ad1a50dd7bff99d3099916576efbf8cf6) method returns as soon as the vehicle confirms it will land, but will actually land at some later point. 

The implication is that developers will need to separately monitor the completion of the requested actions, if this is important to the application.


### Missions

The `Mission` and `MissionItem` APIs provide a the most useful *subset* of MAVLink mission commands as a developer-friendly API. 

Not every mission command behaviour supported by the protocol and PX4 will be supported by DroneCore. For example, at time of writing the API does not allow you to specify commands that jump back to previous mission items.

The API allows you to download/import missions. Note however that this will fail if the mission contains a command that is not supported by the API.


### Connection Status

A device is considered to be disconnected (timed-out) if its heartbeat message is not detected within 3 seconds.

