# Examples

> **Tip** Information about *writing* example code is covered in the [Contributing > Writing Plugins](../contributing/plugins.md) (*plugin developers* should initially create [integration tests](../contributing/plugins.md#integration_tests) rather than examples for new code).

This section contains examples showing how to use *Dronecode SDK*.

Example | Description
--- | ---
[Takeoff and Land](../examples/takeoff_and_land.md) | Shows basic usage of the SDK (connect to port, detect system (vehicle), arm, takeoff, land, get telemetry)
[Fly Mission](../examples/fly_mission.md) | Shows how to create, upload, and run missions.
[Fly QGC Plan Mission](../examples/fly_mission_qgc_plan.md) | Fly a mission imported from a *QGroundControl* mission plan.
[Offboard Velocity Control](../examples/offboard_velocity.md) | Demonstrates how to control a vehicle in Offboard mode using velocity commands (in both the NED and body frames).
[Follow Me Mode](../examples/offboard_velocity.md) | Demonstrates how to put vehicle in [Follow Me Mode](../guide/follow_me.md) and set the current target position and relative position of the drone.
[VTOL Transitions](../examples/transition_vtol_fixed_wing.md) | Shows how to transition a VTOL vehicle between copter and fixed-wing modes.

The examples are "largely" built and run in the same way, as described in the following section (any exceptions are covered in the page for the associated example).

> **Warning** Some of the examples define flight behaviour relative to the default home position in the simulator (e.g. [Fly Mission](../examples/fly_mission.md)). 
  Care should be taken if using them on a real vehicle.

## Trying the Examples {#trying_the_examples}

The easiest way to test the examples is to use a [simulated PX4 vehicle](https://dev.px4.io/en/simulation/) that is running on the same computer.
First start PX4 in SITL (Simulation), optionally start *QGroundControl* to observe the vehicle, then build and run the example code. 

> **Note** The simulator broadcasts to the standard PX4 UDP port for connecting to offboard APIs (14540). The examples connect to this port using either [add_any_connection()](../api_reference/classdronecode__sdk_1_1_dronecode_s_d_k.md#classdronecode__sdk_1_1_dronecode_s_d_k_1a51097e0dad30f0292a2ab4d3e9d91acf) or [add_udp_connection()](../api_reference/classdronecode__sdk_1_1_dronecode_s_d_k.md#classdronecode__sdk_1_1_dronecode_s_d_k_1ac242fb36bc018038fc1fc5ee4e5f21ad).


### Setting up a Simulator

PX4 supports a [number of simulators](https://dev.px4.io/en/simulation/). 
In order to set up the [jMAVSim](https://dev.px4.io/en/simulation/jmavsim.html) or [Gazebo](https://dev.px4.io/en/simulation/gazebo.html) simulator, you can simply follow the standard PX4 toolchain setup instructions for [macOS](https://dev.px4.io/en/setup/dev_env_mac.html) or [Ubuntu Linux](https://dev.px4.io/en/setup/dev_env_linux.html#development-toolchain).

> **Note** JMAVSim can only be used to simulate multicopters. 
  Gazebo additionally supports a number of [other vehicles](https://dev.px4.io/en/simulation/gazebo.html#html#running-the-simulation) (e.g. VTOL, Rovers, fixed-wing etc.).

After running a standard installation, a simulation can be started from the PX4 **/Firmware** directory using the command:
* Multicopter (jMAVSim): `make posix_sitl_default jmavsim`
* Multicopter (Gazebo): `make posix_sitl_default gazebo`
* VTOL (Gazebo):  `make posix_sitl_default gazebo_standard_vtol`


### Using QGroundControl

You can use *QGroundControl* to connect to PX4 and observe vehicle movement and behaviour while the examples are running. 
*QGroundControl* will automatically connect to the PX4 simulation as soon as it is started.

See [QGroundControl > Download and Install](https://docs.qgroundcontrol.com/en/getting_started/download_and_install.html) for information about setting up *QGroundControl* on your platform.


### Building the Examples {#build_examples}

To build the examples follow the instructions below, replacing *takeoff_and_land* with the name of the specific example. 
Any exceptions will be covered in the page for the associated example(s).

#### Linux

First [Build and install the SDK C++ Library](../contributing/build.md) system-wide using the command below:
```sh
make clean
make default
sudo make default install
```

Then build the example:
```sh
cd example/takeoff_and_land/
mkdir build && cd build
cmake ..
make
```

#### Windows

First [Build and install the SDK C++ Library](../contributing/build.md#windows).
Make sure that you [install the library and headers locally](../contributing/build.md#sdk_local_install) in the standard location: 

```sh
cmake --build . --target install
```

Modify the example as described in [Building C++ Apps > SDK Installed Locally](../guide/toolchain.md#sdk_local_install) (this is required for Windows).

Build the example as described in [Building C++ Apps](../guide/toolchain.md#windows). Below we show how for the *takeoff_and_land* example, but all the other examples are built in the same way:
```sh
cd example/takeoff_and_land/
mkdir build && cd build
cmake .. -G "Visual Studio 15 2017 Win64"
cmake --build .
```

> **Note** The debug binary for the example is stored under **\Debug** folder.

### Running the Examples {#running_the_examples}

You can then run the example, specifying the connection URL as the first argument.
When running with the Simulator, you will use the connection string: `udp://:14540`
 
On Linux/macOS you would run the following (from the **/build** directory): 
```sh
./takeoff_and_land udp://:14540
```

For Windows you would run the following (from the **\build\Debug\** directory):
```cmd
.\Debug\takeoff_and_land.exe udp://:14540
```


> **Tip** Most examples will create a binary with the same name as the example. 
> The name that is used is specified in the **CMakeLists.txt** file as the first value in the call to `add_executable()`.

If you have already started the simulation the example code should connect to PX4, 
and you will be able to observe behaviour through the SDK terminal, SITL terminal, and/or *QGroundControl*.

## Troubleshooting

### Linux: Error loading shared libraries

The following error is raised when you run an application/example on Linux and the *Dronecode SDK* shared library cannot be found:

```
error while loading shared libraries: libdronecode_sdk.so: cannot open shared object file: No such file or directory
```

The solution is to update the linker cache so that the system can find the library. 
On Ubuntu call the following:
```
sudo ldconfig
```

For more information/other Linux flavours see [Linux Documentation > Shared Libraries](http://tldp.org/HOWTO/Program-Library-HOWTO/shared-libraries.html).
