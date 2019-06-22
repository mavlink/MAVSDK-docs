# mavsdk::Telemetry::Position Struct Reference
`#include: telemetry.h`

----


[Position](structmavsdk_1_1_telemetry_1_1_position.md) type in global coordinates. 


## Data Fields


double [latitude_deg](#structmavsdk_1_1_telemetry_1_1_position_1af040035143d32f21a4785bd81acd99ea)  - Latitude in degrees (range: -90 to +90)

double [longitude_deg](#structmavsdk_1_1_telemetry_1_1_position_1af848ad6e710ab4642074a6e39b6c579d)  - Longitude in degrees (range: -180 to 180)

float [absolute_altitude_m](#structmavsdk_1_1_telemetry_1_1_position_1a07dc691d181242ce93223892bd87db94)  - Altitude AMSL (above mean sea level) in metres.

float [relative_altitude_m](#structmavsdk_1_1_telemetry_1_1_position_1aac41c299def111b789ec7c94c5b46850)  - Altitude relative to takeoff altitude in metres.


## Field Documentation


### latitude_deg {#structmavsdk_1_1_telemetry_1_1_position_1af040035143d32f21a4785bd81acd99ea}

```cpp
double mavsdk::Telemetry::Position::latitude_deg
```


Latitude in degrees (range: -90 to +90)


### longitude_deg {#structmavsdk_1_1_telemetry_1_1_position_1af848ad6e710ab4642074a6e39b6c579d}

```cpp
double mavsdk::Telemetry::Position::longitude_deg
```


Longitude in degrees (range: -180 to 180)


### absolute_altitude_m {#structmavsdk_1_1_telemetry_1_1_position_1a07dc691d181242ce93223892bd87db94}

```cpp
float mavsdk::Telemetry::Position::absolute_altitude_m
```


Altitude AMSL (above mean sea level) in metres.


### relative_altitude_m {#structmavsdk_1_1_telemetry_1_1_position_1aac41c299def111b789ec7c94c5b46850}

```cpp
float mavsdk::Telemetry::Position::relative_altitude_m
```


Altitude relative to takeoff altitude in metres.

