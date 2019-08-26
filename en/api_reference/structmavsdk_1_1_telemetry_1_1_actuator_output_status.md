# mavsdk::Telemetry::ActuatorOutputStatus Struct Reference
`#include: telemetry.h`

----


The raw values of the actuator outputs type. 


## Data Fields


uint32_t [active](#structmavsdk_1_1_telemetry_1_1_actuator_output_status_1a6325f5b35293353c43cccf1ceaa5a712)  - Active outputs.

float [actuator](#structmavsdk_1_1_telemetry_1_1_actuator_output_status_1a25cbc13041544894ddab6320eae769df)  - Servo / motor output array values.


## Field Documentation


### active {#structmavsdk_1_1_telemetry_1_1_actuator_output_status_1a6325f5b35293353c43cccf1ceaa5a712}

```cpp
uint32_t mavsdk::Telemetry::ActuatorOutputStatus::active
```


Active outputs.


### actuator {#structmavsdk_1_1_telemetry_1_1_actuator_output_status_1a25cbc13041544894ddab6320eae769df}

```cpp
float mavsdk::Telemetry::ActuatorOutputStatus::actuator[32]
```


Servo / motor output array values.

