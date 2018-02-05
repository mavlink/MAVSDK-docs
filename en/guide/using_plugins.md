# Using Plugins (Managing Devices)

Access to drone information, telemetry and control objects are provided by a number of different *plugins*. For example, the [Action](../api_reference/classdronecore_1_1_action.md) plugin is used to arm, takeoff and land the vehicle, while the [Telemetry](../guide/telemetry.md) plugin can be used to query the device GPS status, flight mode, etc. A separate plugin instance must be created for each device that needs it. 

> **Note** All plugins are added/used in the same way. This topic uses the `Action` plugin for the purposes of the demonstration. 

To use a plugin first link the plugin library into the application. Do this by adding it to the `target_link_libraries` section of the app's *cmake* build definition file:

```cmake
target_link_libraries(takeoff_and_land
   dronecore
   dronecore_action
)
```

> **Note** Plugins are named using the convention **dronecore\__plugin\_name_.so**. For more information see [Building C++ Apps](../guide/toolchain.md)


In the application source code: 
1. `#include` the plugin header file. 
   ```cpp
   #include <dronecore/action.h>
   ```
1. Connect to a `Device` object (see [Connecting to Devices](../guide/connections.md)).
1. Make a shared pointer to the plugin object, specifying the `Device` it is to be used with:
   ```cpp
   auto action = std::make_shared<Action>(&device);
   ```
1. The pointer can then be used to invoke actions on the specified device. For example, to takeoff you would call the API as shown:
   ```cpp
   action->takeoff();
   ```
