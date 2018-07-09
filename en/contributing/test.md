# Testing

The SDK has both unit and integration tests, written using the [Google C++ Test Framework](https://github.com/google/googletest/blob/master/googletest/docs/Primer.md) (`gtest`). 
The unit tests are run every time new code is committed to the SDK codelines, and must pass before the code can be merged.

This topic shows how to run the existing tests.

> **Tip** For information on *writing* tests see: [Writing Plugins > Test Code](../contributing/plugins.md#testing).


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
cd wherever/DronecodeSDK/
AUTOSTART_SITL=1 make run_integration_tests
```

To run the tests without the 3D viewer (*gzclient*), use:

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
make && build/default/integration_tests/integration_tests_runner --gtest_filter="SitlTest.TelemetryAsync"  
```


## Gtest Tricks

To list all integration tests:
```
make && build/default/integration_tests/integration_tests_runner --gtest_list_tests
```

To run a single integration test:
```
make && build/default/integration_tests/integration_tests_runner --gtest_filter="SitlTest.TelemetryAsync"
```

To run all telemetry tests:
```
make && build/default/integration_tests/integration_tests_runner --gtest_filter="SitlTest.Telemetry*"
```
