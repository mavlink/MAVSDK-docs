# mavsdk::FollowMe::Config Struct Reference
`#include: follow_me.h`

----


[FollowMe](classmavsdk_1_1_follow_me.md) Configuration. 


**See Also:**
- [get_config()](classmavsdk_1_1_follow_me.md#classmavsdk_1_1_follow_me_1ae952cb2adeeacabcf7942fb12e0aa14f), [set_config()](classmavsdk_1_1_follow_me.md#classmavsdk_1_1_follow_me_1a1d7c0e5598769365aeaec8026578a977)
- [Parameter Reference](https://docs.px4.io/en/advanced_config/parameter_reference.html#follow-target) (PX4 User Guide)


## Public Types


Type | Description
--- | ---
enum [FollowDirection](#structmavsdk_1_1_follow_me_1_1_config_1ab64f85fc0623306450866b943da9581f) | Relative position of following vehicle.

## Data Fields


float [min_height_m](#structmavsdk_1_1_follow_me_1_1_config_1ac295180cfc4a22650c578bbdfa4d7a9f) = 8.0f - Min follow height, in meters.

float [follow_distance_m](#structmavsdk_1_1_follow_me_1_1_config_1a2f1407099516da129f650875e676a7eb) = 8.0f - Horizontal follow distance to target, in meters.

[FollowDirection](structmavsdk_1_1_follow_me_1_1_config.md#structmavsdk_1_1_follow_me_1_1_config_1ab64f85fc0623306450866b943da9581f) [follow_direction](#structmavsdk_1_1_follow_me_1_1_config_1a910ec3aa11abd18610bca4805ac72632) = [FollowDirection::BEHIND](structmavsdk_1_1_follow_me_1_1_config.md#structmavsdk_1_1_follow_me_1_1_config_1ab64f85fc0623306450866b943da9581faef9c2aaa3392278b1fe2fa46124350a9) - Relative position of the following vehicle.

float [responsiveness](#structmavsdk_1_1_follow_me_1_1_config_1a3b0bced94506c4248cbaa9cc0894616a) = 0.5f - Responsiveness, Range (0.0-1.0)

## Static Public Attributes


static constexpr const float [MIN_HEIGHT_M](#structmavsdk_1_1_follow_me_1_1_config_1a6ad0a9ac5a55f4f041e03d2cb9c31dd4) = 8.0f - Min follow height, in meters.


static constexpr const float [MIN_FOLLOW_DIST_M](#structmavsdk_1_1_follow_me_1_1_config_1a342f740394845a8b9a9df16826e75294) = 1.0f - Min follow distance, in meters.


static constexpr const float [MIN_RESPONSIVENESS](#structmavsdk_1_1_follow_me_1_1_config_1aa89d4f33313d1a257e8563c781106145) = 0.f - Min responsiveness.


static constexpr const float [MAX_RESPONSIVENESS](#structmavsdk_1_1_follow_me_1_1_config_1a7e5f8f1d22be2a66297693cbbc8da892) = 1.0f - Max responsiveness.


## Static Public Member Functions


Type | Name | Description
---: | --- | ---
std::string | [to_str](#structmavsdk_1_1_follow_me_1_1_config_1a39e31ef21612508ad679a1d3997292db) ([FollowDirection](structmavsdk_1_1_follow_me_1_1_config.md#structmavsdk_1_1_follow_me_1_1_config_1ab64f85fc0623306450866b943da9581f) direction) | Human-readable string for enum [FollowDirection](structmavsdk_1_1_follow_me_1_1_config.md#structmavsdk_1_1_follow_me_1_1_config_1ab64f85fc0623306450866b943da9581f).


## Member Enumeration Documentation


### enum FollowDirection {#structmavsdk_1_1_follow_me_1_1_config_1ab64f85fc0623306450866b943da9581f}


Relative position of following vehicle.


Value | Description
--- | ---
<span id="structmavsdk_1_1_follow_me_1_1_config_1ab64f85fc0623306450866b943da9581fa3c590d7552bf5fa1953eb0f05c64acd5"></span> `FRONT_RIGHT` | Follow from front right. 
<span id="structmavsdk_1_1_follow_me_1_1_config_1ab64f85fc0623306450866b943da9581faef9c2aaa3392278b1fe2fa46124350a9"></span> `BEHIND` | Follow from behind. 
<span id="structmavsdk_1_1_follow_me_1_1_config_1ab64f85fc0623306450866b943da9581fabb2fe5c916efb43aab8cbb68f997d2ee"></span> `FRONT` | Follow from front. 
<span id="structmavsdk_1_1_follow_me_1_1_config_1ab64f85fc0623306450866b943da9581fa3c30649875f80bc4b253621e9cf4aa8e"></span> `FRONT_LEFT` | Follow from front left. 
<span id="structmavsdk_1_1_follow_me_1_1_config_1ab64f85fc0623306450866b943da9581fab50339a10e1de285ac99d4c3990b8693"></span> `NONE` |  

**See Also:**
- [to_str()](structmavsdk_1_1_follow_me_1_1_config.md#structmavsdk_1_1_follow_me_1_1_config_1a39e31ef21612508ad679a1d3997292db)


## Member Function Documentation


### to_str() {#structmavsdk_1_1_follow_me_1_1_config_1a39e31ef21612508ad679a1d3997292db}
```cpp
static std::string mavsdk::FollowMe::Config::to_str(FollowDirection direction)
```


Human-readable string for enum [FollowDirection](structmavsdk_1_1_follow_me_1_1_config.md#structmavsdk_1_1_follow_me_1_1_config_1ab64f85fc0623306450866b943da9581f).


**Parameters**

* [FollowDirection](structmavsdk_1_1_follow_me_1_1_config.md#structmavsdk_1_1_follow_me_1_1_config_1ab64f85fc0623306450866b943da9581f) **direction** - Follow direction

**Returns**

&emsp;std::string - std::string representing given direction

## Field Documentation


### MIN_HEIGHT_M {#structmavsdk_1_1_follow_me_1_1_config_1a6ad0a9ac5a55f4f041e03d2cb9c31dd4}

```cpp
constexpr const float mavsdk::FollowMe::Config::MIN_HEIGHT_M = 8.0f
```


Min follow height, in meters.


### MIN_FOLLOW_DIST_M {#structmavsdk_1_1_follow_me_1_1_config_1a342f740394845a8b9a9df16826e75294}

```cpp
constexpr const float mavsdk::FollowMe::Config::MIN_FOLLOW_DIST_M = 1.0f
```


Min follow distance, in meters.


### MIN_RESPONSIVENESS {#structmavsdk_1_1_follow_me_1_1_config_1aa89d4f33313d1a257e8563c781106145}

```cpp
constexpr const float mavsdk::FollowMe::Config::MIN_RESPONSIVENESS = 0.f
```


Min responsiveness.


### MAX_RESPONSIVENESS {#structmavsdk_1_1_follow_me_1_1_config_1a7e5f8f1d22be2a66297693cbbc8da892}

```cpp
constexpr const float mavsdk::FollowMe::Config::MAX_RESPONSIVENESS = 1.0f
```


Max responsiveness.


### min_height_m {#structmavsdk_1_1_follow_me_1_1_config_1ac295180cfc4a22650c578bbdfa4d7a9f}

```cpp
float mavsdk::FollowMe::Config::min_height_m = 8.0f
```


Min follow height, in meters.


### follow_distance_m {#structmavsdk_1_1_follow_me_1_1_config_1a2f1407099516da129f650875e676a7eb}

```cpp
float mavsdk::FollowMe::Config::follow_distance_m = 8.0f
```


Horizontal follow distance to target, in meters.


### follow_direction {#structmavsdk_1_1_follow_me_1_1_config_1a910ec3aa11abd18610bca4805ac72632}

```cpp
FollowDirection mavsdk::FollowMe::Config::follow_direction = FollowDirection::BEHIND
```


Relative position of the following vehicle.


### responsiveness {#structmavsdk_1_1_follow_me_1_1_config_1a3b0bced94506c4248cbaa9cc0894616a}

```cpp
float mavsdk::FollowMe::Config::responsiveness = 0.5f
```


Responsiveness, Range (0.0-1.0)

