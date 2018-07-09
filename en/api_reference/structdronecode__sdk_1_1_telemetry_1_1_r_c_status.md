# dronecode_sdk::Telemetry::RCStatus Struct Reference
`#include: telemetry.h`

----


Remote control status type. 


## Data Fields


bool [available_once](#structdronecode__sdk_1_1_telemetry_1_1_r_c_status_1a618920366499c41debae5b89477784f0)  - true if an RC signal has been available once.

bool [available](#structdronecode__sdk_1_1_telemetry_1_1_r_c_status_1a3473f3363022959d96072cf89532939a)  - true if the RC signal is available now.

float [signal_strength_percent](#structdronecode__sdk_1_1_telemetry_1_1_r_c_status_1a303b74c4ca11a77c411e99415ea0a71a)  - Signal strength as a percentage (range: 0 to 100).


## Field Documentation


### available_once {#structdronecode__sdk_1_1_telemetry_1_1_r_c_status_1a618920366499c41debae5b89477784f0}

```cpp
bool dronecode_sdk::Telemetry::RCStatus::available_once
```


true if an RC signal has been available once.


### available {#structdronecode__sdk_1_1_telemetry_1_1_r_c_status_1a3473f3363022959d96072cf89532939a}

```cpp
bool dronecode_sdk::Telemetry::RCStatus::available
```


true if the RC signal is available now.


### signal_strength_percent {#structdronecode__sdk_1_1_telemetry_1_1_r_c_status_1a303b74c4ca11a77c411e99415ea0a71a}

```cpp
float dronecode_sdk::Telemetry::RCStatus::signal_strength_percent
```


Signal strength as a percentage (range: 0 to 100).

