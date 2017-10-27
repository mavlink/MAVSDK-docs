# Offboard Control

The [Offboard](../api_reference/classdronecore_1_1_offboard.md) module provides a simple API 
for controlling the vehicle using velocity and yaw setpoints. It is useful for tasks requiring direct control from a companion computer; for example to implement collision avoidance.

> **Note** The API uses the PX4 [Offboard flight mode](https://docs.px4.io/en/flight_modes/offboard.html). The class can only be used with copter and VTOL vehicles (a PX4 limitation) and currently only supports *velocity setpoint commands* (PX4 additionally supports position and thrust setpoints). 

Client code must specify a setpoint before starting *Offboard mode*. DroneCore automatically resends setpoints at 20Hz (PX4 Offboard mode requires that setpoints are minimally resent at 2Hz). If more precise control is required, clients can call the setpoint methods at whatever rate is required.


## Preconditions

The following code assumes that you already have included DroneCore (`#include <dronecore/dronecore.h>`) 
and that there is a [connection](../guide/connections.md) to a `device` obtained as shown below:
```
Device &device = dc.device();
```

## Starting/Stopping Offboard Mode

To use offboard mode you must first create a setpoint using either [set_velocity_ned()](../api_reference/classdronecore_1_1_offboard.md#classdronecore_1_1_offboard_1a9e7f369a8f7459dc7705f4453a8c307d) or [set_velocity_body()](../api_reference/classdronecore_1_1_offboard.md#classdronecore_1_1_offboard_1ad9dc585be1bc2dba699cf089d4c274cc). You can use any setpoint you like - the vehicle will start acting on the current setpoint as soon as the mode starts. 

After you have created a setpoint call [start()](../api_reference/classdronecore_1_1_offboard.md#classdronecore_1_1_offboard_1a2b3aecd25645101a705cd1d80782311a) or [start_async()](../api_reference/classdronecore_1_1_offboard.md#classdronecore_1_1_offboard_1a5dd9d18eedb0e4a8f1bbbeebf6f99aa8) to switch to offboard mode. 

```cpp
// Create a null setpoint (no velocity or yaw components in any direction)
device.offboard().set_velocity_body({0.0f, 0.0f, 0.0f, 0.0f});

// Start offboard mode.
Offboard::Result offboard_result = device.offboard().start();
if (result != Offboard::Result::SUCCESS) {
        std::cerr << "Offboard::start() failed: " 
        << Offboard::result_str(offboard_result) << std::endl;
    }
```

The methods return/complete with a [Result](../api_reference/classdronecore_1_1_offboard.md#classdronecore_1_1_offboard_1a0f6e5e9f73289f27dc99abbb3ab572ed) indicating whether the command was successful. 
Above we use the synchronous API, and then use [Offboard::result_str()](../api_reference/classdronecore_1_1_offboard.md#classdronecore_1_1_offboard_1a8eb7467e48fe354d34bc45637ca9f5b8) to get a human readable string for the returned enum. 

You can change the setpoints as needed (new setpoints replace any old setpoints).

To stop offboard mode call [Offboard::stop()](../api_reference/classdronecore_1_1_offboard.md#classdronecore_1_1_offboard_1a2cecfbeb40bcd1d314fcfb07eb4dcd60) or [stop_async()](../api_reference/classdronecore_1_1_offboard.md#classdronecore_1_1_offboard_1afbe6f50f63d3bc43acc4dfc2f797ca0a). 
DroneCore will then clear the current setpoint and put the vehicle into 
[Hold flight mode](https://docs.px4.io/en/flight_modes/hold.html). 
The synchronous API is used as shown below:

```cpp
//Stop offboard mode
offboard_result = device.offboard().stop();
if (result != Offboard::Result::SUCCESS) {
        std::cerr << "Offboard::stop() failed: " 
        << Offboard::result_str(offboard_result) << std::endl;
    }
```

> **Note** Offboard mode can also be stopped by moving the vehicle into another mode (e.g. using the `Action` API).


## Velocity Setpoints

The API provides methods to set velocity and yaw components using the NED frame (`set_velocity_ned()`) and the body frame (`set_velocity_body()`). 
The difference is that NED is relative to an absolute co-ordinate system (North, East, Down) while Body frame is relative to the vehicle orientation (front, right, down).

The NED frame is used to move towards, or face the vehicle in, a specific compass direction. Body frame is usually used for tasks where the vehicle needs to deviate from a current path (e.g. to avoid an obstacle) or to rotate the vehicle at a specific rate. Movement up/down is the same in either frame. 

### Move in Compass Direction

The `set_velocity_ned()` can be used to move towards any particular compass direction - e.g. North, West, South-East, etc. 

Calling `set_velocity_ned()` using an initialiser list type declaration for the [VelocityNEDYaw](../api_reference/structdronecore_1_1_offboard_1_1_velocity_n_e_d_yaw.md) argument, the first three values are the 
velocity components in North, East, and Down directions (in metres/second). 

Examples:

* Head North at 3 m/s. 
  ```cpp
  device.offboard().set_velocity_ned({3.0f, 0.0f, 0.0f, 0.0f});
  ```
* Head North-West with 5 m/s on each velocity component (notice that a negative value is required on the `east_m_s` value to move West). 
  ```cpp
  device.offboard().set_velocity_ned({5.0f, -5.0f, 0.0f, 0.0f});
  ```


### Go Up or Down

Both co-ordinate systems use the same definition for "down", and both methods take an argument where the third value is used to specify the velocity component in this direction. The following examples show how you set the velocity component down (positive) or up (negative) using the two methods:

Examples:

* Go *up* at 2 m/s (note, negative value to go up!)
  ```cpp
  device.offboard().set_velocity_ned({0.0f, 0.0f, -2.0f, 0.0f});
  ```
* Go down at 3 m/s
  ```cpp
  device.offboard().set_velocity_body({0.0f, 0.0f, 3.0f, 0.0f});
  ```


### Turn/Yaw Vehicle to Face a Compass Direction

The `set_velocity_ned()` can be used to face the vehicle in a particular direction, independent of the direction of travel. 
The direction is specified in clockwise degrees relative to North (0 is North, 90 is East, 180 is South, etc.)

Calling `set_velocity_ned()` using an initialiser list type declaration for the `VelocityNEDYaw` argument, 
the final (fourth) value is the yaw direction.

Examples:
* Turn to face West
  ```cpp
  device.offboard().set_velocity_ned({0.0f, 0.0f, 0.0f, 270.0f});
  ```
* Turn to face North
  ```cpp
  device.offboard().set_velocity_ned({0.0f, 0.0f, 0.0f, 0.0f});
  ```

It is not possible to control the rate or direction that the vehicle will use to turn towards the setpoint direction (it will turn in whatever direction reaches the setpoint fastest).
  

### Turn/Yaw Vehicle in specified Direction/at Rate

The `set_velocity_body()` can be used to rotate the vehicle at a specific rate and in a specified direction. 
This is set in [VelocityBodyYawspeed::yawspeed_deg_s](../api_reference/structdronecore_1_1_offboard_1_1_velocity_body_yawspeed.md#structdronecore_1_1_offboard_1_1_velocity_body_yawspeed_1a6858130475964eb2d5c5a4236b7f1e31), as the angular rate in degrees/second. Looking from above, the vehicle will turn clockwise if the value is positive and anticlockwise if it is negative. 

Calling `set_velocity_body()` using an initialiser list type declaration the final (fourth) value is the yaw rate/direction.

Examples:

* Turn clock-wise at 60 degrees per second
  ```cpp
  device.offboard().set_velocity_body({0.0f, 0.0f, 0.0f, 60.0f});
  ```
* Turn anti clock-wise at 5 degrees per second
  ```cpp
  device.offboard().set_velocity_body({0.0f, 0.0f, 0.0f, -5.0f});
  ```
  
### Fly Forwards 

Use `set_velocity_body()` to set the velocity components relative to the body frame. To fly forwards, simply set the first parameter (`Offboard::VelocityBodyYawspeed::forward_m_s`) when the vehicle is not rotating.

```cpp
device.offboard().set_velocity_body({5.0f, 0.0f, 0.0f, 0.0f});
```

### Fly a Circle
    
To fly a circle, use `set_velocity_body()` with both forward and rotational components. This will force the vehicle to travel in a curved path.

```cpp
device.offboard().set_velocity_body({5.0f, 0.0f, 0.0f, 30.0f});
```

You can force the vehicle to fly sideways by using the (`Offboard::VelocityBodyYawspeed::right_m_s` value), and in the other direction by using a negative rotation value:
```cpp
// Fly a circle sideways
device.offboard().set_velocity_body({0.0f, -5.0f, 0.0f, -30.0f});
```


## Position/Thrust Setpoints

DroneCore does not support position or thrust setpoints (at time of writing).


## Waiting on Setpoints

The vehicle will obey the last setpoint called (when you call a setpoint the last one is cleared). 
The DroneCore examples use timers to separate commands (e.g. `sleep_for(seconds(8))`) but in a
real-world use case you might use telemetry or sensors to control when the setpoint is changed.


## Further Information

Additional information/examples for the Offboard API are linked below:

* [Example: Offboard Velocity](../examples/offboard_velocity.md)
* Integration tests:
  * [offboard_velocity.cpp](https://github.com/dronecore/DroneCore/blob/master/integration_tests/offboard_velocity.cpp)


