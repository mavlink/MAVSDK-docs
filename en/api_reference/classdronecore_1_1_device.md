# dronecore::Device Class Reference
`#include: device.h`

----


A [Device](classdronecore_1_1_device.md) represents a vehicle such as a drone or robot. 


A device can consist of multiple components such as an autopilot with a gimbal and camera. The device class can access plugins like [dronecore::Action](classdronecore_1_1_action.md) or [dronecore::Telemetry](classdronecore_1_1_telemetry.md) because it is based on DevicePluginContainer.


[Device](classdronecore_1_1_device.md) objects are not created or destroyed directly by API consumers. They are accessed using, for example, [DroneCore::device()](classdronecore_1_1_drone_core.md#classdronecore_1_1_drone_core_1a10872f29d98348484b3fdbc8ce0c8108) and cleaned up when [DroneCore](classdronecore_1_1_drone_core.md) is destroyed. 


## Public Member Functions


Type | Name | Description
---: | --- | ---
| [Device](#classdronecore_1_1_device_1aa64ba685fe110fcb0a8e1b92156f144b) (DeviceImpl *impl) | Constructor (internal use only).
| [~Device](#classdronecore_1_1_device_1a65c697e12eed30109074e18a9cfdc836) () | Destructor (internal use only).


## Constructor & Destructor Documentation


### Device() {#classdronecore_1_1_device_1aa64ba685fe110fcb0a8e1b92156f144b}
```cpp
dronecore::Device::Device(DeviceImpl *impl)
```


Constructor (internal use only).

This constructor does not need to be called by any consumer of the API.

**Parameters**

* [DeviceImpl](classdronecore_1_1_device_impl.md) * **impl** - The underlying device implementation.

<!-- inbodydescription:  --> 
<!-- return_type:  -->
<!-- return_type_comment:  -->
<!-- prot: public -->
<!-- static: no -->
<!-- const: no -->
<!-- explicit: yes -->
<!-- virt: non-virtual -->
<!-- inline: no -->


### ~Device() {#classdronecore_1_1_device_1a65c697e12eed30109074e18a9cfdc836}
```cpp
dronecore::Device::~Device()
```


Destructor (internal use only).

The destructor of [Device](classdronecore_1_1_device.md) does not need to be called by any consumer of the API.

<!-- inbodydescription:  --> 
<!-- return_type:  -->
<!-- return_type_comment:  -->
<!-- prot: public -->
<!-- static: no -->
<!-- const: no -->
<!-- explicit: no -->
<!-- virt: non-virtual -->
<!-- inline: no -->
