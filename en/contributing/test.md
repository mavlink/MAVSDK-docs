# Testing

## Unit Tests

To run the unit tests:

```
make run_unit_tests
```

## Integration Tests

There are three ways to run the integration tests:

1. Automatically with SITL autostart.
2. Manually without SITL autostart.
3. On a real vehicle.

### Autostart PX4 SITL

Make sure that the [PX4 Gazebo simulation](https://dev.px4.io/en/simulation/gazebo.html) is built and works:

```
cd wherever/Firmware/
make posix gazebo
```

Then press Ctrl+C to stop the simulation and run the integration tests:

```
cd wherever/DroneCore/
AUTOSTART_SITL=1 make run_integration_tests
```

To run the tests without 3D viewer (gzclient), use:

```
AUTOSTART_SITL=1 HEADLESS=1 make run_integration_tests
```

### Run PX4 SITL Manually

Build and run the PX4 simulation manually:

```
cd wherever/Firmware/
make posix gazebo
```

```
make run_integration_tests
```

### On a Real Vehicle

Make sure you are connected to a vehicle and check the connection using e.g.

```
make && build/default/integration_tests_runner --gtest_filter="SitlTest.TelemetryAsync"
```

Note that some of the tests might not be suited for real vehicles, especially the takeoff and kill test.

## Gtest tricks

To list all possible tests:
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
