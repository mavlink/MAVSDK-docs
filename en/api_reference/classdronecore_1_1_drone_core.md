# dronecore::DroneCore Class Reference
`#include: dronecore.h`

----


This is the main class of **DroneCore MAVLink API Library** (for the Dronecode Platform). 


It is used to discover vehicles and manage active connections.


An instance of this class must be created (first) in order to use the library. The instance must be destroyed after use in order to break connections and release all resources. 


## Public Types


Type | Description
--- | ---
enum [ConnectionResult](#classdronecore_1_1_drone_core_1a9bdf4a0267d4851342617bdbcbbeead7) {<ul><li style="list-style-type: none;"><a href="#classdronecore_1_1_drone_core_1a9bdf4a0267d4851342617bdbcbbeead7ad0749aaba8b833466dfcbb0428e4f89c">SUCCESS=0</a>, <a href="#classdronecore_1_1_drone_core_1a9bdf4a0267d4851342617bdbcbbeead7a070a0fb40f6c308ab544b227660aadff">TIMEOUT</a>, <a href="#classdronecore_1_1_drone_core_1a9bdf4a0267d4851342617bdbcbbeead7aac87548d79aa92c60dcfac06ae83e5ad">SOCKET_ERROR</a>, <a href="#classdronecore_1_1_drone_core_1a9bdf4a0267d4851342617bdbcbbeead7af69a41125696a14c45a8182ce7ba83a7">BIND_ERROR</a>, <a href="#classdronecore_1_1_drone_core_1a9bdf4a0267d4851342617bdbcbbeead7ac77f1f09dab2c0c9980fca7cfae02518">CONNECTION_ERROR</a>, <a href="#classdronecore_1_1_drone_core_1a9bdf4a0267d4851342617bdbcbbeead7a3e860a081575fc82cc7b6ed2ca602947">NOT_IMPLEMENTED</a>, <a href="#classdronecore_1_1_drone_core_1a9bdf4a0267d4851342617bdbcbbeead7adb6de85627898aecebdcd28613df3164">DEVICE_NOT_CONNECTED</a>, <a href="#classdronecore_1_1_drone_core_1a9bdf4a0267d4851342617bdbcbbeead7a9b40004e356bbecf8c222684be0988c7">DEVICE_BUSY</a>, <a href="#classdronecore_1_1_drone_core_1a9bdf4a0267d4851342617bdbcbbeead7a6fa4dbf368cea972db8d9156799d5dbe">COMMAND_DENIED</a>, <a href="#classdronecore_1_1_drone_core_1a9bdf4a0267d4851342617bdbcbbeead7a588cf56f08269878b055227a8490de67">DESTINATION_IP_UNKNOWN</a>, <a href="#classdronecore_1_1_drone_core_1a9bdf4a0267d4851342617bdbcbbeead7a9532aa7fe8e205a02479a2e43d05f6b1">CONNECTIONS_EXHAUSTED</a><p>}</p></li> | Result type returned when adding a connection.
std::function< void(uint64_t uuid)> [event_callback_t](#classdronecore_1_1_drone_core_1abb488f975ee7e199cd1cb08a317a52c3) | Callback type for discover and timeout notifications.

## Public Member Functions


Type | Name | Description
---: | --- | ---
| [DroneCore](#classdronecore_1_1_drone_core_1a0b94dd09cd46faa41742d3720f210aa2) () | Constructor.
| [~DroneCore](#classdronecore_1_1_drone_core_1abbaedb6fd922c023e53611b484b38582) () | Destructor.
[ConnectionResult](classdronecore_1_1_drone_core.md#classdronecore_1_1_drone_core_1a9bdf4a0267d4851342617bdbcbbeead7) | [add_udp_connection](#classdronecore_1_1_drone_core_1a1bdb0e8825e6dc06fc04d76fba236c5f) () | Adds a UDP connection with the default arguments.
[ConnectionResult](classdronecore_1_1_drone_core.md#classdronecore_1_1_drone_core_1a9bdf4a0267d4851342617bdbcbbeead7) | [add_udp_connection](#classdronecore_1_1_drone_core_1a515e90ba2a12d494f38d4bb493f381e6) (int local_port_number) | Adds a UDP connection with a specific port number.
const std::vector< uint64_t > & | [device_uuids](#classdronecore_1_1_drone_core_1a516b9ba73dae13315a85e4df71dce501) () const | Get vector of device UUIDs.
[Device](classdronecore_1_1_device.md) & | [device](#classdronecore_1_1_drone_core_1a10872f29d98348484b3fdbc8ce0c8108) () const | Get the first discovered device.
[Device](classdronecore_1_1_device.md) & | [device](#classdronecore_1_1_drone_core_1a3f363ed19b923d3a8a7b70bd18135ed4) (uint64_t uuid) const | Get the device with the specified UUID.
void | [register_on_discover](#classdronecore_1_1_drone_core_1a864ec7349eba67b02b8b3792f6c388f9) (event_callback_t callback) | Register callback for device discovery.
void | [register_on_timeout](#classdronecore_1_1_drone_core_1ad8c0dc0100449d21a46a787c810e8978) (event_callback_t callback) | Register callback for device timeout.
## Static Public Member Functions


Type | Name | Description
---: | --- | ---
const char * | [connection_result_str](#classdronecore_1_1_drone_core_1ab842ee94d965c9f71cd0e96b31e17ee2) (ConnectionResult) | Translates the [DroneCore::ConnectionResult](classdronecore_1_1_drone_core.md#classdronecore_1_1_drone_core_1a9bdf4a0267d4851342617bdbcbbeead7) enum to a human-readable English string.


## Constructor & Destructor Documentation


### DroneCore() {#classdronecore_1_1_drone_core_1a0b94dd09cd46faa41742d3720f210aa2}
```cpp
dronecore::DroneCore::DroneCore()
```


Constructor.


<!-- inbodydescription:  --> 
<!-- return_type:  -->
<!-- return_type_comment:  -->
<!-- prot: public -->
<!-- static: no -->
<!-- const: no -->
<!-- explicit: no -->
<!-- virt: non-virtual -->
<!-- inline: no -->


### ~DroneCore() {#classdronecore_1_1_drone_core_1abbaedb6fd922c023e53611b484b38582}
```cpp
dronecore::DroneCore::~DroneCore()
```


Destructor.

Disconnects all connected vehicles and releases all resources.

<!-- inbodydescription:  --> 
<!-- return_type:  -->
<!-- return_type_comment:  -->
<!-- prot: public -->
<!-- static: no -->
<!-- const: no -->
<!-- explicit: no -->
<!-- virt: non-virtual -->
<!-- inline: no -->

## Member Typdef Documentation


### typedef event_callback_t {#classdronecore_1_1_drone_core_1abb488f975ee7e199cd1cb08a317a52c3}

```cpp
typedef std::function<void(uint64_t uuid)> dronecore::DroneCore::event_callback_t
```


Callback type for discover and timeout notifications.


**Parameters**

* **uuid** - UUID of device.

## Member Enumeration Documentation


### enum ConnectionResult {#classdronecore_1_1_drone_core_1a9bdf4a0267d4851342617bdbcbbeead7}


Result type returned when adding a connection.

**Note**: [DroneCore](classdronecore_1_1_drone_core.md) does not throw exceptions. Instead a result of this type will be returned when you add a connection: [add_udp_connection()](classdronecore_1_1_drone_core.md#classdronecore_1_1_drone_core_1a1bdb0e8825e6dc06fc04d76fba236c5f).

 Value | Description
--- | ---
<span id="classdronecore_1_1_drone_core_1a9bdf4a0267d4851342617bdbcbbeead7ad0749aaba8b833466dfcbb0428e4f89c"></span> `SUCCESS` | Connection succeeded. 
<span id="classdronecore_1_1_drone_core_1a9bdf4a0267d4851342617bdbcbbeead7a070a0fb40f6c308ab544b227660aadff"></span> `TIMEOUT` | Connection timed out. 
<span id="classdronecore_1_1_drone_core_1a9bdf4a0267d4851342617bdbcbbeead7aac87548d79aa92c60dcfac06ae83e5ad"></span> `SOCKET_ERROR` | Socket error. 
<span id="classdronecore_1_1_drone_core_1a9bdf4a0267d4851342617bdbcbbeead7af69a41125696a14c45a8182ce7ba83a7"></span> `BIND_ERROR` | Bind error. 
<span id="classdronecore_1_1_drone_core_1a9bdf4a0267d4851342617bdbcbbeead7ac77f1f09dab2c0c9980fca7cfae02518"></span> `CONNECTION_ERROR` | Connection error. 
<span id="classdronecore_1_1_drone_core_1a9bdf4a0267d4851342617bdbcbbeead7a3e860a081575fc82cc7b6ed2ca602947"></span> `NOT_IMPLEMENTED` | Connection type not implemented. 
<span id="classdronecore_1_1_drone_core_1a9bdf4a0267d4851342617bdbcbbeead7adb6de85627898aecebdcd28613df3164"></span> `DEVICE_NOT_CONNECTED` | No device is connected. 
<span id="classdronecore_1_1_drone_core_1a9bdf4a0267d4851342617bdbcbbeead7a9b40004e356bbecf8c222684be0988c7"></span> `DEVICE_BUSY` | Device is busy. 
<span id="classdronecore_1_1_drone_core_1a9bdf4a0267d4851342617bdbcbbeead7a6fa4dbf368cea972db8d9156799d5dbe"></span> `COMMAND_DENIED` | Command is denied. 
<span id="classdronecore_1_1_drone_core_1a9bdf4a0267d4851342617bdbcbbeead7a588cf56f08269878b055227a8490de67"></span> `DESTINATION_IP_UNKNOWN` | Connection IP is unknown. 
<span id="classdronecore_1_1_drone_core_1a9bdf4a0267d4851342617bdbcbbeead7a9532aa7fe8e205a02479a2e43d05f6b1"></span> `CONNECTIONS_EXHAUSTED` | Connections exhausted. 

<!-- inbodydescription:  --> 
<!-- prot: public -->
<!-- static: no -->

## Member Function Documentation


### add_udp_connection() {#classdronecore_1_1_drone_core_1a1bdb0e8825e6dc06fc04d76fba236c5f}
```cpp
DroneCore::ConnectionResult dronecore::DroneCore::add_udp_connection()
```


Adds a UDP connection with the default arguments.

This will listen on UDP port 14540.

**Returns**

&emsp;[ConnectionResult](classdronecore_1_1_drone_core.md#classdronecore_1_1_drone_core_1a9bdf4a0267d4851342617bdbcbbeead7) - The result of adding the connection.

<!-- inbodydescription:  --> 
<!-- return_type: [ConnectionResult](classdronecore_1_1_drone_core.md#classdronecore_1_1_drone_core_1a9bdf4a0267d4851342617bdbcbbeead7) -->
<!-- return_type_comment: The result of adding the connection. -->
<!-- prot: public -->
<!-- static: no -->
<!-- const: no -->
<!-- explicit: no -->
<!-- virt: non-virtual -->
<!-- inline: no -->


### add_udp_connection() {#classdronecore_1_1_drone_core_1a515e90ba2a12d494f38d4bb493f381e6}
```cpp
DroneCore::ConnectionResult dronecore::DroneCore::add_udp_connection(int local_port_number)
```


Adds a UDP connection with a specific port number.


**Parameters**

* int **local_port_number** - The local UDP port to listen to.

**Returns**

&emsp;[ConnectionResult](classdronecore_1_1_drone_core.md#classdronecore_1_1_drone_core_1a9bdf4a0267d4851342617bdbcbbeead7) - The result of adding the connection.

<!-- inbodydescription:  --> 
<!-- return_type: [ConnectionResult](classdronecore_1_1_drone_core.md#classdronecore_1_1_drone_core_1a9bdf4a0267d4851342617bdbcbbeead7) -->
<!-- return_type_comment: The result of adding the connection. -->
<!-- prot: public -->
<!-- static: no -->
<!-- const: no -->
<!-- explicit: no -->
<!-- virt: non-virtual -->
<!-- inline: no -->


### device_uuids() {#classdronecore_1_1_drone_core_1a516b9ba73dae13315a85e4df71dce501}
```cpp
const std::vector< uint64_t > & dronecore::DroneCore::device_uuids() const
```


Get vector of device UUIDs.

This returns a vector of the UUIDs of all devices that have been discovered so far.

**Returns**

&emsp;const std::vector< uint64_t > & - A reference to the vector containing the UUIDs.

<!-- inbodydescription:  --> 
<!-- return_type: const std::vector< uint64_t > & -->
<!-- return_type_comment: A reference to the vector containing the UUIDs. -->
<!-- prot: public -->
<!-- static: no -->
<!-- const: yes -->
<!-- explicit: no -->
<!-- virt: non-virtual -->
<!-- inline: no -->


### device() {#classdronecore_1_1_drone_core_1a10872f29d98348484b3fdbc8ce0c8108}
```cpp
Device & dronecore::DroneCore::device() const
```


Get the first discovered device.

This returns the first discovered device or a null device if no device has yet been found.

**Returns**

&emsp;[Device](classdronecore_1_1_device.md) & - A reference to a device.

<!-- inbodydescription:  --> 
<!-- return_type: [Device](classdronecore_1_1_device.md) & -->
<!-- return_type_comment: A reference to a device. -->
<!-- prot: public -->
<!-- static: no -->
<!-- const: yes -->
<!-- explicit: no -->
<!-- virt: non-virtual -->
<!-- inline: no -->


### device() {#classdronecore_1_1_drone_core_1a3f363ed19b923d3a8a7b70bd18135ed4}
```cpp
Device & dronecore::DroneCore::device(uint64_t uuid) const
```


Get the device with the specified UUID.

This returns a device for a given UUID if such a device has been discovered and a null device otherwise.

**Parameters**

* uint64_t **uuid** - UUID of device to get.

**Returns**

&emsp;[Device](classdronecore_1_1_device.md) & - A reference to the specified device.

<!-- inbodydescription:  --> 
<!-- return_type: [Device](classdronecore_1_1_device.md) & -->
<!-- return_type_comment: A reference to the specified device. -->
<!-- prot: public -->
<!-- static: no -->
<!-- const: yes -->
<!-- explicit: no -->
<!-- virt: non-virtual -->
<!-- inline: no -->


### register_on_discover() {#classdronecore_1_1_drone_core_1a864ec7349eba67b02b8b3792f6c388f9}
```cpp
void dronecore::DroneCore::register_on_discover(event_callback_t callback)
```


Register callback for device discovery.

This sets a callback that will be notified if a new device is discovered.


**Note** Only one callback can be registered at a time. If this function is called several times, previous callbacks will be overwritten.

**Parameters**

* [event_callback_t](classdronecore_1_1_drone_core.md#classdronecore_1_1_drone_core_1abb488f975ee7e199cd1cb08a317a52c3) **callback** - Callback to register.

<!-- inbodydescription:  --> 
<!-- return_type: void -->
<!-- return_type_comment:  -->
<!-- prot: public -->
<!-- static: no -->
<!-- const: no -->
<!-- explicit: no -->
<!-- virt: non-virtual -->
<!-- inline: no -->


### register_on_timeout() {#classdronecore_1_1_drone_core_1ad8c0dc0100449d21a46a787c810e8978}
```cpp
void dronecore::DroneCore::register_on_timeout(event_callback_t callback)
```


Register callback for device timeout.

This sets a callback that will be notified if no heartbeat of the device has been received in 3 seconds.


**Note** Only one callback can be registered at a time. If this function is called several times, previous callbacks will be overwritten.

**Parameters**

* [event_callback_t](classdronecore_1_1_drone_core.md#classdronecore_1_1_drone_core_1abb488f975ee7e199cd1cb08a317a52c3) **callback** - Callback to register.

<!-- inbodydescription:  --> 
<!-- return_type: void -->
<!-- return_type_comment:  -->
<!-- prot: public -->
<!-- static: no -->
<!-- const: no -->
<!-- explicit: no -->
<!-- virt: non-virtual -->
<!-- inline: no -->


### connection_result_str() {#classdronecore_1_1_drone_core_1ab842ee94d965c9f71cd0e96b31e17ee2}
```cpp
static const char * dronecore::DroneCore::connection_result_str(ConnectionResult)
```


Translates the [DroneCore::ConnectionResult](classdronecore_1_1_drone_core.md#classdronecore_1_1_drone_core_1a9bdf4a0267d4851342617bdbcbbeead7) enum to a human-readable English string.


**Parameters**

* [ConnectionResult](classdronecore_1_1_drone_core.md#classdronecore_1_1_drone_core_1a9bdf4a0267d4851342617bdbcbbeead7) **** - 

**Returns**

&emsp;const char * - 

<!-- inbodydescription:  --> 
<!-- return_type: const char * -->
<!-- return_type_comment:  -->
<!-- prot: public -->
<!-- static: yes -->
<!-- const: no -->
<!-- explicit: no -->
<!-- virt: non-virtual -->
<!-- inline: no -->
