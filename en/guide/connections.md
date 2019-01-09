# Connecting to Systems (Vehicles)

The *Dronecode SDK* allows you to connect to multiple vehicles attached to the local WiFi network and/or via serial ports. 

In order to detect vehicles you must first specify the communication ports that the SDK will monitor for new systems. 
Once monitoring a port, the SDK will automatically detect connected vehicles, add them to its collection, and notify registered users of connection and disconnection events.

## Monitoring a Port

Specify the port(s) to watch using one of the (synchronous) connection methods: [add_any_connection()](../api_reference/classdronecode__sdk_1_1_dronecode_s_d_k.md#classdronecode__sdk_1_1_dronecode_s_d_k_1a51097e0dad30f0292a2ab4d3e9d91acf), [add_udp_connection()](../api_reference/classdronecode__sdk_1_1_dronecode_s_d_k.md#classdronecode__sdk_1_1_dronecode_s_d_k_1ac242fb36bc018038fc1fc5ee4e5f21ad), [add_tcp_connection()](../api_reference/classdronecode__sdk_1_1_dronecode_s_d_k.md#classdronecode__sdk_1_1_dronecode_s_d_k_1a7c543c91cf9209745c60a5b4bb6a59b1) or [add_serial_connection()](../api_reference/classdronecode__sdk_1_1_dronecode_s_d_k.md#classdronecode__sdk_1_1_dronecode_s_d_k_1a3b9dfa07541777ec16d9ada6423650b0). All the methods are used similarly, and return immediately with a [ConnectionResult](../api_reference/namespacedronecode__sdk.md#namespacedronecode__sdk_1a8ba260cb5fc0837533a86e236d205c96) indicating whether they succeeded.

The [add_any_connection()](../api_reference/classdronecode__sdk_1_1_dronecode_s_d_k.md#classdronecode__sdk_1_1_dronecode_s_d_k_1a51097e0dad30f0292a2ab4d3e9d91acf) method can be used to set up monitoring for any of the supported port types (while the other methods set up specific connection types). 
The connection details are specified using the string formats shown below:

Connection | URL Format
--- | ---
UDP | `udp://[Bind_host][:Bind_port]`
TCP | `tcp://[Server_host][:Server_port]`
Serial | `serial://[Dev_Node][:Baudrate]`

The code snippet below shows how to set up monitoring with `add_any_connection()`:

```cpp
DronecodeSDK dc;
std::string connection_url="udp://0.0.0.0:14540";
ConnectionResult connection_result = dc.add_any_connection(connection_url);
ASSERT_EQ(connection_result,ConnectionResult::SUCCESS)
```

> **Note** The connection string used above (`udp://0.0.0.0:14540`) is to the [standard PX4 broadcast UDP port](https://dev.px4.io/en/simulation/#default-px4-mavlink-udp-ports) for off-board APIs (14540). This is the normal/most common way for offboard APIs to connect to PX4 over WiFi.

The SDK also provides the [connection_result_str()](../api_reference/namespacedronecode__sdk.md#namespacedronecode__sdk_1a4f99d135d291363375982e84b6928f38) method, which you can use to create a human-readable string for the [ConnectionResult](../api_reference/namespacedronecode__sdk.md#namespacedronecode__sdk_1a8ba260cb5fc0837533a86e236d205c96). The code fragment below shows how you might print the string for the preceding code fragment to the console:
```cpp
std::cout << "Connection string: " << connection_result_str(connection_result) << std::endl;
```


### Register for System-Detection Notifications

The SDK monitors any added communication ports for new systems, which are distinguished by vehicle [UUID](../api_reference/classdronecode__sdk_1_1_info.md#classdronecode__sdk_1_1_info_1a38f1b08ee69a4dbfc22a79ddf6a20ce4). 
Clients can register for notification when new systems are discovered using [register_on_discover()](../api_reference/classdronecode__sdk_1_1_dronecode_s_d_k.md#classdronecode__sdk_1_1_dronecode_s_d_k_1a7e4f9e429d59faa19578cffecc184427), and for systems timing out (no longer connected) using [register_on_timeout()](../api_reference/classdronecode__sdk_1_1_dronecode_s_d_k.md#classdronecode__sdk_1_1_dronecode_s_d_k_1a21d36d607097eb51197427ca04716b9b). 

The methods are used in the same way, and invoke a callback function with the UUID of the system that was discovered/disconnected. 
This UUID can then be used to get a `System` object for managing the associated vehicle (see [Accessing Systems](#accessing-systems) below).

> **Note** If a system does not have a UUID then `DronecodeSDK` will instead use its MAVLink system ID (a number in the range of 1 to 255).
  On a properly configured MAVLink network this will be unique.

The code fragment below shows how to register a callback (in this case the callback is a lambda function that just prints the UUID value to standard `cout`).

```cpp
DronecodeSDK dc;
... //add ports
dc.register_on_discover([](uint64_t uuid) {
    std::cout << "Discovered system with UUID: " << uuid << std::endl;
});
```

## Iterating all Systems

You can iterate all system UUIDs that have been detected by `DronecodeSDK` 
(since it was started, over all communication ports) using the [system_uuids()](../api_reference/classdronecode__sdk_1_1_dronecode_s_d_k.md#classdronecode__sdk_1_1_dronecode_s_d_k_1adff0ce5e9bd666103a3ec5274ecb9b47) method. 
This returns a vector of [UUID](../api_reference/classdronecode__sdk_1_1_info.md#classdronecode__sdk_1_1_info_1a38f1b08ee69a4dbfc22a79ddf6a20ce4) values, from which you can get `System` objects that are used to manage vehicles. 

The following code fragment shows how to iterate through the UUIDs (in this case, just printing them to standard `cout`).

```cpp
//Iterate through detected systems
std::vector<uint64_t> system_vector = dc.system_uuids();
for ( auto i = system_vector.begin(); i != system_vector.end(); i++ ) {
    std::cout << *i << std::endl;
}
```

The vector contains UUIDs for all systems detected by `DronecodeSDK`, including those that may no longer be connected. 
You can use [DronecodeSDK::is_connected(uint64_t)](../api_reference/classdronecode__sdk_1_1_dronecode_s_d_k.md#classdronecode__sdk_1_1_dronecode_s_d_k_1a82017f6833745cfe37870ba795709b2f) to determine if the system with a particular UUID is connected or not. 
If you're only expecting a single connection, then you can use the parameterless `is_connected()` method.


## Accessing Systems

Once `DronecodeSDK` has provided you with a vehicle `UUID` you can use the [DronecodeSDK::system()](../api_reference/classdronecode__sdk_1_1_dronecode_s_d_k.md#classdronecode__sdk_1_1_dronecode_s_d_k_1a33dbbe477d4f321cff32c7cea1aee4eb) method to get its associated [System](../api_reference/classdronecode__sdk_1_1_system.md) object:

```cpp
DronecodeSDK dc;
//... 
//Use UUID named uuid to get the associated System
System &system = dc.system(uuid);
```

> **Tip** If you know that there is only one connected system you can instead call `system()` without any UUID. 
  This will return the first system detected, or a null `System` if none have been discovered.
```
System &system = dc.system()
```

The `System` is used by the *Dronecode SDK* plugin classes to query and control the vehicle. 
For more information see [Using Plugins](../guide/using_plugins.md) (and the other guide topics).
