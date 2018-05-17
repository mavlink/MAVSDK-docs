# dronecore::DroneCore Class Reference
`#include: dronecore.h`

----


This is the main class of **DroneCore MAVLink API Library** (for the Dronecode Platform). 


It is used to discover vehicles and manage active connections.


An instance of this class must be created (first) in order to use the library. The instance must be destroyed after use in order to break connections and release all resources. 


## Public Types


Type | Description
--- | ---
std::function< void(uint64_t uuid)> [event_callback_t](#classdronecore_1_1_drone_core_1abb488f975ee7e199cd1cb08a317a52c3) | Callback type for discover and timeout notifications.

## Public Member Functions


Type | Name | Description
---: | --- | ---
&nbsp; | [DroneCore](#classdronecore_1_1_drone_core_1a0b94dd09cd46faa41742d3720f210aa2) () | Constructor.
&nbsp; | [~DroneCore](#classdronecore_1_1_drone_core_1abbaedb6fd922c023e53611b484b38582) () | Destructor.
[ConnectionResult](namespacedronecore.md#namespacedronecore_1a42d7afdc816d7f750e1a8d4282da0ddc) | [add_any_connection](#classdronecore_1_1_drone_core_1a4d456788b98920c58b07e6a280642168) (const std::string & connection_url) | Adds Connection via URL.
[ConnectionResult](namespacedronecore.md#namespacedronecore_1a42d7afdc816d7f750e1a8d4282da0ddc) | [add_udp_connection](#classdronecore_1_1_drone_core_1a38e5715ec8817515ccaba5034da30bcd) (int local_port=DEFAULT_UDP_PORT) | Adds a UDP connection to the specified port number.
[ConnectionResult](namespacedronecore.md#namespacedronecore_1a42d7afdc816d7f750e1a8d4282da0ddc) | [add_udp_connection](#classdronecore_1_1_drone_core_1a2137a809643ef22d8b14617bf9897fac) (const std::string & local_ip, int local_port=DEFAULT_UDP_PORT) | Adds a UDP connection to the specified port number and local interface.
[ConnectionResult](namespacedronecore.md#namespacedronecore_1a42d7afdc816d7f750e1a8d4282da0ddc) | [add_tcp_connection](#classdronecore_1_1_drone_core_1abaa49c13d6277177974a09ccffde82e1) (int remote_port=DEFAULT_TCP_REMOTE_PORT) | Adds a TCP connection with a specific port number on localhost.
[ConnectionResult](namespacedronecore.md#namespacedronecore_1a42d7afdc816d7f750e1a8d4282da0ddc) | [add_tcp_connection](#classdronecore_1_1_drone_core_1a725640cb53c0d077e753ea2d22717b68) (const std::string & remote_ip=DEFAULT_TCP_REMOTE_IP, int remote_port=DEFAULT_TCP_REMOTE_PORT) | Adds a TCP connection with a specific IP address and port number.
[ConnectionResult](namespacedronecore.md#namespacedronecore_1a42d7afdc816d7f750e1a8d4282da0ddc) | [add_serial_connection](#classdronecore_1_1_drone_core_1aa84b8bfba099631267a0319169c23c8e) (const std::string & dev_path, int baudrate=DEFAULT_SERIAL_BAUDRATE) | Adds a serial connection with a specific port (COM or UART dev node) and baudrate as specified.
std::vector< uint64_t > | [system_uuids](#classdronecore_1_1_drone_core_1ac9503e701727ffa0293a30a6c8326f10) () const | Get vector of system UUIDs.
[System](classdronecore_1_1_system.md) & | [system](#classdronecore_1_1_drone_core_1ac9b0cdfc518ff036d7edf450153fe941) () const | Get the first discovered system.
[System](classdronecore_1_1_system.md) & | [system](#classdronecore_1_1_drone_core_1ab6082fca008ae58b79e87676336506ac) (uint64_t uuid)const | Get the system with the specified UUID.
bool | [is_connected](#classdronecore_1_1_drone_core_1a2adf0c6fc5521fa8f446e048a09f5ec1) () const | Returns `true` if exactly one system is currently connected.
bool | [is_connected](#classdronecore_1_1_drone_core_1a2f78c2263df997d38cf508e327fcde23) (uint64_t uuid)const | Returns `true` if a system is currently connected.
void | [register_on_discover](#classdronecore_1_1_drone_core_1a864ec7349eba67b02b8b3792f6c388f9) ([event_callback_t](classdronecore_1_1_drone_core.md#classdronecore_1_1_drone_core_1abb488f975ee7e199cd1cb08a317a52c3) callback) | Register callback for system discovery.
void | [register_on_timeout](#classdronecore_1_1_drone_core_1ad8c0dc0100449d21a46a787c810e8978) ([event_callback_t](classdronecore_1_1_drone_core.md#classdronecore_1_1_drone_core_1abb488f975ee7e199cd1cb08a317a52c3) callback) | Register callback for system timeout.

## Static Public Attributes


static constexpr auto [DEFAULT_UDP_BIND_IP](#classdronecore_1_1_drone_core_1a58ace8e05507a0ca301718bcd09785cf) = "0.0.0.0" - 


static constexpr int [DEFAULT_UDP_PORT](#classdronecore_1_1_drone_core_1aa989b494349529f412b36984a46f2ca6) = 14540 - 


static constexpr auto [DEFAULT_TCP_REMOTE_IP](#classdronecore_1_1_drone_core_1ade2086911d3052093fb87717f58a99b2) = "127.0.0.1" - 


static constexpr int [DEFAULT_TCP_REMOTE_PORT](#classdronecore_1_1_drone_core_1a0ded56f7f5873f17e424343ed7b2e5af) = 5760 - 


static constexpr int [DEFAULT_SERIAL_BAUDRATE](#classdronecore_1_1_drone_core_1a2b20d34acc312ffe6197aebdc6769a86) = 57600 - 


## Constructor & Destructor Documentation


### DroneCore() {#classdronecore_1_1_drone_core_1a0b94dd09cd46faa41742d3720f210aa2}
```cpp
dronecore::DroneCore::DroneCore()
```


Constructor.


### ~DroneCore() {#classdronecore_1_1_drone_core_1abbaedb6fd922c023e53611b484b38582}
```cpp
dronecore::DroneCore::~DroneCore()
```


Destructor.

Disconnects all connected vehicles and releases all resources.

## Member Typdef Documentation


### typedef event_callback_t {#classdronecore_1_1_drone_core_1abb488f975ee7e199cd1cb08a317a52c3}

```cpp
typedef std::function<void(uint64_t uuid)> dronecore::DroneCore::event_callback_t
```


Callback type for discover and timeout notifications.


**Parameters**

* **uuid** - UUID of system (or MAVLink system ID for systems that don't have a UUID).

## Member Function Documentation


### add_any_connection() {#classdronecore_1_1_drone_core_1a4d456788b98920c58b07e6a280642168}
```cpp
ConnectionResult dronecore::DroneCore::add_any_connection(const std::string &connection_url)
```


Adds Connection via URL.

Supports connection: Serial, TCP or UDP. Connection URL format should be:
<ul>
<li><p>UDP - udp://[Bind_host][:Bind_port]</p></li>
<li><p>TCP - tcp://[Remote_host][:Remote_port]</p></li>
<li><p>Serial - serial://Dev_Node[:Baudrate]</p></li>
</ul>


Default URL : udp://0.0.0.0:14540.
<ul>
<li><p>Default Bind host IP is any local interface (0.0.0.0)</p></li>
</ul>

**Parameters**

* const std::string& **connection_url** - connection URL string.

**Returns**

&emsp;[ConnectionResult](namespacedronecore.md#namespacedronecore_1a42d7afdc816d7f750e1a8d4282da0ddc) - The result of adding the connection.

### add_udp_connection() {#classdronecore_1_1_drone_core_1a38e5715ec8817515ccaba5034da30bcd}
```cpp
ConnectionResult dronecore::DroneCore::add_udp_connection(int local_port=DEFAULT_UDP_PORT)
```


Adds a UDP connection to the specified port number.

Any incoming connections are accepted (0.0.0.0).

**Parameters**

* int **local_port** - The local UDP port to listen to (defaults to 14540, the same as MAVROS).

**Returns**

&emsp;[ConnectionResult](namespacedronecore.md#namespacedronecore_1a42d7afdc816d7f750e1a8d4282da0ddc) - The result of adding the connection.

### add_udp_connection() {#classdronecore_1_1_drone_core_1a2137a809643ef22d8b14617bf9897fac}
```cpp
ConnectionResult dronecore::DroneCore::add_udp_connection(const std::string &local_ip, int local_port=DEFAULT_UDP_PORT)
```


Adds a UDP connection to the specified port number and local interface.

To accept only local connections of the machine, use 127.0.0.1. For any incoming connections, use 0.0.0.0.

**Parameters**

* const std::string& **local_ip** - 
* int **local_port** - The local UDP port to listen to (defaults to 14540, the same as MAVROS).

**Returns**

&emsp;[ConnectionResult](namespacedronecore.md#namespacedronecore_1a42d7afdc816d7f750e1a8d4282da0ddc) - The result of adding the connection.

### add_tcp_connection() {#classdronecore_1_1_drone_core_1abaa49c13d6277177974a09ccffde82e1}
```cpp
ConnectionResult dronecore::DroneCore::add_tcp_connection(int remote_port=DEFAULT_TCP_REMOTE_PORT)
```


Adds a TCP connection with a specific port number on localhost.


**Parameters**

* int **remote_port** - The TCP port to connect to (defaults to 5760).

**Returns**

&emsp;[ConnectionResult](namespacedronecore.md#namespacedronecore_1a42d7afdc816d7f750e1a8d4282da0ddc) - The result of adding the connection.

### add_tcp_connection() {#classdronecore_1_1_drone_core_1a725640cb53c0d077e753ea2d22717b68}
```cpp
ConnectionResult dronecore::DroneCore::add_tcp_connection(const std::string &remote_ip=DEFAULT_TCP_REMOTE_IP, int remote_port=DEFAULT_TCP_REMOTE_PORT)
```


Adds a TCP connection with a specific IP address and port number.


**Parameters**

* const std::string& **remote_ip** - Remote IP address to connect to (defaults to 127.0.0.1).
* int **remote_port** - The TCP port to connect to (defaults to 5760).

**Returns**

&emsp;[ConnectionResult](namespacedronecore.md#namespacedronecore_1a42d7afdc816d7f750e1a8d4282da0ddc) - The result of adding the connection.

### add_serial_connection() {#classdronecore_1_1_drone_core_1aa84b8bfba099631267a0319169c23c8e}
```cpp
ConnectionResult dronecore::DroneCore::add_serial_connection(const std::string &dev_path, int baudrate=DEFAULT_SERIAL_BAUDRATE)
```


Adds a serial connection with a specific port (COM or UART dev node) and baudrate as specified.


**Parameters**

* const std::string& **dev_path** - COM or UART dev node name/path (e.g. "/dev/ttyS0", or "COM3" on Windows).
* int **baudrate** - Baudrate of the serial port (defaults to 57600).

**Returns**

&emsp;[ConnectionResult](namespacedronecore.md#namespacedronecore_1a42d7afdc816d7f750e1a8d4282da0ddc) - The result of adding the connection.

### system_uuids() {#classdronecore_1_1_drone_core_1ac9503e701727ffa0293a30a6c8326f10}
```cpp
std::vector<uint64_t> dronecore::DroneCore::system_uuids() const
```


Get vector of system UUIDs.

This returns a vector of the UUIDs of all systems that have been discovered. If a system doesn't have a UUID then [DroneCore](classdronecore_1_1_drone_core.md) will instead use its MAVLink system ID (range: 0..255).

**Returns**

&emsp;std::vector< uint64_t > - A vector containing the UUIDs.

### system() {#classdronecore_1_1_drone_core_1ac9b0cdfc518ff036d7edf450153fe941}
```cpp
System& dronecore::DroneCore::system() const
```


Get the first discovered system.

This returns the first discovered system or a null system if no system has yet been found.

**Returns**

&emsp;[System](classdronecore_1_1_system.md) & - A reference to a system.

### system() {#classdronecore_1_1_drone_core_1ab6082fca008ae58b79e87676336506ac}
```cpp
System& dronecore::DroneCore::system(uint64_t uuid) const
```


Get the system with the specified UUID.

This returns a system for a given UUID if such a system has been discovered and a null system otherwise.

**Parameters**

* uint64_t **uuid** - UUID of system to get.

**Returns**

&emsp;[System](classdronecore_1_1_system.md) & - A reference to the specified system.

### is_connected() {#classdronecore_1_1_drone_core_1a2adf0c6fc5521fa8f446e048a09f5ec1}
```cpp
bool dronecore::DroneCore::is_connected() const
```


Returns `true` if exactly one system is currently connected.

Connected means we are receiving heartbeats from this system. It means the same as "discovered" and "not timed out".


If multiple systems have connected, this will return `false`.

**Returns**

&emsp;bool - `true` if exactly one system is connected.

### is_connected() {#classdronecore_1_1_drone_core_1a2f78c2263df997d38cf508e327fcde23}
```cpp
bool dronecore::DroneCore::is_connected(uint64_t uuid) const
```


Returns `true` if a system is currently connected.

Connected means we are receiving heartbeats from this system. It means the same as "discovered" and "not timed out".

**Parameters**

* uint64_t **uuid** - UUID of system to check.

**Returns**

&emsp;bool - `true` if system is connected.

### register_on_discover() {#classdronecore_1_1_drone_core_1a864ec7349eba67b02b8b3792f6c388f9}
```cpp
void dronecore::DroneCore::register_on_discover(event_callback_t callback)
```


Register callback for system discovery.

This sets a callback that will be notified if a new system is discovered.


If systems have been discovered before this callback is registered, they will be notified at the time this callback is registered.


> **Note** Only one callback can be registered at a time. If this function is called several times, previous callbacks will be overwritten.

**Parameters**

* [event_callback_t](classdronecore_1_1_drone_core.md#classdronecore_1_1_drone_core_1abb488f975ee7e199cd1cb08a317a52c3) **callback** - Callback to register.

### register_on_timeout() {#classdronecore_1_1_drone_core_1ad8c0dc0100449d21a46a787c810e8978}
```cpp
void dronecore::DroneCore::register_on_timeout(event_callback_t callback)
```


Register callback for system timeout.

This sets a callback that will be notified if no heartbeat of the system has been received in 3 seconds.


> **Note** Only one callback can be registered at a time. If this function is called several times, previous callbacks will be overwritten.

**Parameters**

* [event_callback_t](classdronecore_1_1_drone_core.md#classdronecore_1_1_drone_core_1abb488f975ee7e199cd1cb08a317a52c3) **callback** - Callback to register.

## Field Documentation


### DEFAULT_UDP_BIND_IP {#classdronecore_1_1_drone_core_1a58ace8e05507a0ca301718bcd09785cf}

```cpp
constexpr auto dronecore::DroneCore::DEFAULT_UDP_BIND_IP = "0.0.0.0"
```


### DEFAULT_UDP_PORT {#classdronecore_1_1_drone_core_1aa989b494349529f412b36984a46f2ca6}

```cpp
constexpr int dronecore::DroneCore::DEFAULT_UDP_PORT = 14540
```


### DEFAULT_TCP_REMOTE_IP {#classdronecore_1_1_drone_core_1ade2086911d3052093fb87717f58a99b2}

```cpp
constexpr auto dronecore::DroneCore::DEFAULT_TCP_REMOTE_IP = "127.0.0.1"
```


### DEFAULT_TCP_REMOTE_PORT {#classdronecore_1_1_drone_core_1a0ded56f7f5873f17e424343ed7b2e5af}

```cpp
constexpr int dronecore::DroneCore::DEFAULT_TCP_REMOTE_PORT = 5760
```


### DEFAULT_SERIAL_BAUDRATE {#classdronecore_1_1_drone_core_1a2b20d34acc312ffe6197aebdc6769a86}

```cpp
constexpr int dronecore::DroneCore::DEFAULT_SERIAL_BAUDRATE = 57600
```

