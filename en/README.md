<div style="float:right; padding:10px;"><img src="../assets/site/dronecore_logo_full.png" title="DroneCore Logo" width="400px"/></div>
# DroneCore Guide
[![Slack](https://px4-slack.herokuapp.com/badge.svg)](http://slack.px4.io) 
<!-- 
[![Releases](https://img.shields.io/github/release/PX4/Firmware.svg)](https://github.com/PX4/Firmware/releases) [![Discuss](https://img.shields.io/badge/discuss-px4-ff69b4.svg)](http://discuss.px4.io/) 
-->

DroneCore is a [MAVLink](http://mavlink.org) Library for the [PX4 flight stack](http://px4.io), with APIs for C++, Python, Android, and iOS (coming soon). 

> **Tip** DroneCore is the best way to integrate with PX4 over MAVLink! 
  It is supported by Dronecode, ensuring that it is robust, well tested, and maintained. 

The library provides a simple core API for managing one or more vehicles, providing programmatic access to vehicle information and telemetry, and control over missions, movement and other operations.

Developers can extend the library using plugins in order to add any other required MAVLink API (for example, to integrate PX4 with custom cameras, gimbals, or other hardware over MAVLink).

DroneCore can run on a vehicle-based companion computer or on a ground-based GCS or mobile device. These devices have significantly more processing power that an ordinary flight controller, enabling tasks like computer vision, obstacle avoidance, and route planning.

## Project Status

DroneCore is still in pre-alpha development. 
- The core C++ API has been created and is (largely) stable.
- UDP connections are supported. We are nearly finished writing plugins to support TCP and serial connections.
- Currently you can only develop in C++. [gRPC](https://grpc.io/) is being investigated as a promising technology for writing the cross-platform wrappers.

To use DroneCore you will need to [build the C++ library](contributing/build.md). Instructions for how to write a simple complete example are covered in [Takeoff and Land](examples/takeoff_and_land.md).


## Library Features

The core library is written in C++, with auto-generated bindings for other supported programming languages.

The library is:
- Straightforward and easy to use. It has an API that supports both synchronous (blocking) and asynchronous calls (using callbacks). 
- Fast, robust, and lightweight. Built to handle onboard usage with high rate messaging.
- Cross-platform (Linux, Mac, Windows, iOS, Android).
- Extensible, using compile-time plugins.

The main features provided by the simple core API are (in all programing languages):

* Connect to and manage up to 255 vehicles via a UDP network connection (serial and TCP connections are not yet implemented). 
* Get information about vehicles (vendor, software versions, product versions etc.)
* Get vehicle telemetry and state information (e.g. battery, GPS, RC connection, flight mode etc.) and set telemetry update rates.
* Send commands to arm, disarm, kill, takeoff, land and return to launch.
* Create and manage missions.
* Send commands to directly control vehicle movement.

The [API Reference](api_reference/README.md) provides detailed information about the API. See the [FAQ](getting_started/faq.md) for more information about the library. 

## Getting Started

The [Quick Start](getting_started/README.md) explains how to set up a development environment and write a minimal example for all our supported programming languages/platforms. 

Developers who want to contribute to the API will need to build the C++ library (and other programming language wrappers) from source. For more information see the [contributing section](#contributing) below.
 

## Getting Help

This guide contains information and examples showing how to use DroneCore. If you have specific questions that are not answered by the documentation, these can be raised on:

* [Slack DroneCore Channel](https://px4.slack.com/messages/C68J8H32A) (get a [Slack login here](http://slack.px4.io))
* [Discuss board](http://discuss.px4.io/c/dronecore)

Use Github for bug reports/enhancement requests:

* [C++ API](https://github.com/dronecore/DroneCore/issues)
* [Documentation](https://github.com/dronecore/docs/issues/)
<!-- Add info about where Python etc API issues are reported). -->


## Contributing


DroneCore welcomes contributions! If you want to help or have suggestions/bug reports [please get in touch with the development team](#getting-help). 

The [Contributing](contributing/README.md) section contains everything you need to contribute, including topics about building Dronecore from source code, running our integration and unit tests, and all other aspects of core development. 


## License

* DroneCore is licensed under the permissive [BSD 3-clause](https://github.com/dronecore/DroneCore/blob/master/LICENSE.md).
* This *DroneCore Developer Documentation* is licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) license.

<!-- ## Roadmap   - removed. I think belongs on repo at this point. Can be added back to releases if you want to manage it in docs -->
<!-- ## API overview    - moved to "Getting started" (for now) -->
<!-- ## Authors   - removed - I think this belongs in repo, though arguably could link to the github author tracking -->

