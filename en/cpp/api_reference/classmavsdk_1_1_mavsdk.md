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

## Public Member Functions


Type | Name | Description
---: | --- | ---
&nbsp; | [Mavsdk](#classmavsdk_1_1_mavsdk_1aad81f6df52096ea28d4e646ad7339461) () | Constructor.
&nbsp; | [~Mavsdk](#classmavsdk_1_1_mavsdk_1ac1549f715d6857711b9b9e364a4ca351) () | Destructor.
std::string | [version](#classmavsdk_1_1_mavsdk_1a8fdb97695762d06fd2bccfc6309943fa) () const | Returns the version of MAVSDK.
[ConnectionResult](namespacemavsdk.md#namespacemavsdk_1a0bad93f6d037051ac3906a0bcc09f992) | [add_any_connection](#classmavsdk_1_1_mavsdk_1a405041a5043c610c86540de090626d97) (const std::string & connection_url, [ForwardingOption](namespacemavsdk.md#namespacemavsdk_1a7066729108eae8a605d4dd169e4581b9) forwarding_option=ForwardingOption::ForwardingOff) | Adds Connection via URL.
[ConnectionResult](namespacemavsdk.md#namespacemavsdk_1a0bad93f6d037051ac3906a0bcc09f992) | [add_udp_connection](#classmavsdk_1_1_mavsdk_1aa43dfb00d5118d26ae5aabd0f9ba56b2) (int local_port=[DEFAULT_UDP_PORT](classmavsdk_1_1_mavsdk.md#classmavsdk_1_1_mavsdk_1affddcc7c7849ed86a0c7dab1166e657a), [ForwardingOption](namespacemavsdk.md#namespacemavsdk_1a7066729108eae8a605d4dd169e4581b9) forwarding_option=ForwardingOption::ForwardingOff) | Adds a UDP connection to the specified port number.
[ConnectionResult](namespacemavsdk.md#namespacemavsdk_1a0bad93f6d037051ac3906a0bcc09f992) | [add_udp_connection](#classmavsdk_1_1_mavsdk_1a98fd1c01bd366b27084810875a1b94c1) (const std::string & local_ip, int local_port=[DEFAULT_UDP_PORT](classmavsdk_1_1_mavsdk.md#classmavsdk_1_1_mavsdk_1affddcc7c7849ed86a0c7dab1166e657a), [ForwardingOption](namespacemavsdk.md#namespacemavsdk_1a7066729108eae8a605d4dd169e4581b9) forwarding_option=ForwardingOption::ForwardingOff) | Adds a UDP connection to the specified port number and local interface.
[ConnectionResult](namespacemavsdk.md#namespacemavsdk_1a0bad93f6d037051ac3906a0bcc09f992) | [setup_udp_remote](#classmavsdk_1_1_mavsdk_1adb2a69282a5d3766fd6251662c28616d) (const std::string & remote_ip, int remote_port, [ForwardingOption](namespacemavsdk.md#namespacemavsdk_1a7066729108eae8a605d4dd169e4581b9) forwarding_option=ForwardingOption::ForwardingOff) | Sets up instance to send heartbeats to the specified remote interface and port number.
[ConnectionResult](namespacemavsdk.md#namespacemavsdk_1a0bad93f6d037051ac3906a0bcc09f992) | [add_tcp_connection](#classmavsdk_1_1_mavsdk_1a91c7a70c6e8ffa43844f2ce04f2696f0) (int remote_port=[DEFAULT_TCP_REMOTE_PORT](classmavsdk_1_1_mavsdk.md#classmavsdk_1_1_mavsdk_1a52a6a9e0acd6c0ade566208d253427bd), [ForwardingOption](namespacemavsdk.md#namespacemavsdk_1a7066729108eae8a605d4dd169e4581b9) forwarding_option=ForwardingOption::ForwardingOff) | Adds a TCP connection with a specific port number on localhost.
[ConnectionResult](namespacemavsdk.md#namespacemavsdk_1a0bad93f6d037051ac3906a0bcc09f992) | [add_tcp_connection](#classmavsdk_1_1_mavsdk_1a50ecebb9ee710b9a044d2d5eb57645e4) (const std::string & remote_ip, int remote_port=[DEFAULT_TCP_REMOTE_PORT](classmavsdk_1_1_mavsdk.md#classmavsdk_1_1_mavsdk_1a52a6a9e0acd6c0ade566208d253427bd), [ForwardingOption](namespacemavsdk.md#namespacemavsdk_1a7066729108eae8a605d4dd169e4581b9) forwarding_option=ForwardingOption::ForwardingOff) | Adds a TCP connection with a specific IP address and port number.
[ConnectionResult](namespacemavsdk.md#namespacemavsdk_1a0bad93f6d037051ac3906a0bcc09f992) | [add_serial_connection](#classmavsdk_1_1_mavsdk_1a669ddeec7af571fdbde9f31e343d50ac) (const std::string & dev_path, int baudrate=[DEFAULT_SERIAL_BAUDRATE](classmavsdk_1_1_mavsdk.md#classmavsdk_1_1_mavsdk_1a870d15142914f1db564c12f385d5489b), bool flow_control=false, [ForwardingOption](namespacemavsdk.md#namespacemavsdk_1a7066729108eae8a605d4dd169e4581b9) forwarding_option=ForwardingOption::ForwardingOff) | Adds a serial connection with a specific port (COM or UART dev node) and baudrate as specified.
std::vector< std::shared_ptr< [System](classmavsdk_1_1_system.md) > > | [systems](#classmavsdk_1_1_mavsdk_1aca9c72b300d384341b00ff9ba2c6e5c5) () const | Get a vector of systems which have been discovered or set-up.
void | [set_configuration](#classmavsdk_1_1_mavsdk_1acaeea86253493dc15b6540d2100a1b86) ([Configuration](classmavsdk_1_1_mavsdk_1_1_configuration.md) configuration) | Set [Configuration](classmavsdk_1_1_mavsdk_1_1_configuration.md) of SDK.
void | [set_timeout_s](#classmavsdk_1_1_mavsdk_1a765f37b61462addcfd961e720585d2c6) (double timeout_s) | Set timeout of MAVLink transfers.
void | [subscribe_on_new_system](#classmavsdk_1_1_mavsdk_1a332ae41c7de84d5cfab11fb3e2e65522) ([NewSystemCallback](classmavsdk_1_1_mavsdk.md#classmavsdk_1_1_mavsdk_1a7a283c6a75e852a56be4c5862f8a3fab) callback) | Get notification about a change in systems.

## Static Public Attributes


static constexpr auto [DEFAULT_UDP_BIND_IP](#classmavsdk_1_1_mavsdk_1ac46b2c27d9c428ec46092f10774482fa) = "0.0.0.0" - Default UDP bind IP (accepts any incoming connections).


static constexpr int [DEFAULT_UDP_PORT](#classmavsdk_1_1_mavsdk_1affddcc7c7849ed86a0c7dab1166e657a) = 14540 - Default UDP bind port (same port as used by MAVROS).


static constexpr auto [DEFAULT_TCP_REMOTE_IP](#classmavsdk_1_1_mavsdk_1a0154aac9d933fa212a50dc687816fbad) = "127.0.0.1" - Default TCP remote IP (localhost).


static constexpr int [DEFAULT_TCP_REMOTE_PORT](#classmavsdk_1_1_mavsdk_1a52a6a9e0acd6c0ade566208d253427bd) = 5760 - Default TCP remote port.


static constexpr int [DEFAULT_SERIAL_BAUDRATE](#classmavsdk_1_1_mavsdk_1a870d15142914f1db564c12f385d5489b) = 57600 - Default serial baudrate.


static constexpr double [DEFAULT_TIMEOUT_S](#classmavsdk_1_1_mavsdk_1a74f7b4d32d9551bb9c11ce8668f634a6) = 0.5 - Default internal timeout in seconds.


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


## Member Function Documentation


### version() {#classmavsdk_1_1_mavsdk_1a8fdb97695762d06fd2bccfc6309943fa}
```cpp
std::string mavsdk::Mavsdk::version() const
```


Returns the version of MAVSDK.

Note, you're not supposed to request the version too many times.

**Returns**

&emsp;std::string - A string containing the version.

### add_any_connection() {#classmavsdk_1_1_mavsdk_1a405041a5043c610c86540de090626d97}
```cpp
ConnectionResult mavsdk::Mavsdk::add_any_connection(const std::string &connection_url, ForwardingOption forwarding_option=ForwardingOption::ForwardingOff)
```


Adds Connection via URL.

Supports connection: Serial, TCP or UDP. Connection URL format should be:
<ul>
<li><p>UDP: udp://[host][:bind_port]</p>
</li>
<li><p>TCP: tcp://[host][:remote_port]</p>
</li>
<li><p>Serial: serial://dev_node[:baudrate]</p>
</li>
</ul>


For UDP, the host can be set to either:
<ul>
<li><p>zero IP: 0.0.0.0 -> behave like a server and listen for heartbeats.</p>
</li>
<li><p>some IP: 192.168.1.12 -> behave like a client, initiate connection and start sending heartbeats.</p>
</li>
</ul>

**Parameters**

* const std::string& **connection_url** - connection URL string.
* [ForwardingOption](namespacemavsdk.md#namespacemavsdk_1a7066729108eae8a605d4dd169e4581b9) **forwarding_option** - message forwarding option (when multiple interfaces are used).

**Returns**

&emsp;[ConnectionResult](namespacemavsdk.md#namespacemavsdk_1a0bad93f6d037051ac3906a0bcc09f992) - The result of adding the connection.

### add_udp_connection() {#classmavsdk_1_1_mavsdk_1aa43dfb00d5118d26ae5aabd0f9ba56b2}
```cpp
ConnectionResult mavsdk::Mavsdk::add_udp_connection(int local_port=DEFAULT_UDP_PORT, ForwardingOption forwarding_option=ForwardingOption::ForwardingOff)
```


Adds a UDP connection to the specified port number.

Any incoming connections are accepted (0.0.0.0).

**Parameters**

* int **local_port** - The local UDP port to listen to (defaults to 14540, the same as MAVROS).
* [ForwardingOption](namespacemavsdk.md#namespacemavsdk_1a7066729108eae8a605d4dd169e4581b9) **forwarding_option** - message forwarding option (when multiple interfaces are used).

**Returns**

&emsp;[ConnectionResult](namespacemavsdk.md#namespacemavsdk_1a0bad93f6d037051ac3906a0bcc09f992) - The result of adding the connection.

### add_udp_connection() {#classmavsdk_1_1_mavsdk_1a98fd1c01bd366b27084810875a1b94c1}
```cpp
ConnectionResult mavsdk::Mavsdk::add_udp_connection(const std::string &local_ip, int local_port=DEFAULT_UDP_PORT, ForwardingOption forwarding_option=ForwardingOption::ForwardingOff)
```


Adds a UDP connection to the specified port number and local interface.

To accept only local connections of the machine, use 127.0.0.1. For any incoming connections, use 0.0.0.0.

**Parameters**

* const std::string& **local_ip** - The local UDP IP address to listen to.
* int **local_port** - The local UDP port to listen to (defaults to 14540, the same as MAVROS).
* [ForwardingOption](namespacemavsdk.md#namespacemavsdk_1a7066729108eae8a605d4dd169e4581b9) **forwarding_option** - message forwarding option (when multiple interfaces are used).

**Returns**

&emsp;[ConnectionResult](namespacemavsdk.md#namespacemavsdk_1a0bad93f6d037051ac3906a0bcc09f992) - The result of adding the connection.

### setup_udp_remote() {#classmavsdk_1_1_mavsdk_1adb2a69282a5d3766fd6251662c28616d}
```cpp
ConnectionResult mavsdk::Mavsdk::setup_udp_remote(const std::string &remote_ip, int remote_port, ForwardingOption forwarding_option=ForwardingOption::ForwardingOff)
```


Sets up instance to send heartbeats to the specified remote interface and port number.


**Parameters**

* const std::string& **remote_ip** - The remote UDP IP address to report to.
* int **remote_port** - The local UDP port to report to.
* [ForwardingOption](namespacemavsdk.md#namespacemavsdk_1a7066729108eae8a605d4dd169e4581b9) **forwarding_option** - message forwarding option (when multiple interfaces are used).

**Returns**

&emsp;[ConnectionResult](namespacemavsdk.md#namespacemavsdk_1a0bad93f6d037051ac3906a0bcc09f992) - The result of operation.

### add_tcp_connection() {#classmavsdk_1_1_mavsdk_1a91c7a70c6e8ffa43844f2ce04f2696f0}
```cpp
ConnectionResult mavsdk::Mavsdk::add_tcp_connection(int remote_port=DEFAULT_TCP_REMOTE_PORT, ForwardingOption forwarding_option=ForwardingOption::ForwardingOff)
```


Adds a TCP connection with a specific port number on localhost.


**Parameters**

* int **remote_port** - The TCP port to connect to (defaults to 5760).
* [ForwardingOption](namespacemavsdk.md#namespacemavsdk_1a7066729108eae8a605d4dd169e4581b9) **forwarding_option** - message forwarding option (when multiple interfaces are used).

**Returns**

&emsp;[ConnectionResult](namespacemavsdk.md#namespacemavsdk_1a0bad93f6d037051ac3906a0bcc09f992) - The result of adding the connection.

### add_tcp_connection() {#classmavsdk_1_1_mavsdk_1a50ecebb9ee710b9a044d2d5eb57645e4}
```cpp
ConnectionResult mavsdk::Mavsdk::add_tcp_connection(const std::string &remote_ip, int remote_port=DEFAULT_TCP_REMOTE_PORT, ForwardingOption forwarding_option=ForwardingOption::ForwardingOff)
```


Adds a TCP connection with a specific IP address and port number.


**Parameters**

* const std::string& **remote_ip** - Remote IP address to connect to.
* int **remote_port** - The TCP port to connect to (defaults to 5760).
* [ForwardingOption](namespacemavsdk.md#namespacemavsdk_1a7066729108eae8a605d4dd169e4581b9) **forwarding_option** - message forwarding option (when multiple interfaces are used).

**Returns**

&emsp;[ConnectionResult](namespacemavsdk.md#namespacemavsdk_1a0bad93f6d037051ac3906a0bcc09f992) - The result of adding the connection.

### add_serial_connection() {#classmavsdk_1_1_mavsdk_1a669ddeec7af571fdbde9f31e343d50ac}
```cpp
ConnectionResult mavsdk::Mavsdk::add_serial_connection(const std::string &dev_path, int baudrate=DEFAULT_SERIAL_BAUDRATE, bool flow_control=false, ForwardingOption forwarding_option=ForwardingOption::ForwardingOff)
```


Adds a serial connection with a specific port (COM or UART dev node) and baudrate as specified.


**Parameters**

* const std::string& **dev_path** - COM or UART dev node name/path (e.g. "/dev/ttyS0", or "COM3" on Windows).
* int **baudrate** - Baudrate of the serial port (defaults to 57600).
* bool **flow_control** - enable/disable flow control.
* [ForwardingOption](namespacemavsdk.md#namespacemavsdk_1a7066729108eae8a605d4dd169e4581b9) **forwarding_option** - message forwarding option (when multiple interfaces are used).

**Returns**

&emsp;[ConnectionResult](namespacemavsdk.md#namespacemavsdk_1a0bad93f6d037051ac3906a0bcc09f992) - The result of adding the connection.

### systems() {#classmavsdk_1_1_mavsdk_1aca9c72b300d384341b00ff9ba2c6e5c5}
```cpp
std::vector< std::shared_ptr< System > > mavsdk::Mavsdk::systems() const
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

### set_timeout_s() {#classmavsdk_1_1_mavsdk_1a765f37b61462addcfd961e720585d2c6}
```cpp
void mavsdk::Mavsdk::set_timeout_s(double timeout_s)
```


Set timeout of MAVLink transfers.

The default timeout used is generally DEFAULT_SERIAL_BAUDRATE (0.5 seconds) seconds. If MAVSDK is used on the same host this timeout can be reduced, while if MAVSDK has to communicate over links with high latency it might need to be increased to prevent timeouts.

**Parameters**

* double **timeout_s** - 

### subscribe_on_new_system() {#classmavsdk_1_1_mavsdk_1a332ae41c7de84d5cfab11fb3e2e65522}
```cpp
void mavsdk::Mavsdk::subscribe_on_new_system(NewSystemCallback callback)
```


Get notification about a change in systems.

This gets called whenever a system is added.


> **Note** Only one subscriber is possible at any time. On a second subscription, the previous one is overwritten. To unsubscribe, pass nullptr;

**Parameters**

* [NewSystemCallback](classmavsdk_1_1_mavsdk.md#classmavsdk_1_1_mavsdk_1a7a283c6a75e852a56be4c5862f8a3fab) **callback** - Callback to subscribe.

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


### DEFAULT_TIMEOUT_S {#classmavsdk_1_1_mavsdk_1a74f7b4d32d9551bb9c11ce8668f634a6}

```cpp
constexpr double mavsdk::Mavsdk::DEFAULT_TIMEOUT_S = 0.5
```


Default internal timeout in seconds.

