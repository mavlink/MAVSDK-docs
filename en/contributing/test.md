# Testing


*DroneCore* has both unit and integration tests, written using the *Google C++ Test Framework*. 
The tests are run every time new code is committed to our codelines, and must pass before the code can be merged.

This topic shows how to run the existing tests and write new ones.


## Running Unit Tests

To run all unit tests:

```
make run_unit_tests
```


## Running Integration Tests

Tests can be run against the simulator (either manually starting PX4 SITL or letting the tests start it automatically) or against a real vehicle.

> **Tip** To run SITL you will need to install the *Gazebo* simulator. 
This is included as part of the standard PX4 installation for [macOS](https://dev.px4.io/en/setup/dev_env_mac.html)
and [Linux](https://dev.px4.io/en/setup/dev_env_linux.html#development-toolchain). It does not run on Windows.

### Autostart PX4 SITL

Make sure that the [PX4 Gazebo simulation](https://dev.px4.io/en/simulation/gazebo.html) is built and works:

```
cd wherever/Firmware/
make posix gazebo
```

Then press **Ctrl+C** to stop the simulation and run the integration tests:

```
cd wherever/DroneCore/
AUTOSTART_SITL=1 make run_integration_tests
```

To run the tests without the 3D viewer (gzclient), use:

```
AUTOSTART_SITL=1 HEADLESS=1 make run_integration_tests
```

### Run PX4 SITL Manually

Build and run the PX4 simulation manually:

```
cd wherever/Firmware/
make posix gazebo
```

Then run the tests as shown:
```
make run_integration_tests
```

### Run With a Real Vehicle

> **Warning** Some of the tests might not be suited for real vehicles, especially the takeoff and kill test!

Make sure you are connected to a vehicle and check the connection using e.g.:

```
make && build/default/integration_tests_runner --gtest_filter="SitlTest.TelemetryAsync"
```


## Gtest Tricks

To list all integration tests:
```
make && build/default/integration_tests_runner --gtest_list_tests
```

To run a single integration test:
```
make && build/default/integration_tests_runner --gtest_filter="SitlTest.TelemetryAsync"
```

To run all telemetry tests:
```
make && build/default/integration_tests_runner --gtest_filter="SitlTest.Telemetry*"
```

## Writing Tests {#writing_tests}

The [Google Test Primer](https://github.com/google/googletest/blob/master/googletest/docs/Primer.md)
provides an excellent overview of how tests are written and used.

Most of the existing plugins do not have unit tests, because we do not yet have the ability to [mock MAVLink communications](https://github.com/dronecore/DroneCore/issues/148) (needed to test most plugins). In consequence integration tests are used instead, 
with the simulator providing appropriate MAVLink messages.

> **Note** This section explains how to add tests for the default DroneCore code. 
> Most of the information is also relevant to SDK/Extension plugin tests. See
> [SDK Creation > Testing](../guide/sdk.md#testing) for information about how
> to add tests for extensions to the test runner(s).


### Writing Unit Tests

Unit tests are stored as separate files in the same directory as their associated source code. Often they test the implementation (rather than the public API), and hence are named with the suffix **_impl_test.cpp**.


#### Unit Test Files/Code

Unit tests typically include the file to be tested, **dronecore.h**, and **gtest.h**. There are no standard shared test unit resources so 
test functions are declared using `TEST`. All tests in a file should share the same test-case name (the first argument to `TEST`).

The skeleton [example plugin unit test](https://github.com/dronecore/DroneCore/blob/master/external_example/plugins/example/example_impl_test.cpp) is shown below: 
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

#### Adding Unit Tests

In order to run a unit test its file needs to be added to the DroneCore unit test program (`unit_tests_runner`). For the core plugins this is done in the main DroneCore [DroneCore/CMakeLists.txt](https://github.com/dronecore/DroneCore/blob/master/CMakeLists.txt#L187) file:
```cmake
    add_executable(unit_tests_runner
        core/global_include_test.cpp
        core/mavlink_channels_test.cpp
        core/unittests_main.cpp
        core/http_loader_test.cpp
        core/timeout_handler_test.cpp
        core/call_every_handler_test.cpp
        ${plugin_unittest_source_files}
        ${unit_tests_src}
    )
```

### Writing Integration Tests

DroneCore provides the `integration_tests_runner` application for running the integration tests and 
some helper code to make it easier to log tests and run them against the simulator.

> **Tip** Check out the [Google Test Primer](https://github.com/google/googletest/blob/master/googletest/docs/Primer.md) 
> and the [integration_tests](https://github.com/dronecore/DroneCore/tree/develop/integration_tests) 
> for our existing plugins to better understand how to write your own!

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
    telemetry_simple
    telemetry_async
    telemetry_modes
    telemetry_health
    simple_hover
    async_hover
    takeoff_and_kill
    offboard_velocity
    logging
    info
    mission
    mission_change_speed
    mission_survey
    curl
)
```

