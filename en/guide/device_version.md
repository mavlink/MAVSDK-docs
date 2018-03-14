## Device Information

The [Info](../api_reference/classdronecore_1_1_info.md) class is used to get device information, including the device UUID (MAVLink `SYS_ID` if no UUID is stored in hardware), PX4 firmware version, vendor firmware version, host OS version (e.g. for NuttX) and vendor and product ids/names. 

> **Note** Not all version information will necessarily be relevant on all vehicles. Where this occurs the 
hardware may return garbage values (for example, the simulator provides garbage values for the vendor 
firmware semantic version).

## Preconditions

The following code assumes that you already have included DroneCore (`#include <dronecore/dronecore.h>`) and that there is a [connection to a device](../guide/connections.md) obtained as shown below:
```cpp
Device &device = dc.device(); 
```

The code also assumes that you have defined `info`, a shared pointer to an instance of the `Info` class associated with the device (see [Using Plugins](../guide/using_plugins.md)):
```cpp
#include <dronecore/info.h>
auto info = std::make_shared<Info>(device);
```

## Query Device Information

The code below shows how to query the UUID, version, and product, information and print it to the console:

```cpp
// Get device UUID
std::cout << " UUID: " << info->uuid() << std::endl;

// Wait until version/firmware information has been populated from the vehicle
while (!info->is_complete()) {
    std::cout << "Waiting for Version information to populate from device." << std::endl;
    std::this_thread::sleep_for(std::chrono::seconds(1));
}

// Get the device Version struct
const Info::Version &deviceVersion =  info->get_version();

// Print out the vehicle version information.
std::cout << "  flight_sw_major: " << deviceVersion.flight_sw_major<< std::endl
          << "  flight_sw_minor: " << deviceVersion.flight_sw_minor<< std::endl
          << "  flight_sw_patch: " << deviceVersion.flight_sw_patch<< std::endl
          << "  flight_sw_vendor_major: " << deviceVersion.flight_sw_vendor_major<< std::endl
          << "  flight_sw_vendor_minor: " << deviceVersion.flight_sw_vendor_minor<< std::endl
          << "  flight_sw_vendor_patch: " << deviceVersion.flight_sw_vendor_patch<< std::endl
          << "  flight_sw_git_hash: " << deviceVersion.flight_sw_git_hash<< std::endl
          << "  os_sw_major: " << deviceVersion.os_sw_major<< std::endl
          << "  os_sw_minor: " << deviceVersion.os_sw_minor<< std::endl
          << "  os_sw_patch: " << deviceVersion.os_sw_patch<< std::endl
          << "  os_sw_git_hash: " << deviceVersion.os_sw_git_hash<< std::endl;

// Get the device Product struct
const Info::Product &deviceProduct =  info->get_product();

// Print out the vehicle product information.
std::cout << "  vendor_id: " << deviceProduct.vendor_id<< std::endl
          << "  vendor_name: " << deviceProduct.vendor_name<< std::endl
          << "  product_id: " << deviceProduct.product_id<< std::endl
          << "  product_name: " << deviceProduct.product_id<< std::endl;
```

> **Tip** It is possible to query for the information before all values have been retrieved. Note above how we use `Info::is_complete()` to check that the version information (`Info::Version` and `Info::Product`) has all been obtained from the vehicle before printing it.
