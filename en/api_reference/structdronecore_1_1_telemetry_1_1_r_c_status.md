# dronecore::Telemetry::RCStatus Struct Reference
`#include: telemetry.h`

----


Remote control status type. 


## Data Fields


 bool [available_once](#structdronecore_1_1_telemetry_1_1_r_c_status_1a5e1c0486417223de1fda90cb539393f1) - true if an RC signal has been available once.


 bool [lost](#structdronecore_1_1_telemetry_1_1_r_c_status_1a680e14b6c90918fe059a2c23803a1fbe) - true if the RC signal is lost.


 float [signal_strength_percent](#structdronecore_1_1_telemetry_1_1_r_c_status_1ae050460c05ddf6e48a4e58e7134dad53) - Signal strength as a percentage (range: 0 to 100).


## Field Documentation


### available_once {#structdronecore_1_1_telemetry_1_1_r_c_status_1a5e1c0486417223de1fda90cb539393f1}

```cpp
bool dronecore::Telemetry::RCStatus::available_once
```


true if an RC signal has been available once.


<!-- [<Element 'type' at 0x000001F32A2D3278> available_once](#structdronecore_1_1_telemetry_1_1_r_c_status_1a5e1c0486417223de1fda90cb539393f1) -->
<!-- kind: variable -->
<!-- prot: public -->
<!-- static: no -->
<!-- mutable: no -->
<!-- definition: bool dronecore::Telemetry::RCStatus::available_once -->
<!-- detaileddescription:  -->
<!-- briefdescription: true if an RC signal has been available once. -->

<!-- argsstring:  -->


### lost {#structdronecore_1_1_telemetry_1_1_r_c_status_1a680e14b6c90918fe059a2c23803a1fbe}

```cpp
bool dronecore::Telemetry::RCStatus::lost
```


true if the RC signal is lost.


<!-- [<Element 'type' at 0x000001F32A2F7688> lost](#structdronecore_1_1_telemetry_1_1_r_c_status_1a680e14b6c90918fe059a2c23803a1fbe) -->
<!-- kind: variable -->
<!-- prot: public -->
<!-- static: no -->
<!-- mutable: no -->
<!-- definition: bool dronecore::Telemetry::RCStatus::lost -->
<!-- detaileddescription:  -->
<!-- briefdescription: true if the RC signal is lost. -->

<!-- argsstring:  -->


### signal_strength_percent {#structdronecore_1_1_telemetry_1_1_r_c_status_1ae050460c05ddf6e48a4e58e7134dad53}

```cpp
float dronecore::Telemetry::RCStatus::signal_strength_percent
```


Signal strength as a percentage (range: 0 to 100).


<!-- [<Element 'type' at 0x000001F32A2F7DB8> signal_strength_percent](#structdronecore_1_1_telemetry_1_1_r_c_status_1ae050460c05ddf6e48a4e58e7134dad53) -->
<!-- kind: variable -->
<!-- prot: public -->
<!-- static: no -->
<!-- mutable: no -->
<!-- definition: float dronecore::Telemetry::RCStatus::signal_strength_percent -->
<!-- detaileddescription:  -->
<!-- briefdescription: Signal strength as a percentage (range: 0 to 100). -->

<!-- argsstring:  -->
