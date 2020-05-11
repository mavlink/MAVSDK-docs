# Example: Follow Me Mode

This example demonstrates how to use the [Follow Me](../guide/follow_me.md) plugin. 
It shows how to send the drone both the current position of the target (`FollowMe::TargetLocation`) and the relative position at which it should follow (`FollowMe::Config`).

![Follow Me QGC Screenshot](../../assets/examples/follow_me/follow_me_example_qgc.jpg)

> **Note** A real application using this API will get the position information from the underlying operating system. 
  The example uses a fake position source (`FakeLocationProvider`) to enable it to be run on computers that do not have position information. 
  The `FakeLocationProvider` emulates the typical usage of common positioning APIs used in Android, Linux and iPhone.


## Running the Example {#run_example}

Special notes for this example: 

* Before running this example you will need to install Boost libraries. For Linux this is done as shown below:
  ```sh
  sudo apt-get install libboost-all-dev
  ```
* To use *QGroundControl* with this example you **must** ensure that *GSC Position Streaming* is disabled (otherwise QGC and the SDK will both send position updates and they will conflict). 
  To do this use the latest *QGC Daily Build* and ensure that the **[Application Setting > General](https://docs.qgroundcontrol.com/en/SettingsView/General.html) > Miscellaneous > Stream GCS Position** is set to *Never*.

Otherwise the example is built and run in the normal way ([as described here](../examples/README.md#trying_the_examples)). 

The example terminal output should be similar to that shown below:

> **Note** This is from a debug build of the SDK. 
  A release build will omit the "Debug" messages.

``` 
$ ./follow_me udp://:14540
```
```
[01:55:59|Info ] DronecodeSDK version: 0.2.8 (dronecode_sdk_impl.cpp:25)
Wait for system to connect via heartbeat
[01:55:59|Info ] New device on: 127.0.0.1:14580 (udp_connection.cpp:200)
[01:55:59|Debug] New: System ID: 1 Comp ID: 1 (dronecode_sdk_impl.cpp:286)
[01:55:59|Debug] Component Autopilot added. (system_impl.cpp:335)
[01:56:00|Debug] Found 1 component(s). (system_impl.cpp:462)
[01:56:00|Debug] Discovered 4294967298 (system_impl.cpp:464)
Waiting for system to be ready
...
Waiting for system to be ready
System is ready
Armed
[01:56:07|Debug] MAVLink: info: ARMED by arm/disarm component command (system_impl.cpp:273)
In Air...
[01:56:07|Debug] MAVLink: info: Using minimum takeoff altitude: 2.50 m (system_impl.cpp:273)
[01:56:07|Debug] MAVLink: info: Takeoff detected (system_impl.cpp:273)
[01:56:07|Debug] MAVLink: info: Using minimum takeoff altitude: 2.50 m (system_impl.cpp:273)
[FlightMode: Takeoff] Vehicle is at: nan, nan degrees.
[FlightMode: Takeoff] Vehicle is at: nan, nan degrees.
[FlightMode: Hold] Vehicle is at: nan, nan degrees.
[01:56:12|Debug] Waiting for the system confirmation of the new configuration.. (follow_me_impl.cpp:81)
[FlightMode: FollowMe] Vehicle is at: nan, nan degrees.
[FlightMode: FollowMe] Vehicle is at: 47.3977, 8.54559 degrees.
[FlightMode: FollowMe] Vehicle is at: 47.3977, 8.54559 degrees.
[FlightMode: FollowMe] Vehicle is at: 47.3976, 8.54559 degrees.
[FlightMode: FollowMe] Vehicle is at: 47.3976, 8.54559 degrees.
[FlightMode: FollowMe] Vehicle is at: 47.3976, 8.54559 degrees.
[FlightMode: FollowMe] Vehicle is at: 47.3975, 8.54559 degrees.
[FlightMode: FollowMe] Vehicle is at: 47.3975, 8.54559 degrees.
[FlightMode: FollowMe] Vehicle is at: 47.3974, 8.54559 degrees.
[FlightMode: FollowMe] Vehicle is at: 47.3974, 8.54559 degrees.
[FlightMode: FollowMe] Vehicle is at: 47.3974, 8.54563 degrees.
[FlightMode: FollowMe] Vehicle is at: 47.3974, 8.54567 degrees.
[FlightMode: FollowMe] Vehicle is at: 47.3974, 8.5457 degrees.
[FlightMode: FollowMe] Vehicle is at: 47.3974, 8.54574 degrees.
[FlightMode: FollowMe] Vehicle is at: 47.3974, 8.54577 degrees.
[FlightMode: FollowMe] Vehicle is at: 47.3974, 8.54581 degrees.
[FlightMode: FollowMe] Vehicle is at: 47.3974, 8.54588 degrees.
[FlightMode: FollowMe] Vehicle is at: 47.3974, 8.54592 degrees.
[FlightMode: FollowMe] Vehicle is at: 47.3974, 8.54595 degrees.
[FlightMode: FollowMe] Vehicle is at: 47.3974, 8.54595 degrees.
[FlightMode: FollowMe] Vehicle is at: 47.3975, 8.54595 degrees.
[FlightMode: FollowMe] Vehicle is at: 47.3975, 8.54595 degrees.
[FlightMode: FollowMe] Vehicle is at: 47.3975, 8.54595 degrees.
[FlightMode: FollowMe] Vehicle is at: 47.3976, 8.54595 degrees.
[FlightMode: FollowMe] Vehicle is at: 47.3976, 8.54595 degrees.
[FlightMode: FollowMe] Vehicle is at: 47.3977, 8.54595 degrees.
[FlightMode: FollowMe] Vehicle is at: 47.3977, 8.54595 degrees.
[FlightMode: FollowMe] Vehicle is at: 47.3977, 8.54595 degrees.
[FlightMode: FollowMe] Vehicle is at: 47.3977, 8.54592 degrees.
[FlightMode: FollowMe] Vehicle is at: 47.3977, 8.54588 degrees.
[FlightMode: FollowMe] Vehicle is at: 47.3977, 8.54581 degrees.
[FlightMode: FollowMe] Vehicle is at: 47.3977, 8.54577 degrees.
[FlightMode: FollowMe] Vehicle is at: 47.3977, 8.54574 degrees.
[FlightMode: FollowMe] Vehicle is at: 47.3977, 8.5457 degrees.
[FlightMode: FollowMe] Vehicle is at: 47.3977, 8.54567 degrees.
[FlightMode: FollowMe] Vehicle is at: 47.3977, 8.54563 degrees.
[FlightMode: FollowMe] Vehicle is at: 47.3977, 8.54563 degrees.
waiting until landed
[01:56:53|Debug] MAVLink: info: Landing at current position (system_impl.cpp:273)
waiting until landed
...
waiting until landed
[01:57:12|Debug] MAVLink: info: Landing detected (system_impl.cpp:273)
[01:57:12|Debug] MAVLink: info: DISARMED by auto disarm on land (system_impl.cpp:273)
Landed...
```

## How it works

The example registers with `FakeLocationProvider` for location updates. 
These are passed to the Follow Me plugin, which in turn sends them to the vehicle. 

The operation of the "SDK-specific" part of this code is discussed in the guide: [Follow Me](../guide/follow_me.md).


## Source code {#source_code}

> **Tip** The full source code for the example [can be found on Github here](https://github.com/mavlink/MAVSDK/tree/{{ book.github_branch }}/examples/follow_me).


[CMakeLists.txt](https://github.com/mavlink/MAVSDK/blob/{{ book.github_branch }}/examples/follow_me/CMakeLists.txt)

```make
cmake_minimum_required(VERSION 2.8.12)

project(follow_me)

find_package(Threads REQUIRED)

if(NOT MSVC)
    add_definitions("-std=c++11 -Wall -Wextra -Werror")
else()
    add_definitions("-std=c++11 -WX -W2")
endif()

find_package(MAVSDK REQUIRED)

add_executable(follow_me
    follow_me.cpp
    fake_location_provider.cpp
)

target_link_libraries(follow_me
    MAVSDK::mavsdk_action
    MAVSDK::mavsdk_follow_me
    MAVSDK::mavsdk_telemetry
    MAVSDK::mavsdk
    ${CMAKE_THREAD_LIBS_INIT}
)
```

[follow_me.cpp](https://github.com/mavlink/MAVSDK/blob/{{ book.github_branch }}/examples/follow_me/follow_me.cpp)

```cpp
/**
 * @file follow_me.cpp
 *
 * @brief Example that demonstrates the usage of Follow Me plugin.
 * The example registers with FakeLocationProvider for location updates
 * and sends them to the Follow Me plugin which are sent to drone. You can observe
 * drone following you. We print last location of the drone in flight mode callback.
 *
 * @author Shakthi Prashanth <shakthi.prashanth.m@intel.com>
 * @date 2018-01-03
 */

#include <chrono>
#include <mavsdk/mavsdk.h>
#include <mavsdk/plugins/action/action.h>
#include <mavsdk/plugins/follow_me/follow_me.h>
#include <mavsdk/plugins/telemetry/telemetry.h>
#include <iostream>
#include <memory>
#include <thread>

#include "fake_location_provider.h"

using namespace mavsdk;
using namespace std::placeholders; // for `_1`
using namespace std::chrono; // for seconds(), milliseconds(), etc
using namespace std::this_thread; // for sleep_for()

// For coloring output
#define ERROR_CONSOLE_TEXT "\033[31m" // Turn text on console red
#define TELEMETRY_CONSOLE_TEXT "\033[34m" // Turn text on console blue
#define NORMAL_CONSOLE_TEXT "\033[0m" // Restore normal console colour

inline void action_error_exit(Action::Result result, const std::string& message);
inline void follow_me_error_exit(FollowMe::Result result, const std::string& message);
inline void connection_error_exit(ConnectionResult result, const std::string& message);

void usage(std::string bin_name)
{
    std::cout << NORMAL_CONSOLE_TEXT << "Usage : " << bin_name << " <connection_url>" << std::endl
              << "Connection URL format should be :" << std::endl
              << " For TCP : tcp://[server_host][:server_port]" << std::endl
              << " For UDP : udp://[bind_host][:bind_port]" << std::endl
              << " For Serial : serial:///path/to/serial/dev[:baudrate]" << std::endl
              << "For example, to connect to the simulator use URL: udp://:14540" << std::endl;
}

int main(int argc, char** argv)
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

    if (connection_result != ConnectionResult::Success) {
        std::cout << ERROR_CONSOLE_TEXT << "Connection failed: " << connection_result
                  << NORMAL_CONSOLE_TEXT << std::endl;
        return 1;
    }

    // Wait for the system to connect via heartbeat
    while (!dc.is_connected()) {
        std::cout << "Wait for system to connect via heartbeat" << std::endl;
        sleep_for(seconds(1));
    }

    // System got discovered.
    System& system = dc.system();
    auto action = std::make_shared<Action>(system);
    auto follow_me = std::make_shared<FollowMe>(system);
    auto telemetry = std::make_shared<Telemetry>(system);

    while (!telemetry->health_all_ok()) {
        std::cout << "Waiting for system to be ready" << std::endl;
        sleep_for(seconds(1));
    }
    std::cout << "System is ready" << std::endl;

    // Arm
    Action::Result arm_result = action->arm();
    action_error_exit(arm_result, "Arming failed");
    std::cout << "Armed" << std::endl;

    // Subscribe to receive updates on flight mode. You can find out whether FollowMe is active.
    telemetry->subscribe_flight_mode(std::bind(
        [&](Telemetry::FlightMode flight_mode) {
            const FollowMe::TargetLocation last_location = follow_me->get_last_location();
            std::cout << "[FlightMode: " << flight_mode
                      << "] Vehicle is at: " << last_location.latitude_deg << ", "
                      << last_location.longitude_deg << " degrees." << std::endl;
        },
        std::placeholders::_1));

    // Takeoff
    Action::Result takeoff_result = action->takeoff();
    action_error_exit(takeoff_result, "Takeoff failed");
    std::cout << "In Air..." << std::endl;
    sleep_for(seconds(5)); // Wait for drone to reach takeoff altitude

    // Configure Min height of the drone to be "20 meters" above home & Follow direction as "Front
    // right".
    FollowMe::Config config;
    config.min_height_m = 10.0;
    config.follow_direction = FollowMe::Config::FollowDirection::Behind;
    FollowMe::Result follow_me_result = follow_me->set_config(config);

    // Start Follow Me
    follow_me_result = follow_me->start();
    follow_me_error_exit(follow_me_result, "Failed to start FollowMe mode");

    FakeLocationProvider location_provider;
    // Register for platform-specific Location provider. We're using FakeLocationProvider for the
    // example.
    location_provider.request_location_updates([&follow_me](double lat, double lon) {
        FollowMe::TargetLocation target_location{};
        target_location.latitude_deg = lat;
        target_location.longitude_deg = lon;
        follow_me->set_target_location(target_location);
    });

    while (location_provider.is_running()) {
        sleep_for(seconds(1));
    }

    // Stop Follow Me
    follow_me_result = follow_me->stop();
    follow_me_error_exit(follow_me_result, "Failed to stop FollowMe mode");

    // Stop flight mode updates.
    telemetry->subscribe_flight_mode(nullptr);

    // Land
    const Action::Result land_result = action->land();
    action_error_exit(land_result, "Landing failed");
    while (telemetry->in_air()) {
        std::cout << "waiting until landed" << std::endl;
        sleep_for(seconds(1));
    }
    std::cout << "Landed..." << std::endl;
    return 0;
}

// Handles Action's result
inline void action_error_exit(Action::Result result, const std::string& message)
{
    if (result != Action::Result::Success) {
        std::cerr << ERROR_CONSOLE_TEXT << message << result << NORMAL_CONSOLE_TEXT << std::endl;
        exit(EXIT_FAILURE);
    }
}
// Handles FollowMe's result
inline void follow_me_error_exit(FollowMe::Result result, const std::string& message)
{
    if (result != FollowMe::Result::Success) {
        std::cerr << ERROR_CONSOLE_TEXT << message << result << NORMAL_CONSOLE_TEXT << std::endl;
        exit(EXIT_FAILURE);
    }
}
// Handles connection result
inline void connection_error_exit(ConnectionResult result, const std::string& message)
{
    if (result != ConnectionResult::Success) {
        std::cerr << ERROR_CONSOLE_TEXT << message << result << NORMAL_CONSOLE_TEXT << std::endl;
        exit(EXIT_FAILURE);
    }
}
```

[fake_location_provider.h](https://github.com/mavlink/MAVSDK/blob/{{ book.github_branch }}/examples/follow_me/fake_location_provider.h)

```cpp
#pragma once

#include <functional>
#include <atomic>
#include <thread>

/**
 * @brief The FakeLocationProvider class
 * This class provides periodic reports on the fake location of the system.
 */
class FakeLocationProvider {
public:
    typedef std::function<void(double lat, double lon)> location_callback_t;

    FakeLocationProvider();

    ~FakeLocationProvider();

    void request_location_updates(location_callback_t callback);
    bool is_running() { return !should_exit_; };

private:
    void start();
    void stop();
    void compute_locations();

    std::thread* thread_{nullptr};
    std::atomic<bool> should_exit_{false};

    location_callback_t location_callback_ = nullptr;
    double latitude_deg_ = 47.3977419;
    double longitude_deg_ = 8.5455938;
    size_t count_ = 0u;

    static const size_t MAX_LOCATIONS;
    static const double LATITUDE_DEG_PER_METER;
    static const double LONGITUDE_DEG_PER_METER;
};
```

[fake_location_provider.cpp](https://github.com/mavlink/MAVSDK/blob/{{ book.github_branch }}/examples/follow_me/fake_location_provider.cpp)

```cpp
#include "fake_location_provider.h"
#include <chrono> // for seonds()
#include <thread> // for sleep_for()

using std::this_thread::sleep_for;
using std::chrono::seconds;

FakeLocationProvider::FakeLocationProvider() {}

FakeLocationProvider::~FakeLocationProvider()
{
    stop();
}

void FakeLocationProvider::request_location_updates(location_callback_t callback)
{
    location_callback_ = callback;
    stop();
    start();
}

void FakeLocationProvider::start()
{
    should_exit_ = false;
    thread_ = new std::thread(&FakeLocationProvider::compute_locations, this);
}

void FakeLocationProvider::stop()
{
    should_exit_ = true;

    if (thread_) {
        thread_->join();
        delete thread_;
        thread_ = nullptr;
    }
}

// Rudimentary location provider to draw a square.
void FakeLocationProvider::compute_locations()
{
    while (!should_exit_) {
        if (count_ < 10) {
            location_callback_(latitude_deg_, longitude_deg_);
            latitude_deg_ -= LATITUDE_DEG_PER_METER * 4;
        } else if (count_ < 20) {
            location_callback_(latitude_deg_, longitude_deg_);
            longitude_deg_ += LONGITUDE_DEG_PER_METER * 4;
        } else if (count_ < 30) {
            location_callback_(latitude_deg_, longitude_deg_);
            latitude_deg_ += LATITUDE_DEG_PER_METER * 4;
        } else if (count_ < 40) {
            location_callback_(latitude_deg_, longitude_deg_);
            longitude_deg_ -= LONGITUDE_DEG_PER_METER * 4;
        } else {
            // We're done.
            should_exit_ = true;
        }
        sleep_for(seconds(1));
        ++count_;
    }
}

const double FakeLocationProvider::LATITUDE_DEG_PER_METER = 0.000009044;
const double FakeLocationProvider::LONGITUDE_DEG_PER_METER = 0.000008985;
```
