# mavsdk::Camera::Setting Struct Reference
`#include: camera.h`

----


Type to represent a setting with a selected option. 


## Data Fields


std::string [setting_id](#structmavsdk_1_1_camera_1_1_setting_1a8dcb34e9a21bc0c72a38ff918d7d9efa) {} -

std::string [setting_description](#structmavsdk_1_1_camera_1_1_setting_1a6a86a6d058b991d6df42b881315ace6c) {} -

[Option](structmavsdk_1_1_camera_1_1_option.md) [option](#structmavsdk_1_1_camera_1_1_setting_1a7ae3fde46fe0446a52563e521ea3d3e7) {} -


## Field Documentation


### setting_id {#structmavsdk_1_1_camera_1_1_setting_1a8dcb34e9a21bc0c72a38ff918d7d9efa}

```cpp
std::string mavsdk::Camera::Setting::setting_id {}
```


Name of the setting (machine readable).

### setting_description {#structmavsdk_1_1_camera_1_1_setting_1a6a86a6d058b991d6df42b881315ace6c}

```cpp
std::string mavsdk::Camera::Setting::setting_description {}
```


Description of the setting (human readable).

### option {#structmavsdk_1_1_camera_1_1_setting_1a7ae3fde46fe0446a52563e521ea3d3e7}

```cpp
Option mavsdk::Camera::Setting::option {}
```


Selected option.