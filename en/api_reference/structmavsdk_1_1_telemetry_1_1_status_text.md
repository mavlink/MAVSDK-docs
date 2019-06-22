# mavsdk::Telemetry::StatusText Struct Reference
`#include: telemetry.h`

----


Status Text information type. 


## Public Types


Type | Description
--- | ---
enum [StatusType](#structmavsdk_1_1_telemetry_1_1_status_text_1adbd5dccf79c9889699982a6b6a1d7124) | Status Types.

## Data Fields


enum [mavsdk::Telemetry::StatusText::StatusType](structmavsdk_1_1_telemetry_1_1_status_text.md#structmavsdk_1_1_telemetry_1_1_status_text_1adbd5dccf79c9889699982a6b6a1d7124) [type](#structmavsdk_1_1_telemetry_1_1_status_text_1acb0d4bbd5eac5f74d33e28c7b22fb27f)  - Message type.

std::string [text](#structmavsdk_1_1_telemetry_1_1_status_text_1abb6445887ad0abdb0aa33b027d8d6047)  - Mavlink status message.


## Member Enumeration Documentation


### enum StatusType {#structmavsdk_1_1_telemetry_1_1_status_text_1adbd5dccf79c9889699982a6b6a1d7124}


Status Types.

> **Note** PX4 only supports these 3 status types. If other status types are returned for some reason, they will be marked as INFO type and logged as a warning.

Value | Description
--- | ---
<span id="structmavsdk_1_1_telemetry_1_1_status_text_1adbd5dccf79c9889699982a6b6a1d7124a551b723eafd6a31d444fcb2f5920fbd3"></span> `INFO` | Message type is an information or other. 
<span id="structmavsdk_1_1_telemetry_1_1_status_text_1adbd5dccf79c9889699982a6b6a1d7124a059e9861e0400dfbe05c98a841f3f96b"></span> `WARNING` | Message type is a warning. 
<span id="structmavsdk_1_1_telemetry_1_1_status_text_1adbd5dccf79c9889699982a6b6a1d7124a99cd1c61610c76a57cb8d10d6df6b870"></span> `CRITICAL` | Message type is critical. 

## Field Documentation


### type {#structmavsdk_1_1_telemetry_1_1_status_text_1acb0d4bbd5eac5f74d33e28c7b22fb27f}

```cpp
enum mavsdk::Telemetry::StatusText::StatusType  mavsdk::Telemetry::StatusText::type
```


Message type.


### text {#structmavsdk_1_1_telemetry_1_1_status_text_1abb6445887ad0abdb0aa33b027d8d6047}

```cpp
std::string mavsdk::Telemetry::StatusText::text
```


Mavlink status message.

