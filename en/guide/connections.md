# Connecting to Systems (Vehicles)

The MAVSDK allows you to connect to multiple vehicles attached to the local WiFi network and/or via serial ports. 

In order to detect vehicles you must first specify the communication ports that the SDK will monitor for new systems. 
Once monitoring a port, the SDK will automatically detect connected vehicles, add them to its collection, and notify registered users of connection and disconnection events.

## Monitoring a Port

Specify the port(s) to watch using one of the (synchronous) connection methods: [add_any_connection()](../api_reference/classmavsdk_1_1_mavsdk.md#classmavsdk_1_1_mavsdk_1a229888e2931c16d11edbed07b03174d4), [add_udp_connection()](../api_reference/classmavsdk_1_1_mavsdk.md#classmavsdk_1_1_mavsdk_1a605d3a89cd527222bf131b2c036dc899), [add_tcp_connection()](../api_reference/classmavsdk_1_1_mavsdk.md#classmavsdk_1_1_mavsdk_1a868d224223d2f4e8de7d5e00863b6ceb) or [add_serial_connection()](../api_reference/classmavsdk_1_1_mavsdk.md#classmavsdk_1_1_mavsdk_1a8f27dd954d74b0afdfa4348ce49a10a1).
All the methods are used similarly, and return immediately with a [ConnectionResult](../api_reference/namespacemavsdk.md#namespacemavsdk_1a0bad93f6d037051ac3906a0bcc09f992) indicating whether they succeeded.

The [add_any_connection()](../api_reference/classmavsdk_1_1_mavsdk.md#classmavsdk_1_1_mavsdk_1a229888e2931c16d11edbed07b03174d4) method can be used to set up monitoring for any of the supported port types (while the other methods set up specific connection types).
The connection details are specified using the string formats shown below:

Connection | URL Format
--- | ---
UDP | `udp://[Bind_host][:Bind_port]`
TCP | `tcp://[Server_host][:Server_port]`
Serial | `serial://[Dev_Node][:Baudrate]`

The code snippet below shows how to set up monitoring with `add_any_connection()`:

```cpp
Mavsdk dc;
std::string connection_url="udp://0.0.0.0:14540";
ConnectionResult connection_result = dc.add_any_connection(connection_url);
ASSERT_EQ(connection_result,ConnectionResult::SUCCESS)
```

> **Note** The connection string used above (`udp://0.0.0.0:14540`) is to the [standard PX4 broadcast UDP port](https://dev.px4.io/master/en/simulation/#default-px4-mavlink-udp-ports) for off-board APIs (14540). This is the normal/most common way for offboard APIs to connect to PX4 over WiFi.

The SDK also provides the [connection_result_str()](../api_reference/namespacemavsdk.md#namespacemavsdk_1a59e8a165c1edafab6ab0c04df2c83679) method, which you can use to create a human-readable string for the [ConnectionResult](../api_reference/namespacemavsdk.md#namespacemavsdk_1a0bad93f6d037051ac3906a0bcc09f992).
The code fragment below shows how you might print the string for the preceding code fragment to the console:
```cpp
std::cout << "Connection string: " << connection_result_str(connection_result) << std::endl;
```


### Register for System-Detection Notifications

The SDK monitors any added communication ports for new systems, which are distinguished by vehicle [UUID](../api_reference/classmavsdk_1_1_info.md). 
Clients can register for notification when new systems are discovered using [register_on_discover()](../api_reference/classmavsdk_1_1_mavsdk.md#classmavsdk_1_1_mavsdk_1aa8d55ab10da8f1b868003b44e99c2ecc), and for systems timing out (no longer connected) using [register_on_timeout()](../api_reference/classmavsdk_1_1_mavsdk.md#classmavsdk_1_1_mavsdk_1a4baa7d2dd487e9cff12f5dda11ba3262).

The methods are used in the same way, and invoke a callback function with the UUID of the system that was discovered/disconnected. 
This UUID can then be used to get a `System` object for managing the associated vehicle (see [Accessing Systems](#accessing-systems) below).

> **Note** If a system does not have a UUID then `Mavsdk` will instead use its MAVLink system ID (a number in the range of 1 to 255).
  On a properly configured MAVLink network this will be unique.

The code fragment below shows how to register a callback (in this case the callback is a lambda function that just prints the UUID value to standard `cout`).

```cpp
Mavsdk dc;
... //add ports
dc.register_on_discover([](uint64_t uuid) {
    std::cout << "Discovered system with UUID: " << uuid << std::endl;
});
```

## Iterating all Systems

You can iterate all system UUIDs that have been detected by `Mavsdk` 
(since it was started, over all communication ports) using the [system_uuids()](../api_reference/classmavsdk_1_1_mavsdk.md#classmavsdk_1_1_mavsdk_1a80bd9c663d0e03c24f029fd77e914c3c) method. 
This returns a vector of UUID values, from which you can get `System` objects that are used to manage vehicles.

The following code fragment shows how to iterate through the UUIDs (in this case, just printing them to standard `cout`).

```cpp
//Iterate through detected systems
std::vector<uint64_t> system_vector = dc.system_uuids();
for ( auto i = system_vector.begin(); i != system_vector.end(); i++ ) {
    std::cout << *i << std::endl;
}
```

The vector contains UUIDs for all systems detected by `Mavsdk`, including those that may no longer be connected. 
You can use [Mavsdk::is_connected(uint64_t)](../api_reference/classmavsdk_1_1_mavsdk.md#classmavsdk_1_1_mavsdk_1aced99aea3a52c1245b1d80ff1f22cbd2) to determine if the system with a particular UUID is connected or not.
If you're only expecting a single connection, then you can use the parameterless `is_connected()` method.


## Accessing Systems

Once `Mavsdk` has provided you with a vehicle `UUID` you can use the [Mavsdk::system()](../api_reference/classmavsdk_1_1_mavsdk.md#classmavsdk_1_1_mavsdk_1a2f3e89f37fffbbf1ee2c2089086ed33c) method to get its associated [System](../api_reference/classmavsdk_1_1_system.md) object:

```cpp
Mavsdk dc;
//... 
//Use UUID named uuid to get the associated System
System &system = dc.system(uuid);
```

> **Tip** If you know that there is only one connected system you can instead call `system()` without any UUID. 
  This will return the first system detected, or a null `System` if none have been discovered.
```
System &system = dc.system()
```

The `System` is used by the MAVSDK plugin classes to query and control the vehicle. 
For more information see [Using Plugins](../guide/using_plugins.md) (and the other guide topics).
