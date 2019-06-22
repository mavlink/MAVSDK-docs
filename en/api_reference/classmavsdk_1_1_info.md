# mavsdk::Info Class Reference
`#include: info.h`

----


The [Info](classmavsdk_1_1_info.md) class provides basic infomation about the hardware and/or software of a system. 


## Data Structures


struct [Identification](structmavsdk_1_1_info_1_1_identification.md)

struct [Product](structmavsdk_1_1_info_1_1_product.md)

struct [Version](structmavsdk_1_1_info_1_1_version.md)

## Public Types


Type | Description
--- | ---
enum [Result](#classmavsdk_1_1_info_1ab1798ed39271915800b25aaa05d1d45a) | Possible results returned for requests.

## Public Member Functions


Type | Name | Description
---: | --- | ---
&nbsp; | [Info](#classmavsdk_1_1_info_1a01a29a579c8ecb75ea73d48f8f6adf17) ([System](classmavsdk_1_1_system.md) & system) | Constructor. Creates the plugin for a specific [System](classmavsdk_1_1_system.md).
&nbsp; | [~Info](#classmavsdk_1_1_info_1a2681cccfa006f9ea4f4eb9e498a83c04) () | Destructor (internal use only).
&nbsp; | [Info](#classmavsdk_1_1_info_1a672404baf7e8da437b36b34dff290d2f) (const [Info](classmavsdk_1_1_info.md) &)=delete | Copy Constructor (object is not copyable).
std::pair< [Result](classmavsdk_1_1_info.md#classmavsdk_1_1_info_1ab1798ed39271915800b25aaa05d1d45a), [Identification](structmavsdk_1_1_info_1_1_identification.md) > | [get_identification](#classmavsdk_1_1_info_1a5b51b6a67aebfb61ba1d287627efad4c) () const | Gets the identification of the system.
std::pair< [Result](classmavsdk_1_1_info.md#classmavsdk_1_1_info_1ab1798ed39271915800b25aaa05d1d45a), [Version](structmavsdk_1_1_info_1_1_version.md) > | [get_version](#classmavsdk_1_1_info_1ac0766bb482354bbdae60dfe086311933) () const | Get system version information.
std::pair< [Result](classmavsdk_1_1_info.md#classmavsdk_1_1_info_1ab1798ed39271915800b25aaa05d1d45a), [Product](structmavsdk_1_1_info_1_1_product.md) > | [get_product](#classmavsdk_1_1_info_1a4f1fe91a6cae12a9d78294dcaca26d4c) () const | Get system product information.
const [Info](classmavsdk_1_1_info.md) & | [operator=](#classmavsdk_1_1_info_1a586eb91fd65d602bad1d016dca42b435) (const [Info](classmavsdk_1_1_info.md) &)=delete | Equality operator (object is not copyable).

## Static Public Attributes


static const unsigned [GIT_HASH_STR_LEN](#classmavsdk_1_1_info_1af6cfc083dd14c211b50aff06ffe30718) = 17 - Length of git hash strings.


## Static Public Member Functions


Type | Name | Description
---: | --- | ---
std::string | [result_str](#classmavsdk_1_1_info_1a65a75472cee84487769c740b83f8ffc3) ([Result](classmavsdk_1_1_info.md#classmavsdk_1_1_info_1ab1798ed39271915800b25aaa05d1d45a) result) | Returns a human-readable English string for an Result.


## Constructor & Destructor Documentation


### Info() {#classmavsdk_1_1_info_1a01a29a579c8ecb75ea73d48f8f6adf17}
```cpp
mavsdk::Info::Info(System &system)
```


Constructor. Creates the plugin for a specific [System](classmavsdk_1_1_system.md).

The plugin is typically created as shown below: 

```cpp
auto info = std::make_shared<Info>(system);
```

**Parameters**

* [System](classmavsdk_1_1_system.md)& **system** - The specific system associated with this plugin.

### ~Info() {#classmavsdk_1_1_info_1a2681cccfa006f9ea4f4eb9e498a83c04}
```cpp
mavsdk::Info::~Info()
```


Destructor (internal use only).


### Info() {#classmavsdk_1_1_info_1a672404baf7e8da437b36b34dff290d2f}
```cpp
mavsdk::Info::Info(const Info &)=delete
```


Copy Constructor (object is not copyable).


**Parameters**

* const [Info](classmavsdk_1_1_info.md)&  - 

## Member Enumeration Documentation


### enum Result {#classmavsdk_1_1_info_1ab1798ed39271915800b25aaa05d1d45a}


Possible results returned for requests.

> **Note** [Mavsdk](classmavsdk_1_1_mavsdk.md) does not throw exceptions. Instead a result of this type will be returned.

Value | Description
--- | ---
<span id="classmavsdk_1_1_info_1ab1798ed39271915800b25aaa05d1d45aa696b031073e74bf2cb98e5ef201d4aa3"></span> `UNKNOWN` | Unspecified error. 
<span id="classmavsdk_1_1_info_1ab1798ed39271915800b25aaa05d1d45aad0749aaba8b833466dfcbb0428e4f89c"></span> `SUCCESS` | The request was successful. 
<span id="classmavsdk_1_1_info_1ab1798ed39271915800b25aaa05d1d45aaf5b6f062a23d25fc902f8c5173aaf877"></span> `INFORMATION_NOT_RECEIVED_YET` | The information has not been received yet. 

## Member Function Documentation


### get_identification() {#classmavsdk_1_1_info_1a5b51b6a67aebfb61ba1d287627efad4c}
```cpp
std::pair<Result, Identification> mavsdk::Info::get_identification() const
```


Gets the identification of the system.

If possible this will be a unique identifier provided by hardware.

**Returns**

&emsp;std::pair< [Result](classmavsdk_1_1_info.md#classmavsdk_1_1_info_1ab1798ed39271915800b25aaa05d1d45a), [Identification](structmavsdk_1_1_info_1_1_identification.md) > - a pair containing the result of the request and if successful, the identification information of the system.

### get_version() {#classmavsdk_1_1_info_1ac0766bb482354bbdae60dfe086311933}
```cpp
std::pair<Result, Version> mavsdk::Info::get_version() const
```


Get system version information.


**Returns**

&emsp;std::pair< [Result](classmavsdk_1_1_info.md#classmavsdk_1_1_info_1ab1798ed39271915800b25aaa05d1d45a), [Version](structmavsdk_1_1_info_1_1_version.md) > - a pair containing the result of the request and if successful, the version information about the system.

### get_product() {#classmavsdk_1_1_info_1a4f1fe91a6cae12a9d78294dcaca26d4c}
```cpp
std::pair<Result, Product> mavsdk::Info::get_product() const
```


Get system product information.


**Returns**

&emsp;std::pair< [Result](classmavsdk_1_1_info.md#classmavsdk_1_1_info_1ab1798ed39271915800b25aaa05d1d45a), [Product](structmavsdk_1_1_info_1_1_product.md) > - a pair containing the result of the request and if successful, the product information about the system.

### operator=() {#classmavsdk_1_1_info_1a586eb91fd65d602bad1d016dca42b435}
```cpp
const Info& mavsdk::Info::operator=(const Info &)=delete
```


Equality operator (object is not copyable).


**Parameters**

* const [Info](classmavsdk_1_1_info.md)&  - 

**Returns**

&emsp;const [Info](classmavsdk_1_1_info.md) & - 

### result_str() {#classmavsdk_1_1_info_1a65a75472cee84487769c740b83f8ffc3}
```cpp
static std::string mavsdk::Info::result_str(Result result)
```


Returns a human-readable English string for an Result.


**Parameters**

* [Result](classmavsdk_1_1_info.md#classmavsdk_1_1_info_1ab1798ed39271915800b25aaa05d1d45a) **result** - The enum value for which a human readable string is required.

**Returns**

&emsp;std::string - Human readable string for the Result.

## Field Documentation


### GIT_HASH_STR_LEN {#classmavsdk_1_1_info_1af6cfc083dd14c211b50aff06ffe30718}

```cpp
const unsigned mavsdk::Info::GIT_HASH_STR_LEN = 17
```


Length of git hash strings.

Length is 16 chars + null termination.