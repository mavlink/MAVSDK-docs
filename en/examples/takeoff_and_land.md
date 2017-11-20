# Example: Takeoff and Land

This simple example shows the basic use of many DroneCore features. 

It sets up a UDP connection, waits for a device to appear, arms it, and commands it to takeoff and then land again. While flying the vehicle receives telemetry. The example is implemented in C++ (only).

> **Tip** The full source code for the example [can be found here](https://github.com/dronecore/DroneCore/tree/{{ book.github_branch }}/example/takeoff_land).

## Running the Example {#run_example}

The example is built and run [as described here](../examples/README.md#trying_the_examples) (the standard way).

The example terminal output should be similar to that shown below:

> **Note** This is from a debug build of DroneCore. A release build will omit the "Debug" messages.

```sh
$ ./takeoff_and_land 
Waiting to discover device...
[03:34:57|Info ] New device on: 127.0.0.1:14557 (udp_connection.cpp:210)
[03:34:57|Debug] Discovered 4294967298 (dronecore_impl.cpp:234)
Discovered device with UUID: 4294967298
Arming...
Taking off...
[03:34:59|Debug] MAVLink: info: ARMED by arm/disarm component command (device_impl.cpp:225)
[03:34:59|Debug] MAVLink: info: Using minimum takeoff altitude: 2.50 m (device_impl.cpp:225)
[03:34:59|Debug] MAVLink: info: Takeoff detected (device_impl.cpp:225)
[03:34:59|Debug] MAVLink: critical: Using minimum takeoff altitude: 2.50 m (device_impl.cpp:225)
Altitude: 0 m
Altitude: 1.381 m
Altitude: 2.283 m
Altitude: 2.519 m
Altitude: 2.55 m
Altitude: 2.53 m
Altitude: 2.508 m
Altitude: 2.491 m
Altitude: 2.479 m
Altitude: 2.471 m
Landing...
[03:35:09|Debug] MAVLink: info: Landing at current position (device_impl.cpp:225)
Altitude: 2.321 m
Altitude: 1.587 m
Altitude: 0.813 m
Altitude: 0.025 m
Altitude: -0.483 m
Finished...
```


## Source code {#source_code}

> **Tip** The full source code for the example [can be found on Github here](https://github.com/dronecore/DroneCore/tree/{{ book.github_branch }}/example/takeoff_land).

[CMakeLists.txt](https://github.com/dronecore/DroneCore/blob/{{ book.github_branch }}/example/takeoff_land/CMakeLists.txt)

```make
cmake_minimum_required(VERSION 2.8.12)

project(takeoff_and_land)

if(NOT MSVC)
    add_definitions("-std=c++11 -Wall -Wextra -Werror")
else()
    add_definitions("-std=c++11 -WX -W2")
endif()

add_executable(takeoff_and_land
    takeoff_and_land.cpp
)

target_link_libraries(takeoff_and_land
    dronecore
)
```

[takeoff_and_land.cpp](https://github.com/dronecore/DroneCore/blob/{{ book.github_branch }}/example/takeoff_land/takeoff_and_land.cpp)
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
