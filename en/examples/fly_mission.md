# Example: Fly Mission

This example shows how to create, upload, and run, pause, and restart missions using DroneCore.

![Fly Mission QGC Screenshot](../../assets/examples/fly_mission/fly_mission_example_qgc.jpg)


## Running the Example {#run_example}

The example is built and run [as described here](../examples/README.md#trying_the_examples) (the standard way). 

The example terminal output should be similar to that shown below:

> **Note** This is from a debug build of DroneCore. A release build will omit the "Debug" messages.

```
$ ./fly_mission 
Waiting to discover device...
[03:42:51|Info ] New device on: 127.0.0.1:14557 (udp_connection.cpp:210)
[03:42:51|Debug] MAVLink: info: [logger] file: rootfs/fs/microsd/log/2017-11-14/2 (device_impl.cpp:225)
[03:42:51|Debug] Discovered 4294967298 (dronecore_impl.cpp:234)
Discovered device with UUID: 4294967298
Waiting for device to be ready
...
Waiting for device to be ready
Device ready
Creating and uploading mission
Uploading mission...
[03:43:07|Debug] Send mission item 0 (mission_impl.cpp:712)
[03:43:07|Debug] Send mission item 1 (mission_impl.cpp:712)
[03:43:07|Debug] Send mission item 2 (mission_impl.cpp:712)
[03:43:07|Debug] Send mission item 3 (mission_impl.cpp:712)
[03:43:07|Debug] Send mission item 4 (mission_impl.cpp:712)
[03:43:07|Debug] Send mission item 5 (mission_impl.cpp:712)
[03:43:07|Debug] Send mission item 6 (mission_impl.cpp:712)
[03:43:07|Debug] Send mission item 7 (mission_impl.cpp:712)
[03:43:07|Debug] Send mission item 8 (mission_impl.cpp:712)
[03:43:07|Debug] Send mission item 9 (mission_impl.cpp:712)
[03:43:07|Debug] Send mission item 10 (mission_impl.cpp:712)
[03:43:07|Debug] Send mission item 11 (mission_impl.cpp:712)
[03:43:07|Debug] Send mission item 12 (mission_impl.cpp:712)
[03:43:07|Debug] Send mission item 13 (mission_impl.cpp:712)
[03:43:07|Debug] Send mission item 14 (mission_impl.cpp:712)
[03:43:07|Debug] Send mission item 15 (mission_impl.cpp:712)
[03:43:07|Debug] Send mission item 16 (mission_impl.cpp:712)
[03:43:07|Debug] Send mission item 17 (mission_impl.cpp:712)
[03:43:07|Debug] Send mission item 18 (mission_impl.cpp:712)
[03:43:07|Debug] Send mission item 19 (mission_impl.cpp:712)
[03:43:07|Debug] Send mission item 20 (mission_impl.cpp:712)
[03:43:07|Debug] Send mission item 21 (mission_impl.cpp:712)
[03:43:07|Debug] Send mission item 22 (mission_impl.cpp:712)
[03:43:07|Info ] Mission accepted (mission_impl.cpp:136)
Mission uploaded.
Arming...
[03:43:07|Debug] MAVLink: info: ARMED by arm/disarm component command (device_impl.cpp:225)
Armed.
Starting mission.
Started mission.
[03:43:07|Debug] MAVLink: info: Executing mission. (device_impl.cpp:225)
[03:43:07|Debug] MAVLink: info: Takeoff to 10.0 meters above home. (device_impl.cpp:225)
[03:43:07|Debug] MAVLink: info: Takeoff detected (device_impl.cpp:225)
Mission status update: 0 / 6
Mission status update: 0 / 6
Mission status update: 1 / 6
Mission status update: 1 / 6
Mission status update: 1 / 6
Mission status update: 1 / 6
Mission status update: 2 / 6
Pausing mission...
Mission paused.
Resuming mission...
Resumed mission.
Mission status update: 2 / 6
Mission status update: 2 / 6
Mission status update: 2 / 6
Mission status update: 3 / 6
Mission status update: 3 / 6
Mission status update: 3 / 6
Mission status update: 3 / 6
Mission status update: 4 / 6
Mission status update: 4 / 6
Mission status update: 4 / 6
Mission status update: 4 / 6
Mission status update: 5 / 6
Mission status update: 5 / 6
Mission status update: 5 / 6
Mission status update: 5 / 6
[03:44:10|Debug] MAVLink: info: Mission finished, loitering. (device_impl.cpp:225)
Mission status update: 6 / 6
Commanding RTL...
Commanded RTL.
[03:44:10|Debug] MAVLink: info: RTL: return at 498 m (10 m above home) (device_impl.cpp:225)
[03:44:18|Debug] MAVLink: info: RTL: descend to 493 m (5 m above home) (device_impl.cpp:225)
[03:44:22|Debug] MAVLink: info: RTL: loiter 5.0s (device_impl.cpp:225)
[03:44:27|Debug] MAVLink: info: RTL: land at home (device_impl.cpp:225)
[03:44:40|Debug] MAVLink: info: Landing detected (device_impl.cpp:225)
[03:44:43|Debug] MAVLink: info: DISARMED by auto disarm on land (device_impl.cpp:225)
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
endif()

add_executable(fly_mission
    fly_mission.cpp
)

target_link_libraries(fly_mission
    dronecore
)
```

[fly_mission.cpp](https://github.com/dronecore/DroneCore/blob/{{ book.github_branch }}/example/fly_mission/fly_mission.cpp)

```cpp
//
// Example that demonstrates how add waypoint missions using DroneCore
//
// Author: Julian Oes <julian@oes.ch>, Shakthi Prashanth <shakthi.prashanth.m@intel.com>
//

#include <dronecore/dronecore.h>
#include <iostream>
#include <functional>
#include <memory>
#include <future>


using namespace dronecore;
using namespace std::placeholders; // for `_1`


static std::shared_ptr<MissionItem> add_mission_item(double latitude_deg,
                                                     double longitude_deg,
                                                     float relative_altitude_m,
                                                     float speed_m_s,
                                                     bool is_fly_through,
                                                     float gimbal_pitch_deg,
                                                     float gimbal_yaw_deg,
                                                     MissionItem::CameraAction camera_action);

int main(int /*argc*/, char ** /*argv*/)
{
    DroneCore dc;

    {
        auto prom = std::make_shared<std::promise<void>>();
        auto future_result = prom->get_future();

        std::cout << "Waiting to discover device..." << std::endl;
        dc.register_on_discover([prom](uint64_t uuid) {
            std::cout << "Discovered device with UUID: " << uuid << std::endl;
            prom->set_value();
        });

        DroneCore::ConnectionResult connection_result = dc.add_udp_connection();
        if (connection_result != DroneCore::ConnectionResult::SUCCESS) {
            std::cout << "Connection failed: " << DroneCore::connection_result_str(
                          connection_result) << std::endl;
            return 1;
        }

        future_result.get();
    }

    dc.register_on_timeout([](uint64_t uuid) {
        std::cout << "Device with UUID timed out: " << uuid << std::endl;
        std::cout << "Exiting." << std::endl;
        exit(0);
    });

    // We don't need to specifiy the UUID if it's only one device anyway.
    // If there were multiple, we could specify it with:
    // dc.device(uint64_t uuid);
    Device &device = dc.device();

    while (!device.telemetry().health_all_ok()) {
        std::cout << "Waiting for device to be ready" << std::endl;
        std::this_thread::sleep_for(std::chrono::seconds(1));
    }

    std::cout << "Device ready" << std::endl;
    std::cout << "Creating and uploading mission" << std::endl;

    std::vector<std::shared_ptr<MissionItem>> mission_items;

    mission_items.push_back(
        add_mission_item(47.398170327054473,
                         8.5456490218639658,
                         10.0f, 5.0f, false,
                         20.0f, 60.0f,
                         MissionItem::CameraAction::NONE));

    mission_items.push_back(
        add_mission_item(47.398241338125118,
                         8.5455360114574432,
                         10.0f, 2.0f, true,
                         0.0f, -60.0f,
                         MissionItem::CameraAction::TAKE_PHOTO));

    mission_items.push_back(
        add_mission_item(47.398139363821485, 8.5453846156597137,
                         10.0f, 5.0f, true,
                         -45.0f, 0.0f,
                         MissionItem::CameraAction::START_VIDEO));

    mission_items.push_back(
        add_mission_item(47.398058617228855,
                         8.5454618036746979,
                         10.0f, 2.0f, false,
                         -90.0f, 30.0f,
                         MissionItem::CameraAction::STOP_VIDEO));

    mission_items.push_back(
        add_mission_item(47.398100366082858,
                         8.5456969141960144,
                         10.0f, 5.0f, false,
                         -45.0f, -30.0f,
                         MissionItem::CameraAction::START_PHOTO_INTERVAL));

    mission_items.push_back(
        add_mission_item(47.398001890458097,
                         8.5455576181411743,
                         10.0f, 5.0f, false,
                         0.0f, 0.0f,
                         MissionItem::CameraAction::STOP_PHOTO_INTERVAL));

    {
        std::cout << "Uploading mission..." << std::endl;
        // We only have the send_mission function asynchronous for now, so we wrap it using
        // std::future.
        auto prom = std::make_shared<std::promise<Mission::Result>>();
        auto future_result = prom->get_future();
        device.mission().send_mission_async(
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
    const Action::Result arm_result = device.action().arm();
    if (arm_result != Action::Result::SUCCESS) {
        std::cout << "Arming failed (" << Action::result_str(arm_result) << "), exiting." << std::endl;
        return 1;
    }

    std::cout << "Armed." << std::endl;

    std::atomic<bool> want_to_pause {false};
    // Before starting the mission, we want to be sure to subscribe to the mission progress.
    device.mission().subscribe_progress(
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
        device.mission().start_mission_async(
        [prom](Mission::Result result) {
            prom->set_value(result);
            std::cout << "Started mission." << std::endl;
        });

        const Mission::Result result = future_result.get();
        if (result != Mission::Result::SUCCESS) {
            std::cout << "Mission start failed (" << Mission::result_str(result) << "), exiting." << std::endl;
            return 1;
        }
    }

    while (!want_to_pause) {
        std::this_thread::sleep_for(std::chrono::seconds(1));
    }

    {
        auto prom = std::make_shared<std::promise<Mission::Result>>();
        auto future_result = prom->get_future();

        std::cout << "Pausing mission..." << std::endl;
        device.mission().pause_mission_async(
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
    std::this_thread::sleep_for(std::chrono::seconds(5));

    // Then continue.
    {
        auto prom = std::make_shared<std::promise<Mission::Result>>();
        auto future_result = prom->get_future();

        std::cout << "Resuming mission..." << std::endl;
        device.mission().start_mission_async(
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

    while (!device.mission().mission_finished()) {
        std::this_thread::sleep_for(std::chrono::seconds(1));
    }

    {
        // We are done, and can do RTL to go home.
        std::cout << "Commanding RTL..." << std::endl;
        const Action::Result result = device.action().return_to_launch();
        if (result != Action::Result::SUCCESS) {
            std::cout << "Failed to command RTL (" << Action::result_str(result) << ")" << std::endl;
        } else {
            std::cout << "Commanded RTL." << std::endl;
        }
    }

    // We need to wait a bit, otherwise the armed state might not be correct yet.
    std::this_thread::sleep_for(std::chrono::seconds(2));

    while (device.telemetry().armed()) {
        // Wait until we're done.
        std::this_thread::sleep_for(std::chrono::seconds(1));
    }
    std::cout << "Disarmed, exiting." << std::endl;
}

std::shared_ptr<MissionItem> add_mission_item(double latitude_deg,
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
```
