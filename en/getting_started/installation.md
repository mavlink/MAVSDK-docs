# Installation

This topic explains how to install MAVSDK for all our supported programming languages/platforms ([C++](#cpp), [Swift/iOS](#ios), [Python](#python)).


## C++ {#cpp}

This section show how to install the MAVSDK C++ (core) library on various platforms:
  
- **MacOS:** Install [Homebrew](https://brew.sh/) and use it to install the library:
  ```
  brew install mavsdk
  ```
- **Ubuntu:** Download the **.deb** file for your system from [MAVSDK releases](https://github.com/mavlink/MAVSDK/releases) and install it using `dpkg`:
  ```
  sudo dpkg -i mavsdk_0.24.0_ubuntu18.04_amd64.deb
  ```
- **Fedora:** Download the **.rpm** file for your system from [MAVSDK releases](https://github.com/mavlink/MAVSDK/releases) and install it using `rpm`:
  ```
  sudo rpm -U mavsdk-0.24.0-1.fc30-x86_64.rpm
  ```
- **Arch Linux:** Use `yay` to install the library from [AUR](https://aur.archlinux.org/packages/mavsdk/):
  ```yay
  yay -S mavsdk
  ```
- **Windows/Other platforms/Development:** No binaries are available (yet) for other platforms, including Windows.
  For now you must [build the library from source](../contributing/build.md).

You will also to install a compiler/build toolchain that build your MAVSDK C++ applications.
We recommend `cmake` and the same compiler used to compile the flight stack software (because these are used for the [MAVSDK C++ Examples](../examples/README.md) examples).

> **Tip** The required toolchain is generally set up when you set up the flight stack development environment (e.g. to set up the simulator).


## Python {#python}

Use `pip3` to install [MAVSDK-Python](https://github.com/mavlink/MAVSDK-Python#mavsdk-python):
```bash
pip3 install mavsdk
```
> **Note** MAVSDK-Python is currently only available for Windows, macOS, and Linux x86_64.
  It is not yet suppported for Linux ARM platfroms like RPi (see [MAVSDK-Python#117](https://github.com/mavlink/MAVSDK-Python/issues/117)).

  
## Swift (iOS) {#ios}

[MAVSDK-Swift on GitHub](https://github.com/mavlink/MAVSDK-Swift) as well as the [reference docs](http://dronecode-sdk-swift.s3.eu-central-1.amazonaws.com/docs/master/index.html) should contain everything needed for iOS development of MAVSDK apps.



## Next Steps

Once MAVSDK is installed we recommend you try the examples and read the guides:
- C++: 
  - [C++ QuickStart](../cpp/quickstart.md)
  - Try the [Takeoff and Land](../examples/takeoff_and_land.md) examples
  - See the [Guide](../guide/README.md) for information about how to write MAVSDK apps using C++
- Python:
  - Instructions for running examples (and building from source) can be found on the project Github repo: [MAVSDK-Python](https://github.com/mavlink/MAVSDK-Python#mavsdk-python)
- MAVSDK-Swift:
  - [MAVSDK-Swift on GitHub](https://github.com/mavlink/MAVSDK-Swift)
  - [Reference docs](http://dronecode-sdk-swift.s3.eu-central-1.amazonaws.com/docs/master/index.html)
