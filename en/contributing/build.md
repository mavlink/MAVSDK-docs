# Building DroneCore from Source

To build all of DroneCore from source you will first need to build the C++ library, and then any wrappers. The instructions below show how.

## Build the C++ Library

### macOS {#mac-os-x}

First install:
* [XCode](https://developer.apple.com/xcode/) (for *clang*)
* [Homebrew](https://brew.sh/) (for *cmake*).
  Once you have installed brew, you can install *cmake* via the terminal:
  ```
  brew install cmake
  ```

Then follow the instructions for building the library on [Linux](#linux).

### Linux

To build the *DroneCore* C++ Library on Linux (or macOS after installing the [preconditions above](#mac-os-x)):

1. First install the dependencies
   ```bash
   sudo apt-get update -y
   sudo apt-get install cmake build-essential colordiff astyle git libcurl4-openssl-dev doxygen -y
   ```
   > **Note** If the build reports a missing dependency, confirm that the set above matches the requirements in the [Dockerfile](https://github.com/dronecore/DroneCore/blob/master/Dockerfile).

1. Clone the [DroneCore repository](https://github.com/dronecore/DroneCore) (or your fork): 
   ```sh
   git clone https://github.com/dronecore/DroneCore.git
   cd DroneCore
   ```
1. Checkout the release/branch you want to build (the `develop` branch is checked out by default).
   * Latest stable build (`master`):
     ```
     git checkout master
     ```
   * Head revision with latest features (`develop`):
     ```
     git checkout develop
     ```
1. Update the submodules:
   ```sh
   git submodule update --init --recursive
   ```
1. Build the (debug) C++ library by calling:
   ```sh
   make default
   ```
   > **Tip** You can build *release* binaries by setting `BUILD_TYPE=Release` as shown below:
     ```sh
     make clean
     BUILD_TYPE=Release make
     ```

1. (Optionally) "Install" DroneCore [as described below](#install-artifacts). This is required in order to build DroneCore applications, but not to run DroneCore test code.

1. (Optionally) Build the API Reference documentation by calling:
   ```sh
   make docs
   ```

### Windows

To build the library in Windows, you need:

- [Build Tools for Visual Studio 2017](https://www.visualstudio.com/downloads/#build-tools-for-visual-studio-2017): Download and install (only the "Visual C+ Build Tools" are needed from installer).
- [cmake](https://cmake.org/download/): Download the installer and run it. Make sure to tick "add to PATH" during the installation.
- [curl](https://curl.haxx.se/): Download the source, extract and build it, and make the directory of the header files available as described below.

> **Note** The instructions below assume you downloaded [curl-7.56.1.zip](https://curl.haxx.se/download/curl-7.56.1.zip) and extracted to the root of your C drive. You can use a different *curl* if you want.

To build the *DroneCore* C++ Library on Windows:
1. Clone the [DroneCore repository](https://github.com/dronecore/DroneCore) (or your fork): 
   ```sh
   git clone https://github.com/dronecore/DroneCore.git
   cd DroneCore
   ```
1. Checkout the release/branch you want to build (the `develop` branch is checked out by default).
   * Latest stable build (`master`):
     ```
     git checkout master
     ```
   * Head revision with latest features (`develop`):
     ```
     git checkout develop
     ```
1. Update the submodules:
   ```sh
   git submodule update --init --recursive
   ```
1. Download the [curl-7.56.1.zip](https://curl.haxx.se/download/curl-7.56.1.zip) source and extract it to the root of your C drive.
1. Open the *VS2015 x64 Native Tools Command Prompt*, go to the source directory and enter:
   ```sh
   cd C:\curl-7.56.1\winbuild
   nmake /f Makefile.vc mode=static VC=15 MACHINE=x64 DEBUG=no
   ```
1. Then build *DroneCore* in Windows:
   ```sh
   cd /your/path/to/DroneCore
   mkdir build && cd build
   cmake -DWIN_CURL_INCLUDE_DIR:STRING=C:\\curl-7.56.1\\include -DWIN_CURL_LIB:STRING="C:\curl-7.56.1\builds\libcurl-vc15-x64-release-static-ipv6-sspi-winssl\lib\libcurl_a.lib" -G "Visual Studio 15 2017 Win64" ..
   cmake --build .
   ```

   > **Tip** You can generate *release* binaries by setting `--config Release` in the build step (`--config Debug` is used by default):
     ```sh
     cmake --build . --config Release
     ```

1. (Optionally) "Install" DroneCore [as described below](#install-artifacts). This is required in order to build DroneCore applications, but not to run DroneCore test code.


## Install DroneCore {#install-artifacts}

In order to *use* DroneCore your C++ applications need to be able locate the DroneCore libraries and header files (see [Building C++ Apps](../guide/toolchain.md)). You can either install these to standard system locations or locally within the DroneCore directory.

> **Tip** The example code assumes that DroneCore is installed locally. The example **CMakeLists.txt** file can easily be modified to find the system-wide installation.


### System-wide Install

Installing DroneCore system-wide means that the files you need to build your apps are always in the same place, and your build definition files can be simpler because they do not need to consider relative locations.

> **Warning** System-wide install is not (yet) supported on Windows. If you're a Windows guru, we'd [love your help](../README.md#getting-help) to set this up.

To install the files system-wide:

```sh
make clean  #REQUIRED!
sudo INSTALL_PREFIX=/usr/local make default install
```

> **Note** System-wide install overwrites standard install locations. If you already have DroneCore installed through some other mechanism it will be replaced!

### Local Install

On Linux/macOS the DroneCore headers and static library can be installed locally into the folder **DroneCore/install/** using:

```sh
make default install
```

On Windows specify `--target install` when building, as shown:
```sh
cmake --build . --target install
```


### Using the Compiled C++ Library

The [Building C++ Apps](../guide/toolchain.md) topic explains how use the library in C++ apps.


## Build for Android

> **Tip** You must first build the C++ Library (as shown above).

To build for Android devices or simulators, you first need to install:
- [Android NDK](https://developer.android.com/ndk/downloads/index.html)
- [Android SDK](https://developer.android.com/studio/index.html)

Also, you need to set these three environment variables:

- `NDK_ROOT` to `<your-android-ndk>`
- `ANDROID_TOOLCHAIN_CMAKE` to `<your-android-ndk>/build/cmake/android.toolchain.cmake`
- `ANDROID_CMAKE_BIN` to `<your-android-sdk>/cmake/<version>/bin/cmake`

E.g. you can add the lines below to your .bashrc, (or .zshrc for zshell users, or .profile):

```
export NDK_ROOT=$HOME/Android/android-ndk-r13
export ANDROID_TOOLCHAIN_CMAKE=$HOME/Android/android-ndk-r13/build/cmake/android.toolchain.cmake
export ANDROID_CMAKE_BIN=$HOME/Android/Sdk/cmake/3.6.3155560/bin/cmake
```

Then you build for all Android architectures:
```
make android install
```


## Build for iOS

> **Tip** You must first build the C++ Library (as shown above).

To build for real iOS devices on macOS:

```
make ios install
```

Build for the iOS simulator on macOS:

```
make ios_simulator install
```



## Build with external directory for plugins and custom integration_tests

The library is split into a [core](https://github.com/dronecore/DroneCore/tree/master/core) and [plugins](https://github.com/dronecore/DroneCore/tree/master/plugins). The plugins are included at compile time.
The cmake script [autogenerate_plugin_container.cmake](https://github.com/dronecore/DroneCore/blob/master/autogenerate_plugin_container.cmake) takes care of including the plugin folders and integrations tests.

The architecture goal is that the plugins do not depend on each other but only to the core source. This means you can swap out plugins as needed, however, it will lead to some duplicate functionality across the plugin modules.

You can add modules by copying the [external_example](https://github.com/dronecore/DroneCore/tree/master/external_example) and adapting it:

The external directory needs to contain the folders `integration_tests` and `plugins`.

```
external_example
├── integration_tests
│   ├── CMakeLists.txt
│   └── hello_world.cpp
└── plugins
    └── example
        ├── CMakeLists.txt
        ├── example.cpp
        ├── example.h
        ├── example_impl.cpp
        ├── example_impl.h
        └── example_impl_test.cpp
```

To add an additional library, the library name can be added to the variable `additional_libs` as follows:
```
set(additional_libs "library_name" PARENT_SCOPE)
```

And the required includes as `additional_includes`.
```
set(additional_includes "include_dir" PARENT_SCOPE)
```

To include the external folder in the build, add the folder name to the make command:

```
make EXTERNAL_DIR=external_example
```

To run the external hello world integration test, do:
```
build/default/integration_tests_runner --gtest_filter="ExternalExampleHello"
```


## Building in Docker

You can also build DroneCore on your host computer with a toolchain running in a [Docker](https://docs.docker.com/) container (this saves you from having to install or manage the toolchain directly).

The main steps are:

1. Install Docker on your host computer.
1. Clone the [DroneCore repository](https://github.com/dronecore/DroneCore) (or your fork) and update the submodules:
   ```sh
   git clone https://github.com/dronecore/DroneCore.git
   cd DroneCore
   git submodule update --init --recursive
   ```
1. Enter the following command in your host's terminal:
   ```sh
   docker run --rm -it -v $HOME/<path-to-dronecore-repo>/DroneCore:/home/docker1000/src/DroneCore:rw dronecore/dronecore bash
   ```
   > **Note** The `-v` flag maps a directory on your host (left side) to a path in
   the container (right side). Above you need to specify the left-side path to the DroneCore repository on your host. The container path must be set as above.

   > **Note** The `-v` flag maps a directory on your host (left side) to a path in the container (right side).  You need to specify the left-side path to the DroneCore repository on your host and the container path must be set as above.
   > The `--rm` automatically cleans up leftover docker containers after you exit the docker container.

   Docker will download an image from [Docker Hub](https://hub.docker.com/r/dronecore/dronecore/), use it to create a container, and then open a bash prompt:
   ```
   root*81ebe14d0c1a:/home/docker1000/src/Dronecore#
   ```
1. In the terminal you can build DroneCore using the normal Linux `make` commands:
   ```sh
   # Build the C++ library
   make default
   # Build and install DroneCore
   make default install
   # Run code-style check
   make fix_style
   # Build the docs
   make docs
   # Clean the build
   make clean
   ```

> **Note** Files built in a Docker container are owned by root. In order to clean up the **build** and **install** folders you will need to either call `make clean` in the container or `sudo make clean` in the host computer.

### Running single docker commands

You can also run build commands directly from your host (rather than opening bash), as shown below.

To make and install the C++ Library:
```bash
docker run --rm -it -v $HOME/<path-to-dronecore-repo>/DroneCore:/home/docker1000/src/DroneCore:rw dronecore/dronecore make install
```

To run the code style check:
```bash
docker run --rm -it -v $HOME/<path-to-dronecore-repo>/DroneCore:/home/docker1000/src/DroneCore:rw dronecore/dronecore make fix_style
```

### Building the Docker Image

The approach above downloads a container image ([dronecore/dronecore](https://hub.docker.com/r/dronecore/dronecore/)) from Docker Hub.

You can also build the image yourself using the [Dockerfile](https://github.com/dronecore/DroneCore/blob/master/Dockerfile) in the root of the DroneCore repository (this is based on Ubuntu 16.04). The image can be used in the same way as the one from Docker Hub.

1. Open a command prompt/terminal in the root of the DroneCore repository.
1. Build the image as shown:
   ```sh
   docker build . -t my_image    # 'my_image' can then be used to refer to the image
   ```
1. Open a bash prompt using this image:
   ```sh
   docker run --rm -it -v $HOME/<path-to-dronecore-repo>/DroneCore:/home/docker1000/src/DroneCore:rw my_image bash
   ```

