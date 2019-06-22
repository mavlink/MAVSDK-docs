# mavsdk::Param Class Reference
`#include: param.h`

----


The [Param](classmavsdk_1_1_param.md) class provides raw access to get and set parameters. 


## Public Types


Type | Description
--- | ---
enum [Result](#classmavsdk_1_1_param_1afde69c8b60c41e2f21db148d211881df) | Possible results returned for param requests.

## Public Member Functions


Type | Name | Description
---: | --- | ---
&nbsp; | [Param](#classmavsdk_1_1_param_1a3f15c8d0c238a68cd97a49ba5c3ea1ef) ([System](classmavsdk_1_1_system.md) & system) | Constructor. Creates the plugin for a specific [System](classmavsdk_1_1_system.md).
&nbsp; | [~Param](#classmavsdk_1_1_param_1afe3db48e33da2ff7245e41fe0636fdc3) () | Destructor (internal use only).
&nbsp; | [Param](#classmavsdk_1_1_param_1afc29940366bad9212874584f2d6262ce) (const [Param](classmavsdk_1_1_param.md) &)=delete | Copy Constructor (object is not copyable).
std::pair< [Result](classmavsdk_1_1_param.md#classmavsdk_1_1_param_1afde69c8b60c41e2f21db148d211881df), int32_t > | [get_param_int](#classmavsdk_1_1_param_1a9626637ae624af1d791985eb2ca205bd) (const std::string & name) | Get an int parameter.
[Result](classmavsdk_1_1_param.md#classmavsdk_1_1_param_1afde69c8b60c41e2f21db148d211881df) | [set_param_int](#classmavsdk_1_1_param_1a67cdba8cabf2c65d2beece4e28830c52) (const std::string & name, int32_t value) | Set an int parameter.
std::pair< [Result](classmavsdk_1_1_param.md#classmavsdk_1_1_param_1afde69c8b60c41e2f21db148d211881df), float > | [get_param_float](#classmavsdk_1_1_param_1a05a196a18f314441218afe7f44c0164a) (const std::string & name) | Get a float parameter.
[Result](classmavsdk_1_1_param.md#classmavsdk_1_1_param_1afde69c8b60c41e2f21db148d211881df) | [set_param_float](#classmavsdk_1_1_param_1a9a186b975adcd7eaa661afa5434347a6) (const std::string & name, float value) | Set a float parameter.
const [Param](classmavsdk_1_1_param.md) & | [operator=](#classmavsdk_1_1_param_1a4d75b066cb985d3a38cc8221e18aa608) (const [Param](classmavsdk_1_1_param.md) &)=delete | Equality operator (object is not copyable).

## Static Public Member Functions


Type | Name | Description
---: | --- | ---
std::string | [result_str](#classmavsdk_1_1_param_1a2f55467daae1462e974dac6f6306809e) ([Result](classmavsdk_1_1_param.md#classmavsdk_1_1_param_1afde69c8b60c41e2f21db148d211881df) result) | Returns a human-readable English string for [Param::Result](classmavsdk_1_1_param.md#classmavsdk_1_1_param_1afde69c8b60c41e2f21db148d211881df).


## Constructor & Destructor Documentation


### Param() {#classmavsdk_1_1_param_1a3f15c8d0c238a68cd97a49ba5c3ea1ef}
```cpp
mavsdk::Param::Param(System &system)
```


Constructor. Creates the plugin for a specific [System](classmavsdk_1_1_system.md).

The plugin is typically created as shown below: 

```cpp
auto param = std::make_shared<Param>(system);
```

**Parameters**

* [System](classmavsdk_1_1_system.md)& **system** - The specific system associated with this plugin.

### ~Param() {#classmavsdk_1_1_param_1afe3db48e33da2ff7245e41fe0636fdc3}
```cpp
mavsdk::Param::~Param()
```


Destructor (internal use only).


### Param() {#classmavsdk_1_1_param_1afc29940366bad9212874584f2d6262ce}
```cpp
mavsdk::Param::Param(const Param &)=delete
```


Copy Constructor (object is not copyable).


**Parameters**

* const [Param](classmavsdk_1_1_param.md)&  - 

## Member Enumeration Documentation


### enum Result {#classmavsdk_1_1_param_1afde69c8b60c41e2f21db148d211881df}


Possible results returned for param requests.


Value | Description
--- | ---
<span id="classmavsdk_1_1_param_1afde69c8b60c41e2f21db148d211881dfa696b031073e74bf2cb98e5ef201d4aa3"></span> `UNKNOWN` | Unknown error. 
<span id="classmavsdk_1_1_param_1afde69c8b60c41e2f21db148d211881dfad0749aaba8b833466dfcbb0428e4f89c"></span> `SUCCESS` | Request succeeded. 
<span id="classmavsdk_1_1_param_1afde69c8b60c41e2f21db148d211881dfa070a0fb40f6c308ab544b227660aadff"></span> `TIMEOUT` | Request timed out. 
<span id="classmavsdk_1_1_param_1afde69c8b60c41e2f21db148d211881dfac77f1f09dab2c0c9980fca7cfae02518"></span> `CONNECTION_ERROR` | Connection error. 
<span id="classmavsdk_1_1_param_1afde69c8b60c41e2f21db148d211881dfa9bf67e4befa0dcd99caa7f01f2c9b714"></span> `WRONG_TYPE` | Error. 
<span id="classmavsdk_1_1_param_1afde69c8b60c41e2f21db148d211881dfacb49f6c2d25dfe7801e46902e103369a"></span> `PARAM_NAME_TOO_LONG` | Parameter name too long (> 16). 

## Member Function Documentation


### get_param_int() {#classmavsdk_1_1_param_1a9626637ae624af1d791985eb2ca205bd}
```cpp
std::pair<Result, int32_t> mavsdk::Param::get_param_int(const std::string &name)
```


Get an int parameter.

If the type is wrong, the result will be [Result::WRONG_TYPE](classmavsdk_1_1_param.md#classmavsdk_1_1_param_1afde69c8b60c41e2f21db148d211881dfa9bf67e4befa0dcd99caa7f01f2c9b714).

**Parameters**

* const std::string& **name** - 

**Returns**

&emsp;std::pair< [Result](classmavsdk_1_1_param.md#classmavsdk_1_1_param_1afde69c8b60c41e2f21db148d211881df), int32_t > - a pair of the result of the request and the param (if successful).

### set_param_int() {#classmavsdk_1_1_param_1a67cdba8cabf2c65d2beece4e28830c52}
```cpp
Result mavsdk::Param::set_param_int(const std::string &name, int32_t value)
```


Set an int parameter.

If the type is wrong, the result will be [Result::WRONG_TYPE](classmavsdk_1_1_param.md#classmavsdk_1_1_param_1afde69c8b60c41e2f21db148d211881dfa9bf67e4befa0dcd99caa7f01f2c9b714).

**Parameters**

* const std::string& **name** - 
* int32_t **value** - 

**Returns**

&emsp;[Result](classmavsdk_1_1_param.md#classmavsdk_1_1_param_1afde69c8b60c41e2f21db148d211881df) - result of the request.

### get_param_float() {#classmavsdk_1_1_param_1a05a196a18f314441218afe7f44c0164a}
```cpp
std::pair<Result, float> mavsdk::Param::get_param_float(const std::string &name)
```


Get a float parameter.

If the type is wrong, the result will be [Result::WRONG_TYPE](classmavsdk_1_1_param.md#classmavsdk_1_1_param_1afde69c8b60c41e2f21db148d211881dfa9bf67e4befa0dcd99caa7f01f2c9b714).

**Parameters**

* const std::string& **name** - 

**Returns**

&emsp;std::pair< [Result](classmavsdk_1_1_param.md#classmavsdk_1_1_param_1afde69c8b60c41e2f21db148d211881df), float > - a pair of the result of the request and the param (if successful).

### set_param_float() {#classmavsdk_1_1_param_1a9a186b975adcd7eaa661afa5434347a6}
```cpp
Result mavsdk::Param::set_param_float(const std::string &name, float value)
```


Set a float parameter.

If the type is wrong, the result will be [Result::WRONG_TYPE](classmavsdk_1_1_param.md#classmavsdk_1_1_param_1afde69c8b60c41e2f21db148d211881dfa9bf67e4befa0dcd99caa7f01f2c9b714).

**Parameters**

* const std::string& **name** - 
* float **value** - 

**Returns**

&emsp;[Result](classmavsdk_1_1_param.md#classmavsdk_1_1_param_1afde69c8b60c41e2f21db148d211881df) - result of the request.

### operator=() {#classmavsdk_1_1_param_1a4d75b066cb985d3a38cc8221e18aa608}
```cpp
const Param& mavsdk::Param::operator=(const Param &)=delete
```


Equality operator (object is not copyable).


**Parameters**

* const [Param](classmavsdk_1_1_param.md)&  - 

**Returns**

&emsp;const [Param](classmavsdk_1_1_param.md) & - 

### result_str() {#classmavsdk_1_1_param_1a2f55467daae1462e974dac6f6306809e}
```cpp
static std::string mavsdk::Param::result_str(Result result)
```


Returns a human-readable English string for [Param::Result](classmavsdk_1_1_param.md#classmavsdk_1_1_param_1afde69c8b60c41e2f21db148d211881df).


**Parameters**

* [Result](classmavsdk_1_1_param.md#classmavsdk_1_1_param_1afde69c8b60c41e2f21db148d211881df) **result** - The enum value for which a human readable string is required.

**Returns**

&emsp;std::string - Human readable string for the [Param::Result](classmavsdk_1_1_param.md#classmavsdk_1_1_param_1afde69c8b60c41e2f21db148d211881df).