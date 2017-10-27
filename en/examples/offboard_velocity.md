# Example: Offboard Velocity

This example shows how to how to control a vehicle in *Offboard mode* using velocity commands (in both the NED and body frames).

![Offboard Mode - Velocity Control QGC Screenshot](../../assets/examples/offboard_mode/qgc_offboard_velocity.png)


## Running the Example {#run_example}

The example is built and run [as described here](/examples/README.md#trying_the_examples) (the standard way). 

The example terminal output should be similar to that shown below:

> **Note** This is for a release build of DroneCore. A debug build will display additional information from DroneCore.

```
$ ./offboard 
Wait for device to connect via heartbeat
[11:52:48|Info ] New device on: 127.0.0.1:14557 (udp_connection.cpp:210)
[11:52:48|Debug] mavlink info: [logger] file: rootfs/fs/microsd/log/2017-10-27/0 (device_impl.cpp:223)
[11:52:49|Debug] Discovered 4294967298 (dronecore_impl.cpp:234)
Waiting for device to be ready
...
Waiting for device to be ready
Device is ready
Armed
[11:53:02|Debug] mavlink info: ARMED by arm/disarm component command (device_impl.cpp:223)
In Air...
[11:53:02|Debug] mavlink info: Using minimum takeoff altitude: 2.50 m (device_impl.cpp:223)
[11:53:02|Debug] mavlink info: Takeoff detected (device_impl.cpp:223)
[11:53:02|Debug] mavlink critical: Using minimum takeoff altitude: 2.50 m (device_impl.cpp:223)
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
[11:54:26|Debug] mavlink info: Landing at current position (device_impl.cpp:223)
Landed
ubuntu@ubuntu:~/DroneCore/example/offboard_velocity/build$ 
```

## How it works

The operation of most of this code is discussed in the guide: [Offboard Control](../guide/offboard.md).

## Source code {#source_code}

> **Tip** The full source code for the example [can be found on Github here](https://github.com/dronecore/DroneCore/tree/master/example/offboard_velocity).


[CMakeLists.txt](https://github.com/dronecore/DroneCore/blob/master/example/offboard_velocity/CMakeLists.txt)

```make
##TODO: ADD FINAL TEXT HERE
```

[offboard_velocity.cpp](https://github.com/dronecore/DroneCore/blob/master/example/offboard_velocity/offboard_velocity.cpp)

```cpp
##TODO: ADD FINAL TEXT HERE
```
