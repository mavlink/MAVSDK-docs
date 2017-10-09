# Connecting to Devices

DroneCore allows you to connect to multiple vehicles attached to the local wifi network and/or via serial ports. 

In order to detect vehicles you must first specify the communication ports that DroneCore will monitor for devices. Once monitoring a port, DroneCore will automatically detect connected vehicles, add them to its collection, and notify registered users of connection and disconnection events.

## Monitoring a Port

You specify the ports to watch using one of the (synchronous) connection methods: [add_udp_connection()](../api_reference/classdronecore_1_1_drone_core.md#classdronecore_1_1_drone_core_1ae4d3a7e5cc46d9570beaafdb5f19a1a8), [add_tcp_connection()](../api_reference/classdronecore_1_1_drone_core.md#classdronecore_1_1_drone_core_1ae3c2a16c464fda4cfadce0ec1426bb77) or [add_serial_connection()](../api_reference/classdronecore_1_1_drone_core.md#classdronecore_1_1_drone_core_1aa0e24650330b64753e663cfba51c0292). The methods return immediately with a [DroneCore::ConnectionResult](../api_reference/classdronecore_1_1_drone_core.md#classdronecore_1_1_drone_core_1a9bdf4a0267d4851342617bdbcbbeead7) indicating whether they succeeded. 

Simple code to start monitoring a UDP port might look like this:

```cpp
DroneCore dc;
DroneCore::ConnectionResult connection_result = dc.add_udp_connection();
ASSERT_EQ(connection_result,DroneCore::ConnectionResult::SUCCESS)
```

> **Tip** This is the normal/most common way to connect to PX4 over WiFi, using the standard PX4 broadcast UDP port for off-board APIs (14540). You can also explicitly specify the connection properties/ports if needed.

DroneCore also provides the [DroneCore::connection_result_str()](../api_reference/classdronecore_1_1_drone_core.md#classdronecore_1_1_drone_core_1a84c40dcefcafe888c38a5ed8dd93b0af) method, which you can use to create a human-readable string for the [DroneCore::ConnectionResult](../api_reference/classdronecore_1_1_drone_core.md#classdronecore_1_1_drone_core_1a9bdf4a0267d4851342617bdbcbbeead7). The code fragment below shows how you might print this string to the console:
```cpp
DroneCore dc;
DroneCore::ConnectionResult connection_result = dc.add_udp_connection();
std::cout << "Connection string: " << DroneCore::connection_result_str(connection_result) << std::endl;
```

### Register for Device Notifications

DroneCore monitors any added communication ports for new devices, which are distinguished by vehicle [UUID](../api_reference/classdronecore_1_1_info.md#classdronecore_1_1_info_1a49c7dd5f1a369c8296f0c3a2443bc031).  Clients can register for notification when new devices are discovered using [register_on_discover()](../api_reference/classdronecore_1_1_drone_core.md#classdronecore_1_1_drone_core_1a864ec7349eba67b02b8b3792f6c388f9), and for devices timing out (no longer connected) using [register_on_timeout()](../api_reference/classdronecore_1_1_drone_core.md#classdronecore_1_1_drone_core_1ad8c0dc0100449d21a46a787c810e8978). 

The methods are used in the same way, and invoke a callback function with the UUID of the device that was discovered/disconnected. This UUID can then be used to get a `Device` object for managing the associated vehicle (see [Accessing Devices](#accessing-devices) below).

> **Note** If a device does not have a UUID then DroneCore will instead use its MAVLink system ID (a number in the range of 0 to 255).
On a properly configured MAVLink network this will be unique.

The code fragment below shows how to register a callback (in this case the callback is a lambda function that just prints the UUID value to standard `cout`).

```cpp
DroneCore dc;
... //add ports
dc.register_on_discover([](uint64_t uuid) {
    std::cout << "Discovered device with UUID: " << uuid << std::endl;
});
```

## Iterating all Devices

You can iterate all device UUIDs that have been detected by DroneCore 
(since it was started, over all communication ports) using the [device_uuids()](../api_reference/classdronecore_1_1_drone_core.md#classdronecore_1_1_drone_core_1a20490717da3893be2c6965b905a7c1db) method. This returns a vector of [UUID](../api_reference/classdronecore_1_1_info.md#classdronecore_1_1_info_1a49c7dd5f1a369c8296f0c3a2443bc031) values, from which you can get `Device` objects that are used to manage vehicles. 

The following code fragment shows how to iterate through the UUIDs (in this case, just printing them to standard `cout`).

```cpp
//Iterate through detected devices
std::vector<uint64_t> device_vector= dc.device_uuids();
for ( auto i = device_vector.begin(); i != device_vector.end(); i++ ) {
    std::cout << *i << std::endl;
}
```

The vector contains UUIDs for all devices detected by DroneCore, including those that may no longer be connected. 
You can use [DroneCore::is_connected(uint64_t)](../api_reference/classdronecore_1_1_drone_core.html#classdronecore_1_1_drone_core_1a2f78c2263df997d38cf508e327fcde23) to determine if the device with a particular UUID is connected or not. If you're only expecting a single connection, then you can use the parameterless `is_connected()` method.


## Accessing Devices

Once `DroneCore` has provided you with a vehicle `UUID` you can use the [DroneCore::device()](../api_reference/classdronecore_1_1_drone_core.md#classdronecore_1_1_drone_core_1a5bac6e419e56a1f77a51adef98e94e7c) method to get its associated [Device](../api_reference/classdronecore_1_1_device.md) object:

```cpp
DroneCore dc;
//... 
//Use UUID named uuid to get the associated Device
Device &device = dc.device(uuid);
```

> **Tip** If you know that there is only one connected device you can instead call `device()` without any UUID. This will 
return the first device detected, or a null `Device` if none have been discovered.
```
Device &device = dc.device()
```

The `Device` can be used to query and control the vehicle. You use the device getters to get an instance of a plugin API (e.g. [Device::action()](../api_reference/classdronecore_1_1_device.md#classdronecore_1_1_device_plugin_container_1aea48bd55b1ace227ebb56690794c2192) to get an [Action](../api_reference/classdronecore_1_1_action.md) object) and then call the object's methods. For example, to arm the device you would do:
```cpp
const Action::Result arm_result = device.action().arm();
```
The plugin APIs are covered in other guide topics.