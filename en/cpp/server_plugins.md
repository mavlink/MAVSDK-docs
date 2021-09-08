# Server Plugins

MAVLink protocols are often designed using the client-server pattern, where vehicle-based components like the autopilot typically act as a server, responding to commands sent by a ground station "client".

Initially MAVSDK was mainly developed with the use case of a ground station in mind, so plugins implemented the client-side protocol behaviour.

However, MAVSDK can also be used for the server-side of the protocol e.g. running on a companion computer on the vehicle.
This can be used to extend the functionality "in the air", or as a bridge to a proprietary or non-MAVLink flight controller.
The plugins developed specifically for this case are usually suffixed with `Server`, e.g.:

- [ActionServer](../api_reference/classmavsdk_1_1_action_server.md)
- [MissionRawServer](../api_reference/classmavsdk_1_1_mission_raw_server.md)
- [ParamServer](../api_reference/classmavsdk_1_1_param_server.md)
- [TelemetryServer](../api_reference/classmavsdk_1_1_telemetry_server.md)
- [TrackingServer](../api_reference/classmavsdk_1_1_tracking_server.md)

These server plugins can potentially also be used to test the "non-server" plugins of MAVSDK in the future.
