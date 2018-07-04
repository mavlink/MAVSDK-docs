# dronecore::Camera::SettingOptions Struct Reference
`#include: camera.h`

----


Type to represent a setting with a list of options to choose from. 


## Data Fields


std::string [setting_id](#structdronecore_1_1_camera_1_1_setting_options_1a5435e328eeb84c23061cf0d212d23a2c)  -

std::vector< [Option](structdronecore_1_1_camera_1_1_option.md) > [options](#structdronecore_1_1_camera_1_1_setting_options_1ae6d3a8f91ea8bb7dab0526cbf546c6f7)  -


## Field Documentation


### setting_id {#structdronecore_1_1_camera_1_1_setting_options_1a5435e328eeb84c23061cf0d212d23a2c}

```cpp
std::string dronecore::Camera::SettingOptions::setting_id
```


Name of the setting (machine readable).

### options {#structdronecore_1_1_camera_1_1_setting_options_1ae6d3a8f91ea8bb7dab0526cbf546c6f7}

```cpp
std::vector<Option> dronecore::Camera::SettingOptions::options
```


List of options.