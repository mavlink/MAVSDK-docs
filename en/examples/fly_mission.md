# Example: Fly Mission

The [Fly Mission](https://github.com/dronecore/DroneCore/tree/{{ book.github_branch }}/example/fly_mission) example shows how to create, upload, and run, pause, and restart missions using DroneCore.

![Fly Mission QGC Screenshot](../../assets/examples/fly_mission/fly_mission_example_qgc.jpg)


## Running the Example {#run_example}

The example is built and run in the normal way ([as described here](../examples/README.md#trying_the_examples)). 

The example terminal output should be similar to that shown below:

> **Note** This is from a debug build of DroneCore. A release build will omit the "Debug" messages.

```
$ ./fly_mission udp://:14540
```
```
Waiting to discover system...
[01:04:37|Info ] New device on: 127.0.0.1:14557 (udp_connection.cpp:208)
[01:04:37|Debug] New: System ID: 1 Comp ID: 1 (dronecore_impl.cpp:286)
[01:04:37|Debug] Component Autopilot added. (mavlink_system.cpp:349)
[01:04:37|Debug] Found 1 component(s). (mavlink_system.cpp:481)
[01:04:37|Debug] Discovered 4294967298 (mavlink_system.cpp:483)
Discovered system with UUID: 4294967298
Waiting for system to be ready
System ready
Creating and uploading mission
Uploading mission...
[01:04:38|Debug] Send mission item 0 (mission_impl.cpp:904)
[01:04:38|Debug] Send mission item 1 (mission_impl.cpp:904)
[01:04:38|Debug] Send mission item 2 (mission_impl.cpp:904)
...
[01:04:38|Debug] Send mission item 21 (mission_impl.cpp:904)
[01:04:38|Debug] Send mission item 22 (mission_impl.cpp:904)
[01:04:38|Info ] Mission accepted (mission_impl.cpp:162)
Mission uploaded.
Arming...
Armed.
Starting mission.
[01:04:38|Debug] MAVLink: info: ARMED by arm/disarm component command (mavlink_system.cpp:286)
Started mission.
[01:04:38|Debug] MAVLink: info: [logger] file: rootfs/fs/microsd/log/2018-05-23/0 (mavlink_system.cpp:286)
[01:04:38|Debug] MAVLink: info: Executing mission. (mavlink_system.cpp:286)
[01:04:38|Debug] MAVLink: info: Takeoff to 10.0 meters above home. (mavlink_system.cpp:286)
[01:04:38|Debug] MAVLink: info: Takeoff detected (mavlink_system.cpp:286)
Mission status update: 0 / 6
...
Mission status update: 0 / 6
Mission status update: 1 / 6
...
Mission status update: 1 / 6
Mission status update: 2 / 6
Pausing mission...
Mission paused.
Resuming mission...
Resumed mission.
Mission status update: 2 / 6
...
Mission status update: 2 / 6
Mission status update: 3 / 6
...
Mission status update: 3 / 6
Mission status update: 4 / 6
...
Mission status update: 4 / 6
Mission status update: 5 / 6
...
Mission status update: 5 / 6
[01:05:40|Debug] MAVLink: info: Mission finished, loitering. (mavlink_system.cpp:286)
Mission status update: 6 / 6
Commanding RTL...
Commanded RTL.
[01:05:40|Debug] MAVLink: info: RTL: climb to 518 m (30 m above home) (mavlink_system.cpp:286)
[01:05:48|Debug] MAVLink: info: RTL: return at 518 m (30 m above home) (mavlink_system.cpp:286)
[01:05:55|Debug] MAVLink: info: RTL: descend to 493 m (5 m above home) (mavlink_system.cpp:286)
[01:06:13|Debug] MAVLink: info: RTL: loiter 5.0s (mavlink_system.cpp:286)
[01:06:18|Debug] MAVLink: critical: RTL: land at home (mavlink_system.cpp:286)
[01:06:29|Debug] MAVLink: info: Landing detected (mavlink_system.cpp:286)
[01:06:33|Debug] MAVLink: info: DISARMED by auto disarm on land (mavlink_system.cpp:286)
Mission status update: 6 / 6
Disarmed, exiting.
```

## How it works

The operation of most of this code is discussed in the guide: [Missions](../guide/missions.md).

## Source code {#source_code}

> **Tip** The full source code for the example [can be found on Github here](https://github.com/dronecore/DroneCore/tree/{{ book.github_branch }}/example/fly_mission).


[CMakeLists.txt](https://github.com/dronecore/DroneCore/blob/{{ book.github_branch }}/example/fly_mission/CMakeLists.txt)

```make
cmake_minimum_required(VERSION 2.8.12)

project(fly_mission)

if(NOT MSVC)
    add_definitions("-std=c++11 -Wall -Wextra -Werror")
else()
    add_definitions("-std=c++11 -WX -W2")
    include_directories(${CMAKE_SOURCE_DIR}/../../install/include)
    link_directories(${CMAKE_SOURCE_DIR}/../../install/lib)
endif()

add_executable(fly_mission
    fly_mission.cpp
)

target_link_libraries(fly_mission
    dronecore
    dronecore_action
    dronecore_mission
    dronecore_telemetry
)
```

[fly_mission.cpp](https://github.com/dronecore/DroneCore/blob/{{ book.github_branch }}/example/fly_mission/fly_mission.cpp)

```cpp
/**
* @file fly_mission.cpp
*
* @brief Demonstrates how to Add & Fly Waypoint missions using DroneCore.
* The example is summarised below:
* 1. Adds mission items.
* 2. Starts mission from first mission item.
* 3. Illustrates Pause/Resume mission item.
* 4. Exits after the mission is accomplished.
*
* @author Julian Oes <julian@oes.ch>,
*         Shakthi Prashanth M <shakthi.prashanth.m@intel.com>
* @date 2017-09-06
*/

#include <dronecore/action.h>
#include <dronecore/dronecore.h>
#include <dronecore/mission.h>
#include <dronecore/telemetry.h>
#include <functional>
#include <future>
#include <iostream>
#include <memory>

#define ERROR_CONSOLE_TEXT "\033[31m" //Turn text on console red
#define TELEMETRY_CONSOLE_TEXT "\033[34m" //Turn text on console blue
#define NORMAL_CONSOLE_TEXT "\033[0m"  //Restore normal console colour

using namespace dronecore;
using namespace std::placeholders; // for `_1`
using namespace std::chrono; // for seconds(), milliseconds()
using namespace std::this_thread; // for sleep_for()

// Handles Action's result
inline void handle_action_err_exit(ActionResult result, const std::string &message);
// Handles Mission's result
inline void handle_mission_err_exit(Mission::Result result, const std::string &message);
// Handles Connection result
inline void handle_connection_err_exit(ConnectionResult result,
                                       const std::string &message);

static std::shared_ptr<MissionItem> make_mission_item(double latitude_deg,
                                                      double longitude_deg,
                                                      float relative_altitude_m,
                                                      float speed_m_s,
                                                      bool is_fly_through,
                                                      float gimbal_pitch_deg,
                                                      float gimbal_yaw_deg,
                                                      MissionItem::CameraAction camera_action);

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

    {
        auto prom = std::make_shared<std::promise<void>>();
        auto future_result = prom->get_future();

        std::cout << "Waiting to discover system..." << std::endl;
        dc.register_on_discover([prom](uint64_t uuid) {
            std::cout << "Discovered system with UUID: " << uuid << std::endl;
            prom->set_value();
        });

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
            std::cout << ERROR_CONSOLE_TEXT << "Connection failed: "
                      << connection_result_str(connection_result)
                      << NORMAL_CONSOLE_TEXT << std::endl;
            return 1;
        }

        future_result.get();
    }

    dc.register_on_timeout([](uint64_t uuid) {
        std::cout << "System with UUID timed out: " << uuid << std::endl;
        std::cout << "Exiting." << std::endl;
        exit(0);
    });

    // We don't need to specifiy the UUID if it's only one system anyway.
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
    std::cout << "Creating and uploading mission" << std::endl;

    std::vector<std::shared_ptr<MissionItem>> mission_items;

    mission_items.push_back(
        make_mission_item(47.398170327054473,
                          8.5456490218639658,
                          10.0f, 5.0f, false,
                          20.0f, 60.0f,
                          MissionItem::CameraAction::NONE));

    mission_items.push_back(
        make_mission_item(47.398241338125118,
                          8.5455360114574432,
                          10.0f, 2.0f, true,
                          0.0f, -60.0f,
                          MissionItem::CameraAction::TAKE_PHOTO));

    mission_items.push_back(
        make_mission_item(47.398139363821485, 8.5453846156597137,
                          10.0f, 5.0f, true,
                          -45.0f, 0.0f,
                          MissionItem::CameraAction::START_VIDEO));

    mission_items.push_back(
        make_mission_item(47.398058617228855,
                          8.5454618036746979,
                          10.0f, 2.0f, false,
                          -90.0f, 30.0f,
                          MissionItem::CameraAction::STOP_VIDEO));

    mission_items.push_back(
        make_mission_item(47.398100366082858,
                          8.5456969141960144,
                          10.0f, 5.0f, false,
                          -45.0f, -30.0f,
                          MissionItem::CameraAction::START_PHOTO_INTERVAL));

    mission_items.push_back(
        make_mission_item(47.398001890458097,
                          8.5455576181411743,
                          10.0f, 5.0f, false,
                          0.0f, 0.0f,
                          MissionItem::CameraAction::STOP_PHOTO_INTERVAL));

    {
        std::cout << "Uploading mission..." << std::endl;
        // We only have the upload_mission function asynchronous for now, so we wrap it using
        // std::future.
        auto prom = std::make_shared<std::promise<Mission::Result>>();
        auto future_result = prom->get_future();
        mission->upload_mission_async(
        mission_items, [prom](Mission::Result result) {
            prom->set_value(result);
        });

        const Mission::Result result = future_result.get();
        if (result != Mission::Result::SUCCESS) {
            std::cout << "Mission upload failed (" << Mission::result_str(result) << "), exiting." << std::endl;
            return 1;
        }
        std::cout << "Mission uploaded." << std::endl;
    }

    std::cout << "Arming..." << std::endl;
    const ActionResult arm_result = action->arm();
    handle_action_err_exit(arm_result, "Arm failed: ");
    std::cout << "Armed." << std::endl;

    std::atomic<bool> want_to_pause {false};
    // Before starting the mission, we want to be sure to subscribe to the mission progress.
    mission->subscribe_progress(
    [&want_to_pause](int current, int total) {
        std::cout << "Mission status update: " << current << " / " << total << std::endl;

        if (current >= 2) {
            // We can only set a flag here. If we do more request inside the callback,
            // we risk blocking the system.
            want_to_pause = true;
        }
    });

    {
        std::cout << "Starting mission." << std::endl;
        auto prom = std::make_shared<std::promise<Mission::Result>>();
        auto future_result = prom->get_future();
        mission->start_mission_async(
        [prom](Mission::Result result) {
            prom->set_value(result);
            std::cout << "Started mission." << std::endl;
        });

        const Mission::Result result = future_result.get();
        handle_mission_err_exit(result, "Mission start failed: ");
    }

    while (!want_to_pause) {
        sleep_for(seconds(1));
    }

    {
        auto prom = std::make_shared<std::promise<Mission::Result>>();
        auto future_result = prom->get_future();

        std::cout << "Pausing mission..." << std::endl;
        mission->pause_mission_async(
        [prom](Mission::Result result) {
            prom->set_value(result);
        });

        const Mission::Result result = future_result.get();
        if (result != Mission::Result::SUCCESS) {
            std::cout << "Failed to pause mission (" << Mission::result_str(result) << ")" << std::endl;
        } else {
            std::cout << "Mission paused." << std::endl;
        }
    }

    // Pause for 5 seconds.
    sleep_for(seconds(5));

    // Then continue.
    {
        auto prom = std::make_shared<std::promise<Mission::Result>>();
        auto future_result = prom->get_future();

        std::cout << "Resuming mission..." << std::endl;
        mission->start_mission_async(
        [prom](Mission::Result result) {
            prom->set_value(result);
        });

        const Mission::Result result = future_result.get();
        if (result != Mission::Result::SUCCESS) {
            std::cout << "Failed to resume mission (" << Mission::result_str(result) << ")" << std::endl;
        } else {
            std::cout << "Resumed mission." << std::endl;
        }
    }

    while (!mission->mission_finished()) {
        sleep_for(seconds(1));
    }

    {
        // We are done, and can do RTL to go home.
        std::cout << "Commanding RTL..." << std::endl;
        const ActionResult result = action->return_to_launch();
        if (result != ActionResult::SUCCESS) {
            std::cout << "Failed to command RTL (" << action_result_str(result) << ")" << std::endl;
        } else {
            std::cout << "Commanded RTL." << std::endl;
        }
    }

    // We need to wait a bit, otherwise the armed state might not be correct yet.
    sleep_for(seconds(2));

    while (telemetry->armed()) {
        // Wait until we're done.
        sleep_for(seconds(1));
    }
    std::cout << "Disarmed, exiting." << std::endl;
}

std::shared_ptr<MissionItem> make_mission_item(double latitude_deg,
                                               double longitude_deg,
                                               float relative_altitude_m,
                                               float speed_m_s,
                                               bool is_fly_through,
                                               float gimbal_pitch_deg,
                                               float gimbal_yaw_deg,
                                               MissionItem::CameraAction camera_action)
{
    std::shared_ptr<MissionItem> new_item(new MissionItem());
    new_item->set_position(latitude_deg, longitude_deg);
    new_item->set_relative_altitude(relative_altitude_m);
    new_item->set_speed(speed_m_s);
    new_item->set_fly_through(is_fly_through);
    new_item->set_gimbal_pitch_and_yaw(gimbal_pitch_deg, gimbal_yaw_deg);
    new_item->set_camera_action(camera_action);
    return new_item;
}

inline void handle_action_err_exit(ActionResult result, const std::string &message)
{
    if (result != ActionResult::SUCCESS) {
        std::cerr << ERROR_CONSOLE_TEXT << message << action_result_str(
                      result) << NORMAL_CONSOLE_TEXT << std::endl;
        exit(EXIT_FAILURE);
    }
}

inline void handle_mission_err_exit(Mission::Result result, const std::string &message)
{
    if (result != Mission::Result::SUCCESS) {
        std::cerr << ERROR_CONSOLE_TEXT << message << Mission::result_str(
                      result) << NORMAL_CONSOLE_TEXT << std::endl;
        exit(EXIT_FAILURE);
    }
}

// Handles connection result
inline void handle_connection_err_exit(ConnectionResult result,
                                       const std::string &message)
{
    if (result != ConnectionResult::SUCCESS) {
        std::cerr << ERROR_CONSOLE_TEXT << message
                  << connection_result_str(result)
                  << NORMAL_CONSOLE_TEXT << std::endl;
        exit(EXIT_FAILURE);
    }
}
```
