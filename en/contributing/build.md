# Building DroneCore from Source

To build all of DroneCore from source you will first need to build the C++ library, and then any wrappers. The instructions below show how.

## Build the C++ Library

### Mac OS X

First install:
* [XCode](https://developer.apple.com/xcode/) (for *clang*)
* [Homebrew](https://brew.sh/) (for *cmake*).
  Once you have installed brew, you can install *cmake* via the terminal:
  ```
  brew install cmake
  ```

Then follow the instructions for building the library on [Linux](#linux).

### Linux

To build the *DroneCore* C++ Library on Linux (or Mac OS X after installing the [preconditions above](#mac-os-x)):

1. First install the dependencies
   ```bash
   sudo apt-get update -y
   sudo apt-get install cmake build-essential colordiff astyle git libcurl4-openssl-dev -y
   ```
   > **Note** If the build reports a missing dependency, confirm that the set above matches the requirements in the [Dockerfile](https://github.com/dronecore/DroneCore/blob/master/Dockerfile).

1. Clone the [DroneCore repository](https://github.com/dronecore/DroneCore) (or your fork) and update the submodules:
   ```bash
   git clone https://github.com/dronecore/DroneCore.git
   cd DroneCore
   git submodule update --init --recursive
   ```
1. Build the C++ library by calling:
   ```
   make default
   ```

### Windows

To build the library you'll need to install *Visual Studio Community Edition*. You will also need to download the [curl](https://curl.haxx.se/) source, extract and build it, and make the directory of the header files available when you build DroneCore.

> **Note** The instructions below assume you downloaded [curl-7.54.1.zip](https://curl.haxx.se/download/curl-7.54.1.zip) and extracted to the root of your C drive. You can use a different *curl* if you want.

To build the *DroneCore* C++ Library on Windows:
1. Clone the DroneCore repository (or your fork) and update the submodules:
   ```bash
   git clone https://github.com/dronecore/DroneCore.git
   cd DroneCore
   git submodule update --init --recursive
   ```
1. Download the [curl-7.54.1.zip](https://curl.haxx.se/download/curl-7.54.1.zip) source and extract it to the root of your C drive. 
1. Open the *VS2015 x64 Native Tools Command Prompt*, go to the source directory and enter:
   ```bash
   cd C:\curl-7.54.1\winbuild
   nmake /f Makefile.vc mode=static VC=14 MACHINE=x64 DEBUG=no
   ```
1. Then build *DroneCore* in Windows:
   ```
   cd /your/path/to/DroneCore
   mkdir build && cd build
   cmake -DWIN_CURL_INCLUDE_DIR:STRING=C:\\curl-7.54.1\\include -DWIN_CURL_LIB:STRING="C:\curl-7.54.1\builds\libcurl-vc14-x64-release-static-ipv6-sspi-winssl\lib\libcurl_a.lib" -G "Visual Studio 14 2015 Win64" ..
   cmake --build .
   ```

### Using the Compiled C++ Library

The [Takeoff and Land](../examples/takeoff_and_land.md) example shows how to build and test an example in C++.


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

To build for real iOS devices on Mac OS X:

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

If you want to develop in docker, you can use the [Dockerfile](https://github.com/dronecore/DroneCore/blob/master/Dockerfile) based on Ubuntu 16.04.

Build the image:
```
docker build . -t dronecore
```

To compile in it:
```
docker run -it -v $HOME/<wherever>/DroneCore:/home/docker1000/src/DroneCore:rw dronecore make
```

Or run the code style check:
```
docker run -it -v $HOME/<wherever>/DroneCore:/home/docker1000/src/DroneCore:rw dronecore make fix_style
```

## Install Artifacts

The build artifacts (headers and static library file) can be installed locally into the folder `./install/` using:

```
make default install
```

Or, to install the files system-wide, using:

```
INSTALL_PREFIX=/usr/local make default install
```

Note that when using the library **libdronecore.a**, you need to link to a thread library such as *pthread* on a POSIX system (pthread is not included in the static library because it is included in glibc).

## Build Python Wrapper

TBD.

