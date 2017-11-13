# Building DroneCore from Source

This section explains how to [build](#build_dronecore_cpp) and [install](#install-artifacts) the DroneCore C++ library from source (both "natively" and in docker) for all our target platforms. It also shows how to build DroneCore with extensions and build the API Reference documentation. 


## Build the C++ Library {#build_dronecore_cpp}

This section explains how to build the DroneCore C++ library from source, 
along with its unit and integration tests. 
Build artifacts are created in the **build** subdirectory.

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
   sudo apt-get install cmake build-essential colordiff astyle git libcurl4-openssl-dev libtinyxml2-dev doxygen -y
   ```
   > **Note** If the build reports a missing dependency, confirm that the set above matches the requirements in the [Dockerfile](https://github.com/dronecore/DroneCore/blob/master/Dockerfile).

1. Clone the [DroneCore repository](https://github.com/dronecore/DroneCore) (or your fork) and update the submodules:
   ```sh
   git clone https://github.com/dronecore/DroneCore.git
   cd DroneCore
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

1. (Optionally) "Install" DroneCore [as described below](#install-artifacts). This is required in order to build [DroneCore C++ apps](../guide/toolchain.md), but not to run DroneCore test code.
   
1. (Optionally) Build the API Reference documentation by calling:
   ```sh
   make docs
   ```

### Windows

To build the library you'll need to install *Visual Studio Community Edition*. You will also need to download the [curl](https://curl.haxx.se/) source, extract and build it, and make the directory of the header files available when you build DroneCore.

> **Note** The instructions below assume you downloaded [curl-7.54.1.zip](https://curl.haxx.se/download/curl-7.54.1.zip) and extracted to the root of your C drive. You can use a different *curl* if you want.

To build the *DroneCore* C++ Library on Windows:
1. Clone the DroneCore repository (or your fork) and update the submodules:
   ```sh
   git clone https://github.com/dronecore/DroneCore.git
   cd DroneCore
   git submodule update --init --recursive
   ```
1. Download the [curl-7.54.1.zip](https://curl.haxx.se/download/curl-7.54.1.zip) source and extract it to the root of your C drive. 
1. Open the *VS2015 x64 Native Tools Command Prompt*, go to the source directory and enter:
   ```sh
   cd C:\curl-7.54.1\winbuild
   nmake /f Makefile.vc mode=static VC=14 MACHINE=x64 DEBUG=no
   ```
1. Then build *DroneCore* in Windows:
   ```sh
   cd /your/path/to/DroneCore
   mkdir build && cd build
   cmake -DWIN_CURL_INCLUDE_DIR:STRING=C:\\curl-7.54.1\\include -DWIN_CURL_LIB:STRING="C:\curl-7.54.1\builds\libcurl-vc14-x64-release-static-ipv6-sspi-winssl\lib\libcurl_a.lib" -G "Visual Studio 14 2015 Win64" ..
   cmake --build .
   ```
   
   > **Tip** You can generate *release* binaries by setting `--config Release` in the build step (`--config Debug` is used by default):
     ```sh
     cmake --build . --config Release
     ```

1. (Optionally) "Install" DroneCore [as described below](#install-artifacts). This is required in order to build [Dronecore C++ apps](../guide/toolchain.md), but not to run DroneCore test code.


## Install DroneCore {#install-artifacts}

*Installing* builds DroneCore **and** copies the libraries and header files into a "public" location so that they can be referenced by C++ applications (see [Building C++ Apps](../guide/toolchain.md)). DroneCore supports installation system-wide (recommended) or locally within the DroneCore tree.

> **Warning** System-wide installation is not yet supported on Windows (see [#155](https://github.com/dronecore/DroneCore/issues/155)) so you will need to [install DroneCore locally](#dronecore_local_install).
>
> Windows gurus, we'd [love your help](../README.md#getting-help) to implement this).

### System-wide Install {#dronecore_system_wide_install}

System-wide installation copies DroneCore to the standard system-wide locations for your platform (On Ubuntu Linux this is **/usr/local/**).

> **Warning** System-wide installation overwrites any previously installed version of DroneCore. 

To install DroneCore system-wide:

```sh
make clean  #REQUIRED!
make default
sudo default install
```

> **Tip** The `sudo` command is required (above) in order to install files to system directories.

### Local Install {#dronecore_local_install}

Local installation copies DroneCore headers/library to a user-specified location in the DroneCore directory.

On Linux/macOS use the `INSTALL_PREFIX` variable to specify a path relative to the **DroneCore/build/** folder
(or an absolute path).
For example, to install into the **DroneCore/install/** folder you would call:

```sh
make clean  #REQUIRED!
INSTALL_PREFIX=../../install make default install
```

On Windows specify `--target install` when building, as shown:
```sh
cmake --build . --target install
```


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

```sh
export NDK_ROOT=$HOME/Android/android-ndk-r13
export ANDROID_TOOLCHAIN_CMAKE=$HOME/Android/android-ndk-r13/build/cmake/android.toolchain.cmake
export ANDROID_CMAKE_BIN=$HOME/Android/Sdk/cmake/3.6.3155560/bin/cmake
```

Then you build for all Android architectures:
```sh
make android install
```


## Build for iOS 

> **Tip** You must first build the C++ Library (as shown above).

To build for real iOS devices on macOS:

```sh
make ios install
```

Build for the iOS simulator on macOS:

```sh
make ios_simulator install
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

## Build DroneCore Extensions {#dronecore_extensions}

DroneCore can be extended with plugins and integration tests that are defined "out of tree". These are declared inside a parallel directory that is included into the DroneCore at compile time (by specifying `EXTERNAL_DIR` in the `make` command).

The commands to build and install DroneCore with an extension library are:
```
make clean   # This is required!
make default EXTERNAL_DIR=relative_path_to_external_directory
sudo make default install
```
See [DroneCore Extensions](../guide/dronecore_extensions.md) for more information.
