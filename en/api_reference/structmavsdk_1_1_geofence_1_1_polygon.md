# mavsdk::Geofence::Polygon Struct Reference
`#include: geofence.h`

----


[Polygon](structmavsdk_1_1_geofence_1_1_polygon.md) type. 


## Data Structures


struct [Point](structmavsdk_1_1_geofence_1_1_polygon_1_1_point.md)

## Public Types


Type | Description
--- | ---
enum [Type](#structmavsdk_1_1_geofence_1_1_polygon_1ac9024d1161de25e24d9b4ce290e0b5cd) | [Polygon](structmavsdk_1_1_geofence_1_1_polygon.md) Fence Types.

## Public Member Functions


Type | Name | Description
---: | --- | ---
&nbsp; | [Polygon](#structmavsdk_1_1_geofence_1_1_polygon_1a2d2f3ce5f4f957e8d4e367cd95b376a9) () | Constructor. Creates the [Polygon](structmavsdk_1_1_geofence_1_1_polygon.md) for a specific geometry.
&nbsp; | [~Polygon](#structmavsdk_1_1_geofence_1_1_polygon_1ad54d6befd424528b3f627fc4106b310a) () | Destructor (internal use only).

## Data Fields


std::vector< [Point](structmavsdk_1_1_geofence_1_1_polygon_1_1_point.md) > [points](#structmavsdk_1_1_geofence_1_1_polygon_1a0dd2c3824a7f3486583b95702f71b1d2)  - Vector of points that define the polygon.

[Type](structmavsdk_1_1_geofence_1_1_polygon.md#structmavsdk_1_1_geofence_1_1_polygon_1ac9024d1161de25e24d9b4ce290e0b5cd) [type](#structmavsdk_1_1_geofence_1_1_polygon_1a61814a15865a8406df8ce39dc3cbdf50)  - [Polygon](structmavsdk_1_1_geofence_1_1_polygon.md) fence type.


## Constructor & Destructor Documentation


### Polygon() {#structmavsdk_1_1_geofence_1_1_polygon_1a2d2f3ce5f4f957e8d4e367cd95b376a9}
```cpp
mavsdk::Geofence::Polygon::Polygon()
```


Constructor. Creates the [Polygon](structmavsdk_1_1_geofence_1_1_polygon.md) for a specific geometry.


### ~Polygon() {#structmavsdk_1_1_geofence_1_1_polygon_1ad54d6befd424528b3f627fc4106b310a}
```cpp
mavsdk::Geofence::Polygon::~Polygon()
```


Destructor (internal use only).


## Member Enumeration Documentation


### enum Type {#structmavsdk_1_1_geofence_1_1_polygon_1ac9024d1161de25e24d9b4ce290e0b5cd}


[Polygon](structmavsdk_1_1_geofence_1_1_polygon.md) Fence Types.

> **Note** MAVLink supports inclusion and exclusion polygon fences.

Value | Description
--- | ---
<span id="structmavsdk_1_1_geofence_1_1_polygon_1ac9024d1161de25e24d9b4ce290e0b5cdac63967050843bb454f786e4fd04e2b0a"></span> `INCLUSION` |  
<span id="structmavsdk_1_1_geofence_1_1_polygon_1ac9024d1161de25e24d9b4ce290e0b5cda22da1201928d1af020f468c483bafebc"></span> `EXCLUSION` |  

## Field Documentation


### points {#structmavsdk_1_1_geofence_1_1_polygon_1a0dd2c3824a7f3486583b95702f71b1d2}

```cpp
std::vector<Point> mavsdk::Geofence::Polygon::points
```


Vector of points that define the polygon.


### type {#structmavsdk_1_1_geofence_1_1_polygon_1a61814a15865a8406df8ce39dc3cbdf50}

```cpp
Type mavsdk::Geofence::Polygon::type
```


[Polygon](structmavsdk_1_1_geofence_1_1_polygon.md) fence type.

