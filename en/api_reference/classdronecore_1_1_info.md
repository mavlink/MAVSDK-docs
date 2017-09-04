# dronecore::Info Class Reference
`#include: info.h`

----


The [Info](classdronecore_1_1_info.md) class provides basic info about the hardware and/or software of a device. 


## Data Structures


struct [Version](structdronecore_1_1_info_1_1_version.md)

## Public Member Functions


Type | Name | Description
---: | --- | ---
| [Info](#classdronecore_1_1_info_1ab2433f8a05d19782a7d464dac9f02ade) (InfoImpl *impl) | Constructor (internal use only).
| [~Info](#classdronecore_1_1_info_1a39e608070500b5fca0b4415cdb13f75f) () | Destructor (internal use only).
| [Info](#classdronecore_1_1_info_1af0902805d75577d1195363eda21d7bb1) (const Info &)=delete | Copy Constructor (object is not copyable).
uint64_t | [uuid](#classdronecore_1_1_info_1a1e64e8d3c1d1ffd6b7877fc447d57530) () const | Gets the UUID of the device.
bool | [is_complete](#classdronecore_1_1_info_1a31d294193e6c13de43f19d3c01b846eb) () const | Tests if this [Version](structdronecore_1_1_info_1_1_version.md) object is fully populated from hardware.
[Version](structdronecore_1_1_info_1_1_version.md) | [get_version](#classdronecore_1_1_info_1a8d9796f910f346a3b67a5f3a3fb78291) () const | Get device version information.
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

* [InfoImpl](classdronecore_1_1_info_impl.md) * **impl** - 

<!-- inbodydescription:  --> 
<!-- return_type:  -->
<!-- return_type_comment:  -->
<!-- prot: public -->
<!-- static: no -->
<!-- const: no -->
<!-- explicit: yes -->
<!-- virt: non-virtual -->
<!-- inline: no -->


### ~Info() {#classdronecore_1_1_info_1a39e608070500b5fca0b4415cdb13f75f}
```cpp
dronecore::Info::~Info()
```


Destructor (internal use only).


<!-- inbodydescription:  --> 
<!-- return_type:  -->
<!-- return_type_comment:  -->
<!-- prot: public -->
<!-- static: no -->
<!-- const: no -->
<!-- explicit: no -->
<!-- virt: non-virtual -->
<!-- inline: no -->


### Info() {#classdronecore_1_1_info_1af0902805d75577d1195363eda21d7bb1}
```cpp
dronecore::Info::Info(const Info &)=delete
```


Copy Constructor (object is not copyable).


**Parameters**

* const [Info](classdronecore_1_1_info.md) & **** - 

<!-- inbodydescription:  --> 
<!-- return_type:  -->
<!-- return_type_comment:  -->
<!-- prot: public -->
<!-- static: no -->
<!-- const: no -->
<!-- explicit: no -->
<!-- virt: non-virtual -->
<!-- inline: no -->

## Member Function Documentation


### uuid() {#classdronecore_1_1_info_1a1e64e8d3c1d1ffd6b7877fc447d57530}
```cpp
uint64_t dronecore::Info::uuid() const
```


Gets the UUID of the device.

If possible this will be a unique identifier provided by hardware.

**Returns**

&emsp;uint64_t - The UUID of the device.

<!-- inbodydescription:  --> 
<!-- return_type: uint64_t -->
<!-- return_type_comment: The UUID of the device. -->
<!-- prot: public -->
<!-- static: no -->
<!-- const: yes -->
<!-- explicit: no -->
<!-- virt: non-virtual -->
<!-- inline: no -->


### is_complete() {#classdronecore_1_1_info_1a31d294193e6c13de43f19d3c01b846eb}
```cpp
bool dronecore::Info::is_complete() const
```


Tests if this [Version](structdronecore_1_1_info_1_1_version.md) object is fully populated from hardware.


**Returns**

&emsp;bool - true if [Version](structdronecore_1_1_info_1_1_version.md) object is fully populated from device.

<!-- inbodydescription:  --> 
<!-- return_type: bool -->
<!-- return_type_comment: true if [Version](structdronecore_1_1_info_1_1_version.md) object is fully populated from device. -->
<!-- prot: public -->
<!-- static: no -->
<!-- const: yes -->
<!-- explicit: no -->
<!-- virt: non-virtual -->
<!-- inline: no -->


### get_version() {#classdronecore_1_1_info_1a8d9796f910f346a3b67a5f3a3fb78291}
```cpp
Info::Version dronecore::Info::get_version() const
```


Get device version information.


**Returns**

&emsp;[Version](structdronecore_1_1_info_1_1_version.md) - The version object for the device.

<!-- inbodydescription:  --> 
<!-- return_type: [Version](structdronecore_1_1_info_1_1_version.md) -->
<!-- return_type_comment: The version object for the device. -->
<!-- prot: public -->
<!-- static: no -->
<!-- const: yes -->
<!-- explicit: no -->
<!-- virt: non-virtual -->
<!-- inline: no -->


### operator=() {#classdronecore_1_1_info_1ac82758b486f00562e193a89e3dbff6d3}
```cpp
const Info& dronecore::Info::operator=(const Info &)=delete
```


Equality operator (object is not copyable).


**Parameters**

* const [Info](classdronecore_1_1_info.md) & **** - 

**Returns**

&emsp;const [Info](classdronecore_1_1_info.md) & - 

<!-- inbodydescription:  --> 
<!-- return_type: const [Info](classdronecore_1_1_info.md) & -->
<!-- return_type_comment:  -->
<!-- prot: public -->
<!-- static: no -->
<!-- const: no -->
<!-- explicit: no -->
<!-- virt: non-virtual -->
<!-- inline: no -->

## Field Documentation


### GIT_HASH_STR_LEN {#classdronecore_1_1_info_1aae671143f80e43d2f431e7fe0d3774fd}

```cpp
const unsigned dronecore::Info::GIT_HASH_STR_LEN= 17
```


Length of git hash strings.

Length is 16 chars + null termination.

<!-- [<Element 'type' at 0x000001F32A2F7A48> GIT_HASH_STR_LEN](#classdronecore_1_1_info_1aae671143f80e43d2f431e7fe0d3774fd) -->
<!-- kind: variable -->
<!-- prot: public -->
<!-- static: yes -->
<!-- mutable: no -->
<!-- definition: const unsigned dronecore::Info::GIT_HASH_STR_LEN -->
<!-- detaileddescription: Length is 16 chars + null termination. -->
<!-- briefdescription: Length of git hash strings. -->

<!-- argsstring:  -->
