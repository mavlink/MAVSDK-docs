# Server Plugins

Initially MAVSDK was mainly developed with the use case of a ground station in mind.

However, MAVSDK can also be used "on the vehicle side", e.g. on a companion computer. This can be to extend the functionality "in the air" or as a bridge to a proprietary or non-MAVLink flight controller.
The plugins developed specifically for this case are usually suffixed with `Server`, e.g.:

- [ActionServer](../api_reference/classmavsdk_1_1_action_server.md)
- [MissionRawServer](../api_reference/classmavsdk_1_1_mission_raw_server.md)
- [ParamServer](../api_reference/classmavsdk_1_1_param_server.md), [TelemetryServer](../api_reference/classmavsdk_1_1_telemetry_server.md)
- [TrackingServer](../api_reference/classmavsdk_1_1_tracking_server.md).

These server plugins can potentially also be used to test the "non-server" plugins of MAVSDK in the future.
