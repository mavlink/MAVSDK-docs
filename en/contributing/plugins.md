# Writing Plugins

The *Dronecode SDK* is split into a [core](https://github.com/dronecore/DroneCore/tree/{{ book.github_branch }}/core) and multiple independent [plugins](https://github.com/dronecore/DroneCore/tree/{{ book.github_branch }}/plugins). 

Plugins that are located in the *correct location* (a subfolder of **/plugins**) and have the *correct structure* are built at compile time. 
The [CMakeLists.txt](https://github.com/dronecore/DroneCore/blob/{{ book.github_branch }}/CMakeLists.txt) takes care of including the plugin folders and integration tests.

> **Note** Plugins can also be defined in [SDK Extensions](../guide/sdk_extensions.md). 
> These are defined and tested in exactly the same way as "standard" SDK plugins. 

## Plugin Architecture

Plugins should be written so that they are independent of each other (they will still need to be dependent on the core source). 
This allows plugins to be removed/replaced as needed at the cost of some duplicated functionality across the plugin modules.

The code for each plugin (and its unit test if one has been defined) is stored in a sub-folder of the **plugins** directory. 
Integration tests for all plugins in the library are stored in **integration_tests**.

A simplified view of the folder structure is shown below (showing relevant directories for both the SDK and [SDK Extensions](../guide/sdk_extensions.md)): 

```
├── DroneCore
│   ├── core
│   ├── integration_tests
│   └── plugins
│       ├── action
│       ├── ...
│       └── telemetry
├── SDK_Extensions
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
[Telemetry](https://github.com/dronecore/DroneCore/tree/{{ book.github_branch }}/plugins/telemetry), etc.) or the [example](https://github.com/dronecore/DroneCore/tree/{{ book.github_branch }}/external_example/plugins/example/) plugin into the **plugins** directory (either in the DroneCore tree or a [SDK Extension](../guide/sdk_extensions.md) folder).

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


### Plugin Base Class

All plugins should derive their implementation from `PluginImplBase` (**core/plugin_impl_base.h**) and override virtual methods as needed.


### Plugin Enable/Disable

The SDK provides virtual methods that a plugin should implement to allow the core to better manage resources. 
For example, to prevent callback being created before the `System` is instantiated, or messages being sent when a vehicle is not connected.

Plugin authors should provide an implementation of the following `PluginImplBase` pure virtual methods:
* [init()](#init)/[deinit()](#deinit): These are called when a system is created and just before it is destroyed. These should be used for setting up and cleaning everything that depends on having the `System` instantiated. This includes calls that set up callbacks.
* [enable()](#enable)/[disable()](#disable): These are called when a vehicle is discovered or has timed out. They should be used for managing resources needed to access a connected system/vehicle (e.g. getting a parameter or changing a setting).

The [external example](https://github.com/dronecore/DroneCore/tree/{{ book.github_branch }}/external_example) provides a minimal implementation.

Additional detail is provided for methods below.


##### init() {#init}
```cpp
virtual void init() = 0
```

The `init()` method is called when a plugin is instantiated. 
This happens when a `System` is constructed (this does not mean that the system actually exists and is connected - it might just be an empty dummy system).

Plugins should do initialization steps with other parts of the SDK at this state, e.g. set up callbacks with `_parent` (`DeviceImpl`).

##### deinit() {#deinit}
```cpp
virtual void deinit() = 0
```
The `deinit()` method is called before a plugin is destroyed. This usually happens only at the very end, when a `Dronecode SDK` instance is destroyed.

Plugins should cleanup anything that was set up during `init()`.

##### enable() {#enable}
```cpp
virtual void enable() = 0
```
The `enable()` method is called when a system is discovered (connected). 
Plugins should do all initialization/configuration steps that require a system to be connected. 
For example, setting/getting parameters.

If any threads, call_every or timeouts are needed, they can be started in this method.

##### disable() {#disable}
```cpp
virtual void disable() = 0
```
The `disable()` method is called when a system has timed out. 
The method is also called before `deinit()` is called to stop any systems with active plugins from communicating (in order to prevent warnings and errors because communication to the system no longer works).

If any threads, call_every, or timeouts are running, they should be stopped in this method.


## Test Code {#testing}

Tests must be created for all new and updated plugin code. 
The tests should be exhaustive, and cover all aspects of using the plugin API.

The [Google Test Primer](https://github.com/google/googletest/blob/master/googletest/docs/Primer.md)
provides an excellent overview of how tests are written and used.

> **Note** Testing is the same for plugins in SDK and the [SDK Extensions](../guide/sdk_extensions.md).


### Writing Unit Tests

Most of the existing plugins do not have unit tests, 
because we do not yet have the ability to [mock MAVLink communications](https://github.com/dronecore/DroneCore/issues/148) (needed to test most plugins). 
Unit tests are therefore considered optional!

> **Tip** Comprehensive integration tests should be written instead, with the simulator providing appropriate MAVLink messages.

#### Adding Unit Tests {#adding_unit_tests}

Unit test files are stored in the same directory as their associated source code. 
Often they test the implementation (rather than the public API), 
and hence are named with the suffix **_impl_test.cpp**.

In order to include a test in the SDK unit test program (`unit_tests_runner`), 
it must be added to the `UNIT_TEST_SOURCES` variable in the plugin **CMakeLists.txt** file.

For example, to add the **example_impl_test.cpp** unit test you would 
append the following lines to its **CMakeLists.txt**:

```cmake 
list(APPEND UNIT_TEST_SOURCES
    ${CMAKE_SOURCE_DIR}/plugins/mission/example_impl_test.cpp
)
set(UNIT_TEST_SOURCES ${UNIT_TEST_SOURCES} PARENT_SCOPE)
``` 


#### Unit Test Code

Unit tests typically include the file to be tested, **dronecore.h**, and **gtest.h**. 
There are no standard shared test unit resources so test functions are declared using `TEST`. 
All tests in a file should share the same test-case name (the first argument to `TEST`).

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

The SDK provides the `integration_tests_runner` application for running the integration tests and some helper code to make it easier to log tests and run them against the simulator.

> **Tip** Check out the [Google Test Primer](https://github.com/google/googletest/blob/master/googletest/docs/Primer.md) 
> and the [integration_tests](https://github.com/dronecore/DroneCore/tree/{{ book.github_branch }}/integration_tests) 
> for our existing plugins to better understand how to write your own!


#### Adding Integration Tests

In order to run an integration test it needs to be added to the `integration_tests_runner` program.

Integration tests for core functionality and plugins delivered by the project 
are stored in [DroneCore/integration_tests](https://github.com/dronecore/DroneCore/tree/{{ book.github_branch }}/integration_tests). 
The files are added to the test program in that folder's 
[CMakeLists.txt](https://github.com/dronecore/DroneCore/blob/{{ book.github_branch }}/integration_tests/CMakeLists.txt) file:

```cmake
# This includes all GTests that run integration tests
add_executable(integration_tests_runner
    ../core/unittests_main.cpp
    simple_connect.cpp
    async_connect.cpp
    telemetry_simple.cpp
    ...
    mission_change_speed.cpp
    mission_survey.cpp
    gimbal.cpp
    transition_multicopter_fixedwing.cpp
    follow_me.cpp
)
```

Integration tests for [SDK Extensions](../guide/sdk_extensions.md) are handled in the exactly the same way: 
```
external_example       ## The (example) SDK/external plugin directory.
├── integration_tests
│   ├── CMakeLists.txt
│   └── hello_world.cpp
```

Example extension **CMakeLists.txt** file:
```cmake
add_executable(external_example_integration_tests_runner
    ${CMAKE_SOURCE_DIR}/core/unittests_main.cpp
    hello_world.cpp
)
```
 

#### Integration Test Files/Code

The main SDK-specific functionality is provided by [integration_test_helper.h](https://github.com/dronecore/DroneCore/blob/{{ book.github_branch }}/core/integration_test_helper.h). 
This provides access to the [Plugin/Test Logger](../contributing/dev_logging.md) and a shared test class `SitlTest` for setting up and tearing down the PX4 simulator.

> **Note** All tests must be declared using `TEST_F` and have a first argument `SitlTest` as shown. 
  This is required in order to use the shared class to set up and tear down the simulator between tests.

The example integration test [hello_world.cpp](https://github.com/dronecore/DroneCore/blob/{{ book.github_branch }}/external_example/integration_tests/hello_world.cpp) demonstrates this below. 

```cpp
#include <iostream>
#include <unistd.h>
#include "dronecore.h"
#include "plugins/example/example.h"
#include "integration_test_helper.h"

using namespace dronecore;

TEST_F(SitlTest, ExampleHello)
{
    DroneCore dc;

    ConnectionResult ret = dc.add_udp_connection();
    ASSERT_EQ(ret, ConnectionResult::SUCCESS);

    // Wait for system to connect via heartbeat.
    std::this_thread::sleep_for(std::chrono::seconds(2));
    ASSERT_TRUE(dc.is_connected());

    System &system = dc.system();
    auto example = std::make_shared<Example>(system);

    // Apparently it can say hello.
    example->say_hello();
}
```


## Example Code

> **Note** It is quicker and easier to write and modify [integration tests](#integration_tests) than examples. 
> Do not write example code until the plugin has been accepted!

A simple example should be written that demonstrates basic usage of its API by 3rd parties. 
The example need not cover all functionality, but should demonstrate enough that developers can see how it is used and how the example might be extended.

Where possible examples should demonstrate realistic use cases such that the code can usefully be copied and reused by external developers.


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

