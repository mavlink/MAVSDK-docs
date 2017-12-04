# dronecore::FollowMe Class Reference
`#include: follow_me.h`

----


This class enables vehicle tracking of a specified target (typically a ground station carried by a user). 


The API is used to supply both the position(s) for the target and the relative follow position of the vehicle. Applications must get target position information from the underlying platform (or some other source).


**See Also:**
- [Follow Me Mode](https://docs.px4.io/en/flight_modes/follow_me.html) (PX4 User Guide)


## Data Structures


struct [Config](structdronecore_1_1_follow_me_1_1_config.md)

struct [TargetLocation](structdronecore_1_1_follow_me_1_1_target_location.md)

## Public Types


Type | Description
--- | ---
enum [Result](#classdronecore_1_1_follow_me_1aee7e30070ac95bc63b68c10bd7253b02) | Results of [FollowMe](classdronecore_1_1_follow_me.md) operations.

## Public Member Functions


Type | Name | Description
---: | --- | ---
| [FollowMe](#classdronecore_1_1_follow_me_1a4fb2ce15bde7d521644dc0835cf217e1) (FollowMeImpl *impl) | Constructor (internal use only).
| [~FollowMe](#classdronecore_1_1_follow_me_1a66ffe3c9652bc08a2766f211592316ac) () | Destructor (internal use only).
| [FollowMe](#classdronecore_1_1_follow_me_1a54589c314eeba131aca1c4c56d4b15e3) (const FollowMe &)=delete | Copy constructor (object is not copyable).
const [Config](structdronecore_1_1_follow_me_1_1_config.md) & | [get_config](#classdronecore_1_1_follow_me_1a054aebafe0839a1028f277285b769fe5) () const | Gets current [FollowMe](classdronecore_1_1_follow_me.md) configuration.
bool | [set_config](#classdronecore_1_1_follow_me_1a4b92c3a042911dd9bdb378c686458a34) (const Config &config) | Applies [FollowMe](classdronecore_1_1_follow_me.md) configuration by sending it to device.
bool | [is_active](#classdronecore_1_1_follow_me_1a467349820ac5f42cc388228c399a93ef) () const | Checks whether [FollowMe](classdronecore_1_1_follow_me.md) is active.
void | [set_curr_target_location](#classdronecore_1_1_follow_me_1afb8c24ed93421e904b0f528569c7699a) (const TargetLocation &location) | Sets current location of the moving target App can obtain location of the moving target from Location framework of the underlying platform.
void | [get_last_location](#classdronecore_1_1_follow_me_1ab68273d5ace65ee953afa1797ae49e7c) (TargetLocation &last_location) | Returns the most recent location of the target.
[FollowMe::Result](classdronecore_1_1_follow_me.md#classdronecore_1_1_follow_me_1aee7e30070ac95bc63b68c10bd7253b02) | [start](#classdronecore_1_1_follow_me_1a694749d43d527f85584df25a49b05ccf) () const | Starts [FollowMe](classdronecore_1_1_follow_me.md) mode.
[FollowMe::Result](classdronecore_1_1_follow_me.md#classdronecore_1_1_follow_me_1aee7e30070ac95bc63b68c10bd7253b02) | [stop](#classdronecore_1_1_follow_me_1a6394507b0fb96bceebe6efd17f0529ce) () const | Stops [FollowMe](classdronecore_1_1_follow_me.md) mode.
const [FollowMe](classdronecore_1_1_follow_me.md) & | [operator=](#classdronecore_1_1_follow_me_1accb454508e051d79b2943ba469958f9e) (const FollowMe &)=delete | Equality operator (object is not copyable).

## Static Public Member Functions


Type | Name | Description
---: | --- | ---
std::string | [result_str](#classdronecore_1_1_follow_me_1a50d848b1c7b00e40343b8d62593ca307) (Result result) | Returns English string for [FollowMe](classdronecore_1_1_follow_me.md) error codes.


## Constructor & Destructor Documentation


### FollowMe() {#classdronecore_1_1_follow_me_1a4fb2ce15bde7d521644dc0835cf217e1}
```cpp
dronecore::FollowMe::FollowMe(FollowMeImpl *impl)
```


Constructor (internal use only).


**Parameters**

* FollowMeImpl * **impl** - Private internal implementation.

### ~FollowMe() {#classdronecore_1_1_follow_me_1a66ffe3c9652bc08a2766f211592316ac}
```cpp
dronecore::FollowMe::~FollowMe()
```


Destructor (internal use only).


### FollowMe() {#classdronecore_1_1_follow_me_1a54589c314eeba131aca1c4c56d4b15e3}
```cpp
dronecore::FollowMe::FollowMe(const FollowMe &)=delete
```


Copy constructor (object is not copyable).


**Parameters**

* const [FollowMe](classdronecore_1_1_follow_me.md) & - 

## Member Enumeration Documentation


### enum Result {#classdronecore_1_1_follow_me_1aee7e30070ac95bc63b68c10bd7253b02}


Results of [FollowMe](classdronecore_1_1_follow_me.md) operations.


Value | Description
--- | ---
<span id="classdronecore_1_1_follow_me_1aee7e30070ac95bc63b68c10bd7253b02ad0749aaba8b833466dfcbb0428e4f89c"></span> `SUCCESS` | Request succeeded. 
<span id="classdronecore_1_1_follow_me_1aee7e30070ac95bc63b68c10bd7253b02a23514014e50da2b2583cae24ab1ecd88"></span> `NO_DEVICE` | No device connected. 
<span id="classdronecore_1_1_follow_me_1aee7e30070ac95bc63b68c10bd7253b02ac77f1f09dab2c0c9980fca7cfae02518"></span> `CONNECTION_ERROR` | Connection error. 
<span id="classdronecore_1_1_follow_me_1aee7e30070ac95bc63b68c10bd7253b02a802706a9238e2928077f97736854bad4"></span> `BUSY` | Vehicle busy. 
<span id="classdronecore_1_1_follow_me_1aee7e30070ac95bc63b68c10bd7253b02a6fa4dbf368cea972db8d9156799d5dbe"></span> `COMMAND_DENIED` | Command denied. 
<span id="classdronecore_1_1_follow_me_1aee7e30070ac95bc63b68c10bd7253b02a070a0fb40f6c308ab544b227660aadff"></span> `TIMEOUT` | Request timeout. 
<span id="classdronecore_1_1_follow_me_1aee7e30070ac95bc63b68c10bd7253b02a1b2fe1358d26a4a36841de06904bc0e3"></span> `NOT_ACTIVE` | [FollowMe](classdronecore_1_1_follow_me.md) is not activated. 
<span id="classdronecore_1_1_follow_me_1aee7e30070ac95bc63b68c10bd7253b02a696b031073e74bf2cb98e5ef201d4aa3"></span> `UNKNOWN` | Unknown error. 

**See Also:**
- [result_str()](classdronecore_1_1_follow_me.md#classdronecore_1_1_follow_me_1a50d848b1c7b00e40343b8d62593ca307)


## Member Function Documentation


### get_config() {#classdronecore_1_1_follow_me_1a054aebafe0839a1028f277285b769fe5}
```cpp
const Config& dronecore::FollowMe::get_config() const
```


Gets current [FollowMe](classdronecore_1_1_follow_me.md) configuration.


**Returns**

&emsp;const [Config](structdronecore_1_1_follow_me_1_1_config.md) & - Current [FollowMe](classdronecore_1_1_follow_me.md) configuration.

**See Also:**
- [set_config()](classdronecore_1_1_follow_me.md#classdronecore_1_1_follow_me_1a4b92c3a042911dd9bdb378c686458a34)


### set_config() {#classdronecore_1_1_follow_me_1a4b92c3a042911dd9bdb378c686458a34}
```cpp
bool dronecore::FollowMe::set_config(const Config &config)
```


Applies [FollowMe](classdronecore_1_1_follow_me.md) configuration by sending it to device.


**Parameters**

* const [Config](structdronecore_1_1_follow_me_1_1_config.md) & **config** - [FollowMe](classdronecore_1_1_follow_me.md) configuration to be applied.

**Returns**

&emsp;bool - `true` if configuration is applied successfully, `false` if config values are out-of-range. In case of failure, last configuration is preserved.

**See Also:**
- [get_config()](classdronecore_1_1_follow_me.md#classdronecore_1_1_follow_me_1a054aebafe0839a1028f277285b769fe5)


### is_active() {#classdronecore_1_1_follow_me_1a467349820ac5f42cc388228c399a93ef}
```cpp
bool dronecore::FollowMe::is_active() const
```


Checks whether [FollowMe](classdronecore_1_1_follow_me.md) is active.


**Returns**

&emsp;bool - `true` if [FollowMe](classdronecore_1_1_follow_me.md) is active, `false` otherwise.

### set_curr_target_location() {#classdronecore_1_1_follow_me_1afb8c24ed93421e904b0f528569c7699a}
```cpp
void dronecore::FollowMe::set_curr_target_location(const TargetLocation &location)
```


Sets current location of the moving target App can obtain location of the moving target from Location framework of the underlying platform.

**Notes:**


The following links provide information about location services on different platforms:
<ul>

<li><p>Android - <a href="https://developer.android.com/reference/android/location/Location.html">https://developer.android.com/reference/android/location/Location.html</a></p></li>
<li><p>Apple - <a href="https://developer.apple.com/documentation/corelocation">https://developer.apple.com/documentation/corelocation</a></p></li>
<li><p>Windows - <a href="https://docs.microsoft.com/en-us/uwp/api/Windows.Devices.Geolocation">https://docs.microsoft.com/en-us/uwp/api/Windows.Devices.Geolocation</a></p></li></ul>

**Parameters**

* const [TargetLocation](structdronecore_1_1_follow_me_1_1_target_location.md) & **location** - Current location of the target.

**See Also:**
- [get_last_location()](classdronecore_1_1_follow_me.md#classdronecore_1_1_follow_me_1ab68273d5ace65ee953afa1797ae49e7c)


### get_last_location() {#classdronecore_1_1_follow_me_1ab68273d5ace65ee953afa1797ae49e7c}
```cpp
void dronecore::FollowMe::get_last_location(TargetLocation &last_location)
```


Returns the most recent location of the target.


**Parameters**

* [TargetLocation](structdronecore_1_1_follow_me_1_1_target_location.md) & **last_location** - Last location to be filled.

**See Also:**
- [set_curr_target_location()](classdronecore_1_1_follow_me.md#classdronecore_1_1_follow_me_1afb8c24ed93421e904b0f528569c7699a)


### start() {#classdronecore_1_1_follow_me_1a694749d43d527f85584df25a49b05ccf}
```cpp
FollowMe::Result dronecore::FollowMe::start() const
```


Starts [FollowMe](classdronecore_1_1_follow_me.md) mode.


**Returns**

&emsp;[FollowMe::Result](classdronecore_1_1_follow_me.md#classdronecore_1_1_follow_me_1aee7e30070ac95bc63b68c10bd7253b02) - [FollowMe::Result::SUCCESS](classdronecore_1_1_follow_me.md#classdronecore_1_1_follow_me_1aee7e30070ac95bc63b68c10bd7253b02ad0749aaba8b833466dfcbb0428e4f89c) if succeeded, error otherwise.

### stop() {#classdronecore_1_1_follow_me_1a6394507b0fb96bceebe6efd17f0529ce}
```cpp
FollowMe::Result dronecore::FollowMe::stop() const
```


Stops [FollowMe](classdronecore_1_1_follow_me.md) mode.


**Returns**

&emsp;[FollowMe::Result](classdronecore_1_1_follow_me.md#classdronecore_1_1_follow_me_1aee7e30070ac95bc63b68c10bd7253b02) - [FollowMe::Result::SUCCESS](classdronecore_1_1_follow_me.md#classdronecore_1_1_follow_me_1aee7e30070ac95bc63b68c10bd7253b02ad0749aaba8b833466dfcbb0428e4f89c) if succeeded, error otherwise. See [FollowMe::Result](classdronecore_1_1_follow_me.md#classdronecore_1_1_follow_me_1aee7e30070ac95bc63b68c10bd7253b02) for error codes.

### operator=() {#classdronecore_1_1_follow_me_1accb454508e051d79b2943ba469958f9e}
```cpp
const FollowMe& dronecore::FollowMe::operator=(const FollowMe &)=delete
```


Equality operator (object is not copyable).


**Parameters**

* const [FollowMe](classdronecore_1_1_follow_me.md) & - 

**Returns**

&emsp;const [FollowMe](classdronecore_1_1_follow_me.md) & - 

### result_str() {#classdronecore_1_1_follow_me_1a50d848b1c7b00e40343b8d62593ca307}
```cpp
static std::string dronecore::FollowMe::result_str(Result result)
```


Returns English string for [FollowMe](classdronecore_1_1_follow_me.md) error codes.


**Parameters**

* [Result](classdronecore_1_1_follow_me.md#classdronecore_1_1_follow_me_1aee7e30070ac95bc63b68c10bd7253b02) **result** - [Result](classdronecore_1_1_follow_me.md#classdronecore_1_1_follow_me_1aee7e30070ac95bc63b68c10bd7253b02) code.

**Returns**

&emsp;std::string - Returns std::string describing error code.