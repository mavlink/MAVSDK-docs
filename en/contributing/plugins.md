# Writing Plugins

DroneCore is split into a [core](https://github.com/dronecore/DroneCore/tree/{{ book.github_branch }}/core) and [plugins](https://github.com/dronecore/DroneCore/tree/{{ book.github_branch }}/plugins). 

Plugins that are located in the *correct location* (a subfolder of **/plugins**) and have the *correct structure* are included at compile time. The *cmake* script [autogenerate_plugin_container.cmake](https://github.com/dronecore/DroneCore/blob/{{ book.github_branch }}/autogenerate_plugin_container.cmake) takes care of including the plugin folders and integration tests.

> **Note** Plugins can also be defined in [DroneCore Extensions](../guide/dronecore_extensions.md). 
> These are defined and tested in exactly the same way as "standard" DroneCore plugins. 

## Plugin Architecture

Plugins should be written so that they are independent of each other (they will still need to be dependent on the core source). This allows plugins to be removed/replaced as needed at the cost of some duplicated functionality across the plugin modules.

The code for each plugin and its unit test (if defined) is stored in a sub-folder of the **plugins** directory. Integration tests for all plugins in the library are stored in **integration_tests**.

A simplified view of the folder structure is shown below (showing relevant directories for both DroneCore and a DroneCore Extension): 

```
├── DroneCore
│   ├── core
│   ├── integration_tests
│   └── plugins
│       ├── action
│       ├── ...
│       └── telemetry
├── DroneCore_Extensions
│   ├── integration_tests
│   └── plugins
│       ├── camera
│       ├── another_plugin
│       └── etc.
```

Each plugin must have the same files/structure, as shown for the "example" plugin below.
```
└── plugins
    └── example 
        ├── CMakeLists.txt
        ├── example.cpp
        ├── example.h
        ├── example_impl.cpp
        ├── example_impl.h
        └── example_impl_test.cpp  ##optional
```

## Create a Plugin

To create a new C++ plugin, duplicate either a [standard plugin](https://github.com/dronecore/DroneCore/tree/{{ book.github_branch }}/plugins) (e.g. 
[Action](https://github.com/dronecore/DroneCore/tree/{{ book.github_branch }}/plugins/action), 
[Telemetry](https://github.com/dronecore/DroneCore/tree/{{ book.github_branch }}/plugins/telemetry), etc.) or the [example](https://github.com/dronecore/DroneCore/tree/{{ book.github_branch }}/external_example/plugins/example/) plugin into the **plugins** directory (either in the DroneCore tree or a [DroneCore Extension](../guide/dronecore_extensions.md) folder).

Modify the plugin as needed and update its [CMakeLists.txt](https://github.com/dronecore/DroneCore/blob/{{ book.github_branch }}/external_example/plugins/example/CMakeLists.txt) as appropriate:
* Modify plugin filenames as appropriate
* Add additional libraries using the variable `additional_libs`:
  ```
  set(additional_libs "library_name" PARENT_SCOPE)
  ```
* Add required includes with `additional_includes`:
  ```
  set(additional_includes "include_dir" PARENT_SCOPE)
  ```
* You can also add tests with `unittest_source_files`, as [discussed below](#adding_unit_tests).


## Plugin Code

The [standard plugins](https://github.com/dronecore/DroneCore/tree/{{ book.github_branch }}/plugins) can be reviewed for guidance on
how to write plugin code, including how to send and process MAVLink messages.


### Plugin Enable/Disable

DroneCore provides virtual methods that a plugin should implement allow DroneCore to better manage resources. For example, to prevent callback being created before the `Device` is instantiated, or messages being sent when a vehicle is not connected.

Plugin authors should provide an implementation class that derives from `PluginImplBase` (**core/plugin_impl_base.h**) and implements the following pure virtual methods:
* [init()](#init)/[deinit()](#deinit): These are called when a device is created and just before it is destroyed. These should be used for setting up and cleaning everything that depends on having the `Device` instantiated. This includes calls that set up callbacks.
* [enable()](#enable)/[disable()](#disable): These are called when a vehicle is discovered or has timed out. They should be used for managing resources needed to access a connected device/vehicle (e.g. getting a parameter or changing a setting).


> **Note** The methods are currently optional. For a transitional period, runtime warnings will be displayed if the methods are not implemented.

Additional detail is provided for methods below.


##### init() {#init}
```cpp
virtual void init() = 0
```

The `init()` method is called when a plugin is instantiated. This happens when a `Device` is constructed (this does not mean that the device actually exists and is connected - it might just be an empty dummy device).

Plugins should do initialization steps with other parts of DroneCore at this state, e.g. set up callbacks with `_parent` (`DeviceImpl`).

##### deinit() {#deinit}
```cpp
virtual void deinit() = 0
```
The `deinit()` method is called before a plugin is destroyed. This usually happens only at the very end, when a DroneCore instance is destroyed.

Plugins should cleanup anything that was set up during `init()`.

##### enable() {#enable}
```cpp
virtual void enable() = 0
```
The `enable()` method is called when a device is discovered (connected). Plugins should do all initialization/configuration steps that require a device to be connected. For example, setting/getting parameters.

If any threads, call_every or timeouts are needed, they can be started in this method.

##### disable() {#disable}
```cpp
virtual void disable() = 0
```
The `disable()` method is called when a device has timed out. The method is also called before `deinit()` is called to stop any devices with active plugins from communicating (in order to prevent warnings and errors because communication to the device no longer works).

If any threads, call_every, or timeouts are running, they should be stopped in this method.


## Test Code {#testing}

Tests must be created for all new and updated plugin code. 
The tests should be exhaustive, and cover all aspects of using the plugin API.

The [Google Test Primer](https://github.com/google/googletest/blob/master/googletest/docs/Primer.md)
provides an excellent overview of how tests are written and used.

> **Note** Testing is the same for plugins that are part of DroneCore and part of 
[DroneCore Extensions](../guide/dronecore_extensions.md).


### Writing Unit Tests

Most of the existing plugins do not have unit tests, because we do not yet have the ability to [mock MAVLink communications](https://github.com/dronecore/DroneCore/issues/148) (needed to test most plugins). 
Unit tests are therefore considered optional!

> **Tip** Comprehensive integration tests should be written instead, with the simulator providing appropriate MAVLink messages.

#### Adding Unit Tests {#adding_unit_tests}

Unit tests are stored as separate files in the same directory as their associated source code. 
Often they test the implementation (rather than the public API), 
and hence are named with the suffix **_impl_test.cpp**.

In order to include a test in the DroneCore unit test program (`unit_tests_runner`), 
its file name must be added to the `$unittest_source_files` variable in the 
plugin **CMakeLists.txt** file (you can add multiple files).

The example plugin adds the **example_impl_test.cpp** unit test as shown below:

```cmake
set(unittest_source_files
    # Add unit test file(s) for plugin
    example_impl_test.cpp
    PARENT_SCOPE
)
```

> **Note** Unit tests for *core* functionality are added in the main [DroneCore/CMakeLists.txt](https://github.com/dronecore/DroneCore/blob/{{ book.github_branch }}/CMakeLists.txt#L187) file. 


#### Unit Test Code

Unit tests typically include the file to be tested, **dronecore.h**, and **gtest.h**. There are no standard shared test unit resources so 
test functions are declared using `TEST`. All tests in a file should share the same test-case name (the first argument to `TEST`).

The skeleton [example plugin unit test](https://github.com/dronecore/DroneCore/blob/{{ book.github_branch }}/external_example/plugins/example/example_impl_test.cpp) is shown below: 
```cpp
#include "example_impl.h"
#include "dronecore.h"
#include "global_include.h"
#include <gtest/gtest.h>

namespace dronecore {

TEST(ExampleImpl, NoTest)
{
    ASSERT_TRUE(true);
}

} // namespace dronecore
```



### Writing Integration Tests {#integration_tests}

DroneCore provides the `integration_tests_runner` application for running the integration tests and 
some helper code to make it easier to log tests and run them against the simulator.

> **Tip** Check out the [Google Test Primer](https://github.com/google/googletest/blob/master/googletest/docs/Primer.md) 
> and the [integration_tests](https://github.com/dronecore/DroneCore/tree/develop/integration_tests) 
> for our existing plugins to better understand how to write your own!


#### Adding Integration Tests

In order to run an integration test it needs to be added to the `integration_tests_runner` program.

Integration tests for core functionality and plugins delivered by the project 
are stored in [DroneCore/integration_tests](https://github.com/dronecore/DroneCore/tree/develop/integration_tests). 
The files are added to the test program in that folder's 
[CMakeLists.txt](https://github.com/dronecore/DroneCore/blob/master/integration_tests/CMakeLists.txt#L12) file:

```cmake
list(APPEND integration_tests
    simple_connect
    async_connect
    # ...
    mission_change_speed
    mission_survey
    curl
)
```

Integration tests for [DroneCore Extensions](../guide/dronecore_extensions.md) are handled in the exactly the same way: 
```
external_example       ## The (example) SDK/external plugin directory.
├── integration_tests
│   ├── CMakeLists.txt
│   └── hello_world.cpp
```

Example extension **CMakeLists.txt** file:
```cmake
list(APPEND integration_tests
    # Add the cpp file for each integration test on its own line
    hello_world
)
```
 

#### Integration Test Files/Code

The main DroneCore-specific functionality is provided by [integration_test_helper.h](https://github.com/dronecore/DroneCore/blob/master/core/integration_test_helper.h). 
This provides access to the [Plugin/Test Logger](../contributing/dev_logging.md) 
and a shared test class `SitlTest` for setting up and tearing down the PX4 simulator.

> **Note** All tests must be declared using `TEST_F` and have a first argument `SitlTest` as shown. This is required
> in order to use the shared class to set up and tear down the simulator between tests.

The example integration test [hello_world.cpp](https://github.com/dronecore/DroneCore/blob/master/external_example/integration_tests/hello_world.cpp) demonstrates this below. 

```cpp
#include <iostream>
#include <unistd.h>
#include "dronecore.h"
#include "integration_test_helper.h"

using namespace dronecore;

TEST_F(SitlTest, ExternalExampleHello)
{
    DroneCore dc;

    DroneCore::ConnectionResult ret = dc.add_udp_connection();
    ASSERT_EQ(ret, DroneCore::ConnectionResult::SUCCESS);

    // Wait for device to connect via heartbeat.
    std::this_thread::sleep_for(std::chrono::seconds(2));

    // One vehicle should have connected.
    std::vector<uint64_t> uuids = dc.device_uuids();
    EXPECT_EQ(uuids.size(), 1);

    // Apparently it can say hello.
    dc.device().example().say_hello();
}
```


## Example Code

> **Note** It is quicker and easier to write and modify [integration tests](#integration_tests) than examples. 
> Do not write example code until the plugin has been accepted!

A simple example should be written that demonstrates basic usage of its API by 3rd parties. 
The example need not cover all functionality, but should demonstrate enough that developers 
can see how it is used and how the example might be extended.

Where possible examples should demonstrate realistic use cases such that the code
can usefully be copied and reused by external developers.


## Documentation

### In-Source Comments

The public API must be fully documented using [Doxygen](http://doxygen.nl/manual/docblocks.html) markup.
All items should minimally have a brief description (preceded by the `@brief` tag).

> **Tip** The in-source comments will be compiled to markdown and included in the [API Reference](../api_reference/README.md).
> The process is outlined in [Documentation > API Reference](../contributing/documentation.md#api-reference).

Internal/implementation classes need not be documented, but should be written so that their use can be inferred.

### Example Code Documentation 

The plugin example should be documented in markdown following the same pattern as the existing [examples](../examples/README.md). 

Generally this involves explaining what the example does and displaying the source.
The explanation of how the code works is usually deferred to [guide documentation](#guide).


### Guide Documentation {#guide}

Ideally, [guide](../guide/README.md) documentation should be created. This should be based on example code.

The purpose of the guide is to:
* Show how different parts of the API can be used together
* Highlight usage patterns and limitations that may not be obvious from API reference
* Provide code fragments that can easily be reused

