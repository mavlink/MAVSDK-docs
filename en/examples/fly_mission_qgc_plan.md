# Example: Fly QGroundControl Plan Mission

The [Fly QGroundControl Plan Mission](https://github.com/mavlink/MAVSDK/tree/{{ book.github_branch }}/examples/fly_qgc_mission) example shows how to import a *QGroundControl* mission plan, upload it to a vehicle, run the mission, and then command Return mode ("RTL").

![Fly Mission QGC Screenshot - From Plan](../../assets/examples/fly_qgc_mission/fly_qgc_plan_mission_example_qgc.jpg)


## Running the Example {#run_example}

The example is built and run in the normal way ([as described here](../examples/README.md#trying_the_examples)).

> **Tip** By default the example will load a sample plan from the plugin unit test: [/src/plugins/mission/qgroundcontrol_sample.plan](https://github.com/mavlink/MAVSDK/blob/{{ book.github_branch }}/src/plugins/mission/qgroundcontrol_sample.plan).
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
Importing mission from mission plan: ../../../src/plugins/mission/qgroundcontrol_sample.plan
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

- [CMakeLists.txt](https://github.com/mavlink/MAVSDK/blob/{{ book.github_branch }}/examples/fly_qgc_mission/CMakeLists.txt)
- [fly_qgc_mission.cpp](https://github.com/mavlink/MAVSDK/blob/{{ book.github_branch }}/examples/fly_qgc_mission/fly_qgc_mission.cpp)
