# dronecore::Device Class Reference
`#include: device.h`

----


A [Device](classdronecore_1_1_device.md) represents a vehicle such as a drone or robot. 


A device can consist of multiple components such as an autopilot with a gimbal and camera.


This class is derived from [DevicePluginContainer](classdronecore_1_1_device_plugin_container.md), which provides methods to access plugin classes like [Action](classdronecore_1_1_action.md), [Telemetry](classdronecore_1_1_telemetry.md), [Info](classdronecore_1_1_info.md), [Logging](classdronecore_1_1_logging.md), [Offboard](classdronecore_1_1_offboard.md) and [Mission](classdronecore_1_1_mission.md) (for example, using [DroneCore::device()](classdronecore_1_1_drone_core.md#classdronecore_1_1_drone_core_1a5bac6e419e56a1f77a51adef98e94e7c).[action()](classdronecore_1_1_device_plugin_container.md#classdronecore_1_1_device_plugin_container_1aea48bd55b1ace227ebb56690794c2192)...).


**NOTE** The content of [DevicePluginContainer](classdronecore_1_1_device_plugin_container.md), and hence the available accessors, are auto-generated at compile time.


[Device](classdronecore_1_1_device.md) objects are not created or destroyed directly by API consumers. They are accessed using, for example, [DroneCore::device()](classdronecore_1_1_drone_core.md#classdronecore_1_1_drone_core_1a5bac6e419e56a1f77a51adef98e94e7c) and cleaned up when [DroneCore](classdronecore_1_1_drone_core.md) is destroyed. 


## Public Member Functions


Type | Name | Description
---: | --- | ---
| [Device](#classdronecore_1_1_device_1aa64ba685fe110fcb0a8e1b92156f144b) (DeviceImpl *impl) | Constructor (internal use only).
| [~Device](#classdronecore_1_1_device_1a65c697e12eed30109074e18a9cfdc836) () | Destructor (internal use only).
[Info](classdronecore_1_1_info.md) & | [info](#classdronecore_1_1_device_plugin_container_1a1509e3d7a469cbc3e33471138b1f4dc7) () |
[Logging](classdronecore_1_1_logging.md) & | [logging](#classdronecore_1_1_device_plugin_container_1a0551f966021bdbd9e41700232c33d379) () |
[Telemetry](classdronecore_1_1_telemetry.md) & | [telemetry](#classdronecore_1_1_device_plugin_container_1a9b119348d0f5195c9b0919fbe6196b14) () |
[FollowMe](classdronecore_1_1_follow_me.md) & | [follow_me](#classdronecore_1_1_device_plugin_container_1ae13164c3bb59230c559341b8506c5e03) () |
[Action](classdronecore_1_1_action.md) & | [action](#classdronecore_1_1_device_plugin_container_1aea48bd55b1ace227ebb56690794c2192) () |
[Gimbal](classdronecore_1_1_gimbal.md) & | [gimbal](#classdronecore_1_1_device_plugin_container_1a2fce9f439c565af9a8510c5746c728f0) () |
[Offboard](classdronecore_1_1_offboard.md) & | [offboard](#classdronecore_1_1_device_plugin_container_1a63193bd25273bbda48665e12e012f478) () |
[Mission](classdronecore_1_1_mission.md) & | [mission](#classdronecore_1_1_device_plugin_container_1a8a05778326d0ef4c74146bc42fdcb52d) () |


## Constructor & Destructor Documentation


### Device() {#classdronecore_1_1_device_1aa64ba685fe110fcb0a8e1b92156f144b}
```cpp
dronecore::Device::Device(DeviceImpl *impl)
```


Constructor (internal use only).

This constructor does not need to be called by any consumer of the API.

**Parameters**

* DeviceImpl * **impl** - The underlying device implementation.

### ~Device() {#classdronecore_1_1_device_1a65c697e12eed30109074e18a9cfdc836}
```cpp
dronecore::Device::~Device()
```


Destructor (internal use only).

The destructor of [Device](classdronecore_1_1_device.md) does not need to be called by any consumer of the API.

## Member Function Documentation


### info() {#classdronecore_1_1_device_plugin_container_1a1509e3d7a469cbc3e33471138b1f4dc7}
```cpp
Info& dronecore::DevicePluginContainer::info()
```


Getter for [Info](classdronecore_1_1_info.md) plugin.

**Returns**

&emsp;[Info](classdronecore_1_1_info.md) & - a reference to the info plugin instance

### logging() {#classdronecore_1_1_device_plugin_container_1a0551f966021bdbd9e41700232c33d379}
```cpp
Logging& dronecore::DevicePluginContainer::logging()
```


Getter for [Logging](classdronecore_1_1_logging.md) plugin.

**Returns**

&emsp;[Logging](classdronecore_1_1_logging.md) & - a reference to the logging plugin instance

### telemetry() {#classdronecore_1_1_device_plugin_container_1a9b119348d0f5195c9b0919fbe6196b14}
```cpp
Telemetry& dronecore::DevicePluginContainer::telemetry()
```


Getter for [Telemetry](classdronecore_1_1_telemetry.md) plugin.

**Returns**

&emsp;[Telemetry](classdronecore_1_1_telemetry.md) & - a reference to the telemetry plugin instance

### follow_me() {#classdronecore_1_1_device_plugin_container_1ae13164c3bb59230c559341b8506c5e03}
```cpp
FollowMe& dronecore::DevicePluginContainer::follow_me()
```


Getter for [FollowMe](classdronecore_1_1_follow_me.md) plugin.

**Returns**

&emsp;[FollowMe](classdronecore_1_1_follow_me.md) & - a reference to the follow_me plugin instance

### action() {#classdronecore_1_1_device_plugin_container_1aea48bd55b1ace227ebb56690794c2192}
```cpp
Action& dronecore::DevicePluginContainer::action()
```


Getter for [Action](classdronecore_1_1_action.md) plugin.

**Returns**

&emsp;[Action](classdronecore_1_1_action.md) & - a reference to the action plugin instance

### gimbal() {#classdronecore_1_1_device_plugin_container_1a2fce9f439c565af9a8510c5746c728f0}
```cpp
Gimbal& dronecore::DevicePluginContainer::gimbal()
```


Getter for [Gimbal](classdronecore_1_1_gimbal.md) plugin.

**Returns**

&emsp;[Gimbal](classdronecore_1_1_gimbal.md) & - a reference to the gimbal plugin instance

### offboard() {#classdronecore_1_1_device_plugin_container_1a63193bd25273bbda48665e12e012f478}
```cpp
Offboard& dronecore::DevicePluginContainer::offboard()
```


Getter for [Offboard](classdronecore_1_1_offboard.md) plugin.

**Returns**

&emsp;[Offboard](classdronecore_1_1_offboard.md) & - a reference to the offboard plugin instance

### mission() {#classdronecore_1_1_device_plugin_container_1a8a05778326d0ef4c74146bc42fdcb52d}
```cpp
Mission& dronecore::DevicePluginContainer::mission()
```


Getter for [Mission](classdronecore_1_1_mission.md) plugin.

**Returns**

&emsp;[Mission](classdronecore_1_1_mission.md) & - a reference to the mission plugin instance