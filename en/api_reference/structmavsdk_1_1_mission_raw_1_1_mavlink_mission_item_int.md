# mavsdk::MissionRaw::MavlinkMissionItemInt Struct Reference
`#include: mission_raw.h`

----


[Mission](classmavsdk_1_1_mission.md) item identical to MAVLink MISSION_ITEM_INT. 


## Data Fields


uint8_t [target_system](#structmavsdk_1_1_mission_raw_1_1_mavlink_mission_item_int_1ac9afb40f51ad42223af1b47c8e37714e)  - [System](classmavsdk_1_1_system.md) ID.

uint8_t [target_component](#structmavsdk_1_1_mission_raw_1_1_mavlink_mission_item_int_1a460b9c0d349fb9fcdb1271b73da85c8b)  - Component ID.

uint16_t [seq](#structmavsdk_1_1_mission_raw_1_1_mavlink_mission_item_int_1a8eea1e2d0a79d1ae8f52823de7fc8ced)  - Sequence.

uint8_t [frame](#structmavsdk_1_1_mission_raw_1_1_mavlink_mission_item_int_1a47b9476fc12ba99440a98d944bcfb814)  - The coordinate system of the waypoint.

uint16_t [command](#structmavsdk_1_1_mission_raw_1_1_mavlink_mission_item_int_1a94a0a47417ebe93294a7b4975a716059)  - The scheduled action for the waypoint.

uint8_t [current](#structmavsdk_1_1_mission_raw_1_1_mavlink_mission_item_int_1a5a91b28c5732805e0835001dc7293194)  - false:0, true:1.

uint8_t [autocontinue](#structmavsdk_1_1_mission_raw_1_1_mavlink_mission_item_int_1aa9dea2af950f1b3db5056a1a2b627c28)  - Autocontinue to next waypoint.

float [param1](#structmavsdk_1_1_mission_raw_1_1_mavlink_mission_item_int_1ae6ff678e3b744bd12bc59dcb3adba64f)  - PARAM1, see MAV_CMD enum.

float [param2](#structmavsdk_1_1_mission_raw_1_1_mavlink_mission_item_int_1a9f6d462ab5ff1f85c5c5e88bab37b484)  - PARAM2, see MAV_CMD enum.

float [param3](#structmavsdk_1_1_mission_raw_1_1_mavlink_mission_item_int_1a5f69d9248881b6d7ad95adf1d6a99cee)  - PARAM3, see MAV_CMD enum.

float [param4](#structmavsdk_1_1_mission_raw_1_1_mavlink_mission_item_int_1a720e3cedce363d47b96e92c00c194417)  - PARAM4, see MAV_CMD enum.

int32_t [x](#structmavsdk_1_1_mission_raw_1_1_mavlink_mission_item_int_1ae2430e1edcdb06d256e6a5ed688bbfb0)  - PARAM5 / local: x position in meters * 1e4, global: latitude in degrees * 10^7.

int32_t [y](#structmavsdk_1_1_mission_raw_1_1_mavlink_mission_item_int_1a8b0925fba99555e1de0e370c396b079e)  - PARAM6 / y position: local: x position in meters * 1e4, global: longitude in degrees *10^7.

float [z](#structmavsdk_1_1_mission_raw_1_1_mavlink_mission_item_int_1aced56057e5edeacb132f151b06531435)  - PARAM7 / local: Z coordinate, global: altitude (relative or absolute, depending on frame).

uint8_t [mission_type](#structmavsdk_1_1_mission_raw_1_1_mavlink_mission_item_int_1a56c97f53c61d635de7d8e2351318a613)  - [Mission](classmavsdk_1_1_mission.md) type.


## Field Documentation


### target_system {#structmavsdk_1_1_mission_raw_1_1_mavlink_mission_item_int_1ac9afb40f51ad42223af1b47c8e37714e}

```cpp
uint8_t mavsdk::MissionRaw::MavlinkMissionItemInt::target_system
```


[System](classmavsdk_1_1_system.md) ID.


### target_component {#structmavsdk_1_1_mission_raw_1_1_mavlink_mission_item_int_1a460b9c0d349fb9fcdb1271b73da85c8b}

```cpp
uint8_t mavsdk::MissionRaw::MavlinkMissionItemInt::target_component
```


Component ID.


### seq {#structmavsdk_1_1_mission_raw_1_1_mavlink_mission_item_int_1a8eea1e2d0a79d1ae8f52823de7fc8ced}

```cpp
uint16_t mavsdk::MissionRaw::MavlinkMissionItemInt::seq
```


Sequence.


### frame {#structmavsdk_1_1_mission_raw_1_1_mavlink_mission_item_int_1a47b9476fc12ba99440a98d944bcfb814}

```cpp
uint8_t mavsdk::MissionRaw::MavlinkMissionItemInt::frame
```


The coordinate system of the waypoint.


### command {#structmavsdk_1_1_mission_raw_1_1_mavlink_mission_item_int_1a94a0a47417ebe93294a7b4975a716059}

```cpp
uint16_t mavsdk::MissionRaw::MavlinkMissionItemInt::command
```


The scheduled action for the waypoint.


### current {#structmavsdk_1_1_mission_raw_1_1_mavlink_mission_item_int_1a5a91b28c5732805e0835001dc7293194}

```cpp
uint8_t mavsdk::MissionRaw::MavlinkMissionItemInt::current
```


false:0, true:1.


### autocontinue {#structmavsdk_1_1_mission_raw_1_1_mavlink_mission_item_int_1aa9dea2af950f1b3db5056a1a2b627c28}

```cpp
uint8_t mavsdk::MissionRaw::MavlinkMissionItemInt::autocontinue
```


Autocontinue to next waypoint.


### param1 {#structmavsdk_1_1_mission_raw_1_1_mavlink_mission_item_int_1ae6ff678e3b744bd12bc59dcb3adba64f}

```cpp
float mavsdk::MissionRaw::MavlinkMissionItemInt::param1
```


PARAM1, see MAV_CMD enum.


### param2 {#structmavsdk_1_1_mission_raw_1_1_mavlink_mission_item_int_1a9f6d462ab5ff1f85c5c5e88bab37b484}

```cpp
float mavsdk::MissionRaw::MavlinkMissionItemInt::param2
```


PARAM2, see MAV_CMD enum.


### param3 {#structmavsdk_1_1_mission_raw_1_1_mavlink_mission_item_int_1a5f69d9248881b6d7ad95adf1d6a99cee}

```cpp
float mavsdk::MissionRaw::MavlinkMissionItemInt::param3
```


PARAM3, see MAV_CMD enum.


### param4 {#structmavsdk_1_1_mission_raw_1_1_mavlink_mission_item_int_1a720e3cedce363d47b96e92c00c194417}

```cpp
float mavsdk::MissionRaw::MavlinkMissionItemInt::param4
```


PARAM4, see MAV_CMD enum.


### x {#structmavsdk_1_1_mission_raw_1_1_mavlink_mission_item_int_1ae2430e1edcdb06d256e6a5ed688bbfb0}

```cpp
int32_t mavsdk::MissionRaw::MavlinkMissionItemInt::x
```


PARAM5 / local: x position in meters * 1e4, global: latitude in degrees * 10^7.


### y {#structmavsdk_1_1_mission_raw_1_1_mavlink_mission_item_int_1a8b0925fba99555e1de0e370c396b079e}

```cpp
int32_t mavsdk::MissionRaw::MavlinkMissionItemInt::y
```


PARAM6 / y position: local: x position in meters * 1e4, global: longitude in degrees *10^7.


### z {#structmavsdk_1_1_mission_raw_1_1_mavlink_mission_item_int_1aced56057e5edeacb132f151b06531435}

```cpp
float mavsdk::MissionRaw::MavlinkMissionItemInt::z
```


PARAM7 / local: Z coordinate, global: altitude (relative or absolute, depending on frame).


### mission_type {#structmavsdk_1_1_mission_raw_1_1_mavlink_mission_item_int_1a56c97f53c61d635de7d8e2351318a613}

```cpp
uint8_t mavsdk::MissionRaw::MavlinkMissionItemInt::mission_type
```


[Mission](classmavsdk_1_1_mission.md) type.

