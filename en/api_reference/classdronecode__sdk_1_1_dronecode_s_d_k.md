# dronecode_sdk::DronecodeSDK Class Reference
`#include: dronecode_sdk.h`

----


This is the main class of Dronecode SDK (a MAVLink API Library for the Dronecode Platform). 


It is used to discover vehicles and manage active connections.


An instance of this class must be created (first) in order to use the library. The instance must be destroyed after use in order to break connections and release all resources. 


## Public Types


Type | Description
--- | ---
enum [Configuration](#classdronecode__sdk_1_1_dronecode_s_d_k_1a3cb7c3712a0f330d29b30b501dfab947) | Possible configurations.
std::function< void(uint64_t uuid)> [event_callback_t](#classdronecode__sdk_1_1_dronecode_s_d_k_1a56579e10311b046b887fdec0c313a4b8) | Callback type for discover and timeout notifications.

## Public Member Functions


Type | Name | Description
---: | --- | ---
&nbsp; | [DronecodeSDK](#classdronecode__sdk_1_1_dronecode_s_d_k_1a3ddb4f17301ba5f0f1e66db31b2be424) () | Constructor.
&nbsp; | [~DronecodeSDK](#classdronecode__sdk_1_1_dronecode_s_d_k_1a95f12f7188d501d5379516879f8c2fd2) () | Destructor.
[ConnectionResult](namespacedronecode__sdk.md#namespacedronecode__sdk_1a8ba260cb5fc0837533a86e236d205c96) | [add_any_connection](#classdronecode__sdk_1_1_dronecode_s_d_k_1a51097e0dad30f0292a2ab4d3e9d91acf) (const std::string & connection_url) | Adds Connection via URL.
[ConnectionResult](namespacedronecode__sdk.md#namespacedronecode__sdk_1a8ba260cb5fc0837533a86e236d205c96) | [add_udp_connection](#classdronecode__sdk_1_1_dronecode_s_d_k_1ac242fb36bc018038fc1fc5ee4e5f21ad) (int local_port=[DEFAULT_UDP_PORT](classdronecode__sdk_1_1_dronecode_s_d_k.md#classdronecode__sdk_1_1_dronecode_s_d_k_1a2d814fa2138dd76f180777950ba2a1c2)) | Adds a UDP connection to the specified port number.
[ConnectionResult](namespacedronecode__sdk.md#namespacedronecode__sdk_1a8ba260cb5fc0837533a86e236d205c96) | [add_udp_connection](#classdronecode__sdk_1_1_dronecode_s_d_k_1a98122c953195b9ac7c6ce8df36ff5f2e) (const std::string & local_ip, int local_port=[DEFAULT_UDP_PORT](classdronecode__sdk_1_1_dronecode_s_d_k.md#classdronecode__sdk_1_1_dronecode_s_d_k_1a2d814fa2138dd76f180777950ba2a1c2)) | Adds a UDP connection to the specified port number and local interface.
[ConnectionResult](namespacedronecode__sdk.md#namespacedronecode__sdk_1a8ba260cb5fc0837533a86e236d205c96) | [add_tcp_connection](#classdronecode__sdk_1_1_dronecode_s_d_k_1a7c543c91cf9209745c60a5b4bb6a59b1) (int remote_port=[DEFAULT_TCP_REMOTE_PORT](classdronecode__sdk_1_1_dronecode_s_d_k.md#classdronecode__sdk_1_1_dronecode_s_d_k_1a27efab91c255ec80da081b3a2667130a)) | Adds a TCP connection with a specific port number on localhost.
[ConnectionResult](namespacedronecode__sdk.md#namespacedronecode__sdk_1a8ba260cb5fc0837533a86e236d205c96) | [add_tcp_connection](#classdronecode__sdk_1_1_dronecode_s_d_k_1ae1fda663ab173e0b1dfc644f630506e4) (const std::string & remote_ip, int remote_port=[DEFAULT_TCP_REMOTE_PORT](classdronecode__sdk_1_1_dronecode_s_d_k.md#classdronecode__sdk_1_1_dronecode_s_d_k_1a27efab91c255ec80da081b3a2667130a)) | Adds a TCP connection with a specific IP address and port number.
[ConnectionResult](namespacedronecode__sdk.md#namespacedronecode__sdk_1a8ba260cb5fc0837533a86e236d205c96) | [add_serial_connection](#classdronecode__sdk_1_1_dronecode_s_d_k_1a3b9dfa07541777ec16d9ada6423650b0) (const std::string & dev_path, int baudrate=[DEFAULT_SERIAL_BAUDRATE](classdronecode__sdk_1_1_dronecode_s_d_k.md#classdronecode__sdk_1_1_dronecode_s_d_k_1a535901e195f2910ce16bd85fca2c2e9d)) | Adds a serial connection with a specific port (COM or UART dev node) and baudrate as specified.
void | [set_configuration](#classdronecode__sdk_1_1_dronecode_s_d_k_1aa173ce1f22cbd3985fc9177392c7896b) ([Configuration](classdronecode__sdk_1_1_dronecode_s_d_k.md#classdronecode__sdk_1_1_dronecode_s_d_k_1a3cb7c3712a0f330d29b30b501dfab947) configuration) | Set `Configuration` of SDK.
std::vector< uint64_t > | [system_uuids](#classdronecode__sdk_1_1_dronecode_s_d_k_1adff0ce5e9bd666103a3ec5274ecb9b47) () const | Get vector of system UUIDs.
[System](classdronecode__sdk_1_1_system.md) & | [system](#classdronecode__sdk_1_1_dronecode_s_d_k_1a33dbbe477d4f321cff32c7cea1aee4eb) () const | Get the first discovered system.
[System](classdronecode__sdk_1_1_system.md) & | [system](#classdronecode__sdk_1_1_dronecode_s_d_k_1ad8138a15ad24f448733b76b267c62121) (uint64_t uuid)const | Get the system with the specified UUID.
bool | [is_connected](#classdronecode__sdk_1_1_dronecode_s_d_k_1a046e22e41fef9a654bbd0a814b933a62) () const | Returns `true` if exactly one system is currently connected.
bool | [is_connected](#classdronecode__sdk_1_1_dronecode_s_d_k_1a82017f6833745cfe37870ba795709b2f) (uint64_t uuid)const | Returns `true` if a system is currently connected.
void | [register_on_discover](#classdronecode__sdk_1_1_dronecode_s_d_k_1a7e4f9e429d59faa19578cffecc184427) ([event_callback_t](classdronecode__sdk_1_1_dronecode_s_d_k.md#classdronecode__sdk_1_1_dronecode_s_d_k_1a56579e10311b046b887fdec0c313a4b8) callback) | Register callback for system discovery.
void | [register_on_timeout](#classdronecode__sdk_1_1_dronecode_s_d_k_1a21d36d607097eb51197427ca04716b9b) ([event_callback_t](classdronecode__sdk_1_1_dronecode_s_d_k.md#classdronecode__sdk_1_1_dronecode_s_d_k_1a56579e10311b046b887fdec0c313a4b8) callback) | Register callback for system timeout.

## Static Public Attributes


static constexpr auto [DEFAULT_UDP_BIND_IP](#classdronecode__sdk_1_1_dronecode_s_d_k_1a663e912019e2d7119beb5207bf54e6f8) = "0.0.0.0" - Default UDP bind IP (accepts any incoming connections).


static constexpr int [DEFAULT_UDP_PORT](#classdronecode__sdk_1_1_dronecode_s_d_k_1a2d814fa2138dd76f180777950ba2a1c2) = 14540 - Default UDP bind port (same port as used by MAVROS).


static constexpr auto [DEFAULT_TCP_REMOTE_IP](#classdronecode__sdk_1_1_dronecode_s_d_k_1a47c9fd2b24f3de910e017bf9e8a5c8fc) = "127.0.0.1" - Default TCP remote IP (localhost).


static constexpr int [DEFAULT_TCP_REMOTE_PORT](#classdronecode__sdk_1_1_dronecode_s_d_k_1a27efab91c255ec80da081b3a2667130a) = 5760 - Default TCP remote port.


static constexpr int [DEFAULT_SERIAL_BAUDRATE](#classdronecode__sdk_1_1_dronecode_s_d_k_1a535901e195f2910ce16bd85fca2c2e9d) = 57600 - Default serial baudrate.


## Constructor & Destructor Documentation


### DronecodeSDK() {#classdronecode__sdk_1_1_dronecode_s_d_k_1a3ddb4f17301ba5f0f1e66db31b2be424}
```cpp
dronecode_sdk::DronecodeSDK::DronecodeSDK()
```


Constructor.


### ~DronecodeSDK() {#classdronecode__sdk_1_1_dronecode_s_d_k_1a95f12f7188d501d5379516879f8c2fd2}
```cpp
dronecode_sdk::DronecodeSDK::~DronecodeSDK()
```


Destructor.

Disconnects all connected vehicles and releases all resources.

## Member Typdef Documentation


### typedef event_callback_t {#classdronecode__sdk_1_1_dronecode_s_d_k_1a56579e10311b046b887fdec0c313a4b8}

```cpp
typedef std::function<void(uint64_t uuid)> dronecode_sdk::DronecodeSDK::event_callback_t
```


Callback type for discover and timeout notifications.


**Parameters**

* **uuid** - UUID of system (or MAVLink system ID for systems that don't have a UUID).

## Member Enumeration Documentation


### enum Configuration {#classdronecode__sdk_1_1_dronecode_s_d_k_1a3cb7c3712a0f330d29b30b501dfab947}


Possible configurations.


Value | Description
--- | ---
<span id="classdronecode__sdk_1_1_dronecode_s_d_k_1a3cb7c3712a0f330d29b30b501dfab947af64f82089eddc6133add8c55c65d6687"></span> `GroundStation` | SDK is used as a ground station. 
<span id="classdronecode__sdk_1_1_dronecode_s_d_k_1a3cb7c3712a0f330d29b30b501dfab947a8f2f82e1a7aa48819e9530d5c4977477"></span> `CompanionComputer` | SDK is used on a companion computer onboard the system (e.g. drone). 

## Member Function Documentation


### add_any_connection() {#classdronecode__sdk_1_1_dronecode_s_d_k_1a51097e0dad30f0292a2ab4d3e9d91acf}
```cpp
ConnectionResult dronecode_sdk::DronecodeSDK::add_any_connection(const std::string &connection_url)
```


Adds Connection via URL.

Supports connection: Serial, TCP or UDP. Connection URL format should be:
<ul>
<li><p>UDP - udp://[Bind_host][:Bind_port]</p></li>
<li><p>TCP - tcp://[Remote_host][:Remote_port]</p></li>
<li><p>Serial - serial://Dev_Node[:Baudrate]</p></li>
</ul>

**Parameters**

* const std::string& **connection_url** - connection URL string.

**Returns**

&emsp;[ConnectionResult](namespacedronecode__sdk.md#namespacedronecode__sdk_1a8ba260cb5fc0837533a86e236d205c96) - The result of adding the connection.

### add_udp_connection() {#classdronecode__sdk_1_1_dronecode_s_d_k_1ac242fb36bc018038fc1fc5ee4e5f21ad}
```cpp
ConnectionResult dronecode_sdk::DronecodeSDK::add_udp_connection(int local_port=DEFAULT_UDP_PORT)
```


Adds a UDP connection to the specified port number.

Any incoming connections are accepted (0.0.0.0).

**Parameters**

* int **local_port** - The local UDP port to listen to (defaults to 14540, the same as MAVROS).

**Returns**

&emsp;[ConnectionResult](namespacedronecode__sdk.md#namespacedronecode__sdk_1a8ba260cb5fc0837533a86e236d205c96) - The result of adding the connection.

### add_udp_connection() {#classdronecode__sdk_1_1_dronecode_s_d_k_1a98122c953195b9ac7c6ce8df36ff5f2e}
```cpp
ConnectionResult dronecode_sdk::DronecodeSDK::add_udp_connection(const std::string &local_ip, int local_port=DEFAULT_UDP_PORT)
```


Adds a UDP connection to the specified port number and local interface.

To accept only local connections of the machine, use 127.0.0.1. For any incoming connections, use 0.0.0.0.

**Parameters**

* const std::string& **local_ip** - The local UDP IP address to listen to.
* int **local_port** - The local UDP port to listen to (defaults to 14540, the same as MAVROS).

**Returns**

&emsp;[ConnectionResult](namespacedronecode__sdk.md#namespacedronecode__sdk_1a8ba260cb5fc0837533a86e236d205c96) - The result of adding the connection.

### add_tcp_connection() {#classdronecode__sdk_1_1_dronecode_s_d_k_1a7c543c91cf9209745c60a5b4bb6a59b1}
```cpp
ConnectionResult dronecode_sdk::DronecodeSDK::add_tcp_connection(int remote_port=DEFAULT_TCP_REMOTE_PORT)
```


Adds a TCP connection with a specific port number on localhost.


**Parameters**

* int **remote_port** - The TCP port to connect to (defaults to 5760).

**Returns**

&emsp;[ConnectionResult](namespacedronecode__sdk.md#namespacedronecode__sdk_1a8ba260cb5fc0837533a86e236d205c96) - The result of adding the connection.

### add_tcp_connection() {#classdronecode__sdk_1_1_dronecode_s_d_k_1ae1fda663ab173e0b1dfc644f630506e4}
```cpp
ConnectionResult dronecode_sdk::DronecodeSDK::add_tcp_connection(const std::string &remote_ip, int remote_port=DEFAULT_TCP_REMOTE_PORT)
```


Adds a TCP connection with a specific IP address and port number.


**Parameters**

* const std::string& **remote_ip** - Remote IP address to connect to.
* int **remote_port** - The TCP port to connect to (defaults to 5760).

**Returns**

&emsp;[ConnectionResult](namespacedronecode__sdk.md#namespacedronecode__sdk_1a8ba260cb5fc0837533a86e236d205c96) - The result of adding the connection.

### add_serial_connection() {#classdronecode__sdk_1_1_dronecode_s_d_k_1a3b9dfa07541777ec16d9ada6423650b0}
```cpp
ConnectionResult dronecode_sdk::DronecodeSDK::add_serial_connection(const std::string &dev_path, int baudrate=DEFAULT_SERIAL_BAUDRATE)
```


Adds a serial connection with a specific port (COM or UART dev node) and baudrate as specified.


**Parameters**

* const std::string& **dev_path** - COM or UART dev node name/path (e.g. "/dev/ttyS0", or "COM3" on Windows).
* int **baudrate** - Baudrate of the serial port (defaults to 57600).

**Returns**

&emsp;[ConnectionResult](namespacedronecode__sdk.md#namespacedronecode__sdk_1a8ba260cb5fc0837533a86e236d205c96) - The result of adding the connection.

### set_configuration() {#classdronecode__sdk_1_1_dronecode_s_d_k_1aa173ce1f22cbd3985fc9177392c7896b}
```cpp
void dronecode_sdk::DronecodeSDK::set_configuration(Configuration configuration)
```


Set `Configuration` of SDK.

The default configuration is [Configuration::GroundStation](classdronecode__sdk_1_1_dronecode_s_d_k.md#classdronecode__sdk_1_1_dronecode_s_d_k_1a3cb7c3712a0f330d29b30b501dfab947af64f82089eddc6133add8c55c65d6687) The configuration is used in order to set the MAVLink system ID, the component ID, as well as the MAV_TYPE accordingly.

**Parameters**

* [Configuration](classdronecode__sdk_1_1_dronecode_s_d_k.md#classdronecode__sdk_1_1_dronecode_s_d_k_1a3cb7c3712a0f330d29b30b501dfab947) **configuration** - Configuration chosen.

### system_uuids() {#classdronecode__sdk_1_1_dronecode_s_d_k_1adff0ce5e9bd666103a3ec5274ecb9b47}
```cpp
std::vector<uint64_t> dronecode_sdk::DronecodeSDK::system_uuids() const
```


Get vector of system UUIDs.

This returns a vector of the UUIDs of all systems that have been discovered. If a system doesn't have a UUID then [DronecodeSDK](classdronecode__sdk_1_1_dronecode_s_d_k.md) will instead use its MAVLink system ID (range: 0..255).

**Returns**

&emsp;std::vector< uint64_t > - A vector containing the UUIDs.

### system() {#classdronecode__sdk_1_1_dronecode_s_d_k_1a33dbbe477d4f321cff32c7cea1aee4eb}
```cpp
System& dronecode_sdk::DronecodeSDK::system() const
```


Get the first discovered system.

This returns the first discovered system or a null system if no system has yet been found.

**Returns**

&emsp;[System](classdronecode__sdk_1_1_system.md) & - A reference to a system.

### system() {#classdronecode__sdk_1_1_dronecode_s_d_k_1ad8138a15ad24f448733b76b267c62121}
```cpp
System& dronecode_sdk::DronecodeSDK::system(uint64_t uuid) const
```


Get the system with the specified UUID.

This returns a system for a given UUID if such a system has been discovered and a null system otherwise.

**Parameters**

* uint64_t **uuid** - UUID of system to get.

**Returns**

&emsp;[System](classdronecode__sdk_1_1_system.md) & - A reference to the specified system.

### is_connected() {#classdronecode__sdk_1_1_dronecode_s_d_k_1a046e22e41fef9a654bbd0a814b933a62}
```cpp
bool dronecode_sdk::DronecodeSDK::is_connected() const
```


Returns `true` if exactly one system is currently connected.

Connected means we are receiving heartbeats from this system. It means the same as "discovered" and "not timed out".


If multiple systems have connected, this will return `false`.

**Returns**

&emsp;bool - `true` if exactly one system is connected.

### is_connected() {#classdronecode__sdk_1_1_dronecode_s_d_k_1a82017f6833745cfe37870ba795709b2f}
```cpp
bool dronecode_sdk::DronecodeSDK::is_connected(uint64_t uuid) const
```


Returns `true` if a system is currently connected.

Connected means we are receiving heartbeats from this system. It means the same as "discovered" and "not timed out".

**Parameters**

* uint64_t **uuid** - UUID of system to check.

**Returns**

&emsp;bool - `true` if system is connected.

### register_on_discover() {#classdronecode__sdk_1_1_dronecode_s_d_k_1a7e4f9e429d59faa19578cffecc184427}
```cpp
void dronecode_sdk::DronecodeSDK::register_on_discover(event_callback_t callback)
```


Register callback for system discovery.

This sets a callback that will be notified if a new system is discovered.


If systems have been discovered before this callback is registered, they will be notified at the time this callback is registered.


> **Note** Only one callback can be registered at a time. If this function is called several times, previous callbacks will be overwritten.

**Parameters**

* [event_callback_t](classdronecode__sdk_1_1_dronecode_s_d_k.md#classdronecode__sdk_1_1_dronecode_s_d_k_1a56579e10311b046b887fdec0c313a4b8) **callback** - Callback to register.

### register_on_timeout() {#classdronecode__sdk_1_1_dronecode_s_d_k_1a21d36d607097eb51197427ca04716b9b}
```cpp
void dronecode_sdk::DronecodeSDK::register_on_timeout(event_callback_t callback)
```


Register callback for system timeout.

This sets a callback that will be notified if no heartbeat of the system has been received in 3 seconds.


> **Note** Only one callback can be registered at a time. If this function is called several times, previous callbacks will be overwritten.

**Parameters**

* [event_callback_t](classdronecode__sdk_1_1_dronecode_s_d_k.md#classdronecode__sdk_1_1_dronecode_s_d_k_1a56579e10311b046b887fdec0c313a4b8) **callback** - Callback to register.

## Field Documentation


### DEFAULT_UDP_BIND_IP {#classdronecode__sdk_1_1_dronecode_s_d_k_1a663e912019e2d7119beb5207bf54e6f8}

```cpp
constexpr auto dronecode_sdk::DronecodeSDK::DEFAULT_UDP_BIND_IP = "0.0.0.0"
```


Default UDP bind IP (accepts any incoming connections).


### DEFAULT_UDP_PORT {#classdronecode__sdk_1_1_dronecode_s_d_k_1a2d814fa2138dd76f180777950ba2a1c2}

```cpp
constexpr int dronecode_sdk::DronecodeSDK::DEFAULT_UDP_PORT = 14540
```


Default UDP bind port (same port as used by MAVROS).


### DEFAULT_TCP_REMOTE_IP {#classdronecode__sdk_1_1_dronecode_s_d_k_1a47c9fd2b24f3de910e017bf9e8a5c8fc}

```cpp
constexpr auto dronecode_sdk::DronecodeSDK::DEFAULT_TCP_REMOTE_IP = "127.0.0.1"
```


Default TCP remote IP (localhost).


### DEFAULT_TCP_REMOTE_PORT {#classdronecode__sdk_1_1_dronecode_s_d_k_1a27efab91c255ec80da081b3a2667130a}

```cpp
constexpr int dronecode_sdk::DronecodeSDK::DEFAULT_TCP_REMOTE_PORT = 5760
```


Default TCP remote port.


### DEFAULT_SERIAL_BAUDRATE {#classdronecode__sdk_1_1_dronecode_s_d_k_1a535901e195f2910ce16bd85fca2c2e9d}

```cpp
constexpr int dronecode_sdk::DronecodeSDK::DEFAULT_SERIAL_BAUDRATE = 57600
```


Default serial baudrate.

