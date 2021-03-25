# mavsdk::Mavsdk::Configuration Class Reference
`#include: mavsdk.h`

----


Possible configurations. 


## Public Types


Type | Description
--- | ---
enum [UsageType](#classmavsdk_1_1_mavsdk_1_1_configuration_1a4426913e8669b94b9e88810c500482f8) | UsageTypes of configurations, used for automatic ID setting.

## Public Member Functions


Type | Name | Description
---: | --- | ---
&nbsp; | [Configuration](#classmavsdk_1_1_mavsdk_1_1_configuration_1a10477130d041107e76efd1f94e65b503) (uint8_t system_id, uint8_t component_id, bool always_send_heartbeats) | Create new [Configuration](classmavsdk_1_1_mavsdk_1_1_configuration.md) via manually configured system and component ID.
&nbsp; | [Configuration](#classmavsdk_1_1_mavsdk_1_1_configuration_1afe37b405647f2cdcd7d3e0f6661676e1) ([UsageType](classmavsdk_1_1_mavsdk_1_1_configuration.md#classmavsdk_1_1_mavsdk_1_1_configuration_1a4426913e8669b94b9e88810c500482f8) usage_type) | Create new [Configuration](classmavsdk_1_1_mavsdk_1_1_configuration.md) using a usage type. In this mode, the system and component ID will be automatically chosen.
&nbsp; | [Configuration](#classmavsdk_1_1_mavsdk_1_1_configuration_1a1a65e2e31f06bec1f6692a933c95b03c) ()=delete |
&nbsp; | [~Configuration](#classmavsdk_1_1_mavsdk_1_1_configuration_1a31cad2329ee14898752638d9c3759da9) ()=default |
uint8_t | [get_system_id](#classmavsdk_1_1_mavsdk_1_1_configuration_1a0497bdda816b674b1418ab07889ca781) () const | Get the system id of this configuration.
void | [set_system_id](#classmavsdk_1_1_mavsdk_1_1_configuration_1a28f495bce2cf89ca3c52bdfa938b1761) (uint8_t system_id) | Set the system id of this configuration.
uint8_t | [get_component_id](#classmavsdk_1_1_mavsdk_1_1_configuration_1adfcae3d5b6f047ad24d9c24983375e97) () const | Get the component id of this configuration.
void | [set_component_id](#classmavsdk_1_1_mavsdk_1_1_configuration_1aa590fbafa8ca104e1a004ca537f5798e) (uint8_t component_id) | Set the component id of this configuration.
bool | [get_always_send_heartbeats](#classmavsdk_1_1_mavsdk_1_1_configuration_1a0aa9008fe5a7498f374dbd2adad5f137) () const | Get whether to send heartbeats by default.
void | [set_always_send_heartbeats](#classmavsdk_1_1_mavsdk_1_1_configuration_1a0ad68b52763e205012b34faa5120a792) (bool always_send_heartbeats) | Set whether to send heartbeats by default.
[UsageType](classmavsdk_1_1_mavsdk_1_1_configuration.md#classmavsdk_1_1_mavsdk_1_1_configuration_1a4426913e8669b94b9e88810c500482f8) | [get_usage_type](#classmavsdk_1_1_mavsdk_1_1_configuration_1a7f2e657d2d86870ca07e1d0520f6c117) () const | Usage type of this configuration, used for automatic ID set.
void | [set_usage_type](#classmavsdk_1_1_mavsdk_1_1_configuration_1a7664dce33264446e4d2e8410d5e140c6) ([UsageType](classmavsdk_1_1_mavsdk_1_1_configuration.md#classmavsdk_1_1_mavsdk_1_1_configuration_1a4426913e8669b94b9e88810c500482f8) usage_type) | Set the usage type of this configuration.


## Constructor & Destructor Documentation


### Configuration() {#classmavsdk_1_1_mavsdk_1_1_configuration_1a10477130d041107e76efd1f94e65b503}
```cpp
mavsdk::Mavsdk::Configuration::Configuration(uint8_t system_id, uint8_t component_id, bool always_send_heartbeats)
```


Create new [Configuration](classmavsdk_1_1_mavsdk_1_1_configuration.md) via manually configured system and component ID.


**Parameters**

* uint8_t **system_id** - the system id to store in this configuration
* uint8_t **component_id** - the component id to store in this configuration
* bool **always_send_heartbeats** - send heartbeats by default even without a system connected

### Configuration() {#classmavsdk_1_1_mavsdk_1_1_configuration_1afe37b405647f2cdcd7d3e0f6661676e1}
```cpp
mavsdk::Mavsdk::Configuration::Configuration(UsageType usage_type)
```


Create new [Configuration](classmavsdk_1_1_mavsdk_1_1_configuration.md) using a usage type. In this mode, the system and component ID will be automatically chosen.


**Parameters**

* [UsageType](classmavsdk_1_1_mavsdk_1_1_configuration.md#classmavsdk_1_1_mavsdk_1_1_configuration_1a4426913e8669b94b9e88810c500482f8) **usage_type** - the usage type, used for automatically choosing ids.

### Configuration() {#classmavsdk_1_1_mavsdk_1_1_configuration_1a1a65e2e31f06bec1f6692a933c95b03c}
```cpp
mavsdk::Mavsdk::Configuration::Configuration()=delete
```


### ~Configuration() {#classmavsdk_1_1_mavsdk_1_1_configuration_1a31cad2329ee14898752638d9c3759da9}
```cpp
mavsdk::Mavsdk::Configuration::~Configuration()=default
```


## Member Enumeration Documentation


### enum UsageType {#classmavsdk_1_1_mavsdk_1_1_configuration_1a4426913e8669b94b9e88810c500482f8}


UsageTypes of configurations, used for automatic ID setting.


Value | Description
--- | ---
<span id="classmavsdk_1_1_mavsdk_1_1_configuration_1a4426913e8669b94b9e88810c500482f8a6ca1d2b081cc474f42cb95e3d04e6e68"></span> `Autopilot` | SDK is used as an autopilot. 
<span id="classmavsdk_1_1_mavsdk_1_1_configuration_1a4426913e8669b94b9e88810c500482f8af64f82089eddc6133add8c55c65d6687"></span> `GroundStation` | SDK is used as a ground station. 
<span id="classmavsdk_1_1_mavsdk_1_1_configuration_1a4426913e8669b94b9e88810c500482f8a8f2f82e1a7aa48819e9530d5c4977477"></span> `CompanionComputer` | SDK is used as a companion computer on board the MAV. 
<span id="classmavsdk_1_1_mavsdk_1_1_configuration_1a4426913e8669b94b9e88810c500482f8a90589c47f06eb971d548591f23c285af"></span> `Custom` | the SDK is used in a custom configuration, no automatic ID will be provided 

## Member Function Documentation


### get_system_id() {#classmavsdk_1_1_mavsdk_1_1_configuration_1a0497bdda816b674b1418ab07889ca781}
```cpp
uint8_t mavsdk::Mavsdk::Configuration::get_system_id() const
```


Get the system id of this configuration.


**Returns**

&emsp;uint8_t - `uint8_t` the system id stored in this configuration, from 1-255

### set_system_id() {#classmavsdk_1_1_mavsdk_1_1_configuration_1a28f495bce2cf89ca3c52bdfa938b1761}
```cpp
void mavsdk::Mavsdk::Configuration::set_system_id(uint8_t system_id)
```


Set the system id of this configuration.


**Parameters**

* uint8_t **system_id** - 

### get_component_id() {#classmavsdk_1_1_mavsdk_1_1_configuration_1adfcae3d5b6f047ad24d9c24983375e97}
```cpp
uint8_t mavsdk::Mavsdk::Configuration::get_component_id() const
```


Get the component id of this configuration.


**Returns**

&emsp;uint8_t - `uint8_t` the component id stored in this configuration,from 1-255

### set_component_id() {#classmavsdk_1_1_mavsdk_1_1_configuration_1aa590fbafa8ca104e1a004ca537f5798e}
```cpp
void mavsdk::Mavsdk::Configuration::set_component_id(uint8_t component_id)
```


Set the component id of this configuration.


**Parameters**

* uint8_t **component_id** - 

### get_always_send_heartbeats() {#classmavsdk_1_1_mavsdk_1_1_configuration_1a0aa9008fe5a7498f374dbd2adad5f137}
```cpp
bool mavsdk::Mavsdk::Configuration::get_always_send_heartbeats() const
```


Get whether to send heartbeats by default.


**Returns**

&emsp;bool - whether to always send heartbeats

### set_always_send_heartbeats() {#classmavsdk_1_1_mavsdk_1_1_configuration_1a0ad68b52763e205012b34faa5120a792}
```cpp
void mavsdk::Mavsdk::Configuration::set_always_send_heartbeats(bool always_send_heartbeats)
```


Set whether to send heartbeats by default.


**Parameters**

* bool **always_send_heartbeats** - 

### get_usage_type() {#classmavsdk_1_1_mavsdk_1_1_configuration_1a7f2e657d2d86870ca07e1d0520f6c117}
```cpp
UsageType mavsdk::Mavsdk::Configuration::get_usage_type() const
```


Usage type of this configuration, used for automatic ID set.


**Returns**

&emsp;[UsageType](classmavsdk_1_1_mavsdk_1_1_configuration.md#classmavsdk_1_1_mavsdk_1_1_configuration_1a4426913e8669b94b9e88810c500482f8) - 

### set_usage_type() {#classmavsdk_1_1_mavsdk_1_1_configuration_1a7664dce33264446e4d2e8410d5e140c6}
```cpp
void mavsdk::Mavsdk::Configuration::set_usage_type(UsageType usage_type)
```


Set the usage type of this configuration.


**Parameters**

* [UsageType](classmavsdk_1_1_mavsdk_1_1_configuration.md#classmavsdk_1_1_mavsdk_1_1_configuration_1a4426913e8669b94b9e88810c500482f8) **usage_type** - 