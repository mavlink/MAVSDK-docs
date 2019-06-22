# mavsdk::Telemetry::RCStatus Struct Reference
`#include: telemetry.h`

----


Remote control status type. 


## Data Fields


bool [available_once](#structmavsdk_1_1_telemetry_1_1_r_c_status_1aee99d044c37e05450d8ddd7a46af418e)  - true if an RC signal has been available once.

bool [available](#structmavsdk_1_1_telemetry_1_1_r_c_status_1a4fc0a5fe321e1673401a9ab04928adbf)  - true if the RC signal is available now.

float [signal_strength_percent](#structmavsdk_1_1_telemetry_1_1_r_c_status_1a3a03b9559131701dd2c32a686cbca3f6)  - Signal strength as a percentage (range: 0 to 100).


## Field Documentation


### available_once {#structmavsdk_1_1_telemetry_1_1_r_c_status_1aee99d044c37e05450d8ddd7a46af418e}

```cpp
bool mavsdk::Telemetry::RCStatus::available_once
```


true if an RC signal has been available once.


### available {#structmavsdk_1_1_telemetry_1_1_r_c_status_1a4fc0a5fe321e1673401a9ab04928adbf}

```cpp
bool mavsdk::Telemetry::RCStatus::available
```


true if the RC signal is available now.


### signal_strength_percent {#structmavsdk_1_1_telemetry_1_1_r_c_status_1a3a03b9559131701dd2c32a686cbca3f6}

```cpp
float mavsdk::Telemetry::RCStatus::signal_strength_percent
```


Signal strength as a percentage (range: 0 to 100).

