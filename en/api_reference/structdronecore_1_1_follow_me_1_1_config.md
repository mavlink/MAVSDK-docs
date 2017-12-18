# dronecore::FollowMe::Config Struct Reference
`#include: follow_me.h`

----


[FollowMe](classdronecore_1_1_follow_me.md) Configuration. 


**See Also:**
- [get_config()](classdronecore_1_1_follow_me.md#classdronecore_1_1_follow_me_1a054aebafe0839a1028f277285b769fe5), [set_config()](classdronecore_1_1_follow_me.md#classdronecore_1_1_follow_me_1aedf746d4a0eebdaaddc3d1ba0aeb6720)
- [Parameter Reference](https://docs.px4.io/en/advanced_config/parameter_reference.html#follow-target) (PX4 User Guide)


## Public Types


Type | Description
--- | ---
enum [FollowDirection](#structdronecore_1_1_follow_me_1_1_config_1a048f9f74309c17027c37eadc4dcb2c1a) | Relative position of following vehicle.

## Data Fields


float [min_height_m](#structdronecore_1_1_follow_me_1_1_config_1a62c100d4dc35e3731f3b5d62fb5baad9) = 8.0f - Min follow height, in meters.

float [follow_dist_m](#structdronecore_1_1_follow_me_1_1_config_1ab0e453d6b18cf602548cd63636b103ea) = 8.0f - Horizontal follow distance to target, in meters.

[FollowDirection](structdronecore_1_1_follow_me_1_1_config.md#structdronecore_1_1_follow_me_1_1_config_1a048f9f74309c17027c37eadc4dcb2c1a) [follow_direction](#structdronecore_1_1_follow_me_1_1_config_1a920f7acca4b5e717c9ead1bb89f9d538) = [FollowDirection::BEHIND](structdronecore_1_1_follow_me_1_1_config.md#structdronecore_1_1_follow_me_1_1_config_1a048f9f74309c17027c37eadc4dcb2c1aaef9c2aaa3392278b1fe2fa46124350a9) - Relative position of the following vehicle.

float [responsiveness](#structdronecore_1_1_follow_me_1_1_config_1a836c1179788d24861642bb45b28dc7fe) = 0.5f - Responsiveness, Range (0.0-1.0)

## Static Public Attributes


static constexpr const float [MIN_HEIGHT_M](#structdronecore_1_1_follow_me_1_1_config_1a4bc3dee9ca74031a3ac1a8dea2df12d4) = 8.0f - Min follow height, in meters.


static constexpr const float [MIN_FOLLOW_DIST_M](#structdronecore_1_1_follow_me_1_1_config_1a92f039f840aa3adad740fe048697ce9f) = 1.0f - Min follow distance, in meters.


static constexpr const float [MIN_RESPONSIVENESS](#structdronecore_1_1_follow_me_1_1_config_1ac73d36213f4ac6505ec2d44ad4fd2b4e) = 0.f - Min responsiveness.


static constexpr const float [MAX_RESPONSIVENESS](#structdronecore_1_1_follow_me_1_1_config_1afcdf2d6e55dd9da59a05fb5dbcbeab49) = 1.0f - Max responsiveness.


## Static Public Member Functions


Type | Name | Description
---: | --- | ---
std::string | [to_str](#structdronecore_1_1_follow_me_1_1_config_1a025a841e75b66541ef029d8f837886ad) (FollowDirection direction) | Human-readable string for enum [FollowDirection](structdronecore_1_1_follow_me_1_1_config.md#structdronecore_1_1_follow_me_1_1_config_1a048f9f74309c17027c37eadc4dcb2c1a).


## Member Enumeration Documentation


### enum FollowDirection {#structdronecore_1_1_follow_me_1_1_config_1a048f9f74309c17027c37eadc4dcb2c1a}


Relative position of following vehicle.


Value | Description
--- | ---
<span id="structdronecore_1_1_follow_me_1_1_config_1a048f9f74309c17027c37eadc4dcb2c1aa3c590d7552bf5fa1953eb0f05c64acd5"></span> `FRONT_RIGHT` | Follow from front right. 
<span id="structdronecore_1_1_follow_me_1_1_config_1a048f9f74309c17027c37eadc4dcb2c1aaef9c2aaa3392278b1fe2fa46124350a9"></span> `BEHIND` | Follow from behind. 
<span id="structdronecore_1_1_follow_me_1_1_config_1a048f9f74309c17027c37eadc4dcb2c1aabb2fe5c916efb43aab8cbb68f997d2ee"></span> `FRONT` | Follow from front. 
<span id="structdronecore_1_1_follow_me_1_1_config_1a048f9f74309c17027c37eadc4dcb2c1aa3c30649875f80bc4b253621e9cf4aa8e"></span> `FRONT_LEFT` | Follow from front left. 
<span id="structdronecore_1_1_follow_me_1_1_config_1a048f9f74309c17027c37eadc4dcb2c1aab50339a10e1de285ac99d4c3990b8693"></span> `NONE` |  

**See Also:**
- [to_str()](structdronecore_1_1_follow_me_1_1_config.md#structdronecore_1_1_follow_me_1_1_config_1a025a841e75b66541ef029d8f837886ad)


## Member Function Documentation


### to_str() {#structdronecore_1_1_follow_me_1_1_config_1a025a841e75b66541ef029d8f837886ad}
```cpp
static std::string dronecore::FollowMe::Config::to_str(FollowDirection direction)
```


Human-readable string for enum [FollowDirection](structdronecore_1_1_follow_me_1_1_config.md#structdronecore_1_1_follow_me_1_1_config_1a048f9f74309c17027c37eadc4dcb2c1a).


**Parameters**

* [FollowDirection](structdronecore_1_1_follow_me_1_1_config.md#structdronecore_1_1_follow_me_1_1_config_1a048f9f74309c17027c37eadc4dcb2c1a) **direction** - Follow direction

**Returns**

&emsp;std::string - std::string representing given direction

## Field Documentation


### MIN_HEIGHT_M {#structdronecore_1_1_follow_me_1_1_config_1a4bc3dee9ca74031a3ac1a8dea2df12d4}

```cpp
constexpr const float dronecore::FollowMe::Config::MIN_HEIGHT_M
```


Min follow height, in meters.


### MIN_FOLLOW_DIST_M {#structdronecore_1_1_follow_me_1_1_config_1a92f039f840aa3adad740fe048697ce9f}

```cpp
constexpr const float dronecore::FollowMe::Config::MIN_FOLLOW_DIST_M
```


Min follow distance, in meters.


### MIN_RESPONSIVENESS {#structdronecore_1_1_follow_me_1_1_config_1ac73d36213f4ac6505ec2d44ad4fd2b4e}

```cpp
constexpr const float dronecore::FollowMe::Config::MIN_RESPONSIVENESS
```


Min responsiveness.


### MAX_RESPONSIVENESS {#structdronecore_1_1_follow_me_1_1_config_1afcdf2d6e55dd9da59a05fb5dbcbeab49}

```cpp
constexpr const float dronecore::FollowMe::Config::MAX_RESPONSIVENESS
```


Max responsiveness.


### min_height_m {#structdronecore_1_1_follow_me_1_1_config_1a62c100d4dc35e3731f3b5d62fb5baad9}

```cpp
float dronecore::FollowMe::Config::min_height_m
```


Min follow height, in meters.


### follow_dist_m {#structdronecore_1_1_follow_me_1_1_config_1ab0e453d6b18cf602548cd63636b103ea}

```cpp
float dronecore::FollowMe::Config::follow_dist_m
```


Horizontal follow distance to target, in meters.


### follow_direction {#structdronecore_1_1_follow_me_1_1_config_1a920f7acca4b5e717c9ead1bb89f9d538}

```cpp
FollowDirection dronecore::FollowMe::Config::follow_direction= FollowDirection::BEHIND
```


Relative position of the following vehicle.


### responsiveness {#structdronecore_1_1_follow_me_1_1_config_1a836c1179788d24861642bb45b28dc7fe}

```cpp
float dronecore::FollowMe::Config::responsiveness
```


Responsiveness, Range (0.0-1.0)

