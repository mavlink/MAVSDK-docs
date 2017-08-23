# DroneCore Guide

[![Slack](https://px4-slack.herokuapp.com/badge.svg)](http://slack.px4.io) 

<!-- 
[![Releases](https://img.shields.io/github/release/PX4/Firmware.svg)](https://github.com/PX4/Firmware/releases) [![Discuss](https://img.shields.io/badge/discuss-px4-ff69b4.svg)](http://discuss.px4.io/) 
-->

DroneCore is a [MAVLink](http://mavlink.org) Library for the [PX4 flight stack](http://px4.io), with APIs for C++, Python, Android, and iOS (coming soon). The API can manage one or more vehicles, providing programmatic access to vehicle information and telemetry, and control over missions, movement and other operations.

The library can run on a vehicle-based companion computer or on a ground-based GCS or mobile device. DroneCore applications can run on devices that have significantly more processing power that an ordinary flight controller, enabling tasks like computer vision, obstacle avoidance, and route planning.

## Library Features

The core library is written in C++, with auto-generated bindings for other supported programming languages.

The library is:
- Straightforward and easy to use. It has an API that supports both synchronous (blocking) and asynchronous calls (using callbacks). 
- Fast, robust, and lightweight. Built to handle onboard usage with high rate messaging.
- Cross-platform (Linux, Mac, Windows, iOS, Android).
- Extensible, using compile-time plugins.

The main features provided by the API (in all programing languages) are:

* Connect to and manage up to 255 vehicles via a UDP network connection (serial and TCP connections are not yet implemented). 
* Get information about vehicles (vendor, software versions, product versions etc.)
* Get vehicle telemetry and state information (e.g. battery, GPS, RC connection, flight mode etc.) and set telemetry update rates.
* Send commands to arm, disarm, kill, takeoff, land and return to launch.
* Create and manage missions
* Send commands to directly control vehicle movement.

The [API Reference](api_reference/README.md) provides detailed information about the API. See the [FAQ](getting_started/faq.md) for more information about the library. 

## Getting Started

> **Note** At time of writing all users will need to [build the library](contributing/build.md) in order to use it. In the near future we'll have binary releases for the wrapper APIs.  Instructions for how to write a simple complete example are covered in [Takeoff and Land](examples/takeoff_and_land.md). The text below is "aspirational".

The [Quick Start](getting_started/README.md) explains how to set up a development environment and write a minimal example for all our supported programming languages/platforms. 

Developers who want to contribute to the API will need to build the C++ library (and other programming language wrappers) from source. For more information see the [contributing section](#contributing) below.
 

## Getting Help

This guide contains information and examples showing how to use DroneCore. If you have specific questions that are not answered by the documentation, these can be raised on:

* [Slack DroneCore Channel](https://px4.slack.com/messages/C68J8H32A) (get a [Slack login here](http://slack.px4.io))
* [Discuss board](TBD)

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

