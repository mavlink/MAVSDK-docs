# Example: Fly QGroundControl Plan Mission

The [Fly QGroundControl Plan Mission](https://github.com/Dronecode/DronecodeSDK/tree/{{ book.github_branch }}/example/fly_qgc_mission) example shows how to import a *QGroundControl* mission plan, upload it to a vehicle, run the mission, and then command Return mode ("RTL").

![Fly Mission QGC Screenshot - From Plan](../../assets/examples/fly_qgc_mission/fly_qgc_plan_mission_example_qgc.jpg)


## Running the Example {#run_example}

The example is built and run in the normal way ([as described here](../examples/README.md#trying_the_examples)). 

> **Tip** By default the example will load a sample plan from the plugin unit test: [/plugins/mission/qgroundcontrol_sample.plan](https://github.com/Dronecode/DronecodeSDK/blob/{{ book.github_branch }}/plugins/mission/qgroundcontrol_sample.plan). 
  Alternatively you can specify the plan to load when you start the example:
  ```
  ./fly_qgc_mission <path of QGC Mission plan>
  ```

The example terminal output should be similar to that shown below:

> **Note** This is from a debug build of the SDK. 
  A release build will omit the "Debug" messages.

```
$ ./fly_qgc_mission udp://:14540
```
```
Connection URL: udp://:14540
Importing mission from mission plan: ../../../plugins/mission/qgroundcontrol_sample.plan
Waiting to discover system...
[09:52:04|Info ] New device on: 127.0.0.1:14557 (udp_connection.cpp:208)
[09:52:04|Debug] New: System ID: 1 Comp ID: 1 (dronecode_sdk_impl.cpp:292)
[09:52:04|Debug] Component Autopilot added. (system_impl.cpp:339)
[09:52:04|Debug] MAVLink: info: [logger] file: rootfs/fs/microsd/log/2018-07-09/1 (system_impl.cpp:277)
[09:52:04|Debug] Found 1 component(s). (system_impl.cpp:466)
[09:52:04|Debug] Discovered 4294967298 (system_impl.cpp:468)
Discovered system with UUID: 4294967298
Waiting for system to be ready
System ready
Found 8 mission items in the given QGC plan.
Uploading mission...
[09:52:05|Debug] Send mission item 0 (mission_impl.cpp:898)
[09:52:05|Debug] Send mission item 1 (mission_impl.cpp:898)
...
[09:52:05|Debug] Send mission item 13 (mission_impl.cpp:898)
[09:52:05|Debug] Send mission item 14 (mission_impl.cpp:898)
[09:52:05|Info ] Mission accepted (mission_impl.cpp:163)
Mission uploaded.
Arming...
[09:52:05|Debug] MAVLink: info: ARMED by arm/disarm component command (system_impl.cpp:277)
Armed.
Starting mission.
Started mission.
[09:52:06|Debug] MAVLink: info: Executing Mission (system_impl.cpp:277)
[09:52:06|Debug] MAVLink: info: Takeoff to 10.0 meters above home. (system_impl.cpp:277)
[09:52:06|Debug] MAVLink: info: Takeoff detected (system_impl.cpp:277)
Mission status update: Mission status update: 1 / 8
1 / 8
Mission status update: Mission status update: 11 / 8 / 8

Mission status update: 1 / 8
Mission status update: 2 / 8
...
Mission status update: 2 / 8
Mission status update: 3 / 8
...
Mission status update: 3 / 8
Mission status update: 4 / 8
Mission status update: 4 / 8
Mission status update: 4 / 8
Mission status update: 5 / 8
...
Mission status update: 5 / 8
[09:52:58|Debug] MAVLink: critical: MANUAL CONTROL LOST (at t=75098ms) (system_impl.cpp:277)
[09:52:58|Debug] MAVLink: info: MANUAL CONTROL REGAINED after 519ms (system_impl.cpp:277)
Mission status update: 5 / 8
Mission status update: 6 / 8
...
Mission status update: 6 / 8
Mission status update: 7 / 8
..
Mission status update: 7 / 8
[09:53:06|Debug] MAVLink: info: Mission finished, loitering. (system_impl.cpp:277)
Mission status update: 8 / 8
Commanding RTL...
Commanded RTL.
```

## How it works

The example application performs the following operations:
1. Imports QGC mission items from **.plan** file.
1. Uploads mission items to vehicle.
1. Sets up mission progress monitoring.
1. Starts the mission from the first mission item.
1. Commands the *Return*/RTL action once the mission completes.

The specific code for importing missions is discussed in the guide: [Missions > Import a Mission from a QGC Plan](../guide/missions.md#import_qgc_plan).

## Source code {#source_code}

> **Tip** The full source code for the example [can be found on Github here](https://github.com/Dronecode/DronecodeSDK/tree/{{ book.github_branch }}/example/fly_qgc_mission).


[CMakeLists.txt](https://github.com/Dronecode/DronecodeSDK/blob/{{ book.github_branch }}/example/fly_qgc_mission/CMakeLists.txt)

```make
cmake_minimum_required(VERSION 2.8.12)

project(fly_qgc_mission)

if(NOT MSVC)
    add_definitions("-std=c++11 -Wall -Wextra -Werror")
    # Line below required if /usr/local/include is not in your default includes
    #include_directories(/usr/local/include)
    # Line below required if /usr/local/lib is not in your default linker path
    #link_directories(/usr/local/lib)
else()
    add_definitions("-std=c++11 -WX -W2")
    include_directories(${CMAKE_SOURCE_DIR}/../../install/include)
    link_directories(${CMAKE_SOURCE_DIR}/../../install/lib)
endif()

add_executable(fly_qgc_mission
    fly_qgc_mission.cpp
)

target_link_libraries(fly_qgc_mission
    dronecode_sdk
    dronecode_sdk_action
    dronecode_sdk_mission
    dronecode_sdk_telemetry
)
```

[fly_qgc_mission.cpp](https://github.com/Dronecode/DronecodeSDK/blob/{{ book.github_branch }}/example/fly_qgc_mission/fly_qgc_mission.cpp)

```cpp
/**
 * @file fly_qgc_mission.cpp
 *
 * @brief Demonstrates how to import mission items from QGroundControl plan,
 * and fly them using the Dronecode SDK.
 *
 * Steps to run this example:
 * 1. (a) Create a Mission in QGroundControl and save them to a file (.plan) (OR)
 *    (b) Use a pre-created sample mission plan in "plugins/mission/qgroundcontrol_sample.plan".
 *    Click
 * [here](https://user-images.githubusercontent.com/26615772/31763673-972c5bb6-b4dc-11e7-8ff0-f8b39b6b88c3.png)
 * to see what sample mission plan in QGroundControl looks like.
 * 2. Run the example by passing path of the QGC mission plan as argument (By default, sample
 * mission plan is imported).
 *
 * Example description:
 * 1. Imports QGC mission items from .plan file.
 * 2. Uploads mission items to vehicle.
 * 3. Starts mission from first mission item.
 * 4. Commands RTL once QGC Mission is accomplished.
 *
 * @author Shakthi Prashanth M <shakthi.prashanth.m@intel.com>,
 *         Julian Oes <julian@oes.ch>
 * @date 2018-02-04
 */

#include <dronecode_sdk/action.h>
#include <dronecode_sdk/dronecode_sdk.h>
#include <dronecode_sdk/mission.h>
#include <dronecode_sdk/telemetry.h>
#include <functional>
#include <future>
#include <iostream>
#include <memory>

#define ERROR_CONSOLE_TEXT "\033[31m" // Turn text on console red
#define TELEMETRY_CONSOLE_TEXT "\033[34m" // Turn text on console blue
#define NORMAL_CONSOLE_TEXT "\033[0m" // Restore normal console colour

using namespace dronecode_sdk;
using namespace std::chrono; // for seconds(), milliseconds()
using namespace std::this_thread; // for sleep_for()

// Handles Action's result
inline void handle_action_err_exit(Action::Result result, const std::string &message);
// Handles Mission's result
inline void handle_mission_err_exit(Mission::Result result, const std::string &message);
// Handles Connection result
inline void handle_connection_err_exit(ConnectionResult result, const std::string &message);

void usage(std::string bin_name)
{
    std::cout << NORMAL_CONSOLE_TEXT << "Usage : " << bin_name
              << " <connection_url> [path of QGC Mission plan]" << std::endl
              << "Connection URL format should be :" << std::endl
              << " For TCP : tcp://[server_host][:server_port]" << std::endl
              << " For UDP : udp://[bind_host][:bind_port]" << std::endl
              << " For Serial : serial:///path/to/serial/dev[:baudrate]" << std::endl
              << "For example, to connect to the simulator use URL: udp://:14540" << std::endl;
}

int main(int argc, char **argv)
{
    DronecodeSDK dc;
    std::string connection_url;
    ConnectionResult connection_result;

    // Locate path of QGC Sample plan
    std::string qgc_plan = "../../../plugins/mission/qgroundcontrol_sample.plan";

    if (argc != 2 && argc != 3) {
        usage(argv[0]);
        return 1;
    }

    connection_url = argv[1];
    if (argc == 3) {
        qgc_plan = argv[2];
    }

    std::cout << "Connection URL: " << connection_url << std::endl;
    std::cout << "Importing mission from mission plan: " << qgc_plan << std::endl;

    {
        auto prom = std::make_shared<std::promise<void>>();
        auto future_result = prom->get_future();

        std::cout << "Waiting to discover system..." << std::endl;
        dc.register_on_discover([prom](uint64_t uuid) {
            std::cout << "Discovered system with UUID: " << uuid << std::endl;
            prom->set_value();
        });

        connection_result = dc.add_any_connection(connection_url);
        handle_connection_err_exit(connection_result, "Connection failed: ");

        future_result.get();
    }

    dc.register_on_timeout([](uint64_t uuid) {
        std::cout << "System with UUID timed out: " << uuid << std::endl;
        std::cout << "Exiting." << std::endl;
        exit(0);
    });

    // We don't need to specify the UUID if it's only one system anyway.
    // If there were multiple, we could specify it with:
    // dc.system(uint64_t uuid);
    System &system = dc.system();
    auto action = std::make_shared<Action>(system);
    auto mission = std::make_shared<Mission>(system);
    auto telemetry = std::make_shared<Telemetry>(system);

    while (!telemetry->health_all_ok()) {
        std::cout << "Waiting for system to be ready" << std::endl;
        sleep_for(seconds(1));
    }

    std::cout << "System ready" << std::endl;

    // Import Mission items from QGC plan
    Mission::mission_items_t mission_items;
    Mission::Result import_res = Mission::import_qgroundcontrol_mission(mission_items, qgc_plan);
    handle_mission_err_exit(import_res, "Failed to import mission items: ");

    if (mission_items.size() == 0) {
        std::cerr << "No missions! Exiting..." << std::endl;
        exit(EXIT_FAILURE);
    }
    std::cout << "Found " << mission_items.size() << " mission items in the given QGC plan."
              << std::endl;

    {
        std::cout << "Uploading mission..." << std::endl;
        // Wrap the asynchronous upload_mission function using std::future.
        auto prom = std::make_shared<std::promise<Mission::Result>>();
        auto future_result = prom->get_future();
        mission->upload_mission_async(mission_items,
                                      [prom](Mission::Result result) { prom->set_value(result); });

        const Mission::Result result = future_result.get();
        handle_mission_err_exit(result, "Mission upload failed: ");
        std::cout << "Mission uploaded." << std::endl;
    }

    std::cout << "Arming..." << std::endl;
    const Action::Result arm_result = action->arm();
    handle_action_err_exit(arm_result, "Arm failed: ");
    std::cout << "Armed." << std::endl;

    // Before starting the mission subscribe to the mission progress.
    mission->subscribe_progress([](int current, int total) {
        std::cout << "Mission status update: " << current << " / " << total << std::endl;
    });

    {
        std::cout << "Starting mission." << std::endl;
        auto prom = std::make_shared<std::promise<Mission::Result>>();
        auto future_result = prom->get_future();
        mission->start_mission_async([prom](Mission::Result result) {
            prom->set_value(result);
            std::cout << "Started mission." << std::endl;
        });

        const Mission::Result result = future_result.get();
        handle_mission_err_exit(result, "Mission start failed: ");
    }

    while (!mission->mission_finished()) {
        sleep_for(seconds(1));
    }

    // Wait for some time.
    sleep_for(seconds(5));

    {
        // Mission complete. Command RTL to go home.
        std::cout << "Commanding RTL..." << std::endl;
        const Action::Result result = action->return_to_launch();
        if (result != Action::Result::SUCCESS) {
            std::cout << "Failed to command RTL (" << Action::result_str(result) << ")"
                      << std::endl;
        } else {
            std::cout << "Commanded RTL." << std::endl;
        }
    }

    return 0;
}

inline void handle_action_err_exit(Action::Result result, const std::string &message)
{
    if (result != Action::Result::SUCCESS) {
        std::cerr << ERROR_CONSOLE_TEXT << message << Action::result_str(result)
                  << NORMAL_CONSOLE_TEXT << std::endl;
        exit(EXIT_FAILURE);
    }
}

inline void handle_mission_err_exit(Mission::Result result, const std::string &message)
{
    if (result != Mission::Result::SUCCESS) {
        std::cerr << ERROR_CONSOLE_TEXT << message << Mission::result_str(result)
                  << NORMAL_CONSOLE_TEXT << std::endl;
        exit(EXIT_FAILURE);
    }
}

// Handles connection result
inline void handle_connection_err_exit(ConnectionResult result, const std::string &message)
{
    if (result != ConnectionResult::SUCCESS) {
        std::cerr << ERROR_CONSOLE_TEXT << message << connection_result_str(result)
                  << NORMAL_CONSOLE_TEXT << std::endl;
        exit(EXIT_FAILURE);
    }
}
```
