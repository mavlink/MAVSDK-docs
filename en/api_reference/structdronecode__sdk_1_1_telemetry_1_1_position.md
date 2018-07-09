# dronecode_sdk::Telemetry::Position Struct Reference
`#include: telemetry.h`

----


[Position](structdronecode__sdk_1_1_telemetry_1_1_position.md) type in global coordinates. 


## Data Fields


double [latitude_deg](#structdronecode__sdk_1_1_telemetry_1_1_position_1aa492cc1944b983a7ee9bc334f93ef72e)  - Latitude in degrees (range: -90 to +90)

double [longitude_deg](#structdronecode__sdk_1_1_telemetry_1_1_position_1a4a03be871168af3d5a6731a9f4d63605)  - Longitude in degrees (range: -180 to 180)

float [absolute_altitude_m](#structdronecode__sdk_1_1_telemetry_1_1_position_1ab8bde753179a555e138103d00ad4dd56)  - Altitude AMSL (above mean sea level) in metres.

float [relative_altitude_m](#structdronecode__sdk_1_1_telemetry_1_1_position_1a3341261c702f2a800b0940a6a64e7701)  - Altitude relative to takeoff altitude in metres.


## Field Documentation


### latitude_deg {#structdronecode__sdk_1_1_telemetry_1_1_position_1aa492cc1944b983a7ee9bc334f93ef72e}

```cpp
double dronecode_sdk::Telemetry::Position::latitude_deg
```


Latitude in degrees (range: -90 to +90)


### longitude_deg {#structdronecode__sdk_1_1_telemetry_1_1_position_1a4a03be871168af3d5a6731a9f4d63605}

```cpp
double dronecode_sdk::Telemetry::Position::longitude_deg
```


Longitude in degrees (range: -180 to 180)


### absolute_altitude_m {#structdronecode__sdk_1_1_telemetry_1_1_position_1ab8bde753179a555e138103d00ad4dd56}

```cpp
float dronecode_sdk::Telemetry::Position::absolute_altitude_m
```


Altitude AMSL (above mean sea level) in metres.


### relative_altitude_m {#structdronecode__sdk_1_1_telemetry_1_1_position_1a3341261c702f2a800b0940a6a64e7701}

```cpp
float dronecode_sdk::Telemetry::Position::relative_altitude_m
```


Altitude relative to takeoff altitude in metres.

