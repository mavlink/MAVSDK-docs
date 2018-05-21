# Connecting to Systems (Vehicles)

DroneCore allows you to connect to multiple vehicles attached to the local wifi network and/or via serial ports. 

In order to detect vehicles you must first specify the communication ports that DroneCore will monitor for new systems. Once monitoring a port, DroneCore will automatically detect connected vehicles, add them to its collection, and notify registered users of connection and disconnection events.

## Monitoring a Port

Specify the port(s) to watch using one of the (synchronous) connection methods: [add_any_connection()](../api_reference/classdronecore_1_1_drone_core.md#classdronecore_1_1_drone_core_1a4d456788b98920c58b07e6a280642168), [add_udp_connection()](../api_reference/classdronecore_1_1_drone_core.md#classdronecore_1_1_drone_core_1a38e5715ec8817515ccaba5034da30bcd), [add_tcp_connection()](../api_reference/classdronecore_1_1_drone_core.md#classdronecore_1_1_drone_core_1abaa49c13d6277177974a09ccffde82e1) or [add_serial_connection()](../api_reference/classdronecore_1_1_drone_core.md#classdronecore_1_1_drone_core_1aa84b8bfba099631267a0319169c23c8e). All the methods are used similarly, and return immediately with a [ConnectionResult](../api_reference/namespacedronecore.md#namespacedronecore_1a42d7afdc816d7f750e1a8d4282da0ddc) indicating whether they succeeded.

The [add_any_connection()](../api_reference/classdronecore_1_1_drone_core.md#classdronecore_1_1_drone_core_1a4d456788b98920c58b07e6a280642168) method can be used to set up monitoring for any of the supported port types (while the other methods set up specific connection types). The connection details are specified using the string formats shown below:

Connection | URL Format
--- | ---
UDP | `udp://[Bind_host][:Bind_port]`
TCP | `tcp://[Server_host][:Server_port]`
Serial | `serial://[Dev_Node][:Baudrate]`

The code snippet below shows how to set up monitoring with `add_any_connection()`:

```cpp
DroneCore dc;
std::string connection_url="udp://0.0.0.0:14540";
ConnectionResult connection_result = dc.add_any_connection(connection_url);
ASSERT_EQ(connection_result,ConnectionResult::SUCCESS)
```

> **Note** The connection string used above (`udp://0.0.0.0:14540`) is to the [standard PX4 broadcast UDP port](https://dev.px4.io/en/simulation/#default-px4-mavlink-udp-ports) for off-board APIs (14540). This is the normal/most common way for offboard APIs to connect to PX4 over WiFi.

DroneCore also provides the [connection_result_str()](../api_reference/namespacedronecore.md#namespacedronecore_1a71899c532d8bedfa9654160fc175cce8) method, which you can use to create a human-readable string for the [ConnectionResult](../api_reference/namespacedronecore.md#namespacedronecore_1a42d7afdc816d7f750e1a8d4282da0ddc). The code fragment below shows how you might print the string for the preceding code fragment to the console:
```cpp
std::cout << "Connection string: " << connection_result_str(connection_result) << std::endl;
```


### Register for System-Detection Notifications

DroneCore monitors any added communication ports for new systems, which are distinguished by vehicle [UUID](../api_reference/classdronecore_1_1_info.md#classdronecore_1_1_info_1a49c7dd5f1a369c8296f0c3a2443bc031). Clients can register for notification when new systems are discovered using [register_on_discover()](../api_reference/classdronecore_1_1_drone_core.md#classdronecore_1_1_drone_core_1a864ec7349eba67b02b8b3792f6c388f9), and for systems timing out (no longer connected) using [register_on_timeout()](../api_reference/classdronecore_1_1_drone_core.md#classdronecore_1_1_drone_core_1ad8c0dc0100449d21a46a787c810e8978). 

The methods are used in the same way, and invoke a callback function with the UUID of the system that was discovered/disconnected. This UUID can then be used to get a `System` object for managing the associated vehicle (see [Accessing Systems](#accessing-systems) below).

> **Note** If a system does not have a UUID then DroneCore will instead use its MAVLink system ID (a number in the range of 0 to 255).
On a properly configured MAVLink network this will be unique.

The code fragment below shows how to register a callback (in this case the callback is a lambda function that just prints the UUID value to standard `cout`).

```cpp
DroneCore dc;
... //add ports
dc.register_on_discover([](uint64_t uuid) {
    std::cout << "Discovered system with UUID: " << uuid << std::endl;
});
```

## Iterating all Systems

You can iterate all system UUIDs that have been detected by DroneCore 
(since it was started, over all communication ports) using the [system_uuids()](../api_reference/classdronecore_1_1_drone_core.md#classdronecore_1_1_drone_core_1ac9503e701727ffa0293a30a6c8326f10) method. This returns a vector of [UUID](../api_reference/classdronecore_1_1_info.md#classdronecore_1_1_info_1a49c7dd5f1a369c8296f0c3a2443bc031) values, from which you can get `System` objects that are used to manage vehicles. 

The following code fragment shows how to iterate through the UUIDs (in this case, just printing them to standard `cout`).

```cpp
//Iterate through detected systems
std::vector<uint64_t> system_vector = dc.system_uuids();
for ( auto i = system_vector.begin(); i != system_vector.end(); i++ ) {
    std::cout << *i << std::endl;
}
```

The vector contains UUIDs for all systems detected by DroneCore, including those that may no longer be connected. 
You can use [DroneCore::is_connected(uint64_t)](../api_reference/classdronecore_1_1_drone_core.md#classdronecore_1_1_drone_core_1a2f78c2263df997d38cf508e327fcde23) to determine if the system with a particular UUID is connected or not. If you're only expecting a single connection, then you can use the parameterless `is_connected()` method.


## Accessing Systems

Once `DroneCore` has provided you with a vehicle `UUID` you can use the [DroneCore::system()](../api_reference/classdronecore_1_1_drone_core.md#classdronecore_1_1_drone_core_1ab6082fca008ae58b79e87676336506ac) method to get its associated [System](../api_reference/classdronecore_1_1_system.md) object:

```cpp
DroneCore dc;
//... 
//Use UUID named uuid to get the associated System
System &system = dc.system(uuid);
```

> **Tip** If you know that there is only one connected system you can instead call `system()` without any UUID. This will 
return the first system detected, or a null `System` if none have been discovered.
```
System &system = dc.system()
```

The `System` is used by DroneCore plugin classes to query and control the vehicle. For more information see [Using Plugins](../guide/using_plugins.md) (and the other guide topics).
