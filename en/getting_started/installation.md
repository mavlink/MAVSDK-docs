# Installation

This topic explains how to install/set up MAVSDK for all our supported programming languages/platforms.


## C++

This section show how to install the MAVSDK core library on various platforms.

> **Note** For most supported platforms you can download and install pre-built binaries.
  During development (and for some platforms - e.g. Windows), you must [build the library from source](../contributing/build.md).

### Ubuntu

Download the **.deb** file for your system from [MAVSDK releases](https://github.com/mavlink/MAVSDK/releases) and install it using `dpkg`:

```
sudo dpkg -i mavsdk_0.24.0_ubuntu18.04_amd64.deb
```

### macOS

Use [brew](https://brew.sh/) to install the library:

```
brew install mavsdk
```

### Windows

> **Note** No binaries for Windows are available yet.
  For now you must [build the library from source](../contributing/build.md).

### Fedora

Download the matching **.rpm** file from [MAVSDK releases](https://github.com/mavlink/MAVSDK/releases) and install it using `rpm`:

```
sudo rpm -U mavsdk-0.24.0-1.fc30-x86_64.rpm
```

### Arch Linux

Use `yay` to install the library from [AUR](https://aur.archlinux.org/packages/mavsdk/):

```yay
yay -S mavsdk
```

### Development

For development, or unsupported platforms, you can [build the library from source](../contributing/build.md).


## Swift (iOS) {#ios}

[MAVSDK-Swift on GitHub](https://github.com/mavlink/MAVSDK-Swift) as well as the [reference docs](http://dronecode-sdk-swift.s3.eu-central-1.amazonaws.com/docs/master/index.html) should contain everything needed for iOS development of MAVSDK apps.


## Python

Use `pip3` to install [MAVSDK-Python](https://github.com/mavlink/MAVSDK-Python#mavsdk-python):
```bash
pip3 install mavsdk
```


## Next Steps

Once MAVSDK is installed we recommend you try the examples:
- C++: 
  - Try the [Takeoff and Land](../examples/takeoff_and_land.md) examples
  - See the [Guide](../guide/README.md) for information about how to write MAVSDK apps using C++.
- Python:
  - Instructions for running examples (and building from source) can be found on the project Github repo: [MAVSDK-Python](https://github.com/mavlink/MAVSDK-Python#mavsdk-python)