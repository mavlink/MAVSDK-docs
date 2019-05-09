# dronecode_sdk::Telemetry::StatusText Struct Reference
`#include: telemetry.h`

----


Status Text information type. 


## Public Types


Type | Description
--- | ---
enum [StatusType](#structdronecode__sdk_1_1_telemetry_1_1_status_text_1a138979d00085699bc52fc0ffaf0716e3) | Status Types.

## Data Fields


enum [dronecode_sdk::Telemetry::StatusText::StatusType](structdronecode__sdk_1_1_telemetry_1_1_status_text.md#structdronecode__sdk_1_1_telemetry_1_1_status_text_1a138979d00085699bc52fc0ffaf0716e3) [type](#structdronecode__sdk_1_1_telemetry_1_1_status_text_1a66a8bb3498455cef91de82a99465995c)  - Message type.

std::string [text](#structdronecode__sdk_1_1_telemetry_1_1_status_text_1a49945ba79cb584247ea766beb262c045)  - Mavlink status message.


## Member Enumeration Documentation


### enum StatusType {#structdronecode__sdk_1_1_telemetry_1_1_status_text_1a138979d00085699bc52fc0ffaf0716e3}


Status Types.

> **Note** PX4 only supports these 3 status types. If other status types are returned for some reason, they will be marked as INFO type and logged as a warning.

Value | Description
--- | ---
<span id="structdronecode__sdk_1_1_telemetry_1_1_status_text_1a138979d00085699bc52fc0ffaf0716e3a551b723eafd6a31d444fcb2f5920fbd3"></span> `INFO` | Message type is an information or other. 
<span id="structdronecode__sdk_1_1_telemetry_1_1_status_text_1a138979d00085699bc52fc0ffaf0716e3a059e9861e0400dfbe05c98a841f3f96b"></span> `WARNING` | Message type is a warning. 
<span id="structdronecode__sdk_1_1_telemetry_1_1_status_text_1a138979d00085699bc52fc0ffaf0716e3a99cd1c61610c76a57cb8d10d6df6b870"></span> `CRITICAL` | Message type is critical. 

## Field Documentation


### type {#structdronecode__sdk_1_1_telemetry_1_1_status_text_1a66a8bb3498455cef91de82a99465995c}

```cpp
enum dronecode_sdk::Telemetry::StatusText::StatusType  dronecode_sdk::Telemetry::StatusText::type
```


Message type.


### text {#structdronecode__sdk_1_1_telemetry_1_1_status_text_1a49945ba79cb584247ea766beb262c045}

```cpp
std::string dronecode_sdk::Telemetry::StatusText::text
```


Mavlink status message.

