# mavsdk::Geofence::Polygon Struct Reference
`#include: geofence.h`

----


[Polygon](structmavsdk_1_1_geofence_1_1_polygon.md) type. 


## Public Types


Type | Description
--- | ---
enum [Type](#structmavsdk_1_1_geofence_1_1_polygon_1ac9024d1161de25e24d9b4ce290e0b5cd) | [Geofence](classmavsdk_1_1_geofence.md) polygon types.

## Data Fields


std::vector< [Point](structmavsdk_1_1_geofence_1_1_point.md) > [points](#structmavsdk_1_1_geofence_1_1_polygon_1a0dd2c3824a7f3486583b95702f71b1d2) {} - Points defining the polygon.

[Type](structmavsdk_1_1_geofence_1_1_polygon.md#structmavsdk_1_1_geofence_1_1_polygon_1ac9024d1161de25e24d9b4ce290e0b5cd) [type](#structmavsdk_1_1_geofence_1_1_polygon_1a61814a15865a8406df8ce39dc3cbdf50) {} - Fence type.


## Member Enumeration Documentation


### enum Type {#structmavsdk_1_1_geofence_1_1_polygon_1ac9024d1161de25e24d9b4ce290e0b5cd}


[Geofence](classmavsdk_1_1_geofence.md) polygon types.


Value | Description
--- | ---
<span id="structmavsdk_1_1_geofence_1_1_polygon_1ac9024d1161de25e24d9b4ce290e0b5cda9e3be7835607d7cc3ae456b20ce9a4f4"></span> `Inclusion` | Type representing an inclusion fence. 
<span id="structmavsdk_1_1_geofence_1_1_polygon_1ac9024d1161de25e24d9b4ce290e0b5cda25218e43e67f1b1c1c833bc48c7ca7bb"></span> `Exclusion` | Type representing an exclusion fence. 

## Field Documentation


### points {#structmavsdk_1_1_geofence_1_1_polygon_1a0dd2c3824a7f3486583b95702f71b1d2}

```cpp
std::vector<Point> mavsdk::Geofence::Polygon::points {}
```


Points defining the polygon.


### type {#structmavsdk_1_1_geofence_1_1_polygon_1a61814a15865a8406df8ce39dc3cbdf50}

```cpp
Type mavsdk::Geofence::Polygon::type {}
```


Fence type.

