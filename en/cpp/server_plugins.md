# Server Plugins

Initially, MAVSDK was developed to act as a ground station (client). MAVSDK would issue ground station commands to an
autopilot, which would then execute them. This meant MAVSDK always required an external MAVLink autopilot, simulated or real,
to act as the other-side (server) of the MAVLink service.

MAVSDK has since been extended to provide MAVLink autopilot services. This means it is possible to use MAVSDK to act as a vehicle autopilot
to listen and act on ground station commands. MAVSDK can now also act as a companion computer.

## Adding MAVLink support to your vehicle

Proprietary or non-MAVLink control systems can be given MAVLink support by utilising the MAVSDK `Server` plugins. MAVSDK does not provide 
low-level vehicle control (see: PX4 or Ardupilot), but provides a simple interface for listening and publishing to appropriate MAVLink services.

Adding MAVLink support to your vehicle is as simple as instantiating the required server plugin and actioning the vehicle on the appropriate
callback.

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
