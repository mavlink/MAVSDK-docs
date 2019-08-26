# mavsdk::Telemetry::ActuatorControlTarget Struct Reference
`#include: telemetry.h`

----


The vehicle actuator's rate control type. 


An actuator's control group is e.g. attitude, for the core flight controls, or gimbal for payload. For more information about PX4 groups, check out [https://dev.px4.io/v1.9.0/en/concept/mixing.html#control-pipeline](https://dev.px4.io/v1.9.0/en/concept/mixing.html#control-pipeline)


Actuator controls normed to -1..+1 where 0 is neutral position. Throttle for single rotation direction motors is 0..1, negative range for reverse direction.


For more information about controls, check out [https://mavlink.io/en/messages/common.html#SET_ACTUATOR_CONTROL_TARGET](https://mavlink.io/en/messages/common.html#SET_ACTUATOR_CONTROL_TARGET) 


## Data Fields


uint8_t [group](#structmavsdk_1_1_telemetry_1_1_actuator_control_target_1a66e4a0e793c4e78ef180041416c5ce51)  - Actuator group.

float [controls](#structmavsdk_1_1_telemetry_1_1_actuator_control_target_1a08724e9fdcf464a8cb9465b7bcb43d4e)  - Actuator controls.


## Field Documentation


### group {#structmavsdk_1_1_telemetry_1_1_actuator_control_target_1a66e4a0e793c4e78ef180041416c5ce51}

```cpp
uint8_t mavsdk::Telemetry::ActuatorControlTarget::group
```


Actuator group.


### controls {#structmavsdk_1_1_telemetry_1_1_actuator_control_target_1a08724e9fdcf464a8cb9465b7bcb43d4e}

```cpp
float mavsdk::Telemetry::ActuatorControlTarget::controls[8]
```


Actuator controls.

