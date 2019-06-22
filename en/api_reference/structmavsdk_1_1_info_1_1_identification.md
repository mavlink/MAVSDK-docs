# mavsdk::Info::Identification Struct Reference
`#include: info.h`

----


Type containing identification. 


## Data Fields


uint8_t [hardware_uid](#structmavsdk_1_1_info_1_1_identification_1ac5db4c3496a4b2a118ad703547a542be)  - UID of hardware. This refers to uid2 of MAVLink. If the system does not support uid2 yet, this will be all zero.


## Field Documentation


### hardware_uid {#structmavsdk_1_1_info_1_1_identification_1ac5db4c3496a4b2a118ad703547a542be}

```cpp
uint8_t mavsdk::Info::Identification::hardware_uid[18]
```


UID of hardware. This refers to uid2 of MAVLink. If the system does not support uid2 yet, this will be all zero.

