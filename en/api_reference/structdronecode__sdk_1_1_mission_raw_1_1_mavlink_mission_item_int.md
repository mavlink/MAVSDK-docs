# dronecode_sdk::MissionRaw::MavlinkMissionItemInt Struct Reference
`#include: mission_raw.h`

----


[Mission](classdronecode__sdk_1_1_mission.md) item identical to MAVLink MISSION_ITEM_INT. 


## Data Fields


uint8_t [target_system](#structdronecode__sdk_1_1_mission_raw_1_1_mavlink_mission_item_int_1ab0e9b06482dc0a3aa7b67608cc84d4e4)  - [System](classdronecode__sdk_1_1_system.md) ID.

uint8_t [target_component](#structdronecode__sdk_1_1_mission_raw_1_1_mavlink_mission_item_int_1af77fe0f745028ccea610ac5106c57693)  - Component ID.

uint16_t [seq](#structdronecode__sdk_1_1_mission_raw_1_1_mavlink_mission_item_int_1a33b475db6cf87b406526545177cfdfcf)  - Sequence.

uint8_t [frame](#structdronecode__sdk_1_1_mission_raw_1_1_mavlink_mission_item_int_1af53e9214fb46fa7ca6677f17fa09bab0)  - The coordinate system of the waypoint.

uint16_t [command](#structdronecode__sdk_1_1_mission_raw_1_1_mavlink_mission_item_int_1a04b9785a5167b4e11816e72bc9b50721)  - The scheduled action for the waypoint.

uint8_t [current](#structdronecode__sdk_1_1_mission_raw_1_1_mavlink_mission_item_int_1a6a664f9cda68d9aba7d37fd491fb3481)  - false:0, true:1.

uint8_t [autocontinue](#structdronecode__sdk_1_1_mission_raw_1_1_mavlink_mission_item_int_1a8187c59750f3ef5ee599d762506611df)  - Autocontinue to next waypoint.

float [param1](#structdronecode__sdk_1_1_mission_raw_1_1_mavlink_mission_item_int_1a71fed8b04ad7b2c908a44b7f0451c319)  - PARAM1, see MAV_CMD enum.

float [param2](#structdronecode__sdk_1_1_mission_raw_1_1_mavlink_mission_item_int_1adb82514059307715f78948ff79b0591e)  - PARAM2, see MAV_CMD enum.

float [param3](#structdronecode__sdk_1_1_mission_raw_1_1_mavlink_mission_item_int_1ab96f8cf0229fa6f7e209541692eee491)  - PARAM3, see MAV_CMD enum.

float [param4](#structdronecode__sdk_1_1_mission_raw_1_1_mavlink_mission_item_int_1a942dbfc9faf8a04ec2aa215f56b5449d)  - PARAM4, see MAV_CMD enum.

int32_t [x](#structdronecode__sdk_1_1_mission_raw_1_1_mavlink_mission_item_int_1a69af31129361de2e6665b560010a0fc4)  - PARAM5 / local: x position in meters * 1e4, global: latitude in degrees * 10^7.

int32_t [y](#structdronecode__sdk_1_1_mission_raw_1_1_mavlink_mission_item_int_1aeb0d1b8cc357fb998d7b267f0c4cca1a)  - PARAM6 / y position: local: x position in meters * 1e4, global: longitude in degrees *10^7.

float [z](#structdronecode__sdk_1_1_mission_raw_1_1_mavlink_mission_item_int_1ab69dffe40e8501802eb9f4cd4530de40)  - PARAM7 / local: Z coordinate, global: altitude (relative or absolute, depending on frame).

uint8_t [mission_type](#structdronecode__sdk_1_1_mission_raw_1_1_mavlink_mission_item_int_1aaf17fb795b7dae60cd2fb12f19a054c3)  - [Mission](classdronecode__sdk_1_1_mission.md) type.


## Field Documentation


### target_system {#structdronecode__sdk_1_1_mission_raw_1_1_mavlink_mission_item_int_1ab0e9b06482dc0a3aa7b67608cc84d4e4}

```cpp
uint8_t dronecode_sdk::MissionRaw::MavlinkMissionItemInt::target_system
```


[System](classdronecode__sdk_1_1_system.md) ID.


### target_component {#structdronecode__sdk_1_1_mission_raw_1_1_mavlink_mission_item_int_1af77fe0f745028ccea610ac5106c57693}

```cpp
uint8_t dronecode_sdk::MissionRaw::MavlinkMissionItemInt::target_component
```


Component ID.


### seq {#structdronecode__sdk_1_1_mission_raw_1_1_mavlink_mission_item_int_1a33b475db6cf87b406526545177cfdfcf}

```cpp
uint16_t dronecode_sdk::MissionRaw::MavlinkMissionItemInt::seq
```


Sequence.


### frame {#structdronecode__sdk_1_1_mission_raw_1_1_mavlink_mission_item_int_1af53e9214fb46fa7ca6677f17fa09bab0}

```cpp
uint8_t dronecode_sdk::MissionRaw::MavlinkMissionItemInt::frame
```


The coordinate system of the waypoint.


### command {#structdronecode__sdk_1_1_mission_raw_1_1_mavlink_mission_item_int_1a04b9785a5167b4e11816e72bc9b50721}

```cpp
uint16_t dronecode_sdk::MissionRaw::MavlinkMissionItemInt::command
```


The scheduled action for the waypoint.


### current {#structdronecode__sdk_1_1_mission_raw_1_1_mavlink_mission_item_int_1a6a664f9cda68d9aba7d37fd491fb3481}

```cpp
uint8_t dronecode_sdk::MissionRaw::MavlinkMissionItemInt::current
```


false:0, true:1.


### autocontinue {#structdronecode__sdk_1_1_mission_raw_1_1_mavlink_mission_item_int_1a8187c59750f3ef5ee599d762506611df}

```cpp
uint8_t dronecode_sdk::MissionRaw::MavlinkMissionItemInt::autocontinue
```


Autocontinue to next waypoint.


### param1 {#structdronecode__sdk_1_1_mission_raw_1_1_mavlink_mission_item_int_1a71fed8b04ad7b2c908a44b7f0451c319}

```cpp
float dronecode_sdk::MissionRaw::MavlinkMissionItemInt::param1
```


PARAM1, see MAV_CMD enum.


### param2 {#structdronecode__sdk_1_1_mission_raw_1_1_mavlink_mission_item_int_1adb82514059307715f78948ff79b0591e}

```cpp
float dronecode_sdk::MissionRaw::MavlinkMissionItemInt::param2
```


PARAM2, see MAV_CMD enum.


### param3 {#structdronecode__sdk_1_1_mission_raw_1_1_mavlink_mission_item_int_1ab96f8cf0229fa6f7e209541692eee491}

```cpp
float dronecode_sdk::MissionRaw::MavlinkMissionItemInt::param3
```


PARAM3, see MAV_CMD enum.


### param4 {#structdronecode__sdk_1_1_mission_raw_1_1_mavlink_mission_item_int_1a942dbfc9faf8a04ec2aa215f56b5449d}

```cpp
float dronecode_sdk::MissionRaw::MavlinkMissionItemInt::param4
```


PARAM4, see MAV_CMD enum.


### x {#structdronecode__sdk_1_1_mission_raw_1_1_mavlink_mission_item_int_1a69af31129361de2e6665b560010a0fc4}

```cpp
int32_t dronecode_sdk::MissionRaw::MavlinkMissionItemInt::x
```


PARAM5 / local: x position in meters * 1e4, global: latitude in degrees * 10^7.


### y {#structdronecode__sdk_1_1_mission_raw_1_1_mavlink_mission_item_int_1aeb0d1b8cc357fb998d7b267f0c4cca1a}

```cpp
int32_t dronecode_sdk::MissionRaw::MavlinkMissionItemInt::y
```


PARAM6 / y position: local: x position in meters * 1e4, global: longitude in degrees *10^7.


### z {#structdronecode__sdk_1_1_mission_raw_1_1_mavlink_mission_item_int_1ab69dffe40e8501802eb9f4cd4530de40}

```cpp
float dronecode_sdk::MissionRaw::MavlinkMissionItemInt::z
```


PARAM7 / local: Z coordinate, global: altitude (relative or absolute, depending on frame).


### mission_type {#structdronecode__sdk_1_1_mission_raw_1_1_mavlink_mission_item_int_1aaf17fb795b7dae60cd2fb12f19a054c3}

```cpp
uint8_t dronecode_sdk::MissionRaw::MavlinkMissionItemInt::mission_type
```


[Mission](classdronecode__sdk_1_1_mission.md) type.

