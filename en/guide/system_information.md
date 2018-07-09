# System Information

The [Info](../api_reference/classdronecode__sdk_1_1_info.md) class is used to get system (vehicle) information, including the UUID (MAVLink `SYS_ID` if no UUID is stored in hardware), PX4 firmware version, vendor firmware version, host OS version (e.g. for NuttX) and vendor and product ids/names. 

> **Note** Not all version information will necessarily be relevant on all vehicles. Where this occurs the 
hardware may return garbage values (for example, the simulator provides garbage values for the vendor 
firmware semantic version).

## Preconditions

The following code assumes that you already have included DroneCore (`#include <dronecore/dronecore.h>`) and that there is a [connection to a system](../guide/connections.md) obtained as shown below:
```cpp
System &system = dc.system(); 
```

The code also assumes that you have defined `info`, a shared pointer to an instance of the `Info` class associated with the system (see [Using Plugins](../guide/using_plugins.md)):
```cpp
#include <dronecore/info.h>
auto info = std::make_shared<Info>(system);
```

## Query System Information

The code below shows how to query the UUID, version, and product, information and print it to the console:

```cpp
// Get system UUID
std::cout << " UUID: " << info->uuid() << std::endl;

// Wait until version/firmware information has been populated from the vehicle
while (!info->is_complete()) {
    std::cout << "Waiting for Version information to populate from system." << std::endl;
    std::this_thread::sleep_for(std::chrono::seconds(1));
}

// Get the system Version struct
const Info::Version &systemVersion =  info->get_version();

// Print out the vehicle version information.
std::cout << "  flight_sw_major: " << systemVersion.flight_sw_major<< std::endl
          << "  flight_sw_minor: " << systemVersion.flight_sw_minor<< std::endl
          << "  flight_sw_patch: " << systemVersion.flight_sw_patch<< std::endl
          << "  flight_sw_vendor_major: " << systemVersion.flight_sw_vendor_major<< std::endl
          << "  flight_sw_vendor_minor: " << systemVersion.flight_sw_vendor_minor<< std::endl
          << "  flight_sw_vendor_patch: " << systemVersion.flight_sw_vendor_patch<< std::endl
          << "  flight_sw_git_hash: " << systemVersion.flight_sw_git_hash<< std::endl
          << "  os_sw_major: " << systemVersion.os_sw_major<< std::endl
          << "  os_sw_minor: " << systemVersion.os_sw_minor<< std::endl
          << "  os_sw_patch: " << systemVersion.os_sw_patch<< std::endl
          << "  os_sw_git_hash: " << systemVersion.os_sw_git_hash<< std::endl;

// Get the system Product struct
const Info::Product &systemProduct =  info->get_product();

// Print out the vehicle product information.
std::cout << "  vendor_id: " << systemProduct.vendor_id<< std::endl
          << "  vendor_name: " << systemProduct.vendor_name<< std::endl
          << "  product_id: " << systemProduct.product_id<< std::endl
          << "  product_name: " << systemProduct.product_id<< std::endl;
```

> **Tip** It is possible to query for the information before all values have been retrieved. Note above how we use `Info::is_complete()` to check that the version information (`Info::Version` and `Info::Product`) has all been obtained from the vehicle before printing it.
