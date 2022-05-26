# mavsdk::ComponentInformationServer Class Reference
`#include: component_information_server.h`

----


Provide component information such as parameters. 


## Data Structures


struct [FloatParam](structmavsdk_1_1_component_information_server_1_1_float_param.md)

struct [FloatParamUpdate](structmavsdk_1_1_component_information_server_1_1_float_param_update.md)

## Public Types


Type | Description
--- | ---
enum [Result](#classmavsdk_1_1_component_information_server_1aca86e47230e256d3f812269dcbaa5cad) | Possible results returned for param requests.
std::function< void([Result](classmavsdk_1_1_component_information_server.md#classmavsdk_1_1_component_information_server_1aca86e47230e256d3f812269dcbaa5cad))> [ResultCallback](#classmavsdk_1_1_component_information_server_1a5f65b34949a1954c85f3f02e64dec35f) | Callback type for asynchronous [ComponentInformationServer](classmavsdk_1_1_component_information_server.md) calls.
std::function< void([FloatParamUpdate](structmavsdk_1_1_component_information_server_1_1_float_param_update.md))> [FloatParamCallback](#classmavsdk_1_1_component_information_server_1a6174e3eebb5a10c619c57723623696cf) | Callback type for subscribe_float_param.

## Public Member Functions


Type | Name | Description
---: | --- | ---
&nbsp; | [ComponentInformationServer](#classmavsdk_1_1_component_information_server_1aec0b2946404466539e22ba3bf85eea15) ([System](classmavsdk_1_1_system.md) & system) | Constructor. Creates the plugin for a specific [System](classmavsdk_1_1_system.md).
&nbsp; | [ComponentInformationServer](#classmavsdk_1_1_component_information_server_1adf569b42ae040e3ce0c788715ba05b9f) (std::shared_ptr< [System](classmavsdk_1_1_system.md) > system) | Constructor. Creates the plugin for a specific [System](classmavsdk_1_1_system.md).
&nbsp; | [~ComponentInformationServer](#classmavsdk_1_1_component_information_server_1a359efc7e3079812d0c40bde8bd98a084) () | Destructor (internal use only).
&nbsp; | [ComponentInformationServer](#classmavsdk_1_1_component_information_server_1a7f8fc33e21e00a390da14596465c800d) (const [ComponentInformationServer](classmavsdk_1_1_component_information_server.md) & other) | Copy constructor.
[Result](classmavsdk_1_1_component_information_server.md#classmavsdk_1_1_component_information_server_1aca86e47230e256d3f812269dcbaa5cad) | [provide_float_param](#classmavsdk_1_1_component_information_server_1ac4f9a480ef052b792e65b82c3c08b225) ([FloatParam](structmavsdk_1_1_component_information_server_1_1_float_param.md) param)const | Provide a param of type float.
void | [subscribe_float_param](#classmavsdk_1_1_component_information_server_1aadab6186143edb43d1dddfc2188ac1bd) ([FloatParamCallback](classmavsdk_1_1_component_information_server.md#classmavsdk_1_1_component_information_server_1a6174e3eebb5a10c619c57723623696cf) callback) | Subscribe to float param updates.
const [ComponentInformationServer](classmavsdk_1_1_component_information_server.md) & | [operator=](#classmavsdk_1_1_component_information_server_1a850a10c9d195da5f52807984e72d21fa) (const [ComponentInformationServer](classmavsdk_1_1_component_information_server.md) &)=delete | Equality operator (object is not copyable).


## Constructor & Destructor Documentation


### ComponentInformationServer() {#classmavsdk_1_1_component_information_server_1aec0b2946404466539e22ba3bf85eea15}
```cpp
mavsdk::ComponentInformationServer::ComponentInformationServer(System &system)
```


Constructor. Creates the plugin for a specific [System](classmavsdk_1_1_system.md).

The plugin is typically created as shown below: 

```cpp
auto component_information_server = ComponentInformationServer(system);
```

**Parameters**

* [System](classmavsdk_1_1_system.md)& **system** - The specific system associated with this plugin.

### ComponentInformationServer() {#classmavsdk_1_1_component_information_server_1adf569b42ae040e3ce0c788715ba05b9f}
```cpp
mavsdk::ComponentInformationServer::ComponentInformationServer(std::shared_ptr< System > system)
```


Constructor. Creates the plugin for a specific [System](classmavsdk_1_1_system.md).

The plugin is typically created as shown below: 

```cpp
auto component_information_server = ComponentInformationServer(system);
```

**Parameters**

* std::shared_ptr< [System](classmavsdk_1_1_system.md) > **system** - The specific system associated with this plugin.

### ~ComponentInformationServer() {#classmavsdk_1_1_component_information_server_1a359efc7e3079812d0c40bde8bd98a084}
```cpp
mavsdk::ComponentInformationServer::~ComponentInformationServer()
```


Destructor (internal use only).


### ComponentInformationServer() {#classmavsdk_1_1_component_information_server_1a7f8fc33e21e00a390da14596465c800d}
```cpp
mavsdk::ComponentInformationServer::ComponentInformationServer(const ComponentInformationServer &other)
```


Copy constructor.


**Parameters**

* const [ComponentInformationServer](classmavsdk_1_1_component_information_server.md)& **other** - 

## Member Typdef Documentation


### typedef ResultCallback {#classmavsdk_1_1_component_information_server_1a5f65b34949a1954c85f3f02e64dec35f}

```cpp
using mavsdk::ComponentInformationServer::ResultCallback =  std::function<void(Result)>
```


Callback type for asynchronous [ComponentInformationServer](classmavsdk_1_1_component_information_server.md) calls.


### typedef FloatParamCallback {#classmavsdk_1_1_component_information_server_1a6174e3eebb5a10c619c57723623696cf}

```cpp
using mavsdk::ComponentInformationServer::FloatParamCallback =  std::function<void(FloatParamUpdate)>
```


Callback type for subscribe_float_param.


## Member Enumeration Documentation


### enum Result {#classmavsdk_1_1_component_information_server_1aca86e47230e256d3f812269dcbaa5cad}


Possible results returned for param requests.


Value | Description
--- | ---
<span id="classmavsdk_1_1_component_information_server_1aca86e47230e256d3f812269dcbaa5cada88183b946cc5f0e8c96b2e66e1c74a7e"></span> `Unknown` | Unknown result. 
<span id="classmavsdk_1_1_component_information_server_1aca86e47230e256d3f812269dcbaa5cada505a83f220c02df2f85c3810cd9ceb38"></span> `Success` | Request succeeded. 
<span id="classmavsdk_1_1_component_information_server_1aca86e47230e256d3f812269dcbaa5cada2e665af7b9e17282f7301a1dcc5e6365"></span> `DuplicateParam` | Duplicate param. 
<span id="classmavsdk_1_1_component_information_server_1aca86e47230e256d3f812269dcbaa5cada6d9ebfdcd8bc404f5d64d3cec5a190cc"></span> `InvalidParamStartValue` | Invalid start param value. 
<span id="classmavsdk_1_1_component_information_server_1aca86e47230e256d3f812269dcbaa5cada6f12b0597e5013f1211f1e1af2eb79c9"></span> `InvalidParamDefaultValue` | Invalid default param value. 
<span id="classmavsdk_1_1_component_information_server_1aca86e47230e256d3f812269dcbaa5cada297a4ad19203eb48dcc016ac3a2d3149"></span> `InvalidParamName` | Invalid param name. 
<span id="classmavsdk_1_1_component_information_server_1aca86e47230e256d3f812269dcbaa5cada1119faf72ba0dfb23aeea644fed960ad"></span> `NoSystem` | No system is connected. 

## Member Function Documentation


### provide_float_param() {#classmavsdk_1_1_component_information_server_1ac4f9a480ef052b792e65b82c3c08b225}
```cpp
Result mavsdk::ComponentInformationServer::provide_float_param(FloatParam param) const
```


Provide a param of type float.

This function is blocking.

**Parameters**

* [FloatParam](structmavsdk_1_1_component_information_server_1_1_float_param.md) **param** - 

**Returns**

&emsp;[Result](classmavsdk_1_1_component_information_server.md#classmavsdk_1_1_component_information_server_1aca86e47230e256d3f812269dcbaa5cad) - Result of request.

### subscribe_float_param() {#classmavsdk_1_1_component_information_server_1aadab6186143edb43d1dddfc2188ac1bd}
```cpp
void mavsdk::ComponentInformationServer::subscribe_float_param(FloatParamCallback callback)
```


Subscribe to float param updates.


**Parameters**

* [FloatParamCallback](classmavsdk_1_1_component_information_server.md#classmavsdk_1_1_component_information_server_1a6174e3eebb5a10c619c57723623696cf) **callback** - 

### operator=() {#classmavsdk_1_1_component_information_server_1a850a10c9d195da5f52807984e72d21fa}
```cpp
const ComponentInformationServer& mavsdk::ComponentInformationServer::operator=(const ComponentInformationServer &)=delete
```


Equality operator (object is not copyable).


**Parameters**

* const [ComponentInformationServer](classmavsdk_1_1_component_information_server.md)&  - 

**Returns**

&emsp;const [ComponentInformationServer](classmavsdk_1_1_component_information_server.md) & - 