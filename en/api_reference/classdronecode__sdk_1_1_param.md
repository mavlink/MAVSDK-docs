# dronecode_sdk::Param Class Reference
`#include: param.h`

----


The [Param](classdronecode__sdk_1_1_param.md) class provides raw access to get and set parameters. 


## Public Types


Type | Description
--- | ---
enum [Result](#classdronecode__sdk_1_1_param_1a757c3af24f094d63efa62b798847e3d6) | Possible results returned for param requests.

## Public Member Functions


Type | Name | Description
---: | --- | ---
&nbsp; | [Param](#classdronecode__sdk_1_1_param_1aec4400f9f7005eec4085b96c5d3716a1) ([System](classdronecode__sdk_1_1_system.md) & system) | Constructor. Creates the plugin for a specific [System](classdronecode__sdk_1_1_system.md).
&nbsp; | [~Param](#classdronecode__sdk_1_1_param_1a1e1ce9b859e995c618a4c3de939f3b09) () | Destructor (internal use only).
&nbsp; | [Param](#classdronecode__sdk_1_1_param_1aeac83f8ee26422204e35463cfb073693) (const [Param](classdronecode__sdk_1_1_param.md) &)=delete | Copy Constructor (object is not copyable).
std::pair< [Result](classdronecode__sdk_1_1_param.md#classdronecode__sdk_1_1_param_1a757c3af24f094d63efa62b798847e3d6), int32_t > | [get_param_int](#classdronecode__sdk_1_1_param_1ae1c0fc11f38935855b9805c29d3ef5f2) (const std::string & name) | Get an int parameter.
[Result](classdronecode__sdk_1_1_param.md#classdronecode__sdk_1_1_param_1a757c3af24f094d63efa62b798847e3d6) | [set_param_int](#classdronecode__sdk_1_1_param_1a6c89820f1053c4f7bc5906c9331d205f) (const std::string & name, int32_t value) | Set an int parameter.
std::pair< [Result](classdronecode__sdk_1_1_param.md#classdronecode__sdk_1_1_param_1a757c3af24f094d63efa62b798847e3d6), float > | [get_param_float](#classdronecode__sdk_1_1_param_1a12981bc9b8b67a53162e41554f91bbb8) (const std::string & name) | Get a float parameter.
[Result](classdronecode__sdk_1_1_param.md#classdronecode__sdk_1_1_param_1a757c3af24f094d63efa62b798847e3d6) | [set_param_float](#classdronecode__sdk_1_1_param_1a8651cd567242f2d27be673bef344f473) (const std::string & name, float value) | Set a float parameter.
const [Param](classdronecode__sdk_1_1_param.md) & | [operator=](#classdronecode__sdk_1_1_param_1a77533b40931846200ba69292c1db2356) (const [Param](classdronecode__sdk_1_1_param.md) &)=delete | Equality operator (object is not copyable).

## Static Public Member Functions


Type | Name | Description
---: | --- | ---
std::string | [result_str](#classdronecode__sdk_1_1_param_1a5382b52978bd32c8d78f213f77f844c2) ([Result](classdronecode__sdk_1_1_param.md#classdronecode__sdk_1_1_param_1a757c3af24f094d63efa62b798847e3d6) result) | Returns a human-readable English string for [Param::Result](classdronecode__sdk_1_1_param.md#classdronecode__sdk_1_1_param_1a757c3af24f094d63efa62b798847e3d6).


## Constructor & Destructor Documentation


### Param() {#classdronecode__sdk_1_1_param_1aec4400f9f7005eec4085b96c5d3716a1}
```cpp
dronecode_sdk::Param::Param(System &system)
```


Constructor. Creates the plugin for a specific [System](classdronecode__sdk_1_1_system.md).

The plugin is typically created as shown below: 

```cpp
auto param = std::make_shared<Param>(system);
```

**Parameters**

* [System](classdronecode__sdk_1_1_system.md)& **system** - The specific system associated with this plugin.

### ~Param() {#classdronecode__sdk_1_1_param_1a1e1ce9b859e995c618a4c3de939f3b09}
```cpp
dronecode_sdk::Param::~Param()
```


Destructor (internal use only).


### Param() {#classdronecode__sdk_1_1_param_1aeac83f8ee26422204e35463cfb073693}
```cpp
dronecode_sdk::Param::Param(const Param &)=delete
```


Copy Constructor (object is not copyable).


**Parameters**

* const [Param](classdronecode__sdk_1_1_param.md)&  - 

## Member Enumeration Documentation


### enum Result {#classdronecode__sdk_1_1_param_1a757c3af24f094d63efa62b798847e3d6}


Possible results returned for param requests.


Value | Description
--- | ---
<span id="classdronecode__sdk_1_1_param_1a757c3af24f094d63efa62b798847e3d6a696b031073e74bf2cb98e5ef201d4aa3"></span> `UNKNOWN` | Unknown error. 
<span id="classdronecode__sdk_1_1_param_1a757c3af24f094d63efa62b798847e3d6ad0749aaba8b833466dfcbb0428e4f89c"></span> `SUCCESS` | Request succeeded. 
<span id="classdronecode__sdk_1_1_param_1a757c3af24f094d63efa62b798847e3d6a070a0fb40f6c308ab544b227660aadff"></span> `TIMEOUT` | Request timed out. 
<span id="classdronecode__sdk_1_1_param_1a757c3af24f094d63efa62b798847e3d6ac77f1f09dab2c0c9980fca7cfae02518"></span> `CONNECTION_ERROR` | Connection error. 
<span id="classdronecode__sdk_1_1_param_1a757c3af24f094d63efa62b798847e3d6a9bf67e4befa0dcd99caa7f01f2c9b714"></span> `WRONG_TYPE` | Error. 
<span id="classdronecode__sdk_1_1_param_1a757c3af24f094d63efa62b798847e3d6acb49f6c2d25dfe7801e46902e103369a"></span> `PARAM_NAME_TOO_LONG` | Parameter name too long (> 16). 

## Member Function Documentation


### get_param_int() {#classdronecode__sdk_1_1_param_1ae1c0fc11f38935855b9805c29d3ef5f2}
```cpp
std::pair<Result, int32_t> dronecode_sdk::Param::get_param_int(const std::string &name)
```


Get an int parameter.

If the type is wrong, the result will be [Result::WRONG_TYPE](classdronecode__sdk_1_1_param.md#classdronecode__sdk_1_1_param_1a757c3af24f094d63efa62b798847e3d6a9bf67e4befa0dcd99caa7f01f2c9b714).

**Parameters**

* const std::string& **name** - 

**Returns**

&emsp;std::pair< [Result](classdronecode__sdk_1_1_param.md#classdronecode__sdk_1_1_param_1a757c3af24f094d63efa62b798847e3d6), int32_t > - a pair of the result of the request and the param (if successful).

### set_param_int() {#classdronecode__sdk_1_1_param_1a6c89820f1053c4f7bc5906c9331d205f}
```cpp
Result dronecode_sdk::Param::set_param_int(const std::string &name, int32_t value)
```


Set an int parameter.

If the type is wrong, the result will be [Result::WRONG_TYPE](classdronecode__sdk_1_1_param.md#classdronecode__sdk_1_1_param_1a757c3af24f094d63efa62b798847e3d6a9bf67e4befa0dcd99caa7f01f2c9b714).

**Parameters**

* const std::string& **name** - 
* int32_t **value** - 

**Returns**

&emsp;[Result](classdronecode__sdk_1_1_param.md#classdronecode__sdk_1_1_param_1a757c3af24f094d63efa62b798847e3d6) - result of the request.

### get_param_float() {#classdronecode__sdk_1_1_param_1a12981bc9b8b67a53162e41554f91bbb8}
```cpp
std::pair<Result, float> dronecode_sdk::Param::get_param_float(const std::string &name)
```


Get a float parameter.

If the type is wrong, the result will be [Result::WRONG_TYPE](classdronecode__sdk_1_1_param.md#classdronecode__sdk_1_1_param_1a757c3af24f094d63efa62b798847e3d6a9bf67e4befa0dcd99caa7f01f2c9b714).

**Parameters**

* const std::string& **name** - 

**Returns**

&emsp;std::pair< [Result](classdronecode__sdk_1_1_param.md#classdronecode__sdk_1_1_param_1a757c3af24f094d63efa62b798847e3d6), float > - a pair of the result of the request and the param (if successful).

### set_param_float() {#classdronecode__sdk_1_1_param_1a8651cd567242f2d27be673bef344f473}
```cpp
Result dronecode_sdk::Param::set_param_float(const std::string &name, float value)
```


Set a float parameter.

If the type is wrong, the result will be [Result::WRONG_TYPE](classdronecode__sdk_1_1_param.md#classdronecode__sdk_1_1_param_1a757c3af24f094d63efa62b798847e3d6a9bf67e4befa0dcd99caa7f01f2c9b714).

**Parameters**

* const std::string& **name** - 
* float **value** - 

**Returns**

&emsp;[Result](classdronecode__sdk_1_1_param.md#classdronecode__sdk_1_1_param_1a757c3af24f094d63efa62b798847e3d6) - result of the request.

### operator=() {#classdronecode__sdk_1_1_param_1a77533b40931846200ba69292c1db2356}
```cpp
const Param& dronecode_sdk::Param::operator=(const Param &)=delete
```


Equality operator (object is not copyable).


**Parameters**

* const [Param](classdronecode__sdk_1_1_param.md)&  - 

**Returns**

&emsp;const [Param](classdronecode__sdk_1_1_param.md) & - 

### result_str() {#classdronecode__sdk_1_1_param_1a5382b52978bd32c8d78f213f77f844c2}
```cpp
static std::string dronecode_sdk::Param::result_str(Result result)
```


Returns a human-readable English string for [Param::Result](classdronecode__sdk_1_1_param.md#classdronecode__sdk_1_1_param_1a757c3af24f094d63efa62b798847e3d6).


**Parameters**

* [Result](classdronecode__sdk_1_1_param.md#classdronecode__sdk_1_1_param_1a757c3af24f094d63efa62b798847e3d6) **result** - The enum value for which a human readable string is required.

**Returns**

&emsp;std::string - Human readable string for the [Param::Result](classdronecode__sdk_1_1_param.md#classdronecode__sdk_1_1_param_1a757c3af24f094d63efa62b798847e3d6).