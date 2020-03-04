# Getting Started <div style="float:right; padding:10px; margin-right:20px;"><img src="../../assets/site/sdk_logo_full.png" title="MAVSDK Logo" width="180px"/></div>

This topic explains how to set up a development environment and write a minimal example for all our supported programming languages/platforms.

## C++

To install the library, you can [install pre-built binaries](#install_binaries) for various platforms or [build from source](#build_source).

Once MAVSDK is installed follow the [Takeoff and Land](../examples/takeoff_and_land.md) example to try it out.

> **Note** This [Guide](../guide/README.md) explains how to write MAVSDK apps using C++.

### Install pre-built binaries {#install_binaries}

#### Windows

> **Note** No binaries for Windows are available yet. For now [building from source](#build_source) is required.

#### macOS

Use [brew](https://brew.sh/) to install the library:

```
brew install mavsdk
```

#### Ubuntu

Download the matching .deb file from [MAVSDK releases](https://github.com/mavlink/MAVSDK/releases) and install it using `dpkg`, e.g.:

```
sudo dpkg -i mavsdk_0.24.0_ubuntu18.04_amd64.deb
```

#### Fedora

Download the matching .rpm file from [MAVSDK releases](https://github.com/mavlink/MAVSDK/releases) and install it using `rpm`, e.g.:

```
sudo rpm -U mavsdk-0.24.0-1.fc30-x86_64.rpm
```

#### Arch Linux

The library is available on [AUR](https://aur.archlinux.org/packages/mavsdk/).

It can e.g. be installed using `yay`:

```
yay -S mavsdk
```

### Build from Source {#build_source}

For development, or unsupported platforms, you can [build the library from source](../contributing/build.md).


## iOS {#ios}

[MAVSDK-Swift on GitHub](https://github.com/mavlink/MAVSDK-Swift) as well as the [reference docs](http://dronecode-sdk-swift.s3.eu-central-1.amazonaws.com/docs/master/index.html) should contain everything needed for iOS development of MAVSDK apps.

## Python

To install [MAVSDK-Python](https://github.com/mavlink/MAVSDK-Python#mavsdk-python), simply run:
```
pip3 install mavsdk
```

Instructions for running examples (and building from source) can be found on the project Github repo: [MAVSDK-Python](https://github.com/mavlink/MAVSDK-Python#mavsdk-python)
