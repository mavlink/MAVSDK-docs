# Telemetry

The [Telemetry](../api_reference/classdronecode__sdk_1_1_telemetry.md) class provides simple methods for getting vehicle telemetry, including state and flight mode information.

All the methods have both synchronous and asynchronous versions, and users can set the rate at which the vehicle provides updates for each type of information. All the methods of a particular type (synchronous, asynchronous, and set_rate methods) are used in the same way.


## API Overview

The `Telemetry` API provides methods to return the following types of information:

* [Position](../api_reference/structdronecode__sdk_1_1_telemetry_1_1_position.md) - latitude and longitude in degrees, and altitude relative to sea level and to the takeoff altitude.
* [Battery](../api_reference/structdronecode__sdk_1_1_telemetry_1_1_battery.md) - voltage and percentage power remaining.
* [GroundSpeedNED](../api_reference/structdronecode__sdk_1_1_telemetry_1_1_ground_speed_n_e_d.md) - velocity components in NED coordinates.
* Vehicle attitude/orientation - as a [Quaternion](../api_reference/structdronecode__sdk_1_1_telemetry_1_1_quaternion.md) or [EulerAngle](../api_reference/structdronecode__sdk_1_1_telemetry_1_1_euler_angle.md)
* [GPSInfo](../api_reference/structdronecode__sdk_1_1_telemetry_1_1_g_p_s_info.md) - type of fix, if any, and number of satellites.
* [Health](../api_reference/structdronecode__sdk_1_1_telemetry_1_1_health.md) - calibration status of various sensors and confirmation that position estimates are good enough for position control.
* [RCStatus](../api_reference/structdronecode__sdk_1_1_telemetry_1_1_r_c_status.md) - connection status, signal strength, and whether RC has ever been connected.

In addition there are a number of methods that return vehicle "state":
* Current flight mode ([FlightModes](../api_reference/classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1a881d44b3a1522ea14bff8834edd4145a)).
* Whether the vehicle is "all healthy" (aggregates the vehicle [Health](../api_reference/structdronecode__sdk_1_1_telemetry_1_1_health.md) information). This is used to check if the vehicle is *ready* to arm.
* Whether the vehicle is armed/disarmed.
* Whether the vehicle is flying/in air.


## Create the Plugin

> **Tip** `Telemetry` objects are created in the same way as other DroneCore plugins. General instructions are provided in the topic: [Using Plugins](../guide/using_plugins.md).

The main steps are:

1. Link the plugin library into your application. Do this by adding `dronecore_telemetry` to the `target_link_libraries` section of the app's *cmake* build definition file

   ```cmake
   target_link_libraries(your_application_name
     dronecore
     ...
     dronecore_telemetry
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
1. Create a shared pointer to an instance of `Telemetry` instantiated with the `system`: 
   ```
   #include <dronecore/telemetry.h>
   auto telemetry = std::make_shared<Telemetry>(system);
   ```

The `telemetry` pointer can then used to access the plugin API (as shown in the following sections).


## Setting the Update Rate {#update-rate}

The telemetry update rate determines the frequency at which callbacks will be invoked with new information, and also the probable "freshness" of data obtained when using synchronous telemetry APIs. The default update rate depends on the autopilot and may also be limited by the characteristics of the communications channel. You can set the rate for *each* type of telemetry, and both synchronous or asynchronous rate-setting methods are provided. 

> **Note** For PX4 running on hardware the *default* rates are set on a per-mode basis in [mavlink_main.cpp](https://github.com/PX4/Firmware/blob/master/src/modules/mavlink/mavlink_main.cpp#L2025) (search on `configure_stream`). For PX4 running on SITL, the default rates are defined in the [init file](https://dev.px4.io/en/simulation/#example-startup-file).

The rate-setting methods are all used in the same way, so we just show one example for both the asynchronous and synchronous methods below. In both cases we set the rate for position updates.

To set the position update rate synchronously (in this case using [set_rate_position()](../api_reference/classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1ae7a6e1313b1508fef7163287aa77a6da)):
```cpp
// Set position update rate to 1 Hz.
const Telemetry::Result set_rate_result = telemetry->set_rate_position(1.0);
if (set_rate_result != Telemetry::Result::SUCCESS) {
    // handle rate-setting failure (in this case print error)
    std::cout << "Setting rate failed:" << Telemetry::result_str(set_rate_result) << std::endl;
}
```

To set the position update rate asynchronously with [set_rate_position_async()](../api_reference/classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1aeac791b919a172f96b9b3e6ecb07e288) (here we use a *promise* to block until we have a result):
```cpp
{
    std::cout << "Setting rate updates..." << std::endl;

    auto prom = std::make_shared<std::promise<Telemetry::Result>>();
    auto future_result = prom->get_future();
    // Set position update rate to 1 Hz.
    telemetry->set_rate_position_async(1.0, [prom](Telemetry::Result result) {
        prom->set_value(result); //fulfill promise
    });

    //Block until promise is fulfilled (in callback function)
    const Telemetry::Result result = future_result.get();
    if (result != Telemetry::Result::SUCCESS) {
        // handle rate-setting failure (in this case print error)
        std::cout << "Setting telemetry rate failed (" << Telemetry::result_str(result) << ")." << std::endl;
    }
}
```


## Getting Regular Updates

The best way to get telemetry updates is to use the asynchronous methods. These methods are non-blocking - they take a callback function argument and return immediately. The callback will be invoked with a populated `struct` of the associated type as soon as an update message arrives from the vehicle. The rate at which this occurs can be set through the API [as discussed above](#update-rate). 

For example, the [Telemetry::position_async()](../api_reference/classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1aeac791b919a172f96b9b3e6ecb07e288) has the following prototype, where [position_callback_t](../api_reference/classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1a0b6f61942324aa2cb56e4c6cc97f41c3) is called with a populated [Position](../api_reference/structdronecode__sdk_1_1_telemetry_1_1_position.md):
```cpp
void dronecore::Telemetry::position_async(position_callback_t callback)
```

The code fragment below shows this method being use with a lambda function for the callback, which simply prints out the current position and altitude).
```cpp
telemetry->position_async([](Telemetry::Position position) {
    std::cout << "Altitude: " << position.relative_altitude_m << " m" << std::endl
              << "Latitude: " << position.latitude_deg << std::endl
              << "Longitude: " << position.longitude_deg << std::endl;
});
```


## Detecting Changes (only)

The asynchronous callbacks are updated every time new information is provided by the vehicle. For some types of telemetry you may only wish to report only when the value changes.

The example below shows how to use [flight_mode_async()](../api_reference/classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1ac8842dec06db4bd54c8c2ba2deb0d34a) to report only when the current flight mode changes. The example uses a lambda function callback that captures a variable for the last mode. This variable is compared to the current flight mode to determine whether the value has changed and needs to be reported.

```cpp
// Set up callback to monitor flight mode 'changes' 
Telemetry::FlightMode oldFlightMode=Telemetry::FlightMode::UNKNOWN;
telemetry->flight_mode_async([&oldFlightMode](Telemetry::FlightMode flightMode) {
    if (oldFlightMode != flightMode) {
        //Flight mode changed. Print!
        std::cout << "FlightMode: " << Telemetry::flight_mode_str(flightMode) << std::endl;
        oldFlightMode=flightMode; //Save updated mode.
    }
});
```

This same approach can be used to report only messages that meet some condition.

> **Tip** In future we may add a mechanism *in the API* to support just reporting changes: [Issue #63](https://github.com/dronecore/DroneCore/issues/63).


## Blocking Telemetry Requests (State Management)

Some commands/vehicle operations must be performed in a certain sequence, or can only be called when the vehicle reaches a certain state. For example, in order to takeoff the vehicle must first be armed, and in order to arm, the vehicle must have a home position/GPS lock. For these cases you will want to monitor for the vehicle being in a certain state and block other commands until it is ready to proceed. 

Often the easiest approach is to use synchronous methods and poll for the result. For example, the following code shows how you might poll for whether the vehicle is ready to arm ([health_all_ok()](../api_reference/classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1a630c91d8067e4084c4f303513a0aeb29)).

```cpp
// Check if vehicle is ready to arm
while (!telemetry->health_all_ok()) {
    std::cout << "Vehicle not ready to arm" << std::endl;
    std::this_thread::sleep_for(std::chrono::seconds(1));
}
// now ready to arm ...
```

Similarly, you can use the asynchronous method and block 

```cpp
{
    std::cout << "Waiting for system to be ready" << std::endl;
    auto prom = std::make_shared<std::promise<void>>();
    auto future_result = prom->get_future();
    telemetry->health_all_ok_async(
    [prom](bool result) {
        //fulfill promise if health is OK
        if (result) {// health OK
            prom->set_value();
        }
    });
    
    future_result.get(); //Block until promise is fulfilled.
    // Now ready to arm
}
```

Depending on the architecture of your application, you may even wish to arm the vehicle in your callback function. Usually though it is easier to understand program flow using the approach above.


## Further Information

Additional information/examples for the Telemetry API are linked below:

* [DroneCore Examples](../examples/README.md)
* Integration tests:
  * [telemetry_async.cpp](https://github.com/dronecore/DroneCore/blob/{{ book.github_branch }}/integration_tests/telemetry_async.cpp)
  * [telemetry_health.cpp](https://github.com/dronecore/DroneCore/blob/{{ book.github_branch }}/integration_tests/telemetry_health.cpp)
  * [telemetry_modes.cpp](https://github.com/dronecore/DroneCore/blob/{{ book.github_branch }}/integration_tests/telemetry_modes.cpp)
  * [telemetry_simple.cpp](https://github.com/dronecore/DroneCore/blob/{{ book.github_branch }}/integration_tests/telemetry_simple.cpp)

