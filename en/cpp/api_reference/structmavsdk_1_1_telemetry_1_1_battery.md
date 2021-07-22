# mavsdk::Telemetry::Battery Struct Reference
`#include: telemetry.h`

----


[Battery](structmavsdk_1_1_telemetry_1_1_battery.md) type. 


## Data Fields


uint32_t [id](#structmavsdk_1_1_telemetry_1_1_battery_1a0f020a0775d3b25b91c7d9b035e7ebd7) {0} - [Battery](structmavsdk_1_1_telemetry_1_1_battery.md) ID, for systems with multiple batteries.

float [voltage_v](#structmavsdk_1_1_telemetry_1_1_battery_1aefd1d5569ff2a69bf507b422cbe75742) {float(NAN)} - Voltage in volts.

float [remaining_percent](#structmavsdk_1_1_telemetry_1_1_battery_1aec821550739844e0fa3fe18f91e6fda7) { float(NAN)} - Estimated battery remaining (range: 0.0 to 1.0)


## Field Documentation


### id {#structmavsdk_1_1_telemetry_1_1_battery_1a0f020a0775d3b25b91c7d9b035e7ebd7}

```cpp
uint32_t mavsdk::Telemetry::Battery::id {0}
```


[Battery](structmavsdk_1_1_telemetry_1_1_battery.md) ID, for systems with multiple batteries.


### voltage_v {#structmavsdk_1_1_telemetry_1_1_battery_1aefd1d5569ff2a69bf507b422cbe75742}

```cpp
float mavsdk::Telemetry::Battery::voltage_v {float(NAN)}
```


Voltage in volts.


### remaining_percent {#structmavsdk_1_1_telemetry_1_1_battery_1aec821550739844e0fa3fe18f91e6fda7}

```cpp
float mavsdk::Telemetry::Battery::remaining_percent { float(NAN)}
```


Estimated battery remaining (range: 0.0 to 1.0)

