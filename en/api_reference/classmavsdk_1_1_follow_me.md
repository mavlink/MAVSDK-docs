# mavsdk::FollowMe Class Reference
`#include: follow_me.h`

----


This class enables vehicle tracking of a specified target (typically a ground station carried by a user). 


The API is used to supply both the position(s) for the target and the relative follow position of the vehicle. Applications must get target position information from the underlying platform (or some other source).


**See Also:**
- [Follow Me Mode](https://docs.px4.io/master/en/flight_modes/follow_me.html) (PX4 User Guide)


## Data Structures


struct [Config](structmavsdk_1_1_follow_me_1_1_config.md)

struct [TargetLocation](structmavsdk_1_1_follow_me_1_1_target_location.md)

## Public Types


Type | Description
--- | ---
enum [Result](#classmavsdk_1_1_follow_me_1a2b3f334ea72fd84d9e925fb3756451d8) | Results of [FollowMe](classmavsdk_1_1_follow_me.md) operations.

## Public Member Functions


Type | Name | Description
---: | --- | ---
&nbsp; | [FollowMe](#classmavsdk_1_1_follow_me_1ab85b27fcd899f4861cd2e99c08083b9e) ([System](classmavsdk_1_1_system.md) & system) | Constructor. Creates the plugin for a specific [System](classmavsdk_1_1_system.md).
&nbsp; | [~FollowMe](#classmavsdk_1_1_follow_me_1a7c8769bb4a10665d6df9b6043c86233b) () | Destructor (internal use only).
&nbsp; | [FollowMe](#classmavsdk_1_1_follow_me_1a49025a79508f98211611fb2c03f36e88) (const [FollowMe](classmavsdk_1_1_follow_me.md) &)=delete | Copy constructor (object is not copyable).
const [Config](structmavsdk_1_1_follow_me_1_1_config.md) & | [get_config](#classmavsdk_1_1_follow_me_1a5a39cc685ea4288363ef38ebbd628062) () const | Gets current [FollowMe](classmavsdk_1_1_follow_me.md) configuration.
[Result](classmavsdk_1_1_follow_me.md#classmavsdk_1_1_follow_me_1a2b3f334ea72fd84d9e925fb3756451d8) | [set_config](#classmavsdk_1_1_follow_me_1a1d7c0e5598769365aeaec8026578a977) (const [Config](structmavsdk_1_1_follow_me_1_1_config.md) & config) | Applies [FollowMe](classmavsdk_1_1_follow_me.md) configuration by sending it to system.
bool | [is_active](#classmavsdk_1_1_follow_me_1a48ab77939257e52159bd9ed19335a7de) () const | Checks whether [FollowMe](classmavsdk_1_1_follow_me.md) is active.
void | [set_target_location](#classmavsdk_1_1_follow_me_1a8423c855534f821aeb051997c1a576a5) (const [TargetLocation](structmavsdk_1_1_follow_me_1_1_target_location.md) & location) | Sets location of the moving target.
const [TargetLocation](structmavsdk_1_1_follow_me_1_1_target_location.md) & | [get_last_location](#classmavsdk_1_1_follow_me_1ae78d10ea8c6a5a27dbc26c421d8ae48f) () const | Returns the last location of the target.
[FollowMe::Result](classmavsdk_1_1_follow_me.md#classmavsdk_1_1_follow_me_1a2b3f334ea72fd84d9e925fb3756451d8) | [start](#classmavsdk_1_1_follow_me_1a54434262fb1351f6ad648879606b6dd7) () const | Starts [FollowMe](classmavsdk_1_1_follow_me.md) mode.
[FollowMe::Result](classmavsdk_1_1_follow_me.md#classmavsdk_1_1_follow_me_1a2b3f334ea72fd84d9e925fb3756451d8) | [stop](#classmavsdk_1_1_follow_me_1a157c9a6e4047d317fcb54abc71b390e2) () const | Stops [FollowMe](classmavsdk_1_1_follow_me.md) mode.
const [FollowMe](classmavsdk_1_1_follow_me.md) & | [operator=](#classmavsdk_1_1_follow_me_1a6292f6dd2c91cedde0e3b82952d83510) (const [FollowMe](classmavsdk_1_1_follow_me.md) &)=delete | Equality operator (object is not copyable).

## Static Public Member Functions


Type | Name | Description
---: | --- | ---
std::string | [result_str](#classmavsdk_1_1_follow_me_1ac0c08dafa58a984a78e5352119b32bf8) ([Result](classmavsdk_1_1_follow_me.md#classmavsdk_1_1_follow_me_1a2b3f334ea72fd84d9e925fb3756451d8) result) | Returns English string for [FollowMe](classmavsdk_1_1_follow_me.md) error codes.


## Constructor & Destructor Documentation


### FollowMe() {#classmavsdk_1_1_follow_me_1ab85b27fcd899f4861cd2e99c08083b9e}
```cpp
mavsdk::FollowMe::FollowMe(System &system)
```


Constructor. Creates the plugin for a specific [System](classmavsdk_1_1_system.md).

The plugin is typically created as shown below: 

```cpp
auto follow_me = std::make_shared<FollowMe>(system);
```

**Parameters**

* [System](classmavsdk_1_1_system.md)& **system** - The specific system associated with this plugin.

### ~FollowMe() {#classmavsdk_1_1_follow_me_1a7c8769bb4a10665d6df9b6043c86233b}
```cpp
mavsdk::FollowMe::~FollowMe()
```


Destructor (internal use only).


### FollowMe() {#classmavsdk_1_1_follow_me_1a49025a79508f98211611fb2c03f36e88}
```cpp
mavsdk::FollowMe::FollowMe(const FollowMe &)=delete
```


Copy constructor (object is not copyable).


**Parameters**

* const [FollowMe](classmavsdk_1_1_follow_me.md)&  - 

## Member Enumeration Documentation


### enum Result {#classmavsdk_1_1_follow_me_1a2b3f334ea72fd84d9e925fb3756451d8}


Results of [FollowMe](classmavsdk_1_1_follow_me.md) operations.


Value | Description
--- | ---
<span id="classmavsdk_1_1_follow_me_1a2b3f334ea72fd84d9e925fb3756451d8ad0749aaba8b833466dfcbb0428e4f89c"></span> `SUCCESS` | Request succeeded. 
<span id="classmavsdk_1_1_follow_me_1a2b3f334ea72fd84d9e925fb3756451d8afeae72a3a2feec3c92c2a79a30d31186"></span> `NO_SYSTEM` | No system connected. 
<span id="classmavsdk_1_1_follow_me_1a2b3f334ea72fd84d9e925fb3756451d8ac77f1f09dab2c0c9980fca7cfae02518"></span> `CONNECTION_ERROR` | Connection error. 
<span id="classmavsdk_1_1_follow_me_1a2b3f334ea72fd84d9e925fb3756451d8a802706a9238e2928077f97736854bad4"></span> `BUSY` | Vehicle busy. 
<span id="classmavsdk_1_1_follow_me_1a2b3f334ea72fd84d9e925fb3756451d8a6fa4dbf368cea972db8d9156799d5dbe"></span> `COMMAND_DENIED` | Command denied. 
<span id="classmavsdk_1_1_follow_me_1a2b3f334ea72fd84d9e925fb3756451d8a070a0fb40f6c308ab544b227660aadff"></span> `TIMEOUT` | Request timeout. 
<span id="classmavsdk_1_1_follow_me_1a2b3f334ea72fd84d9e925fb3756451d8a1b2fe1358d26a4a36841de06904bc0e3"></span> `NOT_ACTIVE` | [FollowMe](classmavsdk_1_1_follow_me.md) is not activated. 
<span id="classmavsdk_1_1_follow_me_1a2b3f334ea72fd84d9e925fb3756451d8a93093f549a7c46c8f91528870edbe9e6"></span> `SET_CONFIG_FAILED` | Failed to set [FollowMe](classmavsdk_1_1_follow_me.md) configuration. 
<span id="classmavsdk_1_1_follow_me_1a2b3f334ea72fd84d9e925fb3756451d8a696b031073e74bf2cb98e5ef201d4aa3"></span> `UNKNOWN` | Unknown error. 

**See Also:**
- [result_str()](classmavsdk_1_1_follow_me.md#classmavsdk_1_1_follow_me_1ac0c08dafa58a984a78e5352119b32bf8)


## Member Function Documentation


### get_config() {#classmavsdk_1_1_follow_me_1a5a39cc685ea4288363ef38ebbd628062}
```cpp
const Config& mavsdk::FollowMe::get_config() const
```


Gets current [FollowMe](classmavsdk_1_1_follow_me.md) configuration.


**Returns**

&emsp;const [Config](structmavsdk_1_1_follow_me_1_1_config.md) & - Current [FollowMe](classmavsdk_1_1_follow_me.md) configuration.

**See Also:**
- [set_config()](classmavsdk_1_1_follow_me.md#classmavsdk_1_1_follow_me_1a1d7c0e5598769365aeaec8026578a977)


### set_config() {#classmavsdk_1_1_follow_me_1a1d7c0e5598769365aeaec8026578a977}
```cpp
Result mavsdk::FollowMe::set_config(const Config &config)
```


Applies [FollowMe](classmavsdk_1_1_follow_me.md) configuration by sending it to system.


**Parameters**

* const [Config](structmavsdk_1_1_follow_me_1_1_config.md)& **config** - [FollowMe](classmavsdk_1_1_follow_me.md) configuration to be applied.

**Returns**

&emsp;[Result](classmavsdk_1_1_follow_me.md#classmavsdk_1_1_follow_me_1a2b3f334ea72fd84d9e925fb3756451d8) - [FollowMe::Result::SUCCESS](classmavsdk_1_1_follow_me.md#classmavsdk_1_1_follow_me_1a2b3f334ea72fd84d9e925fb3756451d8ad0749aaba8b833466dfcbb0428e4f89c) if configuration is applied successfully, [FollowMe::Result::SET_CONFIG_FAILED](classmavsdk_1_1_follow_me.md#classmavsdk_1_1_follow_me_1a2b3f334ea72fd84d9e925fb3756451d8a93093f549a7c46c8f91528870edbe9e6) on failure. In case of failure, last configuration is preserved.

**See Also:**
- [get_config()](classmavsdk_1_1_follow_me.md#classmavsdk_1_1_follow_me_1a5a39cc685ea4288363ef38ebbd628062)


### is_active() {#classmavsdk_1_1_follow_me_1a48ab77939257e52159bd9ed19335a7de}
```cpp
bool mavsdk::FollowMe::is_active() const
```


Checks whether [FollowMe](classmavsdk_1_1_follow_me.md) is active.


**Returns**

&emsp;bool - `true` if [FollowMe](classmavsdk_1_1_follow_me.md) is active, `false` otherwise.

### set_target_location() {#classmavsdk_1_1_follow_me_1a8423c855534f821aeb051997c1a576a5}
```cpp
void mavsdk::FollowMe::set_target_location(const TargetLocation &location)
```


Sets location of the moving target.

An app can obtain the location of the moving target from Location framework of the underlying platform.


> **Note** The following links provide information about location services on different platforms:
<ul>
<li><p>Android - <a href="https://developer.android.com/reference/android/location/Location.html">https://developer.android.com/reference/android/location/Location.html</a></p></li>
<li><p>Apple - <a href="https://developer.apple.com/documentation/corelocation">https://developer.apple.com/documentation/corelocation</a></p></li>
<li><p>Windows - <a href="https://docs.microsoft.com/en-us/uwp/api/Windows.Devices.Geolocation">https://docs.microsoft.com/en-us/uwp/api/Windows.Devices.Geolocation</a></p></li>
</ul>

**Parameters**

* const [TargetLocation](structmavsdk_1_1_follow_me_1_1_target_location.md)& **location** - Location of the moving target.

**See Also:**
- [get_last_location()](classmavsdk_1_1_follow_me.md#classmavsdk_1_1_follow_me_1ae78d10ea8c6a5a27dbc26c421d8ae48f)


### get_last_location() {#classmavsdk_1_1_follow_me_1ae78d10ea8c6a5a27dbc26c421d8ae48f}
```cpp
const TargetLocation& mavsdk::FollowMe::get_last_location() const
```


Returns the last location of the target.


**Returns**

&emsp;const [TargetLocation](structmavsdk_1_1_follow_me_1_1_target_location.md) & - Last location of the target.

**See Also:**
- [set_target_location()](classmavsdk_1_1_follow_me.md#classmavsdk_1_1_follow_me_1a8423c855534f821aeb051997c1a576a5)


### start() {#classmavsdk_1_1_follow_me_1a54434262fb1351f6ad648879606b6dd7}
```cpp
FollowMe::Result mavsdk::FollowMe::start() const
```


Starts [FollowMe](classmavsdk_1_1_follow_me.md) mode.


**Returns**

&emsp;[FollowMe::Result](classmavsdk_1_1_follow_me.md#classmavsdk_1_1_follow_me_1a2b3f334ea72fd84d9e925fb3756451d8) - [FollowMe::Result::SUCCESS](classmavsdk_1_1_follow_me.md#classmavsdk_1_1_follow_me_1a2b3f334ea72fd84d9e925fb3756451d8ad0749aaba8b833466dfcbb0428e4f89c) if succeeded, error otherwise.

### stop() {#classmavsdk_1_1_follow_me_1a157c9a6e4047d317fcb54abc71b390e2}
```cpp
FollowMe::Result mavsdk::FollowMe::stop() const
```


Stops [FollowMe](classmavsdk_1_1_follow_me.md) mode.


**Returns**

&emsp;[FollowMe::Result](classmavsdk_1_1_follow_me.md#classmavsdk_1_1_follow_me_1a2b3f334ea72fd84d9e925fb3756451d8) - [FollowMe::Result::SUCCESS](classmavsdk_1_1_follow_me.md#classmavsdk_1_1_follow_me_1a2b3f334ea72fd84d9e925fb3756451d8ad0749aaba8b833466dfcbb0428e4f89c) if succeeded, error otherwise. See [FollowMe::Result](classmavsdk_1_1_follow_me.md#classmavsdk_1_1_follow_me_1a2b3f334ea72fd84d9e925fb3756451d8) for error codes.

### operator=() {#classmavsdk_1_1_follow_me_1a6292f6dd2c91cedde0e3b82952d83510}
```cpp
const FollowMe& mavsdk::FollowMe::operator=(const FollowMe &)=delete
```


Equality operator (object is not copyable).


**Parameters**

* const [FollowMe](classmavsdk_1_1_follow_me.md)&  - 

**Returns**

&emsp;const [FollowMe](classmavsdk_1_1_follow_me.md) & - 

### result_str() {#classmavsdk_1_1_follow_me_1ac0c08dafa58a984a78e5352119b32bf8}
```cpp
static std::string mavsdk::FollowMe::result_str(Result result)
```


Returns English string for [FollowMe](classmavsdk_1_1_follow_me.md) error codes.


**Parameters**

* [Result](classmavsdk_1_1_follow_me.md#classmavsdk_1_1_follow_me_1a2b3f334ea72fd84d9e925fb3756451d8) **result** - [Result](classmavsdk_1_1_follow_me.md#classmavsdk_1_1_follow_me_1a2b3f334ea72fd84d9e925fb3756451d8) code.

**Returns**

&emsp;std::string - Returns std::string describing error code.