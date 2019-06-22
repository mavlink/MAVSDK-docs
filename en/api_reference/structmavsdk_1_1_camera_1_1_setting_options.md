# mavsdk::Camera::SettingOptions Struct Reference
`#include: camera.h`

----


Type to represent a setting with a list of options to choose from. 


## Data Fields


std::string [setting_id](#structmavsdk_1_1_camera_1_1_setting_options_1aca647af6e140ee78b41d85565d673f14) {} -

std::string [setting_description](#structmavsdk_1_1_camera_1_1_setting_options_1a8902e7f9dfc25ee9c8363cf5f4775b92) {} -

std::vector< [Option](structmavsdk_1_1_camera_1_1_option.md) > [options](#structmavsdk_1_1_camera_1_1_setting_options_1a06b292df50c638625ef942b1a19917c3) {} -


## Field Documentation


### setting_id {#structmavsdk_1_1_camera_1_1_setting_options_1aca647af6e140ee78b41d85565d673f14}

```cpp
std::string mavsdk::Camera::SettingOptions::setting_id {}
```


Name of the setting (machine readable).

### setting_description {#structmavsdk_1_1_camera_1_1_setting_options_1a8902e7f9dfc25ee9c8363cf5f4775b92}

```cpp
std::string mavsdk::Camera::SettingOptions::setting_description {}
```


Description of the setting (human readable).

### options {#structmavsdk_1_1_camera_1_1_setting_options_1a06b292df50c638625ef942b1a19917c3}

```cpp
std::vector<Option> mavsdk::Camera::SettingOptions::options {}
```


List of options.