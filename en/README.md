<img src="../assets/site/sdk_logo_full.png" title="MAVSDK Logo" width="400px"/>
# MAVSDK ({{ book.github_branch }})

[![Slack](https://px4-slack.herokuapp.com/badge.svg)](http://slack.px4.io)&nbsp;[![Discuss](https://img.shields.io/badge/discuss-MAVSDK-ff69b4.svg)](https://discuss.px4.io/c/sdk) [![travis-ci build status](https://travis-ci.org/mavlink/MAVSDK.svg?branch=develop)](https://travis-ci.org/mavlink/MAVSDK)
[![Build status](https://ci.appveyor.com/api/projects/status/1ntjvooywpxmoir8/branch/develop?svg=true)](https://ci.appveyor.com/project/Dronecode/dronecore/branch/develop)
[![Coverage Status](https://coveralls.io/repos/github/mavlink/MAVSDK/badge.svg?branch=develop)](https://coveralls.io/github/mavlink/MAVSDK?branch=develop)

The *MAVSDK* is a [MAVLink](https://mavlink.io/en/) Library with APIs for [C++](cpp/README.md), [iOS](http://dronecode-sdk-swift.s3.eu-central-1.amazonaws.com/docs/master/index.html), Python and Android.

> **Tip** The SDK is the best way to integrate with a flight stack over MAVLink!
  It is supported by [Dronecode](https://www.dronecode.org/), ensuring that it is robust, well tested, and maintained.

The library provides a simple API for managing one or more vehicles, providing programmatic access to vehicle information and telemetry, and control over missions, movement and other operations.

The library can run on a vehicle-based companion computer or on a ground-based GCS or mobile device (these devices have significantly more processing power that an ordinary flight controller, enabling tasks like computer vision, obstacle avoidance, and route planning).

Developers can extend the core C++ SDK using plugins in order to add any other required MAVLink API (for example, to integrate a flight controller with custom cameras, gimbals, or other hardware over MAVLink).

Cross-platform wrappers for the core library are actively being developed.
These (primarily) use [gRPC](https://grpc.io/) and [Reactive Extensions](http://reactivex.io/).

## Project Status

The MAVSDK is a robust and well-tested library that is already being used in production environments.

> **Note** Future compatibility is not guaranteed (the API is not "stable").

The current status is:
- C++ core library (2016). Used in production.
- MAVSDK-Swift (2018): Used in production.
- MAVSDK-Python (2019): First PyPi release 2019.
- MAVSDK-Java (2019): Prototype.
- MAVSDK-JavaScript (2019). Proof of concept.
- Other cross-platform wrappers are actively being developed.


## Getting Started

* Python 3 developers install and use [MAVSDK-Python](https://github.com/mavlink/MAVSDK-Python#mavsdk-python) from PyPi (`pip3 install mavsdk`). 
  There is no further setup, so you can then immediately run the [examples](https://github.com/mavlink/MAVSDK-Python/tree/master/examples) in the normal way. 
  The drone API is essentially the same as for the [C++ API](api_reference/README.md).
* iOS developers should start from the [Dronecode-SDK-Swift](http://dronecode-sdk-swift.s3.eu-central-1.amazonaws.com/docs/master/index.html) reference.
* C++ Developers should start at the [C++ Library](cpp/README.md).
 

## Getting Help

This guide contains information and examples showing how to use the SDK.
If you have specific questions that are not answered by the documentation, these can be raised on:

* [Discuss board](https://discuss.px4.io/c/mavsdk)
* [Slack (#mavsdk)](https://px4.slack.com/messages/C68J8H32A) (get a [Slack login here](http://slack.px4.io))

Use Github for bug reports/enhancement requests:

* [C++ API](https://github.com/mavlink/MAVSDK/issues)
* [C++ Documentation](https://github.com/dronecore/sdk_docs/issues)
* [Swift API and Docs](https://github.com/mavlink/MAVSDK-Swift/issues)
<!-- Add info about where Python etc API issues are reported). -->


## Library Features

The core library is written in C++, with auto-generated bindings for other supported programming languages.

The library is:
- Straightforward and easy to use. It has an API that supports both synchronous (blocking) and asynchronous calls (using callbacks). 
- Fast, robust, and lightweight. Built to handle onboard usage with high rate messaging.
- Cross-platform (Linux, macOS, Windows, iOS, Android).
- Extensible, using compile-time plugins.

The main features provided by the core API are (in all programing languages):

* Connect to and manage up to 255 vehicles via a TCP, UDP or serial connection.
* Get information about vehicles (vendor, software versions, product versions etc.)
* Get vehicle telemetry and state information (e.g. battery, GPS, RC connection, flight mode etc.) and set telemetry update rates.
* Send commands to arm, disarm, kill, takeoff, land and return to launch.
* Create and manage missions.
* Control a camera and gimbal both inside and outside of missions.
* Send commands to directly control vehicle movement.
* Send commands to start sensor calibration.

See the [FAQ](getting_started/faq.md) for answers to common questions about the library. 


## Contributing

We welcome contributions! If you want to help or have suggestions/bug reports [please get in touch with the development team](#getting-help). 

The [Contributing](contributing/README.md) (C++) section contains everything you need to contribute, including topics about building the SDK from source code, running our integration and unit tests, and all other aspects of core development. 


## License

* The *MAVSDK* is licensed under the permissive [BSD 3-clause](https://github.com/mavlink/MAVSDK/blob/{{ book.github_branch }}/LICENSE.md).
* This documentation is licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) license.

## Governance

The MAVSDK project is hosted under the governance of the [Dronecode Foundation](https://www.dronecode.org/).

<a href="https://www.dronecode.org/" style="padding:20px" ><img src="../assets/site/logo_dronecode.png" alt="Dronecode Logo" width="110px"/></a>
<a href="https://www.linuxfoundation.org/projects" style="padding:20px;"><img src="../assets/site/logo_linux_foundation.png" alt="Linux Foundation Logo" width="80px" /></a>
<div style="padding:10px">&nbsp;</div>
