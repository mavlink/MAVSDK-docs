<img src="../assets/site/sdk_logo_full.png" title="MAVSDK Logo" width="400px"/>
# MAVSDK ({{ book.github_branch }})

[![Slack](https://px4-slack.herokuapp.com/badge.svg)](http://slack.px4.io)&nbsp;[![Discuss](https://img.shields.io/badge/discuss-MAVSDK-ff69b4.svg)](https://discuss.px4.io/c/sdk) [![GitHub Actions Status](https://github.com/mavlink/MAVSDK/workflows/Build%20and%20Test/badge.svg?branch=develop)](https://github.com/mavlink/MAVSDK/actions?query=branch%3Adevelop)
[![Coverage Status](https://coveralls.io/repos/github/mavlink/MAVSDK/badge.svg?branch=develop)](https://coveralls.io/github/mavlink/MAVSDK?branch=develop)

*MAVSDK* is a collection of libraries for various programming languages to interface with [MAVLink](https://mavlink.io/en/) systems such as drones, cameras or ground systems.

The libraries provides a simple API for managing one or more vehicles, providing programmatic access to vehicle information and telemetry, and control over missions, movement and other operations.

The libraries can be used onboard a drone on a companion computer or on the ground for a  ground station or mobile device.

MAVSDK is cross-platform: Linux, macOS, Windows, Android and iOS.

## Programming Languages

MAVSDK is primarly written in C++ with wrappers available for several programming languages:

- [MAVSDK-C++](https://github.com/mavlink/MAVSDK) (2016). Used in production.
- [MAVSDK-Swift](https://github.com/mavlink/MAVSDK-Swift) (2018): Used in production.
- [MAVSDK-Python](https://github.com/mavlink/MAVSDK-Python) (2019): Used in production.
- [MAVSDK-Java](https://github.com/mavlink/MAVSDK-Java) (2019): Used in production.
- [MAVSDK-Go](https://github.com/mavlink/MAVSDK-Go) (2020): Feature complete.
- [MAVSDK-JavaScript](https://github.com/mavlink/MAVSDK-JavaScript) (2019): Proof of concept.
- [MAVSDK-CSharp](https://github.com/mavlink/MAVSDK-CSharp) (2019). Proof of concept.
- [MAVSDK-Rust](https://github.com/mavlink/MAVSDK-Rust) (2019): Proof of concept.

## Getting Started

Check out the quickstart guide for [C++](cpp/quickstart.md) and [Python](python/quickstart.md)

## Getting Help

This guide contains information and examples showing how to use MAVSDK.
If you have specific questions that are not answered by the documentation, these can be raised on:

* [Discuss board](https://discuss.px4.io/c/mavsdk)
* [Slack (#mavsdk)](https://px4.slack.com/messages/C68J8H32A) (get a [Slack login here](http://slack.px4.io))

Use Github for bug reports/enhancement requests:

* [C++ API](https://github.com/mavlink/MAVSDK/issues)
* [C++ Documentation](https://github.com/mavlink/MAVSDK-docs/issues)
* [Swift API and docs](https://github.com/mavlink/MAVSDK-Swift/issues)
* [Python API and docs](https://github.com/mavlink/MAVSDK-Python/issues)
<!-- Add info about where other API issues are reported). -->


## Contributing

We welcome contributions! If you want to help or have suggestions/bug reports [please get in touch with the development team](#getting-help).

The [Contributing](contributing/README.md) (C++) section contains more information on how and what to contribute, including topics about building MAVSDK from source code, running our integration and unit tests, and all other aspects of core development.


## License

* The *MAVSDK* is licensed under the permissive [BSD 3-clause](https://github.com/mavlink/MAVSDK/blob/{{ book.github_branch }}/LICENSE.md).
* This documentation is licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) license.

## Governance

The MAVSDK project is hosted under the governance of the [Dronecode Foundation](https://www.dronecode.org/).

<a href="https://www.dronecode.org/" style="padding:20px" ><img src="../assets/site/logo_dronecode.png" alt="Dronecode Logo" width="110px"/></a>
<a href="https://www.linuxfoundation.org/projects" style="padding:20px;"><img src="../assets/site/logo_linux_foundation.png" alt="Linux Foundation Logo" width="80px" /></a>
<div style="padding:10px">&nbsp;</div>
