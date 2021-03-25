# mavsdk::Info::Identification Struct Reference
`#include: info.h`

----


[System](classmavsdk_1_1_system.md) identification. 


## Data Fields


std::string [hardware_uid](#structmavsdk_1_1_info_1_1_identification_1a68be9823aae193b5473191d287b5e385) {} - UID of the hardware. This refers to uid2 of MAVLink. If the system does not support uid2 yet, this is all zeros.


## Field Documentation


### hardware_uid {#structmavsdk_1_1_info_1_1_identification_1a68be9823aae193b5473191d287b5e385}

```cpp
std::string mavsdk::Info::Identification::hardware_uid {}
```


UID of the hardware. This refers to uid2 of MAVLink. If the system does not support uid2 yet, this is all zeros.

