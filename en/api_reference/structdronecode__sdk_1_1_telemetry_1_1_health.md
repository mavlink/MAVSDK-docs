# dronecode_sdk::Telemetry::Health Struct Reference
`#include: telemetry.h`

----


Various health flags. 


## Data Fields


bool [gyrometer_calibration_ok](#structdronecode__sdk_1_1_telemetry_1_1_health_1a81d5f88f8c1480c679841743ff076dd7)  - true if the gyrometer is calibrated.

bool [accelerometer_calibration_ok](#structdronecode__sdk_1_1_telemetry_1_1_health_1a9b297bdf5439bcc599490313f1e5d4c6)  - true if the accelerometer is calibrated.

bool [magnetometer_calibration_ok](#structdronecode__sdk_1_1_telemetry_1_1_health_1a8578dcf86f99338336505f78493a33ec)  - true if the magnetometer is calibrated.

bool [level_calibration_ok](#structdronecode__sdk_1_1_telemetry_1_1_health_1aacc0e8c786a931acf9f779423d7cc2fe)  - true if the vehicle has a valid level calibration.

bool [local_position_ok](#structdronecode__sdk_1_1_telemetry_1_1_health_1a4b14520bea72e3e3448df1e2d05075d2)  - true if the local position estimate is good enough to fly in a position control mode.

bool [global_position_ok](#structdronecode__sdk_1_1_telemetry_1_1_health_1a3f3e9709d90920a40c57e3061a93fb8c)  - true if the global position estimate is good enough to fly in a position controlled mode.

bool [home_position_ok](#structdronecode__sdk_1_1_telemetry_1_1_health_1a6c4e0d2b56c034bfcb4063a470f33f52)  - true if the home position has been initialized properly.


## Field Documentation


### gyrometer_calibration_ok {#structdronecode__sdk_1_1_telemetry_1_1_health_1a81d5f88f8c1480c679841743ff076dd7}

```cpp
bool dronecode_sdk::Telemetry::Health::gyrometer_calibration_ok
```


true if the gyrometer is calibrated.


### accelerometer_calibration_ok {#structdronecode__sdk_1_1_telemetry_1_1_health_1a9b297bdf5439bcc599490313f1e5d4c6}

```cpp
bool dronecode_sdk::Telemetry::Health::accelerometer_calibration_ok
```


true if the accelerometer is calibrated.


### magnetometer_calibration_ok {#structdronecode__sdk_1_1_telemetry_1_1_health_1a8578dcf86f99338336505f78493a33ec}

```cpp
bool dronecode_sdk::Telemetry::Health::magnetometer_calibration_ok
```


true if the magnetometer is calibrated.


### level_calibration_ok {#structdronecode__sdk_1_1_telemetry_1_1_health_1aacc0e8c786a931acf9f779423d7cc2fe}

```cpp
bool dronecode_sdk::Telemetry::Health::level_calibration_ok
```


true if the vehicle has a valid level calibration.


### local_position_ok {#structdronecode__sdk_1_1_telemetry_1_1_health_1a4b14520bea72e3e3448df1e2d05075d2}

```cpp
bool dronecode_sdk::Telemetry::Health::local_position_ok
```


true if the local position estimate is good enough to fly in a position control mode.


### global_position_ok {#structdronecode__sdk_1_1_telemetry_1_1_health_1a3f3e9709d90920a40c57e3061a93fb8c}

```cpp
bool dronecode_sdk::Telemetry::Health::global_position_ok
```


true if the global position estimate is good enough to fly in a position controlled mode.


### home_position_ok {#structdronecode__sdk_1_1_telemetry_1_1_health_1a6c4e0d2b56c034bfcb4063a470f33f52}

```cpp
bool dronecode_sdk::Telemetry::Health::home_position_ok
```


true if the home position has been initialized properly.

