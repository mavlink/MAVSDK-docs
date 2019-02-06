# dronecode_sdk::ParamsRaw Class Reference
`#include: params_raw.h`

----


The [ParamsRaw](classdronecode__sdk_1_1_params_raw.md) class provides raw access to get and set parameters. 


## Public Types


Type | Description
--- | ---
enum [Result](#classdronecode__sdk_1_1_params_raw_1a56a99fac0db7b397442482736de52803) | Possible results returned for params_raw requests.

## Public Member Functions


Type | Name | Description
---: | --- | ---
&nbsp; | [ParamsRaw](#classdronecode__sdk_1_1_params_raw_1af25dfed59dd061240520ae9ed2a4d2e8) ([System](classdronecode__sdk_1_1_system.md) & system) | Constructor. Creates the plugin for a specific [System](classdronecode__sdk_1_1_system.md).
&nbsp; | [~ParamsRaw](#classdronecode__sdk_1_1_params_raw_1a89c3ffa2df9d592553e5fae468c72112) () | Destructor (internal use only).
&nbsp; | [ParamsRaw](#classdronecode__sdk_1_1_params_raw_1a09f5d63ca15fd2e4006b03621e2a2c15) (const [ParamsRaw](classdronecode__sdk_1_1_params_raw.md) &)=delete | Copy Constructor (object is not copyable).
std::string | [result_str](#classdronecode__sdk_1_1_params_raw_1a573a6f54493f0e862fbd12cdd3a8ac8c) ([Result](classdronecode__sdk_1_1_params_raw.md#classdronecode__sdk_1_1_params_raw_1a56a99fac0db7b397442482736de52803) result) | Returns a human-readable English string for [ParamsRaw::Result](classdronecode__sdk_1_1_params_raw.md#classdronecode__sdk_1_1_params_raw_1a56a99fac0db7b397442482736de52803).
std::pair< [Result](classdronecode__sdk_1_1_params_raw.md#classdronecode__sdk_1_1_params_raw_1a56a99fac0db7b397442482736de52803), int32_t > | [get_param_int](#classdronecode__sdk_1_1_params_raw_1a5ec45f63958cd939849a2751b9fa602e) (const std::string & name) | Get an int parameter.
[Result](classdronecode__sdk_1_1_params_raw.md#classdronecode__sdk_1_1_params_raw_1a56a99fac0db7b397442482736de52803) | [set_param_int](#classdronecode__sdk_1_1_params_raw_1a989b66a45a4a69919eaeebfdcec2a2e1) (const std::string & name, int32_t value) | Set an int parameter.
std::pair< [Result](classdronecode__sdk_1_1_params_raw.md#classdronecode__sdk_1_1_params_raw_1a56a99fac0db7b397442482736de52803), float > | [get_param_float](#classdronecode__sdk_1_1_params_raw_1ab3d5e0706c3e7a0b2acf4ca0e6299213) (const std::string & name) | Get a float parameter.
[Result](classdronecode__sdk_1_1_params_raw.md#classdronecode__sdk_1_1_params_raw_1a56a99fac0db7b397442482736de52803) | [set_param_float](#classdronecode__sdk_1_1_params_raw_1a169b6d40f0909c127f0195b2fce18a04) (const std::string & name, float value) | Set a float parameter.
const [ParamsRaw](classdronecode__sdk_1_1_params_raw.md) & | [operator=](#classdronecode__sdk_1_1_params_raw_1a419df0713ee17d9fb14ff000b3430f39) (const [ParamsRaw](classdronecode__sdk_1_1_params_raw.md) &)=delete | Equality operator (object is not copyable).


## Constructor & Destructor Documentation


### ParamsRaw() {#classdronecode__sdk_1_1_params_raw_1af25dfed59dd061240520ae9ed2a4d2e8}
```cpp
dronecode_sdk::ParamsRaw::ParamsRaw(System &system)
```


Constructor. Creates the plugin for a specific [System](classdronecode__sdk_1_1_system.md).

The plugin is typically created as shown below: 

```cpp
auto params_raw = std::make_shared<ParamsRaw>(system);
```

**Parameters**

* [System](classdronecode__sdk_1_1_system.md)& **system** - The specific system associated with this plugin.

### ~ParamsRaw() {#classdronecode__sdk_1_1_params_raw_1a89c3ffa2df9d592553e5fae468c72112}
```cpp
dronecode_sdk::ParamsRaw::~ParamsRaw()
```


Destructor (internal use only).


### ParamsRaw() {#classdronecode__sdk_1_1_params_raw_1a09f5d63ca15fd2e4006b03621e2a2c15}
```cpp
dronecode_sdk::ParamsRaw::ParamsRaw(const ParamsRaw &)=delete
```


Copy Constructor (object is not copyable).


**Parameters**

* const [ParamsRaw](classdronecode__sdk_1_1_params_raw.md)&  - 

## Member Enumeration Documentation


### enum Result {#classdronecode__sdk_1_1_params_raw_1a56a99fac0db7b397442482736de52803}


Possible results returned for params_raw requests.


Value | Description
--- | ---
<span id="classdronecode__sdk_1_1_params_raw_1a56a99fac0db7b397442482736de52803a696b031073e74bf2cb98e5ef201d4aa3"></span> `UNKNOWN` | Unknown error. 
<span id="classdronecode__sdk_1_1_params_raw_1a56a99fac0db7b397442482736de52803ad0749aaba8b833466dfcbb0428e4f89c"></span> `SUCCESS` | Request succeeded. 
<span id="classdronecode__sdk_1_1_params_raw_1a56a99fac0db7b397442482736de52803a070a0fb40f6c308ab544b227660aadff"></span> `TIMEOUT` | Request timed out. 
<span id="classdronecode__sdk_1_1_params_raw_1a56a99fac0db7b397442482736de52803ac77f1f09dab2c0c9980fca7cfae02518"></span> `CONNECTION_ERROR` | Connection error. 
<span id="classdronecode__sdk_1_1_params_raw_1a56a99fac0db7b397442482736de52803a9bf67e4befa0dcd99caa7f01f2c9b714"></span> `WRONG_TYPE` | Error. 
<span id="classdronecode__sdk_1_1_params_raw_1a56a99fac0db7b397442482736de52803acb49f6c2d25dfe7801e46902e103369a"></span> `PARAM_NAME_TOO_LONG` | Parameter name too long (> 16). 

## Member Function Documentation


### result_str() {#classdronecode__sdk_1_1_params_raw_1a573a6f54493f0e862fbd12cdd3a8ac8c}
```cpp
std::string dronecode_sdk::ParamsRaw::result_str(Result result)
```


Returns a human-readable English string for [ParamsRaw::Result](classdronecode__sdk_1_1_params_raw.md#classdronecode__sdk_1_1_params_raw_1a56a99fac0db7b397442482736de52803).


**Parameters**

* [Result](classdronecode__sdk_1_1_params_raw.md#classdronecode__sdk_1_1_params_raw_1a56a99fac0db7b397442482736de52803) **result** - The enum value for which a human readable string is required.

**Returns**

&emsp;std::string - Human readable string for the [ParamsRaw::Result](classdronecode__sdk_1_1_params_raw.md#classdronecode__sdk_1_1_params_raw_1a56a99fac0db7b397442482736de52803).

### get_param_int() {#classdronecode__sdk_1_1_params_raw_1a5ec45f63958cd939849a2751b9fa602e}
```cpp
std::pair<Result, int32_t> dronecode_sdk::ParamsRaw::get_param_int(const std::string &name)
```


Get an int parameter.

If the type is wrong, the result will be [Result::WRONG_TYPE](classdronecode__sdk_1_1_params_raw.md#classdronecode__sdk_1_1_params_raw_1a56a99fac0db7b397442482736de52803a9bf67e4befa0dcd99caa7f01f2c9b714).

**Parameters**

* const std::string& **name** - 

**Returns**

&emsp;std::pair< [Result](classdronecode__sdk_1_1_params_raw.md#classdronecode__sdk_1_1_params_raw_1a56a99fac0db7b397442482736de52803), int32_t > - a pair of the result of the request and the param (if successful).

### set_param_int() {#classdronecode__sdk_1_1_params_raw_1a989b66a45a4a69919eaeebfdcec2a2e1}
```cpp
Result dronecode_sdk::ParamsRaw::set_param_int(const std::string &name, int32_t value)
```


Set an int parameter.

If the type is wrong, the result will be [Result::WRONG_TYPE](classdronecode__sdk_1_1_params_raw.md#classdronecode__sdk_1_1_params_raw_1a56a99fac0db7b397442482736de52803a9bf67e4befa0dcd99caa7f01f2c9b714).

**Parameters**

* const std::string& **name** - 
* int32_t **value** - 

**Returns**

&emsp;[Result](classdronecode__sdk_1_1_params_raw.md#classdronecode__sdk_1_1_params_raw_1a56a99fac0db7b397442482736de52803) - result of the request.

### get_param_float() {#classdronecode__sdk_1_1_params_raw_1ab3d5e0706c3e7a0b2acf4ca0e6299213}
```cpp
std::pair<Result, float> dronecode_sdk::ParamsRaw::get_param_float(const std::string &name)
```


Get a float parameter.

If the type is wrong, the result will be [Result::WRONG_TYPE](classdronecode__sdk_1_1_params_raw.md#classdronecode__sdk_1_1_params_raw_1a56a99fac0db7b397442482736de52803a9bf67e4befa0dcd99caa7f01f2c9b714).

**Parameters**

* const std::string& **name** - 

**Returns**

&emsp;std::pair< [Result](classdronecode__sdk_1_1_params_raw.md#classdronecode__sdk_1_1_params_raw_1a56a99fac0db7b397442482736de52803), float > - a pair of the result of the request and the param (if successful).

### set_param_float() {#classdronecode__sdk_1_1_params_raw_1a169b6d40f0909c127f0195b2fce18a04}
```cpp
Result dronecode_sdk::ParamsRaw::set_param_float(const std::string &name, float value)
```


Set a float parameter.

If the type is wrong, the result will be [Result::WRONG_TYPE](classdronecode__sdk_1_1_params_raw.md#classdronecode__sdk_1_1_params_raw_1a56a99fac0db7b397442482736de52803a9bf67e4befa0dcd99caa7f01f2c9b714).

**Parameters**

* const std::string& **name** - 
* float **value** - 

**Returns**

&emsp;[Result](classdronecode__sdk_1_1_params_raw.md#classdronecode__sdk_1_1_params_raw_1a56a99fac0db7b397442482736de52803) - result of the request.

### operator=() {#classdronecode__sdk_1_1_params_raw_1a419df0713ee17d9fb14ff000b3430f39}
```cpp
const ParamsRaw& dronecode_sdk::ParamsRaw::operator=(const ParamsRaw &)=delete
```


Equality operator (object is not copyable).


**Parameters**

* const [ParamsRaw](classdronecode__sdk_1_1_params_raw.md)&  - 

**Returns**

&emsp;const [ParamsRaw](classdronecode__sdk_1_1_params_raw.md) & - 