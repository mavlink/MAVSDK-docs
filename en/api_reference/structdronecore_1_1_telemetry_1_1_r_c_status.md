# dronecore::Telemetry::RCStatus Struct Reference
`#include: telemetry.h`

----


Remote control status type. 


## Data Fields


bool [available_once](#structdronecore_1_1_telemetry_1_1_r_c_status_1a5e1c0486417223de1fda90cb539393f1)  - true if an RC signal has been available once.

bool [available](#structdronecore_1_1_telemetry_1_1_r_c_status_1a541a4647f92a7cdb219cee7cca6963c9)  - true if the RC signal is available now.

float [signal_strength_percent](#structdronecore_1_1_telemetry_1_1_r_c_status_1ae050460c05ddf6e48a4e58e7134dad53)  - Signal strength as a percentage (range: 0 to 100).


## Field Documentation


### available_once {#structdronecore_1_1_telemetry_1_1_r_c_status_1a5e1c0486417223de1fda90cb539393f1}

```cpp
bool dronecore::Telemetry::RCStatus::available_once
```


true if an RC signal has been available once.


### available {#structdronecore_1_1_telemetry_1_1_r_c_status_1a541a4647f92a7cdb219cee7cca6963c9}

```cpp
bool dronecore::Telemetry::RCStatus::available
```


true if the RC signal is available now.


### signal_strength_percent {#structdronecore_1_1_telemetry_1_1_r_c_status_1ae050460c05ddf6e48a4e58e7134dad53}

```cpp
float dronecore::Telemetry::RCStatus::signal_strength_percent
```


Signal strength as a percentage (range: 0 to 100).

