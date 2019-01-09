# dronecode_sdk::Offboard::AttitudeRate Struct Reference
`#include: offboard.h`

----


Type for Attitude rate commands in body coordinates (roll, pitch, yaw angular rate and Thrust). 


## Data Fields


float [roll_deg_s](#structdronecode__sdk_1_1_offboard_1_1_attitude_rate_1adf12487b9838a01de8972ccfae16eebc)  - Roll Angular Rate in degrees/second (positive for clock-wise looking from front).

float [pitch_deg_s](#structdronecode__sdk_1_1_offboard_1_1_attitude_rate_1a9d79dbbec5e0ba78da68e35c9aedc4c5)  - Pitch Angular Rate in degrees/second (positive for head/front moving up).

float [yaw_deg_s](#structdronecode__sdk_1_1_offboard_1_1_attitude_rate_1a5ee297967837f709c79ece774c3cf565)  - Yaw Angular Rate in degrees/second (positive for clock-wise looking from above).

float [thrust_value](#structdronecode__sdk_1_1_offboard_1_1_attitude_rate_1a9b281aeb95060984f2942061e164b8d1)  - Thrust in percentage ranging from 0 to 1 ( 0 to 100 percent).


## Field Documentation


### roll_deg_s {#structdronecode__sdk_1_1_offboard_1_1_attitude_rate_1adf12487b9838a01de8972ccfae16eebc}

```cpp
float dronecode_sdk::Offboard::AttitudeRate::roll_deg_s
```


Roll Angular Rate in degrees/second (positive for clock-wise looking from front).


### pitch_deg_s {#structdronecode__sdk_1_1_offboard_1_1_attitude_rate_1a9d79dbbec5e0ba78da68e35c9aedc4c5}

```cpp
float dronecode_sdk::Offboard::AttitudeRate::pitch_deg_s
```


Pitch Angular Rate in degrees/second (positive for head/front moving up).


### yaw_deg_s {#structdronecode__sdk_1_1_offboard_1_1_attitude_rate_1a5ee297967837f709c79ece774c3cf565}

```cpp
float dronecode_sdk::Offboard::AttitudeRate::yaw_deg_s
```


Yaw Angular Rate in degrees/second (positive for clock-wise looking from above).


### thrust_value {#structdronecode__sdk_1_1_offboard_1_1_attitude_rate_1a9b281aeb95060984f2942061e164b8d1}

```cpp
float dronecode_sdk::Offboard::AttitudeRate::thrust_value
```


Thrust in percentage ranging from 0 to 1 ( 0 to 100 percent).

