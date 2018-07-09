# dronecode_sdk::FollowMe Class Reference
`#include: follow_me.h`

----


This class enables vehicle tracking of a specified target (typically a ground station carried by a user). 


The API is used to supply both the position(s) for the target and the relative follow position of the vehicle. Applications must get target position information from the underlying platform (or some other source).


**See Also:**
- [Follow Me Mode](https://docs.px4.io/en/flight_modes/follow_me.html) (PX4 User Guide)


## Data Structures


struct [Config](structdronecode__sdk_1_1_follow_me_1_1_config.md)

struct [TargetLocation](structdronecode__sdk_1_1_follow_me_1_1_target_location.md)

## Public Types


Type | Description
--- | ---
enum [Result](#classdronecode__sdk_1_1_follow_me_1aee6bb389d91e5bb609d120d76cdbcf76) | Results of [FollowMe](classdronecode__sdk_1_1_follow_me.md) operations.

## Public Member Functions


Type | Name | Description
---: | --- | ---
&nbsp; | [FollowMe](#classdronecode__sdk_1_1_follow_me_1abd4604d2e831210d8abc39aa3e498507) ([System](classdronecode__sdk_1_1_system.md) & system) | Constructor. Creates the plugin for a specific [System](classdronecode__sdk_1_1_system.md).
&nbsp; | [~FollowMe](#classdronecode__sdk_1_1_follow_me_1aa2c65004d1d398cd5f5a212af3ef8615) () | Destructor (internal use only).
&nbsp; | [FollowMe](#classdronecode__sdk_1_1_follow_me_1abd81ad70ad93a8e2451cb873e9ee795b) (const [FollowMe](classdronecode__sdk_1_1_follow_me.md) &)=delete | Copy constructor (object is not copyable).
const [Config](structdronecode__sdk_1_1_follow_me_1_1_config.md) & | [get_config](#classdronecode__sdk_1_1_follow_me_1a40a8d99cb9c34066db38586654d5b32b) () const | Gets current [FollowMe](classdronecode__sdk_1_1_follow_me.md) configuration.
[Result](classdronecode__sdk_1_1_follow_me.md#classdronecode__sdk_1_1_follow_me_1aee6bb389d91e5bb609d120d76cdbcf76) | [set_config](#classdronecode__sdk_1_1_follow_me_1a45c5d737b18e89c1c5dd52d5606431a5) (const [Config](structdronecode__sdk_1_1_follow_me_1_1_config.md) & config) | Applies [FollowMe](classdronecode__sdk_1_1_follow_me.md) configuration by sending it to system.
bool | [is_active](#classdronecode__sdk_1_1_follow_me_1a379a72b4758284de34be5b53f0d4103c) () const | Checks whether [FollowMe](classdronecode__sdk_1_1_follow_me.md) is active.
void | [set_target_location](#classdronecode__sdk_1_1_follow_me_1a22c1812037fae806fa3aa7de040e8c1b) (const [TargetLocation](structdronecode__sdk_1_1_follow_me_1_1_target_location.md) & location) | Sets location of the moving target.
const [TargetLocation](structdronecode__sdk_1_1_follow_me_1_1_target_location.md) & | [get_last_location](#classdronecode__sdk_1_1_follow_me_1abb57f8def2b0b64bff8c9bce8f31f5cf) () const | Returns the last location of the target.
[FollowMe::Result](classdronecode__sdk_1_1_follow_me.md#classdronecode__sdk_1_1_follow_me_1aee6bb389d91e5bb609d120d76cdbcf76) | [start](#classdronecode__sdk_1_1_follow_me_1a289eb9bc3ab78fff26caab955fb3c309) () const | Starts [FollowMe](classdronecode__sdk_1_1_follow_me.md) mode.
[FollowMe::Result](classdronecode__sdk_1_1_follow_me.md#classdronecode__sdk_1_1_follow_me_1aee6bb389d91e5bb609d120d76cdbcf76) | [stop](#classdronecode__sdk_1_1_follow_me_1a0b1ea2494384f734818bc147e12a6f83) () const | Stops [FollowMe](classdronecode__sdk_1_1_follow_me.md) mode.
const [FollowMe](classdronecode__sdk_1_1_follow_me.md) & | [operator=](#classdronecode__sdk_1_1_follow_me_1aebb7c224ccfaad1a9b00c0261e443c64) (const [FollowMe](classdronecode__sdk_1_1_follow_me.md) &)=delete | Equality operator (object is not copyable).

## Static Public Member Functions


Type | Name | Description
---: | --- | ---
std::string | [result_str](#classdronecode__sdk_1_1_follow_me_1a25d6642c109a6c52fdcce8beba31d3db) ([Result](classdronecode__sdk_1_1_follow_me.md#classdronecode__sdk_1_1_follow_me_1aee6bb389d91e5bb609d120d76cdbcf76) result) | Returns English string for [FollowMe](classdronecode__sdk_1_1_follow_me.md) error codes.


## Constructor & Destructor Documentation


### FollowMe() {#classdronecode__sdk_1_1_follow_me_1abd4604d2e831210d8abc39aa3e498507}
```cpp
dronecode_sdk::FollowMe::FollowMe(System &system)
```


Constructor. Creates the plugin for a specific [System](classdronecode__sdk_1_1_system.md).

The plugin is typically created as shown below: 

```cpp
auto follow_me = std::make_shared<FollowMe>(system);
```

**Parameters**

* [System](classdronecode__sdk_1_1_system.md)& **system** - The specific system associated with this plugin.

### ~FollowMe() {#classdronecode__sdk_1_1_follow_me_1aa2c65004d1d398cd5f5a212af3ef8615}
```cpp
dronecode_sdk::FollowMe::~FollowMe()
```


Destructor (internal use only).


### FollowMe() {#classdronecode__sdk_1_1_follow_me_1abd81ad70ad93a8e2451cb873e9ee795b}
```cpp
dronecode_sdk::FollowMe::FollowMe(const FollowMe &)=delete
```


Copy constructor (object is not copyable).


**Parameters**

* const [FollowMe](classdronecode__sdk_1_1_follow_me.md)&  - 

## Member Enumeration Documentation


### enum Result {#classdronecode__sdk_1_1_follow_me_1aee6bb389d91e5bb609d120d76cdbcf76}


Results of [FollowMe](classdronecode__sdk_1_1_follow_me.md) operations.


Value | Description
--- | ---
<span id="classdronecode__sdk_1_1_follow_me_1aee6bb389d91e5bb609d120d76cdbcf76ad0749aaba8b833466dfcbb0428e4f89c"></span> `SUCCESS` | Request succeeded. 
<span id="classdronecode__sdk_1_1_follow_me_1aee6bb389d91e5bb609d120d76cdbcf76afeae72a3a2feec3c92c2a79a30d31186"></span> `NO_SYSTEM` | No system connected. 
<span id="classdronecode__sdk_1_1_follow_me_1aee6bb389d91e5bb609d120d76cdbcf76ac77f1f09dab2c0c9980fca7cfae02518"></span> `CONNECTION_ERROR` | Connection error. 
<span id="classdronecode__sdk_1_1_follow_me_1aee6bb389d91e5bb609d120d76cdbcf76a802706a9238e2928077f97736854bad4"></span> `BUSY` | Vehicle busy. 
<span id="classdronecode__sdk_1_1_follow_me_1aee6bb389d91e5bb609d120d76cdbcf76a6fa4dbf368cea972db8d9156799d5dbe"></span> `COMMAND_DENIED` | Command denied. 
<span id="classdronecode__sdk_1_1_follow_me_1aee6bb389d91e5bb609d120d76cdbcf76a070a0fb40f6c308ab544b227660aadff"></span> `TIMEOUT` | Request timeout. 
<span id="classdronecode__sdk_1_1_follow_me_1aee6bb389d91e5bb609d120d76cdbcf76a1b2fe1358d26a4a36841de06904bc0e3"></span> `NOT_ACTIVE` | [FollowMe](classdronecode__sdk_1_1_follow_me.md) is not activated. 
<span id="classdronecode__sdk_1_1_follow_me_1aee6bb389d91e5bb609d120d76cdbcf76a93093f549a7c46c8f91528870edbe9e6"></span> `SET_CONFIG_FAILED` | Failed to set [FollowMe](classdronecode__sdk_1_1_follow_me.md) configuration. 
<span id="classdronecode__sdk_1_1_follow_me_1aee6bb389d91e5bb609d120d76cdbcf76a696b031073e74bf2cb98e5ef201d4aa3"></span> `UNKNOWN` | Unknown error. 

**See Also:**
- [result_str()](classdronecode__sdk_1_1_follow_me.md#classdronecode__sdk_1_1_follow_me_1a25d6642c109a6c52fdcce8beba31d3db)


## Member Function Documentation


### get_config() {#classdronecode__sdk_1_1_follow_me_1a40a8d99cb9c34066db38586654d5b32b}
```cpp
const Config& dronecode_sdk::FollowMe::get_config() const
```


Gets current [FollowMe](classdronecode__sdk_1_1_follow_me.md) configuration.


**Returns**

&emsp;const [Config](structdronecode__sdk_1_1_follow_me_1_1_config.md) & - Current [FollowMe](classdronecode__sdk_1_1_follow_me.md) configuration.

**See Also:**
- [set_config()](classdronecode__sdk_1_1_follow_me.md#classdronecode__sdk_1_1_follow_me_1a45c5d737b18e89c1c5dd52d5606431a5)


### set_config() {#classdronecode__sdk_1_1_follow_me_1a45c5d737b18e89c1c5dd52d5606431a5}
```cpp
Result dronecode_sdk::FollowMe::set_config(const Config &config)
```


Applies [FollowMe](classdronecode__sdk_1_1_follow_me.md) configuration by sending it to system.


**Parameters**

* const [Config](structdronecode__sdk_1_1_follow_me_1_1_config.md)& **config** - [FollowMe](classdronecode__sdk_1_1_follow_me.md) configuration to be applied.

**Returns**

&emsp;[Result](classdronecode__sdk_1_1_follow_me.md#classdronecode__sdk_1_1_follow_me_1aee6bb389d91e5bb609d120d76cdbcf76) - [FollowMe::Result::SUCCESS](classdronecode__sdk_1_1_follow_me.md#classdronecode__sdk_1_1_follow_me_1aee6bb389d91e5bb609d120d76cdbcf76ad0749aaba8b833466dfcbb0428e4f89c) if configuration is applied successfully, [FollowMe::Result::SET_CONFIG_FAILED](classdronecode__sdk_1_1_follow_me.md#classdronecode__sdk_1_1_follow_me_1aee6bb389d91e5bb609d120d76cdbcf76a93093f549a7c46c8f91528870edbe9e6) on failure. In case of failure, last configuration is preserved.

**See Also:**
- [get_config()](classdronecode__sdk_1_1_follow_me.md#classdronecode__sdk_1_1_follow_me_1a40a8d99cb9c34066db38586654d5b32b)


### is_active() {#classdronecode__sdk_1_1_follow_me_1a379a72b4758284de34be5b53f0d4103c}
```cpp
bool dronecode_sdk::FollowMe::is_active() const
```


Checks whether [FollowMe](classdronecode__sdk_1_1_follow_me.md) is active.


**Returns**

&emsp;bool - `true` if [FollowMe](classdronecode__sdk_1_1_follow_me.md) is active, `false` otherwise.

### set_target_location() {#classdronecode__sdk_1_1_follow_me_1a22c1812037fae806fa3aa7de040e8c1b}
```cpp
void dronecode_sdk::FollowMe::set_target_location(const TargetLocation &location)
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

* const [TargetLocation](structdronecode__sdk_1_1_follow_me_1_1_target_location.md)& **location** - Location of the moving target.

**See Also:**
- [get_last_location()](classdronecode__sdk_1_1_follow_me.md#classdronecode__sdk_1_1_follow_me_1abb57f8def2b0b64bff8c9bce8f31f5cf)


### get_last_location() {#classdronecode__sdk_1_1_follow_me_1abb57f8def2b0b64bff8c9bce8f31f5cf}
```cpp
const TargetLocation& dronecode_sdk::FollowMe::get_last_location() const
```


Returns the last location of the target.


**Returns**

&emsp;const [TargetLocation](structdronecode__sdk_1_1_follow_me_1_1_target_location.md) & - Last location of the target.

**See Also:**
- [set_target_location()](classdronecode__sdk_1_1_follow_me.md#classdronecode__sdk_1_1_follow_me_1a22c1812037fae806fa3aa7de040e8c1b)


### start() {#classdronecode__sdk_1_1_follow_me_1a289eb9bc3ab78fff26caab955fb3c309}
```cpp
FollowMe::Result dronecode_sdk::FollowMe::start() const
```


Starts [FollowMe](classdronecode__sdk_1_1_follow_me.md) mode.


**Returns**

&emsp;[FollowMe::Result](classdronecode__sdk_1_1_follow_me.md#classdronecode__sdk_1_1_follow_me_1aee6bb389d91e5bb609d120d76cdbcf76) - [FollowMe::Result::SUCCESS](classdronecode__sdk_1_1_follow_me.md#classdronecode__sdk_1_1_follow_me_1aee6bb389d91e5bb609d120d76cdbcf76ad0749aaba8b833466dfcbb0428e4f89c) if succeeded, error otherwise.

### stop() {#classdronecode__sdk_1_1_follow_me_1a0b1ea2494384f734818bc147e12a6f83}
```cpp
FollowMe::Result dronecode_sdk::FollowMe::stop() const
```


Stops [FollowMe](classdronecode__sdk_1_1_follow_me.md) mode.


**Returns**

&emsp;[FollowMe::Result](classdronecode__sdk_1_1_follow_me.md#classdronecode__sdk_1_1_follow_me_1aee6bb389d91e5bb609d120d76cdbcf76) - [FollowMe::Result::SUCCESS](classdronecode__sdk_1_1_follow_me.md#classdronecode__sdk_1_1_follow_me_1aee6bb389d91e5bb609d120d76cdbcf76ad0749aaba8b833466dfcbb0428e4f89c) if succeeded, error otherwise. See [FollowMe::Result](classdronecode__sdk_1_1_follow_me.md#classdronecode__sdk_1_1_follow_me_1aee6bb389d91e5bb609d120d76cdbcf76) for error codes.

### operator=() {#classdronecode__sdk_1_1_follow_me_1aebb7c224ccfaad1a9b00c0261e443c64}
```cpp
const FollowMe& dronecode_sdk::FollowMe::operator=(const FollowMe &)=delete
```


Equality operator (object is not copyable).


**Parameters**

* const [FollowMe](classdronecode__sdk_1_1_follow_me.md)&  - 

**Returns**

&emsp;const [FollowMe](classdronecode__sdk_1_1_follow_me.md) & - 

### result_str() {#classdronecode__sdk_1_1_follow_me_1a25d6642c109a6c52fdcce8beba31d3db}
```cpp
static std::string dronecode_sdk::FollowMe::result_str(Result result)
```


Returns English string for [FollowMe](classdronecode__sdk_1_1_follow_me.md) error codes.


**Parameters**

* [Result](classdronecode__sdk_1_1_follow_me.md#classdronecode__sdk_1_1_follow_me_1aee6bb389d91e5bb609d120d76cdbcf76) **result** - [Result](classdronecode__sdk_1_1_follow_me.md#classdronecode__sdk_1_1_follow_me_1aee6bb389d91e5bb609d120d76cdbcf76) code.

**Returns**

&emsp;std::string - Returns std::string describing error code.