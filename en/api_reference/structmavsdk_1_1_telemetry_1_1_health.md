# mavsdk::Telemetry::Health Struct Reference
`#include: telemetry.h`

----


Various health flags. 


## Data Fields


bool [gyrometer_calibration_ok](#structmavsdk_1_1_telemetry_1_1_health_1ae127e9293a03dda55eb818605972fe9e)  - true if the gyrometer is calibrated.

bool [accelerometer_calibration_ok](#structmavsdk_1_1_telemetry_1_1_health_1ac7587e489120abca44883e4a70563b70)  - true if the accelerometer is calibrated.

bool [magnetometer_calibration_ok](#structmavsdk_1_1_telemetry_1_1_health_1ae22b08235a8a35fc52c68ebd5a6a0206)  - true if the magnetometer is calibrated.

bool [level_calibration_ok](#structmavsdk_1_1_telemetry_1_1_health_1a69cfc793b9006bcaec9fa7f02f8a8316)  - true if the vehicle has a valid level calibration.

bool [local_position_ok](#structmavsdk_1_1_telemetry_1_1_health_1a2525623198a4412ae152982d88be776e)  - true if the local position estimate is good enough to fly in a position control mode.

bool [global_position_ok](#structmavsdk_1_1_telemetry_1_1_health_1a7e8c446ef334647863e78e9f0da02e1f)  - true if the global position estimate is good enough to fly in a position controlled mode.

bool [home_position_ok](#structmavsdk_1_1_telemetry_1_1_health_1a0e21a3d67cd82a26654d6b76e6eab056)  - true if the home position has been initialized properly.


## Field Documentation


### gyrometer_calibration_ok {#structmavsdk_1_1_telemetry_1_1_health_1ae127e9293a03dda55eb818605972fe9e}

```cpp
bool mavsdk::Telemetry::Health::gyrometer_calibration_ok
```


true if the gyrometer is calibrated.


### accelerometer_calibration_ok {#structmavsdk_1_1_telemetry_1_1_health_1ac7587e489120abca44883e4a70563b70}

```cpp
bool mavsdk::Telemetry::Health::accelerometer_calibration_ok
```


true if the accelerometer is calibrated.


### magnetometer_calibration_ok {#structmavsdk_1_1_telemetry_1_1_health_1ae22b08235a8a35fc52c68ebd5a6a0206}

```cpp
bool mavsdk::Telemetry::Health::magnetometer_calibration_ok
```


true if the magnetometer is calibrated.


### level_calibration_ok {#structmavsdk_1_1_telemetry_1_1_health_1a69cfc793b9006bcaec9fa7f02f8a8316}

```cpp
bool mavsdk::Telemetry::Health::level_calibration_ok
```


true if the vehicle has a valid level calibration.


### local_position_ok {#structmavsdk_1_1_telemetry_1_1_health_1a2525623198a4412ae152982d88be776e}

```cpp
bool mavsdk::Telemetry::Health::local_position_ok
```


true if the local position estimate is good enough to fly in a position control mode.


### global_position_ok {#structmavsdk_1_1_telemetry_1_1_health_1a7e8c446ef334647863e78e9f0da02e1f}

```cpp
bool mavsdk::Telemetry::Health::global_position_ok
```


true if the global position estimate is good enough to fly in a position controlled mode.


### home_position_ok {#structmavsdk_1_1_telemetry_1_1_health_1a0e21a3d67cd82a26654d6b76e6eab056}

```cpp
bool mavsdk::Telemetry::Health::home_position_ok
```


true if the home position has been initialized properly.

