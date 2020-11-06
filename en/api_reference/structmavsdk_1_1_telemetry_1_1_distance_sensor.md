# mavsdk::Telemetry::DistanceSensor Struct Reference
`#include: telemetry.h`

----


[DistanceSensor](structmavsdk_1_1_telemetry_1_1_distance_sensor.md) message type. 


## Data Fields


float [minimum_distance_m](#structmavsdk_1_1_telemetry_1_1_distance_sensor_1ab5601497cd86fdf3318ae26a312405cc) { float(NAN)} - Minimum distance the sensor can measure, NaN if unknown.

float [maximum_distance_m](#structmavsdk_1_1_telemetry_1_1_distance_sensor_1aca0cdb621fc6df047abab9b3526c45b2) { float(NAN)} - Maximum distance the sensor can measure, NaN if unknown.

float [current_distance_m](#structmavsdk_1_1_telemetry_1_1_distance_sensor_1a16bd239d2498378c57d910f07797a3a1) { float(NAN)} - Current distance reading, NaN if unknown.


## Field Documentation


### minimum_distance_m {#structmavsdk_1_1_telemetry_1_1_distance_sensor_1ab5601497cd86fdf3318ae26a312405cc}

```cpp
float mavsdk::Telemetry::DistanceSensor::minimum_distance_m { float(NAN)}
```


Minimum distance the sensor can measure, NaN if unknown.


### maximum_distance_m {#structmavsdk_1_1_telemetry_1_1_distance_sensor_1aca0cdb621fc6df047abab9b3526c45b2}

```cpp
float mavsdk::Telemetry::DistanceSensor::maximum_distance_m { float(NAN)}
```


Maximum distance the sensor can measure, NaN if unknown.


### current_distance_m {#structmavsdk_1_1_telemetry_1_1_distance_sensor_1a16bd239d2498378c57d910f07797a3a1}

```cpp
float mavsdk::Telemetry::DistanceSensor::current_distance_m { float(NAN)}
```


Current distance reading, NaN if unknown.

