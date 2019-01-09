# dronecode_sdk::Telemetry::GPSInfo Struct Reference
`#include: telemetry.h`

----


GPS information type. 


## Data Fields


int [num_satellites](#structdronecode__sdk_1_1_telemetry_1_1_g_p_s_info_1a07c3d25ecf7daf3ea1ae99224f6859f4)  - Number of visible satellites used for solution.

int [fix_type](#structdronecode__sdk_1_1_telemetry_1_1_g_p_s_info_1a0c13516cc13e286cac491b90ab16e418)  - Fix type (0: no GPS, 1: no fix, 2: 2D fix, 3: 3D fix, 4: DGPS fix, 5: RTK float, 6: RTK fixed).


## Field Documentation


### num_satellites {#structdronecode__sdk_1_1_telemetry_1_1_g_p_s_info_1a07c3d25ecf7daf3ea1ae99224f6859f4}

```cpp
int dronecode_sdk::Telemetry::GPSInfo::num_satellites
```


Number of visible satellites used for solution.


### fix_type {#structdronecode__sdk_1_1_telemetry_1_1_g_p_s_info_1a0c13516cc13e286cac491b90ab16e418}

```cpp
int dronecode_sdk::Telemetry::GPSInfo::fix_type
```


Fix type (0: no GPS, 1: no fix, 2: 2D fix, 3: 3D fix, 4: DGPS fix, 5: RTK float, 6: RTK fixed).

