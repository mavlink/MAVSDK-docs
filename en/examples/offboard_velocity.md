# Example: Offboard Velocity

This example shows how to how to control a vehicle in *Offboard mode* using velocity commands (in both the NED and body frames).

![Offboard Mode - Velocity Control QGC Screenshot](../../assets/examples/offboard_mode/qgc_offboard_velocity.png)


## Running the Example {#run_example}

The example is built and run [as described here](../examples/README.md#trying_the_examples) (the standard way). 

The example terminal output should be similar to that shown below:

> **Note** This is from a debug build of the SDK. 
  A release build will omit the "Debug" messages.

```
$ ./offboard udp://:14540
```
```
Wait for system to connect via heartbeat
[12:53:03|Info ] New device on: 127.0.0.1:14557 (udp_connection.cpp:208)
[12:53:03|Debug] New: System ID: 1 Comp ID: 1 (dronecode_sdk_impl.cpp:286)
[12:53:03|Debug] Component Autopilot added. (mavlink_system.cpp:349)
[12:53:03|Debug] MAVLink: info: [logger] file: rootfs/fs/microsd/log/2018-05-23/0 (mavlink_system.cpp:286)
[12:53:04|Debug] Found 1 component(s). (mavlink_system.cpp:481)
[12:53:04|Debug] Discovered 4294967298 (mavlink_system.cpp:483)
Waiting for system to be ready
System is ready
Armed
[12:53:05|Debug] MAVLink: info: ARMED by arm/disarm component command (mavlink_system.cpp:286)
In Air...
[12:53:05|Debug] MAVLink: info: Using minimum takeoff altitude: 2.50 m (mavlink_system.cpp:286)
[12:53:05|Debug] MAVLink: info: Takeoff detected (mavlink_system.cpp:286)
[12:53:05|Debug] MAVLink: critical: Using minimum takeoff altitude: 2.50 m (mavlink_system.cpp:286)
[NED] Offboard started
[NED] Turn to face East
[NED] Go North and back South
[NED] Turn to face West
[NED] Go up 2 m/s, turn to face South
[NED] Go down 1 m/s, turn to face North
[NED] Offboard stopped
[BODY] Offboard started
[BODY] Turn clock-wise and climb
[BODY] Turn back anti-clockwise
[BODY] Wait for a bit
[BODY] Fly a circle
[BODY] Wait for a bit
[BODY] Fly a circle sideways
[BODY] Wait for a bit
[BODY] Offboard stopped
[12:54:29|Debug] MAVLink: info: Landing at current position (mavlink_system.cpp:286)
Landed
```

## How it works

The operation of most of this code is discussed in the guide: [Offboard Control](../guide/offboard.md).

## Source code {#source_code}

> **Tip** The full source code for the example [can be found on Github here](https://github.com/mavlink/MAVSDK/tree/{{ book.github_branch }}/examples/offboard_velocity).


[CMakeLists.txt](https://github.com/mavlink/MAVSDK/blob/{{ book.github_branch }}/examples/offboard_velocity/CMakeLists.txt)

```make
cmake_minimum_required(VERSION 2.8.12)

project(offboard)

if(MINGW)
    add_definitions("-D_USE_MATH_DEFINES") # For M_PI
endif()

if(MSVC)
    add_definitions("-std=c++11 -WX -W2")
    add_definitions("-D_USE_MATH_DEFINES") # For M_PI
else()
    add_definitions("-std=c++11 -Wall -Wextra -Werror")
endif()

find_package(MAVSDK REQUIRED)

add_executable(offboard
    offboard_velocity.cpp
)

target_link_libraries(offboard
    MAVSDK::mavsdk_action
    MAVSDK::mavsdk_offboard
    MAVSDK::mavsdk_telemetry
    MAVSDK::mavsdk
)
```

[offboard_velocity.cpp](https://github.com/mavlink/MAVSDK/blob/{{ book.github_branch }}/example/offboard_velocity/offboard_velocity.cpp)

```cpp
/**
 * @file offboard_velocity.cpp
 * @brief Example that demonstrates offboard velocity control in local NED and body coordinates
 *
 * @authors Author: Julian Oes <julian@oes.ch>,
 *                  Shakthi Prashanth <shakthi.prashanth.m@intel.com>
 * @date 2017-10-17
 */

#include <chrono>
#include <cmath>
#include <iostream>
#include <thread>

#include <mavsdk/mavsdk.h>
#include <mavsdk/plugins/action/action.h>
#include <mavsdk/plugins/offboard/offboard.h>
#include <mavsdk/plugins/telemetry/telemetry.h>

using namespace mavsdk;
using std::this_thread::sleep_for;
using std::chrono::milliseconds;
using std::chrono::seconds;

#define ERROR_CONSOLE_TEXT "\033[31m" // Turn text on console red
#define TELEMETRY_CONSOLE_TEXT "\033[34m" // Turn text on console blue
#define NORMAL_CONSOLE_TEXT "\033[0m" // Restore normal console colour

// Handles Action's result
inline void action_error_exit(Action::Result result, const std::string &message)
{
    if (result != Action::Result::SUCCESS) {
        std::cerr << ERROR_CONSOLE_TEXT << message << Action::result_str(result)
                  << NORMAL_CONSOLE_TEXT << std::endl;
        exit(EXIT_FAILURE);
    }
}

// Handles Offboard's result
inline void offboard_error_exit(Offboard::Result result, const std::string &message)
{
    if (result != Offboard::Result::SUCCESS) {
        std::cerr << ERROR_CONSOLE_TEXT << message << Offboard::result_str(result)
                  << NORMAL_CONSOLE_TEXT << std::endl;
        exit(EXIT_FAILURE);
    }
}

// Handles connection result
inline void connection_error_exit(ConnectionResult result, const std::string &message)
{
    if (result != ConnectionResult::SUCCESS) {
        std::cerr << ERROR_CONSOLE_TEXT << message << connection_result_str(result)
                  << NORMAL_CONSOLE_TEXT << std::endl;
        exit(EXIT_FAILURE);
    }
}

// Logs during Offboard control
inline void offboard_log(const std::string &offb_mode, const std::string msg)
{
    std::cout << "[" << offb_mode << "] " << msg << std::endl;
}

/**
 * Does Offboard control using NED co-ordinates.
 *
 * returns true if everything went well in Offboard control, exits with a log otherwise.
 */
bool offb_ctrl_ned(std::shared_ptr<mavsdk::Offboard> offboard)
{
    const std::string offb_mode = "NED";
    // Send it once before starting offboard, otherwise it will be rejected.
    offboard->set_velocity_ned({0.0f, 0.0f, 0.0f, 0.0f});

    Offboard::Result offboard_result = offboard->start();
    offboard_error_exit(offboard_result, "Offboard start failed");
    offboard_log(offb_mode, "Offboard started");

    offboard_log(offb_mode, "Turn to face East");
    offboard->set_velocity_ned({0.0f, 0.0f, 0.0f, 90.0f});
    sleep_for(seconds(1)); // Let yaw settle.

    {
        const float step_size = 0.01f;
        const float one_cycle = 2.0f * (float)M_PI;
        const unsigned steps = 2 * unsigned(one_cycle / step_size);

        offboard_log(offb_mode, "Go North and back South");
        for (unsigned i = 0; i < steps; ++i) {
            float vx = 5.0f * sinf(i * step_size);
            offboard->set_velocity_ned({vx, 0.0f, 0.0f, 90.0f});
            sleep_for(milliseconds(10));
        }
    }

    offboard_log(offb_mode, "Turn to face West");
    offboard->set_velocity_ned({0.0f, 0.0f, 0.0f, 270.0f});
    sleep_for(seconds(2));

    offboard_log(offb_mode, "Go up 2 m/s, turn to face South");
    offboard->set_velocity_ned({0.0f, 0.0f, -2.0f, 180.0f});
    sleep_for(seconds(4));

    offboard_log(offb_mode, "Go down 1 m/s, turn to face North");
    offboard->set_velocity_ned({0.0f, 0.0f, 1.0f, 0.0f});
    sleep_for(seconds(4));

    // Now, stop offboard mode.
    offboard_result = offboard->stop();
    offboard_error_exit(offboard_result, "Offboard stop failed: ");
    offboard_log(offb_mode, "Offboard stopped");

    return true;
}

/**
 * Does Offboard control using body co-ordinates.
 *
 * returns true if everything went well in Offboard control, exits with a log otherwise.
 */
bool offb_ctrl_body(std::shared_ptr<mavsdk::Offboard> offboard)
{
    const std::string offb_mode = "BODY";

    // Send it once before starting offboard, otherwise it will be rejected.
    offboard->set_velocity_body({0.0f, 0.0f, 0.0f, 0.0f});

    Offboard::Result offboard_result = offboard->start();
    offboard_error_exit(offboard_result, "Offboard start failed: ");
    offboard_log(offb_mode, "Offboard started");

    offboard_log(offb_mode, "Turn clock-wise and climb");
    offboard->set_velocity_body({0.0f, 0.0f, -1.0f, 60.0f});
    sleep_for(seconds(5));

    offboard_log(offb_mode, "Turn back anti-clockwise");
    offboard->set_velocity_body({0.0f, 0.0f, 0.0f, -60.0f});
    sleep_for(seconds(5));

    offboard_log(offb_mode, "Wait for a bit");
    offboard->set_velocity_body({0.0f, 0.0f, 0.0f, 0.0f});
    sleep_for(seconds(2));

    offboard_log(offb_mode, "Fly a circle");
    offboard->set_velocity_body({5.0f, 0.0f, 0.0f, 30.0f});
    sleep_for(seconds(15));

    offboard_log(offb_mode, "Wait for a bit");
    offboard->set_velocity_body({0.0f, 0.0f, 0.0f, 0.0f});
    sleep_for(seconds(5));

    offboard_log(offb_mode, "Fly a circle sideways");
    offboard->set_velocity_body({0.0f, -5.0f, 0.0f, 30.0f});
    sleep_for(seconds(15));

    offboard_log(offb_mode, "Wait for a bit");
    offboard->set_velocity_body({0.0f, 0.0f, 0.0f, 0.0f});
    sleep_for(seconds(8));

    offboard_result = offboard->stop();
    offboard_error_exit(offboard_result, "Offboard stop failed: ");
    offboard_log(offb_mode, "Offboard stopped");

    return true;
}

/**
 * Does Offboard control using attitude commands.
 *
 * returns true if everything went well in Offboard control, exits with a log otherwise.
 */
bool offb_ctrl_attitude(std::shared_ptr<mavsdk::Offboard> offboard)
{
    const std::string offb_mode = "ATTITUDE";

    // Send it once before starting offboard, otherwise it will be rejected.
    offboard->set_attitude({30.0f, 0.0f, 0.0f, 0.6f});

    Offboard::Result offboard_result = offboard->start();
    offboard_error_exit(offboard_result, "Offboard start failed");
    offboard_log(offb_mode, "Offboard started");

    offboard_log(offb_mode, "ROLL 30");
    offboard->set_attitude({30.0f, 0.0f, 0.0f, 0.6f});
    sleep_for(seconds(2)); // rolling

    offboard_log(offb_mode, "ROLL -30");
    offboard->set_attitude({-30.0f, 0.0f, 0.0f, 0.6f});
    sleep_for(seconds(2)); // Let yaw settle.

    offboard_log(offb_mode, "ROLL 0");
    offboard->set_attitude({0.0f, 0.0f, 0.0f, 0.6f});
    sleep_for(seconds(2)); // Let yaw settle.

    // Now, stop offboard mode.
    offboard_result = offboard->stop();
    offboard_error_exit(offboard_result, "Offboard stop failed: ");
    offboard_log(offb_mode, "Offboard stopped");

    return true;
}

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
    Mavsdk dc;
    std::string connection_url;
    ConnectionResult connection_result;

    if (argc == 2) {
        connection_url = argv[1];
        connection_result = dc.add_any_connection(connection_url);
    } else {
        usage(argv[0]);
        return 1;
    }

    if (connection_result != ConnectionResult::SUCCESS) {
        std::cout << ERROR_CONSOLE_TEXT
                  << "Connection failed: " << connection_result_str(connection_result)
                  << NORMAL_CONSOLE_TEXT << std::endl;
        return 1;
    }

    // Wait for the system to connect via heartbeat
    while (!dc.is_connected()) {
        std::cout << "Wait for system to connect via heartbeat" << std::endl;
        sleep_for(seconds(1));
    }

    // System got discovered.
    System &system = dc.system();
    auto action = std::make_shared<Action>(system);
    auto offboard = std::make_shared<Offboard>(system);
    auto telemetry = std::make_shared<Telemetry>(system);

    while (!telemetry->health_all_ok()) {
        std::cout << "Waiting for system to be ready" << std::endl;
        sleep_for(seconds(1));
    }
    std::cout << "System is ready" << std::endl;

    Action::Result arm_result = action->arm();
    action_error_exit(arm_result, "Arming failed");
    std::cout << "Armed" << std::endl;

    Action::Result takeoff_result = action->takeoff();
    action_error_exit(takeoff_result, "Takeoff failed");
    std::cout << "In Air..." << std::endl;
    sleep_for(seconds(5));

    //  using attitude control
    bool ret = offb_ctrl_attitude(offboard);
    if (ret == false) {
        return EXIT_FAILURE;
    }

    //  using local NED co-ordinates
    ret = offb_ctrl_ned(offboard);
    if (ret == false) {
        return EXIT_FAILURE;
    }

    //  using body co-ordinates
    ret = offb_ctrl_body(offboard);
    if (ret == false) {
        return EXIT_FAILURE;
    }

    const Action::Result land_result = action->land();
    action_error_exit(land_result, "Landing failed");

    // Check if vehicle is still in air
    while (telemetry->in_air()) {
        std::cout << "Vehicle is landing..." << std::endl;
        sleep_for(seconds(1));
    }
    std::cout << "Landed!" << std::endl;

    // We are relying on auto-disarming but let's keep watching the telemetry for a bit longer.
    sleep_for(seconds(3));
    std::cout << "Finished..." << std::endl;

    return EXIT_SUCCESS;
}
```
