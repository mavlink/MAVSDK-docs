# mavsdk::FollowMe::Config Struct Reference
`#include: follow_me.h`

----


Configuration type. 


## Public Types


Type | Description
--- | ---
enum [FollowDirection](#structmavsdk_1_1_follow_me_1_1_config_1ab64f85fc0623306450866b943da9581f) | Direction relative to the target that the vehicle should follow.

## Data Fields


float [min_height_m](#structmavsdk_1_1_follow_me_1_1_config_1ac295180cfc4a22650c578bbdfa4d7a9f) {8.0} - Minimum height for the vehicle in meters (recommended minimum 8 meters)

float [follow_distance_m](#structmavsdk_1_1_follow_me_1_1_config_1a2f1407099516da129f650875e676a7eb) {8.0} - Distance from target for vehicle to follow in meters (recommended minimum 1 meter)

[FollowDirection](structmavsdk_1_1_follow_me_1_1_config.md#structmavsdk_1_1_follow_me_1_1_config_1ab64f85fc0623306450866b943da9581f) [follow_direction](#structmavsdk_1_1_follow_me_1_1_config_1a910ec3aa11abd18610bca4805ac72632) {} - Direction to follow in.

float [responsiveness](#structmavsdk_1_1_follow_me_1_1_config_1a3b0bced94506c4248cbaa9cc0894616a) {0.5} - How responsive the vehicle is to the motion of the target (range 0.0 to 1.0)


## Member Enumeration Documentation


### enum FollowDirection {#structmavsdk_1_1_follow_me_1_1_config_1ab64f85fc0623306450866b943da9581f}


Direction relative to the target that the vehicle should follow.


Value | Description
--- | ---
<span id="structmavsdk_1_1_follow_me_1_1_config_1ab64f85fc0623306450866b943da9581fa6adf97f83acf6453d4a6a4b1070f3754"></span> `None` | Do not follow. 
<span id="structmavsdk_1_1_follow_me_1_1_config_1ab64f85fc0623306450866b943da9581fa382c70faebc9dd21aff0801c33c5c4eb"></span> `Behind` | Follow from behind. 
<span id="structmavsdk_1_1_follow_me_1_1_config_1ab64f85fc0623306450866b943da9581fa5835bab1ade0060909e31a06af2e2cde"></span> `Front` | Follow from front. 
<span id="structmavsdk_1_1_follow_me_1_1_config_1ab64f85fc0623306450866b943da9581fa17a1a1897fa234ffd995f32ff31c4075"></span> `FrontRight` | Follow from front right. 
<span id="structmavsdk_1_1_follow_me_1_1_config_1ab64f85fc0623306450866b943da9581fa3a86c1ecef856c6360b14ee920abd2d4"></span> `FrontLeft` | Follow from front left. 

## Field Documentation


### min_height_m {#structmavsdk_1_1_follow_me_1_1_config_1ac295180cfc4a22650c578bbdfa4d7a9f}

```cpp
float mavsdk::FollowMe::Config::min_height_m {8.0}
```


Minimum height for the vehicle in meters (recommended minimum 8 meters)


### follow_distance_m {#structmavsdk_1_1_follow_me_1_1_config_1a2f1407099516da129f650875e676a7eb}

```cpp
float mavsdk::FollowMe::Config::follow_distance_m {8.0}
```


Distance from target for vehicle to follow in meters (recommended minimum 1 meter)


### follow_direction {#structmavsdk_1_1_follow_me_1_1_config_1a910ec3aa11abd18610bca4805ac72632}

```cpp
FollowDirection mavsdk::FollowMe::Config::follow_direction {}
```


Direction to follow in.


### responsiveness {#structmavsdk_1_1_follow_me_1_1_config_1a3b0bced94506c4248cbaa9cc0894616a}

```cpp
float mavsdk::FollowMe::Config::responsiveness {0.5}
```


How responsive the vehicle is to the motion of the target (range 0.0 to 1.0)

