# mavsdk::Geofence::Polygon Struct Reference
`#include: geofence.h`

----


[Polygon](structmavsdk_1_1_geofence_1_1_polygon.md) type. 


## Public Types


Type | Description
--- | ---
enum [FenceType](#structmavsdk_1_1_geofence_1_1_polygon_1adc10ba21843249e35d43badbec54499d) | [Geofence](classmavsdk_1_1_geofence.md) polygon types.

## Data Fields


std::vector< [Point](structmavsdk_1_1_geofence_1_1_point.md) > [points](#structmavsdk_1_1_geofence_1_1_polygon_1a0dd2c3824a7f3486583b95702f71b1d2) {} - Points defining the polygon.

[FenceType](structmavsdk_1_1_geofence_1_1_polygon.md#structmavsdk_1_1_geofence_1_1_polygon_1adc10ba21843249e35d43badbec54499d) [fence_type](#structmavsdk_1_1_geofence_1_1_polygon_1af61a1478f60ae8bb2d620a05c62995af) {} - Fence type.


## Member Enumeration Documentation


### enum FenceType {#structmavsdk_1_1_geofence_1_1_polygon_1adc10ba21843249e35d43badbec54499d}


[Geofence](classmavsdk_1_1_geofence.md) polygon types.


Value | Description
--- | ---
<span id="structmavsdk_1_1_geofence_1_1_polygon_1adc10ba21843249e35d43badbec54499da9e3be7835607d7cc3ae456b20ce9a4f4"></span> `Inclusion` | Type representing an inclusion fence. 
<span id="structmavsdk_1_1_geofence_1_1_polygon_1adc10ba21843249e35d43badbec54499da25218e43e67f1b1c1c833bc48c7ca7bb"></span> `Exclusion` | Type representing an exclusion fence. 

## Field Documentation


### points {#structmavsdk_1_1_geofence_1_1_polygon_1a0dd2c3824a7f3486583b95702f71b1d2}

```cpp
std::vector<Point> mavsdk::Geofence::Polygon::points {}
```


Points defining the polygon.


### fence_type {#structmavsdk_1_1_geofence_1_1_polygon_1af61a1478f60ae8bb2d620a05c62995af}

```cpp
FenceType mavsdk::Geofence::Polygon::fence_type {}
```


Fence type.

