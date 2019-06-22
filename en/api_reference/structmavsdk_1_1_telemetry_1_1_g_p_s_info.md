# mavsdk::Telemetry::GPSInfo Struct Reference
`#include: telemetry.h`

----


GPS information type. 


## Data Fields


int [num_satellites](#structmavsdk_1_1_telemetry_1_1_g_p_s_info_1abd2d3f5733a111fe40cbb828b2c5827c)  - Number of visible satellites used for solution.

int [fix_type](#structmavsdk_1_1_telemetry_1_1_g_p_s_info_1a3a8b8b1c0047a8c7b40ea28d1439f4fc)  - Fix type (0: no GPS, 1: no fix, 2: 2D fix, 3: 3D fix, 4: DGPS fix, 5: RTK float, 6: RTK fixed).


## Field Documentation


### num_satellites {#structmavsdk_1_1_telemetry_1_1_g_p_s_info_1abd2d3f5733a111fe40cbb828b2c5827c}

```cpp
int mavsdk::Telemetry::GPSInfo::num_satellites
```


Number of visible satellites used for solution.


### fix_type {#structmavsdk_1_1_telemetry_1_1_g_p_s_info_1a3a8b8b1c0047a8c7b40ea28d1439f4fc}

```cpp
int mavsdk::Telemetry::GPSInfo::fix_type
```


Fix type (0: no GPS, 1: no fix, 2: 2D fix, 3: 3D fix, 4: DGPS fix, 5: RTK float, 6: RTK fixed).

