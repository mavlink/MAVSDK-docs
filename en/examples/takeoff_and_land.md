# Example: Takeoff and Land

This example shows how to use basic DroneCore features. 

It sets up a UDP connection, waits for a device to appear, and commands it to takeoff and then land again. While flying the vehicle receives telemetry. The example is implemented in C++ and <????>.


<!-- [Gitbook-api-theme](https://github.com/GitbookIO/theme-api#gitbook-api-theme) shows how the methods work -->

> **Tip** The full source code for the example [can be found here](https://github.com/dronecore/DroneCore/blob/master/example/).

{% method %}
## Build Example {#build_example}

To build and try it, start PX4 in SITL and build and run the example as follows:


{% sample lang="cpp" %}
Build and install the DroneCore library first:

```
make default install
```

Then build the example:

```
cd example/
mkdir build && cd build
cmake ..
make && ./takeoff_and_land
```

Note that the example needs to be linked to a thread library (see [CMakeLists.txt](https://github.com/dronecore/DroneCore/blob/master/example/CMakeLists.txt))

{% sample lang="python" %}
XXXX
{% endmethod %}


{% method %}
## Source code {#source_code}

The full source code for the example [can be found here](https://github.com/dronecore/DroneCore/blob/master/example/).

{% sample lang="cpp" %}
[CMakeLists.txt](https://github.com/dronecore/DroneCore/blob/master/example/CMakeLists.txt)

```make
cmake_minimum_required(VERSION 2.8.12)

project(takeoff_and_land)

add_definitions("-std=c++11 -Wall -Wextra -Werror")

# Add DEBUG define for Debug target
set(CMAKE_CXX_FLAGS_DEBUG "-DDEBUG")

# This finds thread libs on Linux, Mac, and Windows.
find_package(Threads REQUIRED)

include_directories(
    # Not needed if installed system-wide
    ../install/include
)

add_executable(takeoff_and_land
    takeoff_and_land.cpp
)

target_link_libraries(takeoff_and_land
    ${CMAKE_SOURCE_DIR}/../install/lib/libdronecore.a
    # If installed system-wide:
    # dronecore
    ${CMAKE_THREAD_LIBS_INIT}
)

```

[takeoff_and_land.cpp](https://github.com/dronecore/DroneCore/blob/master/example/takeoff_and_land.cpp)
```cpp
// Simple example to demonstrate how to use DroneCore.
//
// Author: Julian Oes <julian@oes.ch>

#include <dronecore/dronecore.h>
#include <iostream>
#include <thread>
#include <chrono>
#include <cstdint>

using namespace dronecore;

int main(int /*argc*/, char ** /*argv*/)
{
    DroneCore dc;

    bool discovered_device = false;

    DroneCore::ConnectionResult connection_result = dc.add_udp_connection();

    if (connection_result != DroneCore::ConnectionResult::SUCCESS) {
        std::cout << "Connection failed: " << DroneCore::connection_result_str(
                      connection_result) << std::endl;
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
        std::cout << "No device found, exiting." << std::endl;
        return 1;
    }

    // We don't need to specify the UUID if it's only one device anyway.
    // If there were multiple, we could specify it with:
    // dc.device(uint64_t uuid);
    Device &device = dc.device();

    // We want to listen to the altitude of the drone at 1 Hz.
    const Telemetry::Result set_rate_result = dc.device().telemetry().set_rate_position(1.0);
    if (set_rate_result != Telemetry::Result::SUCCESS) {
        std::cout << "Setting rate failed:" << Telemetry::result_str(set_rate_result) << std::endl;
        return 1;
    }

    device.telemetry().position_async([](Telemetry::Position position) {
        std::cout << "\033[34m" // set to blue
                  << "Altitude: " << position.relative_altitude_m << " m"
                  << "\033[0m" // set to default color again
                  << std::endl;
    });

    std::cout << "Arming..." << std::endl;
    const Action::Result arm_result = device.action().arm();

    if (arm_result != Action::Result::SUCCESS) {
        std::cout << "Arming failed:" << Action::result_str(arm_result) << std::endl;
        return 1;
    }

    std::cout << "Taking off..." << std::endl;
    const Action::Result takeoff_result = device.action().takeoff();
    if (takeoff_result != Action::Result::SUCCESS) {
        std::cout << "Takeoff failed:" << Action::result_str(takeoff_result) << std::endl;
        return 1;
    }

    // Let it hover for a bit before landing again.
    std::this_thread::sleep_for(std::chrono::seconds(10));

    std::cout << "Landing..." << std::endl;
    const Action::Result land_result = device.action().land();
    if (land_result != Action::Result::SUCCESS) {
        std::cout << "Land failed:" << Action::result_str(land_result) << std::endl;
        return 1;
    }

    // We are relying on auto-disarming but let's keep watching the telemetry infos a bit longer.
    std::this_thread::sleep_for(std::chrono::seconds(5));

    return 0;
}
```

{% sample lang="python" %}
This is perhaps where equivalent Python example might live. 
{% endmethod %}


