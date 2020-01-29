# mavsdk::Shell Class Reference
`#include: shell.h`

----


This class allow users to communicate with vehicle's system shell. 


## Data Structures


struct [ShellMessage](structmavsdk_1_1_shell_1_1_shell_message.md)

## Public Types


Type | Description
--- | ---
enum [Result](#classmavsdk_1_1_shell_1a768bfa296ba3309f936f887fb86c9ba8) | [Shell](classmavsdk_1_1_shell.md) Result Code enum.
std::function< void([Result](classmavsdk_1_1_shell.md#classmavsdk_1_1_shell_1a768bfa296ba3309f936f887fb86c9ba8) result, [ShellMessage](structmavsdk_1_1_shell_1_1_shell_message.md) response)> [result_callback_t](#classmavsdk_1_1_shell_1a22aa50b455d6a3f81b4a29a9d339a8fa) | Callback type for shell requests.

## Public Member Functions


Type | Name | Description
---: | --- | ---
&nbsp; | [Shell](#classmavsdk_1_1_shell_1a31a80044ee4822e8b9ac1c515b0eea90) ([System](classmavsdk_1_1_system.md) & system) | Constructor. Creates the plugin for a specific [System](classmavsdk_1_1_system.md).
&nbsp; | [~Shell](#classmavsdk_1_1_shell_1a26b0e0d6a00d89c3d22c0f8a580c54c4) () | Destructor (internal use only).
&nbsp; | [Shell](#classmavsdk_1_1_shell_1a7fdf25f0db49675a24c6ce61be9f82b5) (const [Shell](classmavsdk_1_1_shell.md) &)=delete | Copy constructor (object is not copyable).
[Shell::Result](classmavsdk_1_1_shell.md#classmavsdk_1_1_shell_1a768bfa296ba3309f936f887fb86c9ba8) | [shell_command](#classmavsdk_1_1_shell_1a71647880750275ae20f9e9ff35759bff) ([ShellMessage](structmavsdk_1_1_shell_1_1_shell_message.md) shell_message) | Send the shell message.
[Shell::Result](classmavsdk_1_1_shell.md#classmavsdk_1_1_shell_1a768bfa296ba3309f936f887fb86c9ba8) | [shell_command_response_async](#classmavsdk_1_1_shell_1aa619d754d68953adb87afa5af864151e) ([result_callback_t](classmavsdk_1_1_shell.md#classmavsdk_1_1_shell_1a22aa50b455d6a3f81b4a29a9d339a8fa) callback) | Set [Shell](classmavsdk_1_1_shell.md) message Response callback (asynchronous).
const [Shell](classmavsdk_1_1_shell.md) & | [operator=](#classmavsdk_1_1_shell_1a492f8b2e36ef2468522bfd0f51f4b9b8) (const [Shell](classmavsdk_1_1_shell.md) &)=delete | Equality operator (object is not copyable).

## Static Public Member Functions


Type | Name | Description
---: | --- | ---
const char * | [result_code_str](#classmavsdk_1_1_shell_1a906fe10a4f5a9443e84fc9486221b3ff) ([Result](classmavsdk_1_1_shell.md#classmavsdk_1_1_shell_1a768bfa296ba3309f936f887fb86c9ba8) result) | Get human-readable English string for Shell::Result::ResultCode.


## Constructor & Destructor Documentation


### Shell() {#classmavsdk_1_1_shell_1a31a80044ee4822e8b9ac1c515b0eea90}
```cpp
mavsdk::Shell::Shell(System &system)
```


Constructor. Creates the plugin for a specific [System](classmavsdk_1_1_system.md).

The plugin is typically created as shown below: 

```cpp
auto shell = std::make_shared<Shell>(system);
```

**Parameters**

* [System](classmavsdk_1_1_system.md)& **system** - The specific system associated with this plugin.

### ~Shell() {#classmavsdk_1_1_shell_1a26b0e0d6a00d89c3d22c0f8a580c54c4}
```cpp
mavsdk::Shell::~Shell()
```


Destructor (internal use only).


### Shell() {#classmavsdk_1_1_shell_1a7fdf25f0db49675a24c6ce61be9f82b5}
```cpp
mavsdk::Shell::Shell(const Shell &)=delete
```


Copy constructor (object is not copyable).


**Parameters**

* const [Shell](classmavsdk_1_1_shell.md)&  - 

## Member Typdef Documentation


### typedef result_callback_t {#classmavsdk_1_1_shell_1a22aa50b455d6a3f81b4a29a9d339a8fa}

```cpp
typedef std::function<void(Result result, ShellMessage response)> mavsdk::Shell::result_callback_t
```


Callback type for shell requests.


## Member Enumeration Documentation


### enum Result {#classmavsdk_1_1_shell_1a768bfa296ba3309f936f887fb86c9ba8}


[Shell](classmavsdk_1_1_shell.md) Result Code enum.


Value | Description
--- | ---
<span id="classmavsdk_1_1_shell_1a768bfa296ba3309f936f887fb86c9ba8a696b031073e74bf2cb98e5ef201d4aa3"></span> `UNKNOWN` | Unknown error. 
<span id="classmavsdk_1_1_shell_1a768bfa296ba3309f936f887fb86c9ba8ad0749aaba8b833466dfcbb0428e4f89c"></span> `SUCCESS` | Request succeeded. 
<span id="classmavsdk_1_1_shell_1a768bfa296ba3309f936f887fb86c9ba8afeae72a3a2feec3c92c2a79a30d31186"></span> `NO_SYSTEM` | No system connected. 
<span id="classmavsdk_1_1_shell_1a768bfa296ba3309f936f887fb86c9ba8ac77f1f09dab2c0c9980fca7cfae02518"></span> `CONNECTION_ERROR` | Connection error. 
<span id="classmavsdk_1_1_shell_1a768bfa296ba3309f936f887fb86c9ba8a8e399aedb37789c2596e6c36b6c63547"></span> `NO_RESPONSE` | Response does not received. 
<span id="classmavsdk_1_1_shell_1a768bfa296ba3309f936f887fb86c9ba8a802706a9238e2928077f97736854bad4"></span> `BUSY` | [Shell](classmavsdk_1_1_shell.md) busy (transfer in progress) 

## Member Function Documentation


### shell_command() {#classmavsdk_1_1_shell_1a71647880750275ae20f9e9ff35759bff}
```cpp
Shell::Result mavsdk::Shell::shell_command(ShellMessage shell_message)
```


Send the shell message.

If shell_message.data string have not trailing newline - it will be added.


If response data looks like not completed try to increase timeout value in request.

**Parameters**

* [ShellMessage](structmavsdk_1_1_shell_1_1_shell_message.md) **shell_message** - [Shell](classmavsdk_1_1_shell.md) `struct`.

**Returns**

&emsp;[Shell::Result](classmavsdk_1_1_shell.md#classmavsdk_1_1_shell_1a768bfa296ba3309f936f887fb86c9ba8) - 

### shell_command_response_async() {#classmavsdk_1_1_shell_1aa619d754d68953adb87afa5af864151e}
```cpp
Shell::Result mavsdk::Shell::shell_command_response_async(result_callback_t callback)
```


Set [Shell](classmavsdk_1_1_shell.md) message Response callback (asynchronous).


**Parameters**

* [result_callback_t](classmavsdk_1_1_shell.md#classmavsdk_1_1_shell_1a22aa50b455d6a3f81b4a29a9d339a8fa) **callback** - Function to call with responses.

**Returns**

&emsp;[Shell::Result](classmavsdk_1_1_shell.md#classmavsdk_1_1_shell_1a768bfa296ba3309f936f887fb86c9ba8) - 

### operator=() {#classmavsdk_1_1_shell_1a492f8b2e36ef2468522bfd0f51f4b9b8}
```cpp
const Shell& mavsdk::Shell::operator=(const Shell &)=delete
```


Equality operator (object is not copyable).


**Parameters**

* const [Shell](classmavsdk_1_1_shell.md)&  - 

**Returns**

&emsp;const [Shell](classmavsdk_1_1_shell.md) & - 

### result_code_str() {#classmavsdk_1_1_shell_1a906fe10a4f5a9443e84fc9486221b3ff}
```cpp
static const char* mavsdk::Shell::result_code_str(Result result)
```


Get human-readable English string for Shell::Result::ResultCode.


**Parameters**

* [Result](classmavsdk_1_1_shell.md#classmavsdk_1_1_shell_1a768bfa296ba3309f936f887fb86c9ba8) **result** - The enum value for which string is needed.

**Returns**

&emsp;const char * - Human readable string for the Shell::Result::ResultCode.