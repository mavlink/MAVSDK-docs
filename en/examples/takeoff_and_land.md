# Example: Takeoff and Land

This simple example shows the basic use of many *Dronecode SDK* features. 

It sets up a UDP connection, waits for a vehicle (system) to appear, arms it, and commands it to takeoff and then land again. 
While flying the vehicle receives telemetry. The example is implemented in C++ (only).

> **Tip** The full source code for the example [can be found here](https://github.com/dronecore/DroneCore/tree/{{ book.github_branch }}/example/takeoff_land).

## Running the Example {#run_example}

The example is built and run [as described here](../examples/README.md#trying_the_examples) (the standard way).

The example terminal output should be similar to that shown below:

> **Note** This is from a debug build of the SDK. 
  A release build will omit the "Debug" messages.

```sh
$ ./takeoff_and_land udp://:14540
```
```sh
Waiting to discover system...
[11:51:14|Info ] New device on: 127.0.0.1:14557 (udp_connection.cpp:208)
[11:51:14|Debug] New: System ID: 1 Comp ID: 1 (dronecore_impl.cpp:286)
[11:51:14|Debug] Component Autopilot added. (mavlink_system.cpp:349)
[11:51:14|Debug] MAVLink: info: [logger] file: rootfs/fs/microsd/log/2018-05-23/0 (mavlink_system.cpp:286)
[11:51:15|Debug] Found 1 component(s). (mavlink_system.cpp:481)
[11:51:15|Debug] Discovered 4294967298 (mavlink_system.cpp:483)
Discovered system with UUID: 4294967298
Vehicle is getting ready to arm
Vehicle is getting ready to arm
Altitude: 0.007 m
Vehicle is getting ready to arm
Altitude: 0 m
Arming...
Taking off...
[11:51:29|Debug] MAVLink: info: ARMED by arm/disarm component command (mavlink_system.cpp:286)
[11:51:29|Debug] MAVLink: info: Using minimum takeoff altitude: 2.50 m (mavlink_system.cpp:286)
[11:51:30|Debug] MAVLink: info: Takeoff detected (mavlink_system.cpp:286)
[11:51:30|Debug] MAVLink: critical: Using minimum takeoff altitude: 2.50 m (mavlink_system.cpp:286)
Altitude: 0.048 m
Altitude: 1.6 m
Altitude: 2.26 m
...
Altitude: 2.506 m
Altitude: 2.486 m
[11:51:39|Debug] MAVLink: info: data link #0 lost (mavlink_system.cpp:286)
Altitude: 2.479 m
Landing...
[11:51:39|Debug] MAVLink: info: Landing at current position (mavlink_system.cpp:286)
Altitude: 2.277 m
...
Altitude: 0.099 m
Altitude: -0.464 m
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
    include_directories(${CMAKE_SOURCE_DIR}/../../install/include)
    link_directories(${CMAKE_SOURCE_DIR}/../../install/lib)
endif()

add_executable(takeoff_and_land
    takeoff_and_land.cpp
)

target_link_libraries(takeoff_and_land
    dronecore
    dronecore_telemetry
    dronecore_action
)
```

[takeoff_and_land.cpp](https://github.com/dronecore/DroneCore/blob/{{ book.github_branch }}/example/takeoff_land/takeoff_and_land.cpp)
```cpp
//
// Simple example to demonstrate how to use DroneCore.
//
// Author: Julian Oes <julian@oes.ch>

#include <chrono>
#include <cstdint>
#include <dronecore/action.h>
#include <dronecore/dronecore.h>
#include <dronecore/telemetry.h>
#include <iostream>
#include <thread>

using namespace dronecore;
using namespace std::this_thread;
using namespace std::chrono;

#define ERROR_CONSOLE_TEXT "\033[31m" //Turn text on console red
#define TELEMETRY_CONSOLE_TEXT "\033[34m" //Turn text on console blue
#define NORMAL_CONSOLE_TEXT "\033[0m"  //Restore normal console colour

void usage(std::string bin_name)
{
    std::cout << NORMAL_CONSOLE_TEXT << "Usage : " << bin_name << " <connection_url>" << std::endl
              << "Connection URL format should be :" << std::endl
              << " For TCP : tcp://[server_host][:server_port]" << std::endl
              << " For UDP : udp://[bind_host][:bind_port]" << std::endl
              << " For Serial : serial:///path/to/serial/dev[:baudrate]" << std::endl
              << "For example, to connect to the simulator use URL: udp://:14540" << std::endl;
}


int main(int argc, char **argv)
{
    DroneCore dc;
    std::string connection_url;
    ConnectionResult connection_result;

    bool discovered_system = false;
    if (argc == 2) {
        connection_url = argv[1];
        connection_result = dc.add_any_connection(connection_url);
    } else {
        usage(argv[0]);
        return 1;
    }

    if (connection_result != ConnectionResult::SUCCESS) {
        std::cout << ERROR_CONSOLE_TEXT << "Connection failed: "
                  << connection_result_str(connection_result)
                  << NORMAL_CONSOLE_TEXT << std::endl;
        return 1;
    }

    std::cout << "Waiting to discover system..." << std::endl;
    dc.register_on_discover([&discovered_system](uint64_t uuid) {
        std::cout << "Discovered system with UUID: " << uuid << std::endl;
        discovered_system = true;
    });

    // We usually receive heartbeats at 1Hz, therefore we should find a system after around 2 seconds.
    sleep_for(seconds(2));

    if (!discovered_system) {
        std::cout << ERROR_CONSOLE_TEXT << "No system found, exiting." << NORMAL_CONSOLE_TEXT << std::endl;
        return 1;
    }

    // We don't need to specify the UUID if it's only one system anyway.
    // If there were multiple, we could specify it with:
    // dc.system(uint64_t uuid);
    System &system = dc.system();

    auto telemetry = std::make_shared<Telemetry>(system);
    auto action = std::make_shared<Action>(system);

    // We want to listen to the altitude of the drone at 1 Hz.
    const Telemetry::Result set_rate_result = telemetry->set_rate_position(1.0);
    if (set_rate_result != Telemetry::Result::SUCCESS) {
        std::cout << ERROR_CONSOLE_TEXT << "Setting rate failed:" << Telemetry::result_str(
                      set_rate_result) << NORMAL_CONSOLE_TEXT << std::endl;
        return 1;
    }


    // Set up callback to monitor altitude while the vehicle is in flight
    telemetry->position_async([](Telemetry::Position position) {
        std::cout << TELEMETRY_CONSOLE_TEXT // set to blue
                  << "Altitude: " << position.relative_altitude_m << " m"
                  << NORMAL_CONSOLE_TEXT // set to default color again
                  << std::endl;
    });

    // Check if vehicle is ready to arm
    while (telemetry->health_all_ok() != true) {
        std::cout << "Vehicle is getting ready to arm" << std::endl;
        sleep_for(seconds(1));
    }

    // Arm vehicle
    std::cout << "Arming..." << std::endl;
    const ActionResult arm_result = action->arm();

    if (arm_result != ActionResult::SUCCESS) {
        std::cout << ERROR_CONSOLE_TEXT << "Arming failed:" << action_result_str(
                      arm_result) << NORMAL_CONSOLE_TEXT << std::endl;
        return 1;
    }

    // Take off
    std::cout << "Taking off..." << std::endl;
    const ActionResult takeoff_result = action->takeoff();
    if (takeoff_result != ActionResult::SUCCESS) {
        std::cout << ERROR_CONSOLE_TEXT << "Takeoff failed:" << action_result_str(
                      takeoff_result) << NORMAL_CONSOLE_TEXT << std::endl;
        return 1;
    }

    // Let it hover for a bit before landing again.
    sleep_for(seconds(10));

    std::cout << "Landing..." << std::endl;
    const ActionResult land_result = action->land();
    if (land_result != ActionResult::SUCCESS) {
        std::cout << ERROR_CONSOLE_TEXT << "Land failed:" << action_result_str(
                      land_result) << NORMAL_CONSOLE_TEXT << std::endl;
        return 1;
    }

    // We are relying on auto-disarming but let's keep watching the telemetry for a bit longer.
    sleep_for(seconds(5));
    std::cout << "Finished..." << std::endl;
    return 0;
}
```
