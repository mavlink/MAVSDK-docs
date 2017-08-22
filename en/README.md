# DroneCore Developer Documentation

[![Slack](https://px4-slack.herokuapp.com/badge.svg)](http://slack.px4.io) 

<!-- 
[![Releases](https://img.shields.io/github/release/PX4/Firmware.svg)](https://github.com/PX4/Firmware/releases) [![Discuss](https://img.shields.io/badge/discuss-px4-ff69b4.svg)](http://discuss.px4.io/) 
-->

> **Warning** This guide is under construction.

DroneCore is a [MAVLink](http://mavlink.org) Library for the [PX4 flight stack](http://px4.io), with APIs for C++, Python, Android, and iOS (coming soon). The API can manage one or more vehicles, providing programmatic access to vehicle information and telemetry, and control over missions, movement and other operations.

The library can run on a vehicle-based companion computer or on a ground-based GCS or mobile device. DroneCore applications can run on devices that have significantly more processing power that an ordinary flight controller, enabling tasks like computer vision, obstacle avoidance, and route planning.



For additional background information read below, and see the [FAQ](getting_started/faq.md).

## Library Features

> **Warning** This bit is under construction.

The library currently supports MAVLink messaging with one or more vehicles (up to 255) via a UDP network connection (serial and TCP connections are not yet implemented). 

The core library is written in C++. The other supported programming language bindings are auto-generated.

It has been designed to be:
- Straightforward and easy to use API that supports both synchronous (blocking) and asynchronous calls (using callbacks). 
- Fast and lightweight.
- Cross-platform (Linux, Mac, Windows, iOS, Android).
- Extensible (using compile-time plugins).

The main features are: ... <!-- add what is supported by the API -->

API Reference can be found ....

## Getting Started

Instructions how to build the library can be found in [Building](contributing/build.md). Instructions for how to write a simple complete example are covered in [Takeoff and Land](examples/takeoff_and_land.md).

## Where to get help

Slack 

## Contributing

Instructions how to build the library can be found in [Building](contributing/build.md). <!-- also testing -->

## License

* DroneCore is licensed under the permissive [BSD 3-clause](https://github.com/dronecore/DroneCore/blob/master/LICENSE.md).
* This *DroneCore Developer Documentation* is licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) license.

<!-- ## Roadmap   - removed. I think belongs on repo at this point. Can be added back to releases if you want to manage it in docs -->
<!-- ## API overview    - moved to "Getting started" (for now) -->
<!-- ## Authors   - removed - I think this belongs in repo, though arguably could link to the github author tracking -->

