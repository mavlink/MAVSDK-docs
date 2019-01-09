# dronecode_sdk::Info Class Reference
`#include: info.h`

----


The [Info](classdronecode__sdk_1_1_info.md) class provides basic infomation about the hardware and/or software of a system. 


## Data Structures


struct [Identification](structdronecode__sdk_1_1_info_1_1_identification.md)

struct [Product](structdronecode__sdk_1_1_info_1_1_product.md)

struct [Version](structdronecode__sdk_1_1_info_1_1_version.md)

## Public Types


Type | Description
--- | ---
enum [Result](#classdronecode__sdk_1_1_info_1ae09075d43cda9c7b617dbcb01102eee9) | Possible results returned for requests.

## Public Member Functions


Type | Name | Description
---: | --- | ---
&nbsp; | [Info](#classdronecode__sdk_1_1_info_1ae943f4e7d0ca0bfd07a9eeb51f70dc31) ([System](classdronecode__sdk_1_1_system.md) & system) | Constructor. Creates the plugin for a specific [System](classdronecode__sdk_1_1_system.md).
&nbsp; | [~Info](#classdronecode__sdk_1_1_info_1a65fa131293c5a567ad8c410bae6b8c25) () | Destructor (internal use only).
&nbsp; | [Info](#classdronecode__sdk_1_1_info_1a157860dd0494775070965393a4dbf40a) (const [Info](classdronecode__sdk_1_1_info.md) &)=delete | Copy Constructor (object is not copyable).
std::pair< [Result](classdronecode__sdk_1_1_info.md#classdronecode__sdk_1_1_info_1ae09075d43cda9c7b617dbcb01102eee9), [Identification](structdronecode__sdk_1_1_info_1_1_identification.md) > | [get_identification](#classdronecode__sdk_1_1_info_1aedebb22d4c5951f80d68b3c99457fc67) () const | Gets the identification of the system.
std::pair< [Result](classdronecode__sdk_1_1_info.md#classdronecode__sdk_1_1_info_1ae09075d43cda9c7b617dbcb01102eee9), [Version](structdronecode__sdk_1_1_info_1_1_version.md) > | [get_version](#classdronecode__sdk_1_1_info_1ac61216d58d9f806b2f0c86061a449a55) () const | Get system version information.
std::pair< [Result](classdronecode__sdk_1_1_info.md#classdronecode__sdk_1_1_info_1ae09075d43cda9c7b617dbcb01102eee9), [Product](structdronecode__sdk_1_1_info_1_1_product.md) > | [get_product](#classdronecode__sdk_1_1_info_1aa1102ede7d9b6edaf33396ee17e12859) () const | Get system product information.
const [Info](classdronecode__sdk_1_1_info.md) & | [operator=](#classdronecode__sdk_1_1_info_1a7b19c97d51e77ac7eafa69418677b578) (const [Info](classdronecode__sdk_1_1_info.md) &)=delete | Equality operator (object is not copyable).

## Static Public Attributes


static const unsigned [GIT_HASH_STR_LEN](#classdronecode__sdk_1_1_info_1aa708e5ebc77ebce409a1c4c3bef7cc98) = 17 - Length of git hash strings.


## Static Public Member Functions


Type | Name | Description
---: | --- | ---
std::string | [result_str](#classdronecode__sdk_1_1_info_1ac28cc1d3d0f2715f5209106b327a5c9f) ([Result](classdronecode__sdk_1_1_info.md#classdronecode__sdk_1_1_info_1ae09075d43cda9c7b617dbcb01102eee9) result) | Returns a human-readable English string for an Result.


## Constructor & Destructor Documentation


### Info() {#classdronecode__sdk_1_1_info_1ae943f4e7d0ca0bfd07a9eeb51f70dc31}
```cpp
dronecode_sdk::Info::Info(System &system)
```


Constructor. Creates the plugin for a specific [System](classdronecode__sdk_1_1_system.md).

The plugin is typically created as shown below: 

```cpp
auto info = std::make_shared<Info>(system);
```

**Parameters**

* [System](classdronecode__sdk_1_1_system.md)& **system** - The specific system associated with this plugin.

### ~Info() {#classdronecode__sdk_1_1_info_1a65fa131293c5a567ad8c410bae6b8c25}
```cpp
dronecode_sdk::Info::~Info()
```


Destructor (internal use only).


### Info() {#classdronecode__sdk_1_1_info_1a157860dd0494775070965393a4dbf40a}
```cpp
dronecode_sdk::Info::Info(const Info &)=delete
```


Copy Constructor (object is not copyable).


**Parameters**

* const [Info](classdronecode__sdk_1_1_info.md)&  - 

## Member Enumeration Documentation


### enum Result {#classdronecode__sdk_1_1_info_1ae09075d43cda9c7b617dbcb01102eee9}


Possible results returned for requests.

> **Note** [DronecodeSDK](classdronecode__sdk_1_1_dronecode_s_d_k.md) does not throw exceptions. Instead a result of this type will be returned.

Value | Description
--- | ---
<span id="classdronecode__sdk_1_1_info_1ae09075d43cda9c7b617dbcb01102eee9a696b031073e74bf2cb98e5ef201d4aa3"></span> `UNKNOWN` | Unspecified error. 
<span id="classdronecode__sdk_1_1_info_1ae09075d43cda9c7b617dbcb01102eee9ad0749aaba8b833466dfcbb0428e4f89c"></span> `SUCCESS` | The request was successful. 
<span id="classdronecode__sdk_1_1_info_1ae09075d43cda9c7b617dbcb01102eee9af5b6f062a23d25fc902f8c5173aaf877"></span> `INFORMATION_NOT_RECEIVED_YET` | The information has not been received yet. 

## Member Function Documentation


### get_identification() {#classdronecode__sdk_1_1_info_1aedebb22d4c5951f80d68b3c99457fc67}
```cpp
std::pair<Result, Identification> dronecode_sdk::Info::get_identification() const
```


Gets the identification of the system.

If possible this will be a unique identifier provided by hardware.

**Returns**

&emsp;std::pair< [Result](classdronecode__sdk_1_1_info.md#classdronecode__sdk_1_1_info_1ae09075d43cda9c7b617dbcb01102eee9), [Identification](structdronecode__sdk_1_1_info_1_1_identification.md) > - a pair containing the result of the request and if successful, the identification information of the system.

### get_version() {#classdronecode__sdk_1_1_info_1ac61216d58d9f806b2f0c86061a449a55}
```cpp
std::pair<Result, Version> dronecode_sdk::Info::get_version() const
```


Get system version information.


**Returns**

&emsp;std::pair< [Result](classdronecode__sdk_1_1_info.md#classdronecode__sdk_1_1_info_1ae09075d43cda9c7b617dbcb01102eee9), [Version](structdronecode__sdk_1_1_info_1_1_version.md) > - a pair containing the result of the request and if successful, the version information about the system.

### get_product() {#classdronecode__sdk_1_1_info_1aa1102ede7d9b6edaf33396ee17e12859}
```cpp
std::pair<Result, Product> dronecode_sdk::Info::get_product() const
```


Get system product information.


**Returns**

&emsp;std::pair< [Result](classdronecode__sdk_1_1_info.md#classdronecode__sdk_1_1_info_1ae09075d43cda9c7b617dbcb01102eee9), [Product](structdronecode__sdk_1_1_info_1_1_product.md) > - a pair containing the result of the request and if successful, the product information about the system.

### operator=() {#classdronecode__sdk_1_1_info_1a7b19c97d51e77ac7eafa69418677b578}
```cpp
const Info& dronecode_sdk::Info::operator=(const Info &)=delete
```


Equality operator (object is not copyable).


**Parameters**

* const [Info](classdronecode__sdk_1_1_info.md)&  - 

**Returns**

&emsp;const [Info](classdronecode__sdk_1_1_info.md) & - 

### result_str() {#classdronecode__sdk_1_1_info_1ac28cc1d3d0f2715f5209106b327a5c9f}
```cpp
static std::string dronecode_sdk::Info::result_str(Result result)
```


Returns a human-readable English string for an Result.


**Parameters**

* [Result](classdronecode__sdk_1_1_info.md#classdronecode__sdk_1_1_info_1ae09075d43cda9c7b617dbcb01102eee9) **result** - The enum value for which a human readable string is required.

**Returns**

&emsp;std::string - Human readable string for the Result.

## Field Documentation


### GIT_HASH_STR_LEN {#classdronecode__sdk_1_1_info_1aa708e5ebc77ebce409a1c4c3bef7cc98}

```cpp
const unsigned dronecode_sdk::Info::GIT_HASH_STR_LEN = 17
```


Length of git hash strings.

Length is 16 chars + null termination.