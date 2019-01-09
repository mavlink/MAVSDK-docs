# dronecode_sdk::FollowMe::Config Struct Reference
`#include: follow_me.h`

----


[FollowMe](classdronecode__sdk_1_1_follow_me.md) Configuration. 


**See Also:**
- [get_config()](classdronecode__sdk_1_1_follow_me.md#classdronecode__sdk_1_1_follow_me_1a40a8d99cb9c34066db38586654d5b32b), [set_config()](classdronecode__sdk_1_1_follow_me.md#classdronecode__sdk_1_1_follow_me_1a45c5d737b18e89c1c5dd52d5606431a5)
- [Parameter Reference](https://docs.px4.io/en/advanced_config/parameter_reference.html#follow-target) (PX4 User Guide)


## Public Types


Type | Description
--- | ---
enum [FollowDirection](#structdronecode__sdk_1_1_follow_me_1_1_config_1a77e7606205b178a1b31acfd6ab76f48d) | Relative position of following vehicle.

## Data Fields


float [min_height_m](#structdronecode__sdk_1_1_follow_me_1_1_config_1a04473d0c0b80d2944a89af28c29a645a) = 8.0f - Min follow height, in meters.

float [follow_distance_m](#structdronecode__sdk_1_1_follow_me_1_1_config_1ac45a35ac4acdaca498ca8829f7667f02) = 8.0f - Horizontal follow distance to target, in meters.

[FollowDirection](structdronecode__sdk_1_1_follow_me_1_1_config.md#structdronecode__sdk_1_1_follow_me_1_1_config_1a77e7606205b178a1b31acfd6ab76f48d) [follow_direction](#structdronecode__sdk_1_1_follow_me_1_1_config_1aa74621aae52c82e5d33e54f921d85d52) = [FollowDirection::BEHIND](structdronecode__sdk_1_1_follow_me_1_1_config.md#structdronecode__sdk_1_1_follow_me_1_1_config_1a77e7606205b178a1b31acfd6ab76f48daef9c2aaa3392278b1fe2fa46124350a9) - Relative position of the following vehicle.

float [responsiveness](#structdronecode__sdk_1_1_follow_me_1_1_config_1a13d3ab3178f3855d5e2d07e43deae0cb) = 0.5f - Responsiveness, Range (0.0-1.0)

## Static Public Attributes


static constexpr const float [MIN_HEIGHT_M](#structdronecode__sdk_1_1_follow_me_1_1_config_1a769375cbc66745d775b693e02957fbfd) = 8.0f - Min follow height, in meters.


static constexpr const float [MIN_FOLLOW_DIST_M](#structdronecode__sdk_1_1_follow_me_1_1_config_1a9baca7ed2e61f44f559c2a12add1565a) = 1.0f - Min follow distance, in meters.


static constexpr const float [MIN_RESPONSIVENESS](#structdronecode__sdk_1_1_follow_me_1_1_config_1ab56eefec96397e9e053115395eee209e) = 0.f - Min responsiveness.


static constexpr const float [MAX_RESPONSIVENESS](#structdronecode__sdk_1_1_follow_me_1_1_config_1a42f4b2ec662b658681c963d9b01f053b) = 1.0f - Max responsiveness.


## Static Public Member Functions


Type | Name | Description
---: | --- | ---
std::string | [to_str](#structdronecode__sdk_1_1_follow_me_1_1_config_1abf9f71fba7447f25b9953d0c4fd64628) ([FollowDirection](structdronecode__sdk_1_1_follow_me_1_1_config.md#structdronecode__sdk_1_1_follow_me_1_1_config_1a77e7606205b178a1b31acfd6ab76f48d) direction) | Human-readable string for enum [FollowDirection](structdronecode__sdk_1_1_follow_me_1_1_config.md#structdronecode__sdk_1_1_follow_me_1_1_config_1a77e7606205b178a1b31acfd6ab76f48d).


## Member Enumeration Documentation


### enum FollowDirection {#structdronecode__sdk_1_1_follow_me_1_1_config_1a77e7606205b178a1b31acfd6ab76f48d}


Relative position of following vehicle.


Value | Description
--- | ---
<span id="structdronecode__sdk_1_1_follow_me_1_1_config_1a77e7606205b178a1b31acfd6ab76f48da3c590d7552bf5fa1953eb0f05c64acd5"></span> `FRONT_RIGHT` | Follow from front right. 
<span id="structdronecode__sdk_1_1_follow_me_1_1_config_1a77e7606205b178a1b31acfd6ab76f48daef9c2aaa3392278b1fe2fa46124350a9"></span> `BEHIND` | Follow from behind. 
<span id="structdronecode__sdk_1_1_follow_me_1_1_config_1a77e7606205b178a1b31acfd6ab76f48dabb2fe5c916efb43aab8cbb68f997d2ee"></span> `FRONT` | Follow from front. 
<span id="structdronecode__sdk_1_1_follow_me_1_1_config_1a77e7606205b178a1b31acfd6ab76f48da3c30649875f80bc4b253621e9cf4aa8e"></span> `FRONT_LEFT` | Follow from front left. 
<span id="structdronecode__sdk_1_1_follow_me_1_1_config_1a77e7606205b178a1b31acfd6ab76f48dab50339a10e1de285ac99d4c3990b8693"></span> `NONE` |  

**See Also:**
- [to_str()](structdronecode__sdk_1_1_follow_me_1_1_config.md#structdronecode__sdk_1_1_follow_me_1_1_config_1abf9f71fba7447f25b9953d0c4fd64628)


## Member Function Documentation


### to_str() {#structdronecode__sdk_1_1_follow_me_1_1_config_1abf9f71fba7447f25b9953d0c4fd64628}
```cpp
static std::string dronecode_sdk::FollowMe::Config::to_str(FollowDirection direction)
```


Human-readable string for enum [FollowDirection](structdronecode__sdk_1_1_follow_me_1_1_config.md#structdronecode__sdk_1_1_follow_me_1_1_config_1a77e7606205b178a1b31acfd6ab76f48d).


**Parameters**

* [FollowDirection](structdronecode__sdk_1_1_follow_me_1_1_config.md#structdronecode__sdk_1_1_follow_me_1_1_config_1a77e7606205b178a1b31acfd6ab76f48d) **direction** - Follow direction

**Returns**

&emsp;std::string - std::string representing given direction

## Field Documentation


### MIN_HEIGHT_M {#structdronecode__sdk_1_1_follow_me_1_1_config_1a769375cbc66745d775b693e02957fbfd}

```cpp
constexpr const float dronecode_sdk::FollowMe::Config::MIN_HEIGHT_M = 8.0f
```


Min follow height, in meters.


### MIN_FOLLOW_DIST_M {#structdronecode__sdk_1_1_follow_me_1_1_config_1a9baca7ed2e61f44f559c2a12add1565a}

```cpp
constexpr const float dronecode_sdk::FollowMe::Config::MIN_FOLLOW_DIST_M = 1.0f
```


Min follow distance, in meters.


### MIN_RESPONSIVENESS {#structdronecode__sdk_1_1_follow_me_1_1_config_1ab56eefec96397e9e053115395eee209e}

```cpp
constexpr const float dronecode_sdk::FollowMe::Config::MIN_RESPONSIVENESS = 0.f
```


Min responsiveness.


### MAX_RESPONSIVENESS {#structdronecode__sdk_1_1_follow_me_1_1_config_1a42f4b2ec662b658681c963d9b01f053b}

```cpp
constexpr const float dronecode_sdk::FollowMe::Config::MAX_RESPONSIVENESS = 1.0f
```


Max responsiveness.


### min_height_m {#structdronecode__sdk_1_1_follow_me_1_1_config_1a04473d0c0b80d2944a89af28c29a645a}

```cpp
float dronecode_sdk::FollowMe::Config::min_height_m = 8.0f
```


Min follow height, in meters.


### follow_distance_m {#structdronecode__sdk_1_1_follow_me_1_1_config_1ac45a35ac4acdaca498ca8829f7667f02}

```cpp
float dronecode_sdk::FollowMe::Config::follow_distance_m = 8.0f
```


Horizontal follow distance to target, in meters.


### follow_direction {#structdronecode__sdk_1_1_follow_me_1_1_config_1aa74621aae52c82e5d33e54f921d85d52}

```cpp
FollowDirection dronecode_sdk::FollowMe::Config::follow_direction = FollowDirection::BEHIND
```


Relative position of the following vehicle.


### responsiveness {#structdronecode__sdk_1_1_follow_me_1_1_config_1a13d3ab3178f3855d5e2d07e43deae0cb}

```cpp
float dronecode_sdk::FollowMe::Config::responsiveness = 0.5f
```


Responsiveness, Range (0.0-1.0)

