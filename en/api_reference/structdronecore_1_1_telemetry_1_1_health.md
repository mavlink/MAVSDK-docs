# dronecore::Telemetry::Health Struct Reference
`#include: telemetry.h`

----


Various health flags. 


## Data Fields


 bool [gyrometer_calibration_ok](#structdronecore_1_1_telemetry_1_1_health_1a20d42a65fe962216969dc8eef6a221a8) - true if the gyrometer is calibrated.


 bool [accelerometer_calibration_ok](#structdronecore_1_1_telemetry_1_1_health_1aca75d649d8caf7004f42bd418a407cbc) - true if the accelerometer is calibrated.


 bool [magnetometer_calibration_ok](#structdronecore_1_1_telemetry_1_1_health_1a30651ed802acff96c88365fb2ca9fc5c) - true if the magnetometer is calibrated.


 bool [level_calibration_ok](#structdronecore_1_1_telemetry_1_1_health_1a470b87fb4865c89fb225dda1c77d6db6) - true if the vehicle has a valid level calibration.


 bool [local_position_ok](#structdronecore_1_1_telemetry_1_1_health_1a54a4cacaf2ae764857165dd1077d6c91) - true if the local position estimate is good enough to fly in a position control mode.


 bool [global_position_ok](#structdronecore_1_1_telemetry_1_1_health_1a5f02efb9cc25a6db1ee2b9d70149ba6f) - true if the global position estimate is good enough to fly in a position controlled mode.


 bool [home_position_ok](#structdronecore_1_1_telemetry_1_1_health_1a3736323422843fb5e37b988a95d5575a) - true if the home position has been initialized properly.


## Field Documentation


### gyrometer_calibration_ok {#structdronecore_1_1_telemetry_1_1_health_1a20d42a65fe962216969dc8eef6a221a8}

```cpp
bool dronecore::Telemetry::Health::gyrometer_calibration_ok
```


true if the gyrometer is calibrated.


### accelerometer_calibration_ok {#structdronecore_1_1_telemetry_1_1_health_1aca75d649d8caf7004f42bd418a407cbc}

```cpp
bool dronecore::Telemetry::Health::accelerometer_calibration_ok
```


true if the accelerometer is calibrated.


### magnetometer_calibration_ok {#structdronecore_1_1_telemetry_1_1_health_1a30651ed802acff96c88365fb2ca9fc5c}

```cpp
bool dronecore::Telemetry::Health::magnetometer_calibration_ok
```


true if the magnetometer is calibrated.


### level_calibration_ok {#structdronecore_1_1_telemetry_1_1_health_1a470b87fb4865c89fb225dda1c77d6db6}

```cpp
bool dronecore::Telemetry::Health::level_calibration_ok
```


true if the vehicle has a valid level calibration.


### local_position_ok {#structdronecore_1_1_telemetry_1_1_health_1a54a4cacaf2ae764857165dd1077d6c91}

```cpp
bool dronecore::Telemetry::Health::local_position_ok
```


true if the local position estimate is good enough to fly in a position control mode.


### global_position_ok {#structdronecore_1_1_telemetry_1_1_health_1a5f02efb9cc25a6db1ee2b9d70149ba6f}

```cpp
bool dronecore::Telemetry::Health::global_position_ok
```


true if the global position estimate is good enough to fly in a position controlled mode.


### home_position_ok {#structdronecore_1_1_telemetry_1_1_health_1a3736323422843fb5e37b988a95d5575a}

```cpp
bool dronecore::Telemetry::Health::home_position_ok
```


true if the home position has been initialized properly.

