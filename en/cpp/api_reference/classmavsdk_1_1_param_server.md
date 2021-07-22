# mavsdk::ParamServer Class Reference
`#include: param_server.h`

----


Provide raw access to retrieve and provide server parameters. 


## Data Structures


struct [AllParams](structmavsdk_1_1_param_server_1_1_all_params.md)

struct [FloatParam](structmavsdk_1_1_param_server_1_1_float_param.md)

struct [IntParam](structmavsdk_1_1_param_server_1_1_int_param.md)

## Public Types


Type | Description
--- | ---
enum [Result](#classmavsdk_1_1_param_server_1a6f7fcc017f43dcf68837dbc35ee4f469) | Possible results returned for param requests.
std::function< void([Result](classmavsdk_1_1_param_server.md#classmavsdk_1_1_param_server_1a6f7fcc017f43dcf68837dbc35ee4f469))> [ResultCallback](#classmavsdk_1_1_param_server_1a669845877bb8e14482fb46542825c625) | Callback type for asynchronous [ParamServer](classmavsdk_1_1_param_server.md) calls.

## Public Member Functions


Type | Name | Description
---: | --- | ---
&nbsp; | [ParamServer](#classmavsdk_1_1_param_server_1a1381f2cd17459a70b04167fe0c230134) ([System](classmavsdk_1_1_system.md) & system) | Constructor. Creates the plugin for a specific [System](classmavsdk_1_1_system.md).
&nbsp; | [ParamServer](#classmavsdk_1_1_param_server_1a2d57795672afad77a1c55cda9e6d57d6) (std::shared_ptr< [System](classmavsdk_1_1_system.md) > system) | Constructor. Creates the plugin for a specific [System](classmavsdk_1_1_system.md).
&nbsp; | [~ParamServer](#classmavsdk_1_1_param_server_1a6066a31b1b6f6ce29a30617634ba1184) () | Destructor (internal use only).
&nbsp; | [ParamServer](#classmavsdk_1_1_param_server_1a4cffcb488093838f72414c94e6c40fd0) (const [ParamServer](classmavsdk_1_1_param_server.md) & other) | Copy constructor.
std::pair< [Result](classmavsdk_1_1_param_server.md#classmavsdk_1_1_param_server_1a6f7fcc017f43dcf68837dbc35ee4f469), int32_t > | [retrieve_param_int](#classmavsdk_1_1_param_server_1a95c445dbdd2b764248c811da0230b0b4) (std::string name)const | Retrieve an int parameter.
[Result](classmavsdk_1_1_param_server.md#classmavsdk_1_1_param_server_1a6f7fcc017f43dcf68837dbc35ee4f469) | [provide_param_int](#classmavsdk_1_1_param_server_1a9de5dade4020eda7fb1cc07c6868dad1) (std::string name, int32_t value)const | Provide an int parameter.
std::pair< [Result](classmavsdk_1_1_param_server.md#classmavsdk_1_1_param_server_1a6f7fcc017f43dcf68837dbc35ee4f469), float > | [retrieve_param_float](#classmavsdk_1_1_param_server_1a2845916c07a7e47e7444a49f88b23320) (std::string name)const | Retrieve a float parameter.
[Result](classmavsdk_1_1_param_server.md#classmavsdk_1_1_param_server_1a6f7fcc017f43dcf68837dbc35ee4f469) | [provide_param_float](#classmavsdk_1_1_param_server_1a7893e4b00609eb0826835b3d8930db1f) (std::string name, float value)const | Provide a float parameter.
[ParamServer::AllParams](structmavsdk_1_1_param_server_1_1_all_params.md) | [retrieve_all_params](#classmavsdk_1_1_param_server_1aaf6b3862213d415ff26730afad95565f) () const | Retrieve all parameters.
const [ParamServer](classmavsdk_1_1_param_server.md) & | [operator=](#classmavsdk_1_1_param_server_1a29ce1d2c4a2b80fbe4a0b7e7470e14af) (const [ParamServer](classmavsdk_1_1_param_server.md) &)=delete | Equality operator (object is not copyable).


## Constructor & Destructor Documentation


### ParamServer() {#classmavsdk_1_1_param_server_1a1381f2cd17459a70b04167fe0c230134}
```cpp
mavsdk::ParamServer::ParamServer(System &system)
```


Constructor. Creates the plugin for a specific [System](classmavsdk_1_1_system.md).

The plugin is typically created as shown below: 

```cpp
auto param_server = ParamServer(system);
```

**Parameters**

* [System](classmavsdk_1_1_system.md)& **system** - The specific system associated with this plugin.

### ParamServer() {#classmavsdk_1_1_param_server_1a2d57795672afad77a1c55cda9e6d57d6}
```cpp
mavsdk::ParamServer::ParamServer(std::shared_ptr< System > system)
```


Constructor. Creates the plugin for a specific [System](classmavsdk_1_1_system.md).

The plugin is typically created as shown below: 

```cpp
auto param_server = ParamServer(system);
```

**Parameters**

* std::shared_ptr< [System](classmavsdk_1_1_system.md) > **system** - The specific system associated with this plugin.

### ~ParamServer() {#classmavsdk_1_1_param_server_1a6066a31b1b6f6ce29a30617634ba1184}
```cpp
mavsdk::ParamServer::~ParamServer()
```


Destructor (internal use only).


### ParamServer() {#classmavsdk_1_1_param_server_1a4cffcb488093838f72414c94e6c40fd0}
```cpp
mavsdk::ParamServer::ParamServer(const ParamServer &other)
```


Copy constructor.


**Parameters**

* const [ParamServer](classmavsdk_1_1_param_server.md)& **other** - 

## Member Typdef Documentation


### typedef ResultCallback {#classmavsdk_1_1_param_server_1a669845877bb8e14482fb46542825c625}

```cpp
using mavsdk::ParamServer::ResultCallback =  std::function<void(Result)>
```


Callback type for asynchronous [ParamServer](classmavsdk_1_1_param_server.md) calls.


## Member Enumeration Documentation


### enum Result {#classmavsdk_1_1_param_server_1a6f7fcc017f43dcf68837dbc35ee4f469}


Possible results returned for param requests.


Value | Description
--- | ---
<span id="classmavsdk_1_1_param_server_1a6f7fcc017f43dcf68837dbc35ee4f469a88183b946cc5f0e8c96b2e66e1c74a7e"></span> `Unknown` | Unknown result. 
<span id="classmavsdk_1_1_param_server_1a6f7fcc017f43dcf68837dbc35ee4f469a505a83f220c02df2f85c3810cd9ceb38"></span> `Success` | Request succeeded. 
<span id="classmavsdk_1_1_param_server_1a6f7fcc017f43dcf68837dbc35ee4f469a38c300f4fc9ce8a77aad4a30de05cad8"></span> `NotFound` | Not Found. 
<span id="classmavsdk_1_1_param_server_1a6f7fcc017f43dcf68837dbc35ee4f469afdf152936dcbf201445440856357f6ac"></span> `WrongType` | Wrong type. 
<span id="classmavsdk_1_1_param_server_1a6f7fcc017f43dcf68837dbc35ee4f469aa2b5cfc4e45ca036892b3dadc483e655"></span> `ParamNameTooLong` | Parameter name too long (> 16). 

## Member Function Documentation


### retrieve_param_int() {#classmavsdk_1_1_param_server_1a95c445dbdd2b764248c811da0230b0b4}
```cpp
std::pair<Result, int32_t> mavsdk::ParamServer::retrieve_param_int(std::string name) const
```


Retrieve an int parameter.

If the type is wrong, the result will be `WRONG_TYPE`.


This function is blocking.

**Parameters**

* std::string **name** - 

**Returns**

&emsp;std::pair< [Result](classmavsdk_1_1_param_server.md#classmavsdk_1_1_param_server_1a6f7fcc017f43dcf68837dbc35ee4f469), int32_t > - Result of request.

### provide_param_int() {#classmavsdk_1_1_param_server_1a9de5dade4020eda7fb1cc07c6868dad1}
```cpp
Result mavsdk::ParamServer::provide_param_int(std::string name, int32_t value) const
```


Provide an int parameter.

If the type is wrong, the result will be `WRONG_TYPE`.


This function is blocking.

**Parameters**

* std::string **name** - 
* int32_t **value** - 

**Returns**

&emsp;[Result](classmavsdk_1_1_param_server.md#classmavsdk_1_1_param_server_1a6f7fcc017f43dcf68837dbc35ee4f469) - Result of request.

### retrieve_param_float() {#classmavsdk_1_1_param_server_1a2845916c07a7e47e7444a49f88b23320}
```cpp
std::pair<Result, float> mavsdk::ParamServer::retrieve_param_float(std::string name) const
```


Retrieve a float parameter.

If the type is wrong, the result will be `WRONG_TYPE`.


This function is blocking.

**Parameters**

* std::string **name** - 

**Returns**

&emsp;std::pair< [Result](classmavsdk_1_1_param_server.md#classmavsdk_1_1_param_server_1a6f7fcc017f43dcf68837dbc35ee4f469), float > - Result of request.

### provide_param_float() {#classmavsdk_1_1_param_server_1a7893e4b00609eb0826835b3d8930db1f}
```cpp
Result mavsdk::ParamServer::provide_param_float(std::string name, float value) const
```


Provide a float parameter.

If the type is wrong, the result will be `WRONG_TYPE`.


This function is blocking.

**Parameters**

* std::string **name** - 
* float **value** - 

**Returns**

&emsp;[Result](classmavsdk_1_1_param_server.md#classmavsdk_1_1_param_server_1a6f7fcc017f43dcf68837dbc35ee4f469) - Result of request.

### retrieve_all_params() {#classmavsdk_1_1_param_server_1aaf6b3862213d415ff26730afad95565f}
```cpp
ParamServer::AllParams mavsdk::ParamServer::retrieve_all_params() const
```


Retrieve all parameters.

This function is blocking.

**Returns**

&emsp;[ParamServer::AllParams](structmavsdk_1_1_param_server_1_1_all_params.md) - Result of request.

### operator=() {#classmavsdk_1_1_param_server_1a29ce1d2c4a2b80fbe4a0b7e7470e14af}
```cpp
const ParamServer& mavsdk::ParamServer::operator=(const ParamServer &)=delete
```


Equality operator (object is not copyable).


**Parameters**

* const [ParamServer](classmavsdk_1_1_param_server.md)&  - 

**Returns**

&emsp;const [ParamServer](classmavsdk_1_1_param_server.md) & - 