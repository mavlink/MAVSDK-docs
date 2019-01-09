# dronecode_sdk::Info::Identification Struct Reference
`#include: info.h`

----


Type containing identification. 


## Data Fields


uint8_t [hardware_uid](#structdronecode__sdk_1_1_info_1_1_identification_1a38ad127a94190d4f3c73cb556a4e0c6c)  - UID of hardware. This refers to uid2 of MAVLink. If the system does not support uid2 yet, this will be all zero.


## Field Documentation


### hardware_uid {#structdronecode__sdk_1_1_info_1_1_identification_1a38ad127a94190d4f3c73cb556a4e0c6c}

```cpp
uint8_t dronecode_sdk::Info::Identification::hardware_uid[18]
```


UID of hardware. This refers to uid2 of MAVLink. If the system does not support uid2 yet, this will be all zero.

