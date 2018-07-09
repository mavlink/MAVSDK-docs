# Actions (Take-off, Landing, Arming, etc)

The [Action](../api_reference/classdronecode__sdk_1_1_action.md) class is used for commanding the vehicle to arm, takeoff, land, return home and land, disarm, kill and transition between VTOL modes. 

Most of the methods have both synchronous and asynchronous versions. 
The methods send commands to a vehicle, and return/complete with the vehicle's response. 
It is important to understand that a successful response indicates whether or not the vehicle intends to act on the command, not that it has finished the action (e.g. arming, landing, taking off etc.).

> **Note** The implication is that you may need to monitor for completion of actions!


## Create the Plugin

> **Tip** `Action` objects are created in the same way as for other SDK plugins. 
General instructions are provided in the topic: [Using Plugins](../guide/using_plugins.md).

The main steps are:

1. Link the plugin library into your application. 
   Do this by adding `dronecore_action` to the `target_link_libraries` section of the app's *cmake* build definition file

   ```cmake
   target_link_libraries(your_application_name
     dronecore
     ...
     dronecore_action
     ...
   )
   ```
1. [Create a connection](../guide/connections.md) to a `system`. For example (basic code without error checking):
   ```
   #include <dronecore/dronecore.h>
   DroneCore dc;
   ConnectionResult conn_result = dc.add_udp_connection();
   // Wait for the system to connect via heartbeat
   while (!dc.is_connected()) {
      sleep_for(seconds(1));
   }
   // System got discovered.
   System &system = dc.system();
   ```
1. Create a shared pointer to an instance of `Action` instantiated with the `system`: 
   ```
   #include <dronecore/action.h>
   auto action = std::make_shared<Action>(system);
   ```

The `action` pointer can then used to access the plugin API (as shown in the following sections). 

> **Note** Some of the sections below additionally assume you have created a `Telemetry` instance that can be accessed using `telemetry`.


## Taking Off

The recommended way to take off using the SDK (and PX4) is to use either of the [takeoff()](../api_reference/classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1a1d6244edfd39272d97bf8b126eb98629) or [takeoff_async()](../api_reference/classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1a2aec10a2b14f5e82f05edc6e2feac83e) methods. If a takeoff command is accepted the vehicle will change to the [Takeoff mode](https://docs.px4.io/en/flight_modes/takeoff.html), fly to the takeoff altitude, and then hover (in takeoff mode) until another instruction is received. 

> **Note** PX4/SDK also provides other ways to take off:
> - A copter or VTOL will take off automatically if a mission is started (fixed-wing will not). 
> - You can also take off by manually driving the vehicle using the offboard API. 

The vehicle will only take off once *armed*, and can only arm once it is "healthy" (has been calibrated, the home position has been set, and there is a high-enough quality GPS lock). After it starts flying, code needs to check that takeoff is complete before sending additional instructions.


### Health Check

The code fragment below shows very simple code to synchronously poll for health status (using [Telemetry:health_all_ok()](../api_reference/classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1a630c91d8067e4084c4f303513a0aeb29)) prior to arming:

```cpp
// Wait until health is OK and vehicle is ready to arm
while (telemetry->health_all_ok() != true) {
    std::cout << "Vehicle not ready to arm ..." << std::endl;
    std::this_thread::sleep_for(std::chrono::seconds(1));
}
```

The code fragment below performs the same task, but additionally exits the app if calibration is required reports what conditions are still required before the vehicle is "healthy":

```cpp
// Exit if calibration is required
Telemetry::Health check_health = telemetry->health();
bool calibration_required = false;
if (!check_health.gyrometer_calibration_ok) {
    std::cout << ERROR_CONSOLE_TEXT << "Gyro requires calibration." << NORMAL_CONSOLE_TEXT << std::endl;
    calibration_required=true;
}
if (!check_health.accelerometer_calibration_ok) {
    std::cout << ERROR_CONSOLE_TEXT << "Accelerometer requires calibration." << NORMAL_CONSOLE_TEXT << std::endl;
    calibration_required=true;
}
if (!check_health.magnetometer_calibration_ok) {
    std::cout << ERROR_CONSOLE_TEXT << "Magnetometer (compass) requires calibration." << NORMAL_CONSOLE_TEXT << std::endl;
    calibration_required=true;
}
if (!check_health.level_calibration_ok) {
    std::cout << ERROR_CONSOLE_TEXT << "Level calibration required." << NORMAL_CONSOLE_TEXT << std::endl;
    calibration_required=true;
}
if (calibration_required) {
    return 1;
}


// Check if ready to arm (reporting status)
while (telemetry->health_all_ok() != true) {
    std::cout << ERROR_CONSOLE_TEXT << "Vehicle not ready to arm. Waiting on:" << NORMAL_CONSOLE_TEXT << std::endl;
    Telemetry::Health current_health = telemetry->health();
    if (!current_health.global_position_ok) {
        std::cout << ERROR_CONSOLE_TEXT << "  - GPS fix." << NORMAL_CONSOLE_TEXT << std::endl;
    }
    if (!current_health.local_position_ok) {
        std::cout << ERROR_CONSOLE_TEXT << "  - Local position estimate." << NORMAL_CONSOLE_TEXT << std::endl;
    }
    if (!current_health.home_position_ok) {
        std::cout << ERROR_CONSOLE_TEXT << "  - Home position to be set." << NORMAL_CONSOLE_TEXT << std::endl;
    }
    std::this_thread::sleep_for(std::chrono::seconds(1));
}
```

> **Note** Vehicle health can also be checked using [Telemetry:health_all_ok_async()](../api_reference/classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1a83b384cd04b2ed17db805cfad8bafab5). 


### Arming

Once the vehicle is ready, use the following synchronous code to arm:
```cpp
// Arm vehicle
std::cout << "Arming..." << std::endl;
const Action::Result arm_result = action->arm();

if (arm_result != Action::Result::SUCCESS) {
    std::cout << "Arming failed:" 
      << Action::result_str(arm_result) 
      <<  std::endl;
    return 1; //Exit if arming fails
}
```

> **Tip** If the `arm()` method returns `Action::Result::SUCCESS` then the vehicle is armed and can proceed to takeoff. This can be confirmed using [Telemetry::armed()](../api_reference/classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1a0ca7da7922c22509ce6d55d4ad19bcf7).


### Get/Set Takeoff Altitude

The default/current takeoff altitude can be queried using [get_takeoff_altitude_m()](../api_reference/classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1a1888deebcc48d906c3c19473596e6fec). This target can be changed at any point before takeoff using [set_takeoff_altitude()](../api_reference/classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1adc6f7f6668d3681afa4d820095154c9d). The code fragment below shows how to set the takeoff altitude to 3 metres:
```cpp
action->set_takeoff_altitude(3.0);
```

### Takeoff Action

Once the vehicle is armed it can be commanded to take off. The code below uses the synchronous `takeoff()` method, and fails if the vehicle refuses the command:
```cpp
// Command Take off
std::cout << "Taking off..." << std::endl;
const Action::Result takeoff_result = action->takeoff();
if (takeoff_result != Action::Result::SUCCESS) {
    std::cout << "Takeoff failed:" << Action::result_str(
        takeoff_result) << std::endl;
    return 1;
}
```

If the command succeeds the vehicle will takeoff, and hover at the takeoff altitude. Code should wait until takeoff has completed before sending the next instruction. Unfortunately there is no specific indicator to inform code that takeoff is complete. 

> **Note** One alternative is to simply wait for enough time that the vehicle *should* have reached the takeoff altitude.

The code below checks for takeoff completion by polling the current altitude until the target altitude is reached:

```cpp
float target_alt=action->get_takeoff_altitude_m();
float current_position=0;
while (current_position<target_alt) {
    current_position = telemetry->position().relative_altitude_m;
    std::this_thread::sleep_for(std::chrono::seconds(1));
}
// Reached target altitude - continue with next instruction.
```


## Landing

The best way to land the vehicle at the current location is to use the [land()](../api_reference/classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1a08367528cdf25404b7db6db457e3c6f9) or [land_async()](../api_reference/classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1a7f10240cde2ff237795e3688802d857b) methods. If the command is accepted the vehicle will change to the [Land mode](https://docs.px4.io/en/flight_modes/land.html) and land at the current point. 

> **Note** DroneCore does not at time of writing recommend other approaches for landing: land mission items are not supported and manually landing the vehicle using the offboard is not as safe. 

The code below shows how to use the land action.

```cpp
const Action::Result land_result = action->land();
if (land_result != Action::Result::SUCCESS) {
    //Land failed, so exit (in reality might try a return to land or kill.)
    return 1;
}
```

The vehicle should land and then automatically disarm. If you want to monitor the landing you can trigger completion of the
app based on the armed state, as shown below.

```cpp
while (telemetry->armed()) {
    std::this_thread::sleep_for(std::chrono::seconds(1));
}
std::cout << "Disarmed, exiting." << std::endl;
```


## Return/RTL

[Return mode](https://docs.px4.io/en/flight_modes/return.html) (also known as "Return to Launch", "Return to Land", "Return to Home") flies the vehicle back to the home position and may also land the vehicle (depending on vehicle configuration). This mode is invoked from DroneCore using the [return_to_launch()](../api_reference/classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1a740a3bf125560edaf810865a616b2d24) or [return_to_launch_async()](../api_reference/classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1aa1253c356c7628d329dfa98d78eb39ee) methods. 

The code below shows how to use the synchronous method:

```cpp
const Action::Result rtl_result = telemetry->return_to_launch();
if (rtl_result != Action::Result::SUCCESS) {
    //RTL failed, so exit (in reality might send kill command.)
    return 1;
}
```

Depending on the vehicle it may land or hover around the return point. For vehicles that are configured to land you can use the same code as in the [previous section](#landing) to determine when the vehicle has disarmed.

## Disarm/Kill

Use the disarm or kill methods to stop the drone motors (the difference is that disarming will only succeed if the drone considers itself landed, while kill will disarm a vehicle even in flight).

The methods are listed below. These are used in the same way as other similar `Action` APIs:
- [disarm()](../api_reference/classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1a0ab29022df5d93d4f590d83a3e9c4349), [disarm_async](../api_reference/classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1acc0a17411a25f5641ae21046b459e79e)
- [kill()](../api_reference/classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1a615cff3ac4321340a9871416d2ca1db8), [kill_async](../api_reference/classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1a1d7d09191d9319c7912962b2dd02caa7)


> **Tip** PX4 will automatically disarm the vehicle after landing. The disarm methods explicitly invoke the same functionality.


## Get/Set Cruise Speed

You can get/set the normal horizontal velocity used in *Return mode*, *Hold mode*, *Takeoff* (and other [AUTO Flight Modes](https://docs.px4.io/en/getting_started/flight_modes.html#categories) using the following methods:
* [set_max_speed()](../api_reference/classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1abc27410a9b2a938b21ab59c5ef9ee941)
* [get_max_speed_m_s](../api_reference/classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1abc27410a9b2a938b21ab59c5ef9ee941)

> **Note** These methods get/set the [MPC_XY_CRUISE](https://dev.px4.io/en/advanced/parameter_reference.html#MPC_XY_CRUISE) parameter. They are used in the same way as the other `Action` methods.



## Switch Between VTOL Modes {#transition_vtol}

DroneCore provides methods to transition between VTOL fixed wing and multicopter modes, with both synchronous and asynchronous versions:
* [transition_to_fixedwing()](../api_reference/classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1a559e6cfa22f937acc0bbd1f9ac4e54fa), [transition_to_multicopter()](../api_reference/classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1a3af080379382fedbc3ad8bdbaf3c4e4c)
* [transition_to_fixedwing_async()](../api_reference/classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1af5b02f05ffdc2e0787a7633410710d9d), [transition_to_multicopter_async()](../api_reference/classdronecode__sdk_1_1_action.md#classdronecode__sdk_1_1_action_1a053aa7430852a4200b201abda1b3b3e4)

The associated action will only be executed for VTOL vehicles (on other vehicle types the command will fail with a `Result` of `VTOL_TRANSITION_SUPPORT_UNKNOWN` or `NO_VTOL_TRANSITION_SUPPORT`). The command will succeed if called when the vehicle is already in the mode.

The code fragment below shows how to call the synchronous action to transition to fixed wing, 
and to print the result of the call (the other synchronous method is used in the same way). 

```cpp
const Action::Result fw_result = action->transition_to_fixedwing();

if (fw_result != Action::Result::SUCCESS) {
    std::cout << "Transition to fixed wing failed: " 
        << Action::result_str(fw_result) << std::endl;
}
```


## Further Information

Additional information/examples for the Action API are linked below:

* [Example: Takeoff and Land](../examples/takeoff_and_land.md)
* [Example: VTOL Transitions](../examples/transition_vtol_fixed_wing.md)
* Integration tests:
  * [simple_hover.cpp](https://github.com/dronecore/DroneCore/blob/{{ book.github_branch }}/integration_tests/simple_hover.cpp)
  * [async_hover.cpp](https://github.com/dronecore/DroneCore/blob/{{ book.github_branch }}/integration_tests/async_hover.cpp)
  * [takeoff_and_kill.cpp](https://github.com/dronecore/DroneCore/blob/{{ book.github_branch }}/integration_tests/takeoff_and_kill.cpp)
  * [transition_multicopter_fixedwing.cpp](https://github.com/dronecore/DroneCore/blob/{{ book.github_branch }}/integration_tests/transition_multicopter_fixedwing.cpp)

