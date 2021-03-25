# Contributing

MAVSDK welcomes contributions!
If you want to help or have suggestions/bug reports [please get in touch with the development team](../README.md#getting-help).

This section contains everything you need to contribute, including topics about building the SDK from source code, running our integration and unit tests, and all other aspects of core development.


## Library Features

The core library (MAVSDK-C++) is written in C++, with auto-generated bindings for other supported programming languages.

The library is:
- Straightforward and easy to use. It has an API that supports both synchronous (blocking) and asynchronous calls (using callbacks).
- Fast, robust, and lightweight. Built to handle onboard usage with high rate messaging.
- Cross-platform (Linux, macOS, Windows, iOS, Android).
- Extensible, using compile-time plugins.

The main features provided by the API are (in all programing languages):

* Connect to and manage up to 255 vehicles via a TCP, UDP or serial connection.
* Get information about vehicles (vendor, software versions, product versions etc.)
* Get vehicle telemetry and state information (e.g. battery, GPS, RC connection, flight mode etc.) and set telemetry update rates.
* Send commands to arm, disarm, kill, takeoff, land and return to launch.
* Create and manage missions.
* Control a camera and gimbal both inside and outside of missions.
* Send commands to directly control vehicle movement.
* Send commands to start sensor calibration.

See the [FAQ](../faq.md) for answers to common questions about the library.
