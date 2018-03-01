# dronecore::Device Class Reference
`#include: UNKNOWN`

----


## Data Structures


struct [MavlinkHandlerTableEntry](structdronecore_1_1_device_1_1_mavlink_handler_table_entry.md)

## Public Types


Type | Description
--- | ---
enum [FlightMode](#classdronecore_1_1_device_1abe2b638e92f46ad3bdc124429a5929e8) | 
std::function< void(const mavlink_message_t &)> [mavlink_message_handler_t](#classdronecore_1_1_device_1a1bca06c484ee8a4f18f0371a2a492e7b) | 
std::function< void(MavlinkCommands::Result, float)> [command_result_callback_t](#classdronecore_1_1_device_1a6ee9b5b6b3d40554ced23537168d801e) | 
std::function< void(bool success)> [success_t](#classdronecore_1_1_device_1aa90d45a543d894492d30618438e5ced4) | 
std::function< void(bool success, float value)> [get_param_float_callback_t](#classdronecore_1_1_device_1a8eabc97aec9a0ac69f79df2caabd8687) | 
std::function< void(bool success, int32_t value)> [get_param_int_callback_t](#classdronecore_1_1_device_1a38ead6807abd7c8d72a8cf3909b4560d) | 

## Public Member Functions


Type | Name | Description
---: | --- | ---
&nbsp; | [Device](#classdronecore_1_1_device_1af07b4defa38736ce928377af2f31fb6e) (DroneCoreImpl * parent, uint8_t target_system_id) |
&nbsp; | [~Device](#classdronecore_1_1_device_1a65c697e12eed30109074e18a9cfdc836) () |
&nbsp; | [Device](#classdronecore_1_1_device_1acf95b02d5d1d705ce3dc1438786e0c91) (const [Device](classdronecore_1_1_device.md) &)=delete |
void | [process_mavlink_message](#classdronecore_1_1_device_1a7324f5f4cc1f7bce40a2e8c237f1212e) (const mavlink_message_t & message) |
void | [register_mavlink_message_handler](#classdronecore_1_1_device_1aa7ae3afa910a2043185e319cfaaa4196) (uint16_t msg_id, mavlink_message_handler_t callback, const void * cookie) |
void | [unregister_all_mavlink_message_handlers](#classdronecore_1_1_device_1a7fd2014818f2e41cc93b6c31d259f21c) (const void * cookie) |
void | [register_timeout_handler](#classdronecore_1_1_device_1afc704e09b8331cdd36341a1ffd331c11) (std::function< void()> callback, double duration_s, void ** cookie) |
void | [refresh_timeout_handler](#classdronecore_1_1_device_1ad7d945426276c079ffc9d173583d1427) (const void * cookie) |
void | [unregister_timeout_handler](#classdronecore_1_1_device_1a95673878b3a69db3817def10310a565d) (const void * cookie) |
void | [add_call_every](#classdronecore_1_1_device_1a466bede03fdf9be31cefb206ef561114) (std::function< void()> callback, float interval_s, void ** cookie) |
void | [change_call_every](#classdronecore_1_1_device_1aed059a1d5a9f2ee4e11963e5d371577c) (float interval_s, const void * cookie) |
void | [reset_call_every](#classdronecore_1_1_device_1a38c719f6ccadf6a17e61c47c14cdf234) (const void * cookie) |
void | [remove_call_every](#classdronecore_1_1_device_1a5a101b41ec651a6a764a01d3208934e2) (const void * cookie) |
bool | [send_message](#classdronecore_1_1_device_1a9d09cd1b8b9689080337f7efd9e9d77d) (const mavlink_message_t & message) |
MavlinkCommands::Result | [send_command_with_ack](#classdronecore_1_1_device_1afcc8c11d47f681c41705d82ee3cd74ea) (uint16_t command, const MavlinkCommands::Params & params, uint8_t component_id=0) |
void | [send_command_with_ack_async](#classdronecore_1_1_device_1a0ef6cf5c11820fb2ae00bd96f9abd4de) (uint16_t command, const MavlinkCommands::Params & params, command_result_callback_t callback, uint8_t component_id=0) |
MavlinkCommands::Result | [set_msg_rate](#classdronecore_1_1_device_1af10ca5a146f0129c51566486a20d98ed) (uint16_t message_id, double rate_hz, uint8_t component_id=0) |
void | [set_msg_rate_async](#classdronecore_1_1_device_1ad3af9775d80d5301c19808822da6f9aa) (uint16_t message_id, double rate_hz, command_result_callback_t callback, uint8_t component_id=0) |
void | [request_autopilot_version](#classdronecore_1_1_device_1abd185340eaad71374b8f8647a5594502) () |
uint64_t | [get_target_uuid](#classdronecore_1_1_device_1a54bdadb4e8e52c9d159099749c29b7b4) () const |
uint8_t | [get_target_system_id](#classdronecore_1_1_device_1a55d2b2b871b2435420885b9594ca5b9b) () const |
uint8_t | [get_target_component_id](#classdronecore_1_1_device_1a41f2b9cf224c09d0c17081620ac201c5) () const |
void | [set_target_system_id](#classdronecore_1_1_device_1a01f14b9dffc35b045bbfe76f411c84f8) (uint8_t system_id) |
bool | [target_supports_mission_int](#classdronecore_1_1_device_1afbe6f90ecace24d8b7081a01be3686c3) () const |
bool | [is_armed](#classdronecore_1_1_device_1ad8b067dc607c3fd7bd86c2961409ce60) () const |
void | [set_param_float_async](#classdronecore_1_1_device_1a1b784f4c51451f23cb978b1982ead1bf) (const std::string & name, float value, success_t callback) |
void | [set_param_int_async](#classdronecore_1_1_device_1aa8fe748620f9934df97582943b20b372) (const std::string & name, int32_t value, success_t callback) |
void | [set_param_ext_float_async](#classdronecore_1_1_device_1a46ca0087cd5135a12a9f163455876fe2) (const std::string & name, float value, success_t callback) |
void | [set_param_ext_int_async](#classdronecore_1_1_device_1ab494873b3e6e99706c89c669d867c0bf) (const std::string & name, int32_t value, success_t callback) |
MavlinkCommands::Result | [set_flight_mode](#classdronecore_1_1_device_1acafac8ecf0801045ad894e80bcd9d9a8) (FlightMode mode) |
void | [set_flight_mode_async](#classdronecore_1_1_device_1a56d240c32839524470a8784f5c72e8a0) (FlightMode mode, command_result_callback_t callback) |
void | [get_param_float_async](#classdronecore_1_1_device_1a48dbd54b03ad86c9784dfac75274713f) (const std::string & name, get_param_float_callback_t callback) |
void | [get_param_int_async](#classdronecore_1_1_device_1a682a74475e24cac262ac90b18e5dd49a) (const std::string & name, get_param_int_callback_t callback) |
void | [get_param_ext_float_async](#classdronecore_1_1_device_1a6050f2993f78689c778cdb4240bb3606) (const std::string & name, get_param_float_callback_t callback) |
void | [get_param_ext_int_async](#classdronecore_1_1_device_1a7b4050c8aa12e198d99b23be4f281c7f) (const std::string & name, get_param_int_callback_t callback) |
bool | [is_connected](#classdronecore_1_1_device_1afac855ffb266017d932c4060140af717) () const |
Time & | [get_time](#classdronecore_1_1_device_1a6009c92dbd4ffd14367ad4ee1d4b3054) () |
void | [register_plugin](#classdronecore_1_1_device_1a7622b2667c5454c490a0d6722f738ec3) (PluginImplBase * plugin_impl) |
void | [unregister_plugin](#classdronecore_1_1_device_1aac00d6ae3d53154900785b882df5edf4) (PluginImplBase * plugin_impl) |
void | [lock_communication](#classdronecore_1_1_device_1a15d93e6a12f2208f8fa56466b7f2f819) () |
void | [unlock_communication](#classdronecore_1_1_device_1a801aab463023eb3e64670c86349fa54c) () |
const [Device](classdronecore_1_1_device.md) & | [operator=](#classdronecore_1_1_device_1ad03d3cdf0aaa8e4cb21becb6c7806c33) (const [Device](classdronecore_1_1_device.md) &)=delete |

## Static Public Member Functions


Type | Name | Description
---: | --- | ---
uint8_t | [get_own_system_id](#classdronecore_1_1_device_1ab598504aa60a5acf830161daf8eed908) () |
uint8_t | [get_own_component_id](#classdronecore_1_1_device_1aa6dc1543b0ae9439a6bacca0dc9c52e6) () |


## Constructor & Destructor Documentation


### Device() {#classdronecore_1_1_device_1af07b4defa38736ce928377af2f31fb6e}
```cpp
dronecore::Device::Device(DroneCoreImpl *parent, uint8_t target_system_id)
```


**Parameters**

* DroneCoreImpl * **parent** - 
* uint8_t **target_system_id** - 

### ~Device() {#classdronecore_1_1_device_1a65c697e12eed30109074e18a9cfdc836}
```cpp
dronecore::Device::~Device()
```


### Device() {#classdronecore_1_1_device_1acf95b02d5d1d705ce3dc1438786e0c91}
```cpp
dronecore::Device::Device(const Device &)=delete
```


**Parameters**

* const [Device](classdronecore_1_1_device.md) & - 

## Member Typdef Documentation


### typedef mavlink_message_handler_t {#classdronecore_1_1_device_1a1bca06c484ee8a4f18f0371a2a492e7b}

```cpp
typedef std::function<void(const mavlink_message_t &)> dronecore::Device::mavlink_message_handler_t
```


### typedef command_result_callback_t {#classdronecore_1_1_device_1a6ee9b5b6b3d40554ced23537168d801e}

```cpp
typedef std::function<void(MavlinkCommands::Result, float)> dronecore::Device::command_result_callback_t
```


### typedef success_t {#classdronecore_1_1_device_1aa90d45a543d894492d30618438e5ced4}

```cpp
typedef std::function<void(bool success)> dronecore::Device::success_t
```


### typedef get_param_float_callback_t {#classdronecore_1_1_device_1a8eabc97aec9a0ac69f79df2caabd8687}

```cpp
typedef std::function<void(bool success, float value)> dronecore::Device::get_param_float_callback_t
```


### typedef get_param_int_callback_t {#classdronecore_1_1_device_1a38ead6807abd7c8d72a8cf3909b4560d}

```cpp
typedef std::function<void(bool success, int32_t value)> dronecore::Device::get_param_int_callback_t
```


## Member Enumeration Documentation


### enum FlightMode {#classdronecore_1_1_device_1abe2b638e92f46ad3bdc124429a5929e8}


Value | Description
--- | ---
<span id="classdronecore_1_1_device_1abe2b638e92f46ad3bdc124429a5929e8a0c6d9dfb485b43c6fba87439f9f73ac4"></span> `HOLD` |  
<span id="classdronecore_1_1_device_1abe2b638e92f46ad3bdc124429a5929e8a0d4a147a2cf60f0761f239bf3ee2745e"></span> `RETURN_TO_LAUNCH` |  
<span id="classdronecore_1_1_device_1abe2b638e92f46ad3bdc124429a5929e8a8fabc74a4ed0781d663336cbf8c9c53d"></span> `TAKEOFF` |  
<span id="classdronecore_1_1_device_1abe2b638e92f46ad3bdc124429a5929e8a479a809c0b6eaaefd3b1df16f976df06"></span> `LAND` |  
<span id="classdronecore_1_1_device_1abe2b638e92f46ad3bdc124429a5929e8aa46075d70b9612df685b11436d195196"></span> `MISSION` |  
<span id="classdronecore_1_1_device_1abe2b638e92f46ad3bdc124429a5929e8ac4099cf323b2f571c3d4917db6b1a20d"></span> `FOLLOW_ME` |  
<span id="classdronecore_1_1_device_1abe2b638e92f46ad3bdc124429a5929e8a6687898e86a83f245901f96d313930b1"></span> `OFFBOARD` |  

## Member Function Documentation


### process_mavlink_message() {#classdronecore_1_1_device_1a7324f5f4cc1f7bce40a2e8c237f1212e}
```cpp
void dronecore::Device::process_mavlink_message(const mavlink_message_t &message)
```


**Parameters**

* const mavlink_message_t & **message** - 

### register_mavlink_message_handler() {#classdronecore_1_1_device_1aa7ae3afa910a2043185e319cfaaa4196}
```cpp
void dronecore::Device::register_mavlink_message_handler(uint16_t msg_id, mavlink_message_handler_t callback, const void *cookie)
```


**Parameters**

* uint16_t **msg_id** - 
* mavlink_message_handler_t **callback** - 
* const void * **cookie** - 

### unregister_all_mavlink_message_handlers() {#classdronecore_1_1_device_1a7fd2014818f2e41cc93b6c31d259f21c}
```cpp
void dronecore::Device::unregister_all_mavlink_message_handlers(const void *cookie)
```


**Parameters**

* const void * **cookie** - 

### register_timeout_handler() {#classdronecore_1_1_device_1afc704e09b8331cdd36341a1ffd331c11}
```cpp
void dronecore::Device::register_timeout_handler(std::function< void()> callback, double duration_s, void **cookie)
```


**Parameters**

* std::function< void()> **callback** - 
* double **duration_s** - 
* void ** **cookie** - 

### refresh_timeout_handler() {#classdronecore_1_1_device_1ad7d945426276c079ffc9d173583d1427}
```cpp
void dronecore::Device::refresh_timeout_handler(const void *cookie)
```


**Parameters**

* const void * **cookie** - 

### unregister_timeout_handler() {#classdronecore_1_1_device_1a95673878b3a69db3817def10310a565d}
```cpp
void dronecore::Device::unregister_timeout_handler(const void *cookie)
```


**Parameters**

* const void * **cookie** - 

### add_call_every() {#classdronecore_1_1_device_1a466bede03fdf9be31cefb206ef561114}
```cpp
void dronecore::Device::add_call_every(std::function< void()> callback, float interval_s, void **cookie)
```


**Parameters**

* std::function< void()> **callback** - 
* float **interval_s** - 
* void ** **cookie** - 

### change_call_every() {#classdronecore_1_1_device_1aed059a1d5a9f2ee4e11963e5d371577c}
```cpp
void dronecore::Device::change_call_every(float interval_s, const void *cookie)
```


**Parameters**

* float **interval_s** - 
* const void * **cookie** - 

### reset_call_every() {#classdronecore_1_1_device_1a38c719f6ccadf6a17e61c47c14cdf234}
```cpp
void dronecore::Device::reset_call_every(const void *cookie)
```


**Parameters**

* const void * **cookie** - 

### remove_call_every() {#classdronecore_1_1_device_1a5a101b41ec651a6a764a01d3208934e2}
```cpp
void dronecore::Device::remove_call_every(const void *cookie)
```


**Parameters**

* const void * **cookie** - 

### send_message() {#classdronecore_1_1_device_1a9d09cd1b8b9689080337f7efd9e9d77d}
```cpp
bool dronecore::Device::send_message(const mavlink_message_t &message)
```


**Parameters**

* const mavlink_message_t & **message** - 

**Returns**

&emsp;bool - 

### send_command_with_ack() {#classdronecore_1_1_device_1afcc8c11d47f681c41705d82ee3cd74ea}
```cpp
MavlinkCommands::Result dronecore::Device::send_command_with_ack(uint16_t command, const MavlinkCommands::Params &params, uint8_t component_id=0)
```


**Parameters**

* uint16_t **command** - 
* const MavlinkCommands::Params & **params** - 
* uint8_t **component_id** - 

**Returns**

&emsp;MavlinkCommands::Result - 

### send_command_with_ack_async() {#classdronecore_1_1_device_1a0ef6cf5c11820fb2ae00bd96f9abd4de}
```cpp
void dronecore::Device::send_command_with_ack_async(uint16_t command, const MavlinkCommands::Params &params, command_result_callback_t callback, uint8_t component_id=0)
```


**Parameters**

* uint16_t **command** - 
* const MavlinkCommands::Params & **params** - 
* command_result_callback_t **callback** - 
* uint8_t **component_id** - 

### set_msg_rate() {#classdronecore_1_1_device_1af10ca5a146f0129c51566486a20d98ed}
```cpp
MavlinkCommands::Result dronecore::Device::set_msg_rate(uint16_t message_id, double rate_hz, uint8_t component_id=0)
```


**Parameters**

* uint16_t **message_id** - 
* double **rate_hz** - 
* uint8_t **component_id** - 

**Returns**

&emsp;MavlinkCommands::Result - 

### set_msg_rate_async() {#classdronecore_1_1_device_1ad3af9775d80d5301c19808822da6f9aa}
```cpp
void dronecore::Device::set_msg_rate_async(uint16_t message_id, double rate_hz, command_result_callback_t callback, uint8_t component_id=0)
```


**Parameters**

* uint16_t **message_id** - 
* double **rate_hz** - 
* command_result_callback_t **callback** - 
* uint8_t **component_id** - 

### request_autopilot_version() {#classdronecore_1_1_device_1abd185340eaad71374b8f8647a5594502}
```cpp
void dronecore::Device::request_autopilot_version()
```


### get_target_uuid() {#classdronecore_1_1_device_1a54bdadb4e8e52c9d159099749c29b7b4}
```cpp
uint64_t dronecore::Device::get_target_uuid() const
```


**Returns**

&emsp;uint64_t - 

### get_target_system_id() {#classdronecore_1_1_device_1a55d2b2b871b2435420885b9594ca5b9b}
```cpp
uint8_t dronecore::Device::get_target_system_id() const
```


**Returns**

&emsp;uint8_t - 

### get_target_component_id() {#classdronecore_1_1_device_1a41f2b9cf224c09d0c17081620ac201c5}
```cpp
uint8_t dronecore::Device::get_target_component_id() const
```


**Returns**

&emsp;uint8_t - 

### set_target_system_id() {#classdronecore_1_1_device_1a01f14b9dffc35b045bbfe76f411c84f8}
```cpp
void dronecore::Device::set_target_system_id(uint8_t system_id)
```


**Parameters**

* uint8_t **system_id** - 

### target_supports_mission_int() {#classdronecore_1_1_device_1afbe6f90ecace24d8b7081a01be3686c3}
```cpp
bool dronecore::Device::target_supports_mission_int() const
```


**Returns**

&emsp;bool - 

### is_armed() {#classdronecore_1_1_device_1ad8b067dc607c3fd7bd86c2961409ce60}
```cpp
bool dronecore::Device::is_armed() const
```


**Returns**

&emsp;bool - 

### set_param_float_async() {#classdronecore_1_1_device_1a1b784f4c51451f23cb978b1982ead1bf}
```cpp
void dronecore::Device::set_param_float_async(const std::string &name, float value, success_t callback)
```


**Parameters**

* const std::string & **name** - 
* float **value** - 
* success_t **callback** - 

### set_param_int_async() {#classdronecore_1_1_device_1aa8fe748620f9934df97582943b20b372}
```cpp
void dronecore::Device::set_param_int_async(const std::string &name, int32_t value, success_t callback)
```


**Parameters**

* const std::string & **name** - 
* int32_t **value** - 
* success_t **callback** - 

### set_param_ext_float_async() {#classdronecore_1_1_device_1a46ca0087cd5135a12a9f163455876fe2}
```cpp
void dronecore::Device::set_param_ext_float_async(const std::string &name, float value, success_t callback)
```


**Parameters**

* const std::string & **name** - 
* float **value** - 
* success_t **callback** - 

### set_param_ext_int_async() {#classdronecore_1_1_device_1ab494873b3e6e99706c89c669d867c0bf}
```cpp
void dronecore::Device::set_param_ext_int_async(const std::string &name, int32_t value, success_t callback)
```


**Parameters**

* const std::string & **name** - 
* int32_t **value** - 
* success_t **callback** - 

### set_flight_mode() {#classdronecore_1_1_device_1acafac8ecf0801045ad894e80bcd9d9a8}
```cpp
MavlinkCommands::Result dronecore::Device::set_flight_mode(FlightMode mode)
```


**Parameters**

* FlightMode **mode** - 

**Returns**

&emsp;MavlinkCommands::Result - 

### set_flight_mode_async() {#classdronecore_1_1_device_1a56d240c32839524470a8784f5c72e8a0}
```cpp
void dronecore::Device::set_flight_mode_async(FlightMode mode, command_result_callback_t callback)
```


**Parameters**

* FlightMode **mode** - 
* command_result_callback_t **callback** - 

### get_param_float_async() {#classdronecore_1_1_device_1a48dbd54b03ad86c9784dfac75274713f}
```cpp
void dronecore::Device::get_param_float_async(const std::string &name, get_param_float_callback_t callback)
```


**Parameters**

* const std::string & **name** - 
* get_param_float_callback_t **callback** - 

### get_param_int_async() {#classdronecore_1_1_device_1a682a74475e24cac262ac90b18e5dd49a}
```cpp
void dronecore::Device::get_param_int_async(const std::string &name, get_param_int_callback_t callback)
```


**Parameters**

* const std::string & **name** - 
* get_param_int_callback_t **callback** - 

### get_param_ext_float_async() {#classdronecore_1_1_device_1a6050f2993f78689c778cdb4240bb3606}
```cpp
void dronecore::Device::get_param_ext_float_async(const std::string &name, get_param_float_callback_t callback)
```


**Parameters**

* const std::string & **name** - 
* get_param_float_callback_t **callback** - 

### get_param_ext_int_async() {#classdronecore_1_1_device_1a7b4050c8aa12e198d99b23be4f281c7f}
```cpp
void dronecore::Device::get_param_ext_int_async(const std::string &name, get_param_int_callback_t callback)
```


**Parameters**

* const std::string & **name** - 
* get_param_int_callback_t **callback** - 

### is_connected() {#classdronecore_1_1_device_1afac855ffb266017d932c4060140af717}
```cpp
bool dronecore::Device::is_connected() const
```


**Returns**

&emsp;bool - 

### get_time() {#classdronecore_1_1_device_1a6009c92dbd4ffd14367ad4ee1d4b3054}
```cpp
Time& dronecore::Device::get_time()
```


**Returns**

&emsp;Time & - 

### register_plugin() {#classdronecore_1_1_device_1a7622b2667c5454c490a0d6722f738ec3}
```cpp
void dronecore::Device::register_plugin(PluginImplBase *plugin_impl)
```


**Parameters**

* PluginImplBase * **plugin_impl** - 

### unregister_plugin() {#classdronecore_1_1_device_1aac00d6ae3d53154900785b882df5edf4}
```cpp
void dronecore::Device::unregister_plugin(PluginImplBase *plugin_impl)
```


**Parameters**

* PluginImplBase * **plugin_impl** - 

### lock_communication() {#classdronecore_1_1_device_1a15d93e6a12f2208f8fa56466b7f2f819}
```cpp
void dronecore::Device::lock_communication()
```


### unlock_communication() {#classdronecore_1_1_device_1a801aab463023eb3e64670c86349fa54c}
```cpp
void dronecore::Device::unlock_communication()
```


### operator=() {#classdronecore_1_1_device_1ad03d3cdf0aaa8e4cb21becb6c7806c33}
```cpp
const Device& dronecore::Device::operator=(const Device &)=delete
```


**Parameters**

* const [Device](classdronecore_1_1_device.md) & - 

**Returns**

&emsp;const [Device](classdronecore_1_1_device.md) & - 

### get_own_system_id() {#classdronecore_1_1_device_1ab598504aa60a5acf830161daf8eed908}
```cpp
static uint8_t dronecore::Device::get_own_system_id()
```


**Returns**

&emsp;uint8_t - 

### get_own_component_id() {#classdronecore_1_1_device_1aa6dc1543b0ae9439a6bacca0dc9c52e6}
```cpp
static uint8_t dronecore::Device::get_own_component_id()
```


**Returns**

&emsp;uint8_t - 