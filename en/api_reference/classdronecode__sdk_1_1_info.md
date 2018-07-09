# dronecode_sdk::Info Class Reference
`#include: info.h`

----


The [Info](classdronecode__sdk_1_1_info.md) class provides basic infomation about the hardware and/or software of a system. 


## Data Structures


struct [Product](structdronecode__sdk_1_1_info_1_1_product.md)

struct [Version](structdronecode__sdk_1_1_info_1_1_version.md)

## Public Member Functions


Type | Name | Description
---: | --- | ---
&nbsp; | [Info](#classdronecode__sdk_1_1_info_1ae943f4e7d0ca0bfd07a9eeb51f70dc31) ([System](classdronecode__sdk_1_1_system.md) & system) | Constructor. Creates the plugin for a specific [System](classdronecode__sdk_1_1_system.md).
&nbsp; | [~Info](#classdronecode__sdk_1_1_info_1a65fa131293c5a567ad8c410bae6b8c25) () | Destructor (internal use only).
&nbsp; | [Info](#classdronecode__sdk_1_1_info_1a157860dd0494775070965393a4dbf40a) (const [Info](classdronecode__sdk_1_1_info.md) &)=delete | Copy Constructor (object is not copyable).
uint64_t | [uuid](#classdronecode__sdk_1_1_info_1a38f1b08ee69a4dbfc22a79ddf6a20ce4) () const | Gets the UUID of the system.
bool | [is_complete](#classdronecode__sdk_1_1_info_1ae62c038fbdc9745a30d4a74954ed5e2d) () const | Tests if the [Version](structdronecode__sdk_1_1_info_1_1_version.md) and [Product](structdronecode__sdk_1_1_info_1_1_product.md) objects are fully populated from hardware.
[Version](structdronecode__sdk_1_1_info_1_1_version.md) | [get_version](#classdronecode__sdk_1_1_info_1aa6a391957d79965ee6ac98b94f189655) () const | Get system version information.
[Product](structdronecode__sdk_1_1_info_1_1_product.md) | [get_product](#classdronecode__sdk_1_1_info_1a219585dff33dd305fd22ee7f741a7f2a) () const | Get system product information.
const [Info](classdronecode__sdk_1_1_info.md) & | [operator=](#classdronecode__sdk_1_1_info_1a7b19c97d51e77ac7eafa69418677b578) (const [Info](classdronecode__sdk_1_1_info.md) &)=delete | Equality operator (object is not copyable).

## Static Public Attributes


static const unsigned [GIT_HASH_STR_LEN](#classdronecode__sdk_1_1_info_1aa708e5ebc77ebce409a1c4c3bef7cc98) = 17 - Length of git hash strings.


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

## Member Function Documentation


### uuid() {#classdronecode__sdk_1_1_info_1a38f1b08ee69a4dbfc22a79ddf6a20ce4}
```cpp
uint64_t dronecode_sdk::Info::uuid() const
```


Gets the UUID of the system.

If possible this will be a unique identifier provided by hardware.

**Returns**

&emsp;uint64_t - The UUID of the system.

### is_complete() {#classdronecode__sdk_1_1_info_1ae62c038fbdc9745a30d4a74954ed5e2d}
```cpp
bool dronecode_sdk::Info::is_complete() const
```


Tests if the [Version](structdronecode__sdk_1_1_info_1_1_version.md) and [Product](structdronecode__sdk_1_1_info_1_1_product.md) objects are fully populated from hardware.


**Returns**

&emsp;bool - `true` if [Version](structdronecode__sdk_1_1_info_1_1_version.md) and [Product](structdronecode__sdk_1_1_info_1_1_product.md) objects are fully populated from system.

### get_version() {#classdronecode__sdk_1_1_info_1aa6a391957d79965ee6ac98b94f189655}
```cpp
Version dronecode_sdk::Info::get_version() const
```


Get system version information.


**Returns**

&emsp;[Version](structdronecode__sdk_1_1_info_1_1_version.md) - The version object for the system.

### get_product() {#classdronecode__sdk_1_1_info_1a219585dff33dd305fd22ee7f741a7f2a}
```cpp
Product dronecode_sdk::Info::get_product() const
```


Get system product information.


**Returns**

&emsp;[Product](structdronecode__sdk_1_1_info_1_1_product.md) - The product object for the system.

### operator=() {#classdronecode__sdk_1_1_info_1a7b19c97d51e77ac7eafa69418677b578}
```cpp
const Info& dronecode_sdk::Info::operator=(const Info &)=delete
```


Equality operator (object is not copyable).


**Parameters**

* const [Info](classdronecode__sdk_1_1_info.md)&  - 

**Returns**

&emsp;const [Info](classdronecode__sdk_1_1_info.md) & - 

## Field Documentation


### GIT_HASH_STR_LEN {#classdronecode__sdk_1_1_info_1aa708e5ebc77ebce409a1c4c3bef7cc98}

```cpp
const unsigned dronecode_sdk::Info::GIT_HASH_STR_LEN = 17
```


Length of git hash strings.

Length is 16 chars + null termination.