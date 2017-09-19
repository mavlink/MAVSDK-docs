# Example: Takeoff and Land

This example shows how to use basic DroneCore features. 

It sets up a UDP connection, waits for a device to appear, and commands it to takeoff and then land again. While flying the vehicle receives telemetry. The example is implemented in C++ (only).


<!-- [Gitbook-api-theme](https://github.com/GitbookIO/theme-api#gitbook-api-theme) shows how the methods work -->

> **Tip** The full source code for the example [can be found here](https://github.com/dronecore/DroneCore/tree/master/example/takeoff_land).

## Build Example {#build_example}

To build and try it, start PX4 in SITL and build and run the example as follows:

### Linux
First [Build and install the DroneCore C++ Library](../contributing/build.md).
Make sure that you install the library and headers in the standard location:

```
make default install
```

Then build the example:

```
cd example/takeoff_land/
mkdir build && cd build
cmake ..
make && ./takeoff_and_land
```

Note that the example needs to be linked to a thread library (see [CMakeLists.txt](https://github.com/dronecore/DroneCore/blob/master/example/takeoff_land/CMakeLists.txt))

### Windows

First [Build and install the DroneCore C++ Library](../contributing/build.md).
Make sure that you install the library and headers in the standard location:

```
cmake --build . --target install
```

Build the example using:
```
cd example/takeoff_land/
mkdir build && cd build
cmake --build .
```

The debug binary for the example is stored under \Debug folder.

## Running the Example



```bash
$ ./takeoff_and_land 
Waiting to discover device...
Partner IP: 127.0.0.1:14557
Discovered device with UUID: 4294967298
Arming...
Taking off...
Altitude: -0.042 m
Altitude: 0.054 m
Altitude: 0.989 m
Altitude: 2.128 m
Altitude: 2.434 m
Altitude: 2.446 m
Altitude: 2.408 m
Altitude: 2.377 m
Altitude: 2.369 m
Altitude: 2.374 m
Landing...
Altitude: 1.758 m
Altitude: 0.782 m
Altitude: -0.068 m
Altitude: -0.441 m
Altitude: -0.573 m
Finished...
```


## Source code {#source_code}

The full source code for the example [can be found here](https://github.com/dronecore/DroneCore/blob/master/example/).


[CMakeLists.txt](https://github.com/dronecore/DroneCore/blob/master/example/takeoff_land/CMakeLists.txt)

```make
cmake_minimum_required(VERSION 2.8.12)

project(takeoff_and_land)

if(NOT MSVC)
    add_definitions("-std=c++11 -Wall -Wextra -Werror")
else()
    add_definitions("-std=c++11 -WX -W2")
    set(platform_libs "Ws2_32.lib")
endif()

# Add DEBUG define for Debug target
set(CMAKE_CXX_FLAGS_DEBUG "-DDEBUG")

# This finds thread libs on Linux, Mac, and Windows.
find_package(Threads REQUIRED)

# Not needed if DroneCore installed system-wide
include_directories(
    ${CMAKE_SOURCE_DIR}/../../install/include
)

add_executable(takeoff_and_land
    takeoff_and_land.cpp
)

# Not needed if DroneCore installed system-wide
if(WINDOWS)
    set(dronecore_lib "${CMAKE_SOURCE_DIR}/../../install/lib/dronecore.lib")
else()
    set(dronecore_lib "${CMAKE_SOURCE_DIR}/../../install/lib/libdronecore.a")
endif()

target_link_libraries(takeoff_and_land
    ${dronecore_lib}  # Remove/comment out this line if DroneCore used locally
    # dronecore  # Uncomment/add this line if DroneCore installed system-wide
    ${CMAKE_THREAD_LIBS_INIT}
    ${platform_libs}
)
```

[takeoff_and_land.cpp](https://github.com/dronecore/DroneCore/blob/master/example/takeoff_land/takeoff_and_land.cpp)
```cpp
//
// Simple example to demonstrate how to use DroneCore.
//
// Author: Julian Oes <julian@oes.ch>

#include <dronecore/dronecore.h>
#include <iostream>
#include <thread>
#include <chrono>
#include <cstdint>

using namespace dronecore;

#define ERROR_CONSOLE_TEXT "\033[31m" //Turn text on console red
#define TELEMETRY_CONSOLE_TEXT "\033[34m" //Turn text on console blue
#define NORMAL_CONSOLE_TEXT "\033[0m"  //Restore normal console colour

int main(int /*argc*/, char ** /*argv*/)
{
    DroneCore dc;

    bool discovered_device = false;

    DroneCore::ConnectionResult connection_result = dc.add_udp_connection();

    if (connection_result != DroneCore::ConnectionResult::SUCCESS) {
        std::cout << ERROR_CONSOLE_TEXT << "Connection failed: "
                  << DroneCore::connection_result_str(connection_result)
                  << NORMAL_CONSOLE_TEXT << std::endl;
        return 1;
    }

    std::cout << "Waiting to discover device..." << std::endl;
    dc.register_on_discover([&discovered_device](uint64_t uuid) {
        std::cout << "Discovered device with UUID: " << uuid << std::endl;
        discovered_device = true;
    });

    // We usually receive heartbeats at 1Hz, therefore we should find a device after around 2 seconds.
    std::this_thread::sleep_for(std::chrono::seconds(2));

    if (!discovered_device) {
        std::cout << ERROR_CONSOLE_TEXT << "No device found, exiting." << NORMAL_CONSOLE_TEXT << std::endl;
        return 1;
    }

    // We don't need to specify the UUID if it's only one device anyway.
    // If there were multiple, we could specify it with:
    // dc.device(uint64_t uuid);
    Device &device = dc.device();

    // We want to listen to the altitude of the drone at 1 Hz.
    const Telemetry::Result set_rate_result = dc.device().telemetry().set_rate_position(1.0);
    if (set_rate_result != Telemetry::Result::SUCCESS) {
        std::cout << ERROR_CONSOLE_TEXT << "Setting rate failed:" << Telemetry::result_str(
                      set_rate_result) << NORMAL_CONSOLE_TEXT << std::endl;
        return 1;
    }


    // Set up callback to monitor altitude while the vehicle is in flight
    device.telemetry().position_async([](Telemetry::Position position) {
        std::cout << TELEMETRY_CONSOLE_TEXT // set to blue
                  << "Altitude: " << position.relative_altitude_m << " m"
                  << NORMAL_CONSOLE_TEXT // set to default color again
                  << std::endl;
    });


    // Check if vehicle is ready to arm
    if (device.telemetry().health_all_ok() != true) {
        std::cout << ERROR_CONSOLE_TEXT << "Vehicle not ready to arm" << NORMAL_CONSOLE_TEXT << std::endl;
        return 1;
    }

    // Arm vehicle
    std::cout << "Arming..." << std::endl;
    const Action::Result arm_result = device.action().arm();

    if (arm_result != Action::Result::SUCCESS) {
        std::cout << ERROR_CONSOLE_TEXT << "Arming failed:" << Action::result_str(
                      arm_result) << NORMAL_CONSOLE_TEXT << std::endl;
        return 1;
    }

    // Take off
    std::cout << "Taking off..." << std::endl;
    const Action::Result takeoff_result = device.action().takeoff();
    if (takeoff_result != Action::Result::SUCCESS) {
        std::cout << ERROR_CONSOLE_TEXT << "Takeoff failed:" << Action::result_str(
                      takeoff_result) << NORMAL_CONSOLE_TEXT << std::endl;
        return 1;
    }

    // Let it hover for a bit before landing again.
    std::this_thread::sleep_for(std::chrono::seconds(10));

    std::cout << "Landing..." << std::endl;
    const Action::Result land_result = device.action().land();
    if (land_result != Action::Result::SUCCESS) {
        std::cout << ERROR_CONSOLE_TEXT << "Land failed:" << Action::result_str(
                      land_result) << NORMAL_CONSOLE_TEXT << std::endl;
        return 1;
    }

    // We are relying on auto-disarming but let's keep watching the telemetry for a bit longer.
    std::this_thread::sleep_for(std::chrono::seconds(5));
    std::cout << "Finished..." << std::endl;
    return 0;
}
```
