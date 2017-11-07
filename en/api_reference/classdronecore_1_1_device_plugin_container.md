# dronecore::DevicePluginContainer Class Reference
`#include: device_plugin_container.h`

----


The [DevicePluginContainer](classdronecore_1_1_device_plugin_container.md) contains all plugins for a device. 


The content of the [DevicePluginContainer](classdronecore_1_1_device_plugin_container.md) is auto-generated at compile time. Plugins such as [Action](classdronecore_1_1_action.md) or [Telemetry](classdronecore_1_1_telemetry.md) are included so that they can be accessed using [DroneCore::device()](classdronecore_1_1_drone_core.md#classdronecore_1_1_drone_core_1a5bac6e419e56a1f77a51adef98e94e7c).[action()](classdronecore_1_1_device_plugin_container.md#classdronecore_1_1_device_plugin_container_1aea48bd55b1ace227ebb56690794c2192)... 


## Public Member Functions


Type | Name | Description
---: | --- | ---
| [DevicePluginContainer](#classdronecore_1_1_device_plugin_container_1af4c0f2facc64a99818737971f7f1cc77) (const DevicePluginContainer &)=delete |
[Action](classdronecore_1_1_action.md) & | [action](#classdronecore_1_1_device_plugin_container_1aea48bd55b1ace227ebb56690794c2192) () |
[Gimbal](classdronecore_1_1_gimbal.md) & | [gimbal](#classdronecore_1_1_device_plugin_container_1a2fce9f439c565af9a8510c5746c728f0) () |
[Info](classdronecore_1_1_info.md) & | [info](#classdronecore_1_1_device_plugin_container_1a1509e3d7a469cbc3e33471138b1f4dc7) () |
[Logging](classdronecore_1_1_logging.md) & | [logging](#classdronecore_1_1_device_plugin_container_1a0551f966021bdbd9e41700232c33d379) () |
[Mission](classdronecore_1_1_mission.md) & | [mission](#classdronecore_1_1_device_plugin_container_1a8a05778326d0ef4c74146bc42fdcb52d) () |
[Offboard](classdronecore_1_1_offboard.md) & | [offboard](#classdronecore_1_1_device_plugin_container_1a63193bd25273bbda48665e12e012f478) () |
[Telemetry](classdronecore_1_1_telemetry.md) & | [telemetry](#classdronecore_1_1_device_plugin_container_1a9b119348d0f5195c9b0919fbe6196b14) () |
const [DevicePluginContainer](classdronecore_1_1_device_plugin_container.md) & | [operator=](#classdronecore_1_1_device_plugin_container_1abb90ffceec0873823fb78067d8d6e385) (const DevicePluginContainer &)=delete |


## Constructor & Destructor Documentation


### DevicePluginContainer() {#classdronecore_1_1_device_plugin_container_1af4c0f2facc64a99818737971f7f1cc77}
```cpp
dronecore::DevicePluginContainer::DevicePluginContainer(const DevicePluginContainer &)=delete
```


**Parameters**

* const [DevicePluginContainer](classdronecore_1_1_device_plugin_container.md) & - 

## Member Function Documentation


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

### mission() {#classdronecore_1_1_device_plugin_container_1a8a05778326d0ef4c74146bc42fdcb52d}
```cpp
Mission& dronecore::DevicePluginContainer::mission()
```


Getter for [Mission](classdronecore_1_1_mission.md) plugin.

**Returns**

&emsp;[Mission](classdronecore_1_1_mission.md) & - a reference to the mission plugin instance

### offboard() {#classdronecore_1_1_device_plugin_container_1a63193bd25273bbda48665e12e012f478}
```cpp
Offboard& dronecore::DevicePluginContainer::offboard()
```


Getter for [Offboard](classdronecore_1_1_offboard.md) plugin.

**Returns**

&emsp;[Offboard](classdronecore_1_1_offboard.md) & - a reference to the offboard plugin instance

### telemetry() {#classdronecore_1_1_device_plugin_container_1a9b119348d0f5195c9b0919fbe6196b14}
```cpp
Telemetry& dronecore::DevicePluginContainer::telemetry()
```


Getter for [Telemetry](classdronecore_1_1_telemetry.md) plugin.

**Returns**

&emsp;[Telemetry](classdronecore_1_1_telemetry.md) & - a reference to the telemetry plugin instance

### operator=() {#classdronecore_1_1_device_plugin_container_1abb90ffceec0873823fb78067d8d6e385}
```cpp
const DevicePluginContainer& dronecore::DevicePluginContainer::operator=(const DevicePluginContainer &)=delete
```


**Parameters**

* const [DevicePluginContainer](classdronecore_1_1_device_plugin_container.md) & - 

**Returns**

&emsp;const [DevicePluginContainer](classdronecore_1_1_device_plugin_container.md) & - 