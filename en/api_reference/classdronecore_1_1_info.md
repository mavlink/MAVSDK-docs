# dronecore::Info Class Reference
`#include: info.h`

----


The [Info](classdronecore_1_1_info.md) class provides basic infomation about the hardware and/or software of a device. 


## Data Structures


struct [Version](structdronecore_1_1_info_1_1_version.md)

## Public Member Functions


Type | Name | Description
---: | --- | ---
| [Info](#classdronecore_1_1_info_1ab2433f8a05d19782a7d464dac9f02ade) (InfoImpl *impl) | Constructor (internal use only).
| [~Info](#classdronecore_1_1_info_1a39e608070500b5fca0b4415cdb13f75f) () | Destructor (internal use only).
| [Info](#classdronecore_1_1_info_1af0902805d75577d1195363eda21d7bb1) (const Info &)=delete | Copy Constructor (object is not copyable).
uint64_t | [uuid](#classdronecore_1_1_info_1a49c7dd5f1a369c8296f0c3a2443bc031) () const | Gets the UUID of the device.
bool | [is_complete](#classdronecore_1_1_info_1a088438b73c715fb20c02792fed1815f7) () const | Tests if this [Version](structdronecore_1_1_info_1_1_version.md) object is fully populated from hardware.
[Version](structdronecore_1_1_info_1_1_version.md) | [get_version](#classdronecore_1_1_info_1a6e41fae8c6ad352e70b1e93b4a1589f9) () const | Get device version information.
const [Info](classdronecore_1_1_info.md) & | [operator=](#classdronecore_1_1_info_1ac82758b486f00562e193a89e3dbff6d3) (const Info &)=delete | Equality operator (object is not copyable).

## Static Public Attributes


static const unsigned [GIT_HASH_STR_LEN](#classdronecore_1_1_info_1aae671143f80e43d2f431e7fe0d3774fd)= 17 - Length of git hash strings.


## Constructor & Destructor Documentation


### Info() {#classdronecore_1_1_info_1ab2433f8a05d19782a7d464dac9f02ade}
```cpp
dronecore::Info::Info(InfoImpl *impl)
```


Constructor (internal use only).


**Parameters**

* InfoImpl * **impl** - 

### ~Info() {#classdronecore_1_1_info_1a39e608070500b5fca0b4415cdb13f75f}
```cpp
dronecore::Info::~Info()
```


Destructor (internal use only).


### Info() {#classdronecore_1_1_info_1af0902805d75577d1195363eda21d7bb1}
```cpp
dronecore::Info::Info(const Info &)=delete
```


Copy Constructor (object is not copyable).


**Parameters**

* const [Info](classdronecore_1_1_info.md) & - 

## Member Function Documentation


### uuid() {#classdronecore_1_1_info_1a49c7dd5f1a369c8296f0c3a2443bc031}
```cpp
uint64_t dronecore::Info::uuid() const
```


Gets the UUID of the device.

If possible this will be a unique identifier provided by hardware.

**Returns**

&emsp;uint64_t - The UUID of the device.

### is_complete() {#classdronecore_1_1_info_1a088438b73c715fb20c02792fed1815f7}
```cpp
bool dronecore::Info::is_complete() const
```


Tests if this [Version](structdronecore_1_1_info_1_1_version.md) object is fully populated from hardware.


**Returns**

&emsp;bool - `true` if [Version](structdronecore_1_1_info_1_1_version.md) object is fully populated from device.

### get_version() {#classdronecore_1_1_info_1a6e41fae8c6ad352e70b1e93b4a1589f9}
```cpp
Version dronecore::Info::get_version() const
```


Get device version information.


**Returns**

&emsp;[Version](structdronecore_1_1_info_1_1_version.md) - The version object for the device.

### operator=() {#classdronecore_1_1_info_1ac82758b486f00562e193a89e3dbff6d3}
```cpp
const Info& dronecore::Info::operator=(const Info &)=delete
```


Equality operator (object is not copyable).


**Parameters**

* const [Info](classdronecore_1_1_info.md) & - 

**Returns**

&emsp;const [Info](classdronecore_1_1_info.md) & - 

## Field Documentation


### GIT_HASH_STR_LEN {#classdronecore_1_1_info_1aae671143f80e43d2f431e7fe0d3774fd}

```cpp
const unsigned dronecore::Info::GIT_HASH_STR_LEN= 17
```


Length of git hash strings.

Length is 16 chars + null termination.