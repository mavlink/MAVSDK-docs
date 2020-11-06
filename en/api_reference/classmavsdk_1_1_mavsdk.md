# mavsdk::Mavsdk Class Reference
`#include: mavsdk.h`

----


This is the main class of MAVSDK (a MAVLink API Library). 


It is used to discover vehicles and manage active connections.


An instance of this class must be created (first) in order to use the library. The instance must be destroyed after use in order to break connections and release all resources. 


## Data Structures


struct [Configuration](classmavsdk_1_1_mavsdk_1_1_configuration.md)

## Public Types


Type | Description
--- | ---
std::function< void()> [NewSystemCallback](#classmavsdk_1_1_mavsdk_1a7a283c6a75e852a56be4c5862f8a3fab) | Callback type discover and timeout notifications.
std::function< void(uint64_t uuid)> [event_callback_t](#classmavsdk_1_1_mavsdk_1a827a58394300cac929670ab592de8818) | Callback type for discover and timeout notifications (deprecated).

## Public Member Functions


Type | Name | Description
---: | --- | ---
&nbsp; | [Mavsdk](#classmavsdk_1_1_mavsdk_1aad81f6df52096ea28d4e646ad7339461) () | Constructor.
&nbsp; | [~Mavsdk](#classmavsdk_1_1_mavsdk_1ac1549f715d6857711b9b9e364a4ca351) () | Destructor.
std::string | [version](#classmavsdk_1_1_mavsdk_1a8fdb97695762d06fd2bccfc6309943fa) () const | Returns the version of MAVSDK.
[ConnectionResult](namespacemavsdk.md#namespacemavsdk_1a0bad93f6d037051ac3906a0bcc09f992) | [add_any_connection](#classmavsdk_1_1_mavsdk_1a229888e2931c16d11edbed07b03174d4) (const std::string & connection_url) | Adds Connection via URL.
[ConnectionResult](namespacemavsdk.md#namespacemavsdk_1a0bad93f6d037051ac3906a0bcc09f992) | [add_udp_connection](#classmavsdk_1_1_mavsdk_1a605d3a89cd527222bf131b2c036dc899) (int local_port=[DEFAULT_UDP_PORT](classmavsdk_1_1_mavsdk.md#classmavsdk_1_1_mavsdk_1affddcc7c7849ed86a0c7dab1166e657a)) | Adds a UDP connection to the specified port number.
[ConnectionResult](namespacemavsdk.md#namespacemavsdk_1a0bad93f6d037051ac3906a0bcc09f992) | [add_udp_connection](#classmavsdk_1_1_mavsdk_1a20b51cc972876eef5101e35a5c289c13) (const std::string & local_ip, int local_port=[DEFAULT_UDP_PORT](classmavsdk_1_1_mavsdk.md#classmavsdk_1_1_mavsdk_1affddcc7c7849ed86a0c7dab1166e657a)) | Adds a UDP connection to the specified port number and local interface.
[ConnectionResult](namespacemavsdk.md#namespacemavsdk_1a0bad93f6d037051ac3906a0bcc09f992) | [setup_udp_remote](#classmavsdk_1_1_mavsdk_1a438b86fab92fa85cd8bc5dff90991eed) (const std::string & remote_ip, int remote_port) | Sets up instance to send heartbeats to the specified remote interface and port number.
[ConnectionResult](namespacemavsdk.md#namespacemavsdk_1a0bad93f6d037051ac3906a0bcc09f992) | [add_tcp_connection](#classmavsdk_1_1_mavsdk_1a868d224223d2f4e8de7d5e00863b6ceb) (int remote_port=[DEFAULT_TCP_REMOTE_PORT](classmavsdk_1_1_mavsdk.md#classmavsdk_1_1_mavsdk_1a52a6a9e0acd6c0ade566208d253427bd)) | Adds a TCP connection with a specific port number on localhost.
[ConnectionResult](namespacemavsdk.md#namespacemavsdk_1a0bad93f6d037051ac3906a0bcc09f992) | [add_tcp_connection](#classmavsdk_1_1_mavsdk_1a950038afdd201f89e97a3e60e227869a) (const std::string & remote_ip, int remote_port=[DEFAULT_TCP_REMOTE_PORT](classmavsdk_1_1_mavsdk.md#classmavsdk_1_1_mavsdk_1a52a6a9e0acd6c0ade566208d253427bd)) | Adds a TCP connection with a specific IP address and port number.
[ConnectionResult](namespacemavsdk.md#namespacemavsdk_1a0bad93f6d037051ac3906a0bcc09f992) | [add_serial_connection](#classmavsdk_1_1_mavsdk_1a8bb8d79c35c44eb3b57fe658c060b093) (const std::string & dev_path, int baudrate=[DEFAULT_SERIAL_BAUDRATE](classmavsdk_1_1_mavsdk.md#classmavsdk_1_1_mavsdk_1a870d15142914f1db564c12f385d5489b), bool flow_control=false) | Adds a serial connection with a specific port (COM or UART dev node) and baudrate as specified.
std::vector< std::shared_ptr< [System](classmavsdk_1_1_system.md) > > | [systems](#classmavsdk_1_1_mavsdk_1a0d0bc4cdab14d96877b52baec5113fa8) () const | Get a vector of systems which have been discovered or set-up.
void | [set_configuration](#classmavsdk_1_1_mavsdk_1acaeea86253493dc15b6540d2100a1b86) ([Configuration](classmavsdk_1_1_mavsdk_1_1_configuration.md) configuration) | Set [Configuration](classmavsdk_1_1_mavsdk_1_1_configuration.md) of SDK.
DEPRECATED std::vector< uint64_t > | [system_uuids](#classmavsdk_1_1_mavsdk_1a21e860cb6d24a0c94e8381a8552563fd) () const | Get vector of system UUIDs (deprecated).
DEPRECATED [System](classmavsdk_1_1_system.md) & | [system](#classmavsdk_1_1_mavsdk_1a94227abeef7ccb938126ca94b1d034e9) () const | Get the first discovered system.
DEPRECATED [System](classmavsdk_1_1_system.md) & | [system](#classmavsdk_1_1_mavsdk_1aa21bb28b338c89d670b839491568ff31) (uint64_t uuid)const | Get the system with the specified UUID (deprecated).
void | [subscribe_on_new_system](#classmavsdk_1_1_mavsdk_1a332ae41c7de84d5cfab11fb3e2e65522) ([NewSystemCallback](classmavsdk_1_1_mavsdk.md#classmavsdk_1_1_mavsdk_1a7a283c6a75e852a56be4c5862f8a3fab) callback) | Get notification about a change in systems.
DEPRECATED bool | [is_connected](#classmavsdk_1_1_mavsdk_1af45d884188908b13c4bef938555b2634) () const | Returns `true` if exactly one system is currently connected.
DEPRECATED bool | [is_connected](#classmavsdk_1_1_mavsdk_1adcc7d75add77b8d7beb750cc49f54c89) (uint64_t uuid)const | Returns `true` if a system is currently connected (deprecated).
DEPRECATED void | [register_on_discover](#classmavsdk_1_1_mavsdk_1ac724800e74359b0ff26fade5f101d8a6) ([event_callback_t](classmavsdk_1_1_mavsdk.md#classmavsdk_1_1_mavsdk_1a827a58394300cac929670ab592de8818) callback) | Register callback for system discovery.
DEPRECATED void | [register_on_timeout](#classmavsdk_1_1_mavsdk_1a2008e8a34d1098a5473cc0335eacd0ac) ([event_callback_t](classmavsdk_1_1_mavsdk.md#classmavsdk_1_1_mavsdk_1a827a58394300cac929670ab592de8818) callback) | Register callback for system timeout.

## Static Public Attributes


static constexpr auto [DEFAULT_UDP_BIND_IP](#classmavsdk_1_1_mavsdk_1ac46b2c27d9c428ec46092f10774482fa) = "0.0.0.0" - Default UDP bind IP (accepts any incoming connections).


static constexpr int [DEFAULT_UDP_PORT](#classmavsdk_1_1_mavsdk_1affddcc7c7849ed86a0c7dab1166e657a) = 14540 - Default UDP bind port (same port as used by MAVROS).


static constexpr auto [DEFAULT_TCP_REMOTE_IP](#classmavsdk_1_1_mavsdk_1a0154aac9d933fa212a50dc687816fbad) = "127.0.0.1" - Default TCP remote IP (localhost).


static constexpr int [DEFAULT_TCP_REMOTE_PORT](#classmavsdk_1_1_mavsdk_1a52a6a9e0acd6c0ade566208d253427bd) = 5760 - Default TCP remote port.


static constexpr int [DEFAULT_SERIAL_BAUDRATE](#classmavsdk_1_1_mavsdk_1a870d15142914f1db564c12f385d5489b) = 57600 - Default serial baudrate.


## Constructor & Destructor Documentation


### Mavsdk() {#classmavsdk_1_1_mavsdk_1aad81f6df52096ea28d4e646ad7339461}
```cpp
mavsdk::Mavsdk::Mavsdk()
```


Constructor.


### ~Mavsdk() {#classmavsdk_1_1_mavsdk_1ac1549f715d6857711b9b9e364a4ca351}
```cpp
mavsdk::Mavsdk::~Mavsdk()
```


Destructor.

Disconnects all connected vehicles and releases all resources.

## Member Typdef Documentation


### typedef NewSystemCallback {#classmavsdk_1_1_mavsdk_1a7a283c6a75e852a56be4c5862f8a3fab}

```cpp
using mavsdk::Mavsdk::NewSystemCallback =  std::function<void()>
```


Callback type discover and timeout notifications.


### typedef event_callback_t {#classmavsdk_1_1_mavsdk_1a827a58394300cac929670ab592de8818}

```cpp
typedef std::function<void(uint64_t uuid)> mavsdk::Mavsdk::event_callback_t
```


Callback type for discover and timeout notifications (deprecated).

> **Note** This typedef is deprecated because the UUID is replaced by uid with 18 bytes.

**Parameters**

* **uuid** - UUID of system (or MAVLink system ID for systems that don't have a UUID).

## Member Function Documentation


### version() {#classmavsdk_1_1_mavsdk_1a8fdb97695762d06fd2bccfc6309943fa}
```cpp
std::string mavsdk::Mavsdk::version() const
```


Returns the version of MAVSDK.

Note, you're not supposed to request the version too many times.

**Returns**

&emsp;std::string - A string containing the version.

### add_any_connection() {#classmavsdk_1_1_mavsdk_1a229888e2931c16d11edbed07b03174d4}
```cpp
ConnectionResult mavsdk::Mavsdk::add_any_connection(const std::string &connection_url)
```


Adds Connection via URL.

Supports connection: Serial, TCP or UDP. Connection URL format should be:
<ul>
<li><p>UDP - udp://[Bind_host][:Bind_port]</p>
</li>
<li><p>TCP - tcp://[Remote_host][:Remote_port]</p>
</li>
<li><p>Serial - serial://Dev_Node[:Baudrate]</p>
</li>
</ul>

**Parameters**

* const std::string& **connection_url** - connection URL string.

**Returns**

&emsp;[ConnectionResult](namespacemavsdk.md#namespacemavsdk_1a0bad93f6d037051ac3906a0bcc09f992) - The result of adding the connection.

### add_udp_connection() {#classmavsdk_1_1_mavsdk_1a605d3a89cd527222bf131b2c036dc899}
```cpp
ConnectionResult mavsdk::Mavsdk::add_udp_connection(int local_port=DEFAULT_UDP_PORT)
```


Adds a UDP connection to the specified port number.

Any incoming connections are accepted (0.0.0.0).

**Parameters**

* int **local_port** - The local UDP port to listen to (defaults to 14540, the same as MAVROS).

**Returns**

&emsp;[ConnectionResult](namespacemavsdk.md#namespacemavsdk_1a0bad93f6d037051ac3906a0bcc09f992) - The result of adding the connection.

### add_udp_connection() {#classmavsdk_1_1_mavsdk_1a20b51cc972876eef5101e35a5c289c13}
```cpp
ConnectionResult mavsdk::Mavsdk::add_udp_connection(const std::string &local_ip, int local_port=DEFAULT_UDP_PORT)
```


Adds a UDP connection to the specified port number and local interface.

To accept only local connections of the machine, use 127.0.0.1. For any incoming connections, use 0.0.0.0.

**Parameters**

* const std::string& **local_ip** - The local UDP IP address to listen to.
* int **local_port** - The local UDP port to listen to (defaults to 14540, the same as MAVROS).

**Returns**

&emsp;[ConnectionResult](namespacemavsdk.md#namespacemavsdk_1a0bad93f6d037051ac3906a0bcc09f992) - The result of adding the connection.

### setup_udp_remote() {#classmavsdk_1_1_mavsdk_1a438b86fab92fa85cd8bc5dff90991eed}
```cpp
ConnectionResult mavsdk::Mavsdk::setup_udp_remote(const std::string &remote_ip, int remote_port)
```


Sets up instance to send heartbeats to the specified remote interface and port number.


**Parameters**

* const std::string& **remote_ip** - The remote UDP IP address to report to.
* int **remote_port** - The local UDP port to report to.

**Returns**

&emsp;[ConnectionResult](namespacemavsdk.md#namespacemavsdk_1a0bad93f6d037051ac3906a0bcc09f992) - The result of operation.

### add_tcp_connection() {#classmavsdk_1_1_mavsdk_1a868d224223d2f4e8de7d5e00863b6ceb}
```cpp
ConnectionResult mavsdk::Mavsdk::add_tcp_connection(int remote_port=DEFAULT_TCP_REMOTE_PORT)
```


Adds a TCP connection with a specific port number on localhost.


**Parameters**

* int **remote_port** - The TCP port to connect to (defaults to 5760).

**Returns**

&emsp;[ConnectionResult](namespacemavsdk.md#namespacemavsdk_1a0bad93f6d037051ac3906a0bcc09f992) - The result of adding the connection.

### add_tcp_connection() {#classmavsdk_1_1_mavsdk_1a950038afdd201f89e97a3e60e227869a}
```cpp
ConnectionResult mavsdk::Mavsdk::add_tcp_connection(const std::string &remote_ip, int remote_port=DEFAULT_TCP_REMOTE_PORT)
```


Adds a TCP connection with a specific IP address and port number.


**Parameters**

* const std::string& **remote_ip** - Remote IP address to connect to.
* int **remote_port** - The TCP port to connect to (defaults to 5760).

**Returns**

&emsp;[ConnectionResult](namespacemavsdk.md#namespacemavsdk_1a0bad93f6d037051ac3906a0bcc09f992) - The result of adding the connection.

### add_serial_connection() {#classmavsdk_1_1_mavsdk_1a8bb8d79c35c44eb3b57fe658c060b093}
```cpp
ConnectionResult mavsdk::Mavsdk::add_serial_connection(const std::string &dev_path, int baudrate=DEFAULT_SERIAL_BAUDRATE, bool flow_control=false)
```


Adds a serial connection with a specific port (COM or UART dev node) and baudrate as specified.


**Parameters**

* const std::string& **dev_path** - COM or UART dev node name/path (e.g. "/dev/ttyS0", or "COM3" on Windows).
* int **baudrate** - Baudrate of the serial port (defaults to 57600).
* bool **flow_control** - enable/disable flow control

**Returns**

&emsp;[ConnectionResult](namespacemavsdk.md#namespacemavsdk_1a0bad93f6d037051ac3906a0bcc09f992) - The result of adding the connection.

### systems() {#classmavsdk_1_1_mavsdk_1a0d0bc4cdab14d96877b52baec5113fa8}
```cpp
std::vector<std::shared_ptr<System> > mavsdk::Mavsdk::systems() const
```


Get a vector of systems which have been discovered or set-up.


**Returns**

&emsp;std::vector< std::shared_ptr< [System](classmavsdk_1_1_system.md) > > - The vector of systems which are available.

### set_configuration() {#classmavsdk_1_1_mavsdk_1acaeea86253493dc15b6540d2100a1b86}
```cpp
void mavsdk::Mavsdk::set_configuration(Configuration configuration)
```


Set [Configuration](classmavsdk_1_1_mavsdk_1_1_configuration.md) of SDK.

The default configuration is `Configuration::GroundStation` The configuration is used in order to set the MAVLink system ID, the component ID, as well as the MAV_TYPE accordingly.

**Parameters**

* [Configuration](classmavsdk_1_1_mavsdk_1_1_configuration.md) **configuration** - [Configuration](classmavsdk_1_1_mavsdk_1_1_configuration.md) chosen.

### system_uuids() {#classmavsdk_1_1_mavsdk_1a21e860cb6d24a0c94e8381a8552563fd}
```cpp
DEPRECATED std::vector<uint64_t> mavsdk::Mavsdk::system_uuids() const
```


Get vector of system UUIDs (deprecated).

This returns a vector of the UUIDs of all systems that have been discovered. If a system doesn't have a UUID then [Mavsdk](classmavsdk_1_1_mavsdk.md) will instead use its MAVLink system ID (range: 0..255).


> **Note** This method will be deprecated because the UUID will be replaced by a uid with 18 bytes.

**Returns**

&emsp;DEPRECATED std::vector< uint64_t > - A vector containing the UUIDs.

### system() {#classmavsdk_1_1_mavsdk_1a94227abeef7ccb938126ca94b1d034e9}
```cpp
DEPRECATED System& mavsdk::Mavsdk::system() const
```


Get the first discovered system.

This returns the first discovered system or a null system if no system has yet been found.


> **Note** This method will be deprecated because it will be replaced by a vector of system pointers.

**Returns**

&emsp;DEPRECATED [System](classmavsdk_1_1_system.md) & - A reference to a system.

### system() {#classmavsdk_1_1_mavsdk_1aa21bb28b338c89d670b839491568ff31}
```cpp
DEPRECATED System& mavsdk::Mavsdk::system(uint64_t uuid) const
```


Get the system with the specified UUID (deprecated).

This returns a system for a given UUID if such a system has been discovered and a null system otherwise.


> **Note** This method will be deprecated because the UUID will be replaced by a uid with 18 bytes.

**Parameters**

* uint64_t **uuid** - UUID of system to get.

**Returns**

&emsp;DEPRECATED [System](classmavsdk_1_1_system.md) & - A reference to the specified system.

### subscribe_on_new_system() {#classmavsdk_1_1_mavsdk_1a332ae41c7de84d5cfab11fb3e2e65522}
```cpp
void mavsdk::Mavsdk::subscribe_on_new_system(NewSystemCallback callback)
```


Get notification about a change in systems.

This gets called whenever a system is added.


> **Note** Only one subscriber is possible at any time. On a second subscription, the previous one is overwritten. To unsubscribe, pass nullptr;

**Parameters**

* [NewSystemCallback](classmavsdk_1_1_mavsdk.md#classmavsdk_1_1_mavsdk_1a7a283c6a75e852a56be4c5862f8a3fab) **callback** - Callback to subscribe.

### is_connected() {#classmavsdk_1_1_mavsdk_1af45d884188908b13c4bef938555b2634}
```cpp
DEPRECATED bool mavsdk::Mavsdk::is_connected() const
```


Returns `true` if exactly one system is currently connected.

Connected means we are receiving heartbeats from this system. It means the same as "discovered" and "not timed out".


If multiple systems have connected, this will return `false`.


> **Note** This method will be deprecated because is_connected will be a method of the system, not of mavsdk.

**Returns**

&emsp;DEPRECATED bool - `true` if exactly one system is connected.

### is_connected() {#classmavsdk_1_1_mavsdk_1adcc7d75add77b8d7beb750cc49f54c89}
```cpp
DEPRECATED bool mavsdk::Mavsdk::is_connected(uint64_t uuid) const
```


Returns `true` if a system is currently connected (deprecated).

Connected means we are receiving heartbeats from this system. It means the same as "discovered" and "not timed out".


> **Note** This method will be deprecated because the UUID will be replaced by uid with 18 bytes.

**Parameters**

* uint64_t **uuid** - UUID of system to check.

**Returns**

&emsp;DEPRECATED bool - `true` if system is connected.

### register_on_discover() {#classmavsdk_1_1_mavsdk_1ac724800e74359b0ff26fade5f101d8a6}
```cpp
DEPRECATED void mavsdk::Mavsdk::register_on_discover(event_callback_t callback)
```


Register callback for system discovery.

This sets a callback that will be notified if a new system is discovered.


If systems have been discovered before this callback is registered, they will be notified at the time this callback is registered.


> **Note** Only one callback can be registered at a time. If this function is called several times, previous callbacks will be overwritten.


> **Note** This method will be deprecated because event_callback_t is deprecated and it will be replaced by [subscribe_on_new_system()](classmavsdk_1_1_mavsdk.md#classmavsdk_1_1_mavsdk_1a332ae41c7de84d5cfab11fb3e2e65522).

**Parameters**

* [event_callback_t](classmavsdk_1_1_mavsdk.md#classmavsdk_1_1_mavsdk_1a827a58394300cac929670ab592de8818) **callback** - Callback to register.

**Returns**

&emsp;DEPRECATED void - 

### register_on_timeout() {#classmavsdk_1_1_mavsdk_1a2008e8a34d1098a5473cc0335eacd0ac}
```cpp
DEPRECATED void mavsdk::Mavsdk::register_on_timeout(event_callback_t callback)
```


Register callback for system timeout.

This sets a callback that will be notified if no heartbeat of the system has been received in 3 seconds.


> **Note** Only one callback can be registered at a time. If this function is called several times, previous callbacks will be overwritten.


> **Note** This method will be deprecated because event_callback_t is deprecated and it will be replaced by [subscribe_on_new_system()](classmavsdk_1_1_mavsdk.md#classmavsdk_1_1_mavsdk_1a332ae41c7de84d5cfab11fb3e2e65522).

**Parameters**

* [event_callback_t](classmavsdk_1_1_mavsdk.md#classmavsdk_1_1_mavsdk_1a827a58394300cac929670ab592de8818) **callback** - Callback to register.

**Returns**

&emsp;DEPRECATED void - 

## Field Documentation


### DEFAULT_UDP_BIND_IP {#classmavsdk_1_1_mavsdk_1ac46b2c27d9c428ec46092f10774482fa}

```cpp
constexpr auto mavsdk::Mavsdk::DEFAULT_UDP_BIND_IP = "0.0.0.0"
```


Default UDP bind IP (accepts any incoming connections).


### DEFAULT_UDP_PORT {#classmavsdk_1_1_mavsdk_1affddcc7c7849ed86a0c7dab1166e657a}

```cpp
constexpr int mavsdk::Mavsdk::DEFAULT_UDP_PORT = 14540
```


Default UDP bind port (same port as used by MAVROS).


### DEFAULT_TCP_REMOTE_IP {#classmavsdk_1_1_mavsdk_1a0154aac9d933fa212a50dc687816fbad}

```cpp
constexpr auto mavsdk::Mavsdk::DEFAULT_TCP_REMOTE_IP = "127.0.0.1"
```


Default TCP remote IP (localhost).


### DEFAULT_TCP_REMOTE_PORT {#classmavsdk_1_1_mavsdk_1a52a6a9e0acd6c0ade566208d253427bd}

```cpp
constexpr int mavsdk::Mavsdk::DEFAULT_TCP_REMOTE_PORT = 5760
```


Default TCP remote port.


### DEFAULT_SERIAL_BAUDRATE {#classmavsdk_1_1_mavsdk_1a870d15142914f1db564c12f385d5489b}

```cpp
constexpr int mavsdk::Mavsdk::DEFAULT_SERIAL_BAUDRATE = 57600
```


Default serial baudrate.

