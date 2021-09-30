# Server Plugins

MAVSDK was originally developed to act as a ground station ("client"), issuing commands to an autopilot or companion computer ("server"), which would then execute them.
This meant MAVSDK always required an external MAVLink autopilot, simulated or real, to act as the other-side (server) of the MAVLink service.

MAVSDK can also be used for the server-side of the protocol e.g. acting as an autopilot or companion computer.
In this case MAVSDK listens for commands from a ground station (or from MAVSDK running as a client).

MAVSDK server plugins provide a simple interface for listening and publishing to appropriate MAVLink services (they do not implement low-level vehicle control in the same way as a full flight stack such as PX4 or ArduPilot). 

## Adding MAVLink support to your vehicle

Proprietary or non-MAVLink control systems can be given MAVLink support by utilising the MAVSDK `Server` plugins.

Adding MAVLink support to your vehicle is as simple as instantiating the required server plugin and actioning the vehicle on the appropriate callback.

## Examples

The [Autopilot_Server](../examples/autopilot_server.md) example uses many different MAVSDK server plugins to replicate a simple vehicle and autopilot system, with telemetry, mission handling, parameters and more.

## Plugins

The plugins developed specifically for this case are usually suffixed with `Server`, e.g.:

- [ActionServer](../api_reference/classmavsdk_1_1_action_server.md)
- [MissionRawServer](../api_reference/classmavsdk_1_1_mission_raw_server.md)
- [ParamServer](../api_reference/classmavsdk_1_1_param_server.md)
- [TelemetryServer](../api_reference/classmavsdk_1_1_telemetry_server.md)
- [TrackingServer](../api_reference/classmavsdk_1_1_tracking_server.md)

These server plugins can potentially also be used to test the "client" plugins of MAVSDK in the future.
