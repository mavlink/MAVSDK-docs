# Building MAVSDK Library from Source

This section explains how to build and install the MAVSDK C++ library from source for all our target platforms.

Note that there are separate instructions to [build the mavsdk_server](build_mavsdk_server.md).

## Build the C++ Library {#build_sdk_cpp}

This section explains how to build the library along with its unit and integration tests.

### Requirements {#requirements}

The build requirements are git, cmake, and a compiler such as GCC, Clang, or MSVC.

#### Linux

**Ubuntu**:
```bash
sudo apt-get update
sudo apt-get install build-essential cmake git
```

**Fedora**:
```bash
sudo dnf update
sudo dnf groupinstall "Development Tools" "Development Libraries"
sudo dnf install cmake git
```

**Arch Linux**:
```bash
sudo pacman -Sy base-devel cmake git
```

#### macOS

First install XCode Command line tools:
```
xcode-select --install
```

And [Homebrew](https://brew.sh/) (for cmake).
Once you have installed brew, you can install `cmake` using `brew` in the terminal:
```
brew install cmake
```

#### Windows

To build the library in Windows, you need:

- [Build Tools for Visual Studio 2019](https://www.visualstudio.com/downloads/): Download and install (only the "Visual C+ Build Tools" are needed from installer).
- [cmake](https://cmake.org/download/): Download the installer and run it.
  Make sure to tick "add to PATH" during the installation.
- [git](https://git-scm.com/download/win) or any other tool to work with git.

> Note: Building using Cygwin or MingW is not supported.

### Getting the source

Download the source using git:
```bash
git clone https://github.com/mavlink/MAVSDK.git
```

Make sure to get all the submodules as well:
```
git submodule update --init --recursive
```

### Building

#### Debug

To build the MAVSDK C++ Library for development, use the debug build.

Configure first, then build:
```bash
cmake -DCMAKE_BUILD_TYPE=Debug -Bbuild/default -H.
cmake --build build/default -j8
```

####  Release

Once you ship software, make sure to use the release build with optimizations turned on:

**Linux/macOS:**

 ```bash
 cmake -Bbuild/default -DCMAKE_BUILD_TYPE=Release -H.
 cmake --build build/default -j8
 ```

**Windows:**

```bash
cmake -Bbuild/default -H. -DCMAKE_BUILD_TYPE=Release
cmake --build build/default -j8 --config Release
```

> Note: It is not usual to use CMAKE_BUILD_TYPE on Windows (with MSVC), however, our build requires it for the dependencies which are built at configure time.

## Installing the C++ Library {#build_sdk_cpp}

*Installing* builds the SDK **and** copies the libraries and header files into a "public" location so that they can be referenced by C++ applications (see [Building C++ Apps](../guide/toolchain.md)).


### System-wide Install {#sdk_system_wide_install}

By default (when `CMAKE_INSTALL_PREFIX` is not set, cmake tries to install system-wide. For Linux/macOS that's `/usr/local`, for Windows it is somewhere in `C:\Program Files`.

To install system-wide the command needs to be run with sudo on Linux/macOS:

```bash
sudo cmake --build build/default --target install
```

or run in a command prompt with admin privileges on Windows, or using `runas`:

```bash
runas cmake --build build/default --target install
```

> **Warning** Make sure to prevent conflicts between libraries installed in your system.
> The mavsdk library installed via a .deb or .rpm file will be installed in `/usr/` while the built library will be installed in `/usr/local`.
> It's recommended to only have one installed at any time to prevent conflicts.

### Local Install {#sdk_local_install}

The install path can be set in the configure call using `CMAKE_INSTALL_PREFIX`:

For example, to install into the `MAVSDK/install/` folder you woul set the `CMAKE_INSTALL_PREFIX` variable to specify a path relative to the folder from which you call `cmake` (or an absolute path).
```
cmake -DCMAKE_BUILD_TYPE=Release -DCMAKE_INSTALL_PREFIX=install -Bbuild/default -H.
cmake --build build/default --target install
```

> **Tip** If you already have run *cmake* without setting `CMAKE_INSTALL_PREFIX`, you may need to clean the build first:
  ```sh
  rm -rf build/default
  ```

## MAVLink headers and dialects

MAVSDK uses the dialect [common.xml](https://mavlink.io/en/messages/common.html) by default.
It does so by checking out the [mavlink/mavlink](https://github.com/mavlink/mavlink/) repository at configure time and using [Pymavlink](https://github.com/ArduPilot/pymavlink) to generate the C headers.

There are two options to change the default mentioned above.

### Change dialect

If you need to build with a dialect other than `common`, you can specify that during the configure step:

```sh
cmake -Bbuild/default -DMAVLINK_DIALECT=mydialect -H.
```

If you also want to swap out the repository and git commit, you can do so in [third_party/mavlink/CMakeLists.txt](https://github.com/mavlink/MAVSDK/blob/bbdb9e96f5567a488925093f641d249f8e01b2de/third_party/mavlink/CMakeLists.txt#L20-L21).

### Provide C headers manually

Instead of depending on the generation of the MAVLink C headers as part of the cmake configure step, you can provide the generated C headers manually.
This can be useful if you already have the headers generated in your worspace or CI, or if you don't have Python available during the configure step (e.g. as is the case for the dockcross images).

To provide the generated C headers manually, you have to set the path during the configure step:

Let's say the mavlink headers are "next to" the MAVSDK directory:
```sh
cmake -Bbuild/default -DMAVLINK_DIALECT=mydialect -DMAVLINK_HEADERS=../mavlink-headers -H.
```

Note that the structure of the headers needs to be like this:

```sh
mavlink-headers # <-- This is the directory referenced
└── mavlink
    └── v2.0
        ├── checksum.h
        ├── mydialect
        │   ├── mydialect.h
        │   ├── mavlink.h
        │   ├── mavlink_msg_...

```

## Other build flags

During the configure step, there are various flags that an be set using `-DFLAG=Value`:

- `CMAKE_BUILD_TYPE`: as documented above, to chose between `Debug` and `Release` build.
- `CMAKE_INSTALL_PREFIX`: as documented above, to specify directory to install library artefacts.
- `BUILD_SHARED_LIBS`: set to `ON` to build dynamic libraries (such as .so on Linux, .dylib on macOS, .dll on Windows). Set to `OFF` to build static libraries (such as .a on Linux and macOS, .lib on Windows).
- `SUPERBUILD`: set to `OFF` to use system dependencies instead of dependencies downloaded and built using cmake.
- `CMAKE_PREFIX_PATH`: can be used to set the path where the dependencies can be found if `SUPERBUILD` is set to `OFF`.
- `BUILD_MAVSDK_SERVER`: set to `ON` to build mavsdk_server, see instruction to [build mavsdk_server](build_mavsdk_server.md).
- `ASAN`: set to `ON` to enable address sanitizer.
- `UBSAN`: set to `ON` to enable undefined behavior sanitizer.
- `LSAN`: set to `ON` to enable leak sanitizer.
- `WERROR`: set to `ON` to error on warnings, mostly used for CI.

## Troubleshooting

### Git submodules out of date

Some common build issues can be resolved by updating submodules and cleaning the distribution:
```
cd MAVSDK
git submodule update --recursive
rm -rf build
```

Then attempt to build again.

### MSVC vs. MingW

We only try to support building using MSVC, MingW is not working, mostly because the defines/flags for it are missing.

### Undefined reference to mavsdk...

If you only just built the library and installed it system-wide may also need to [update the linker cache](http://tldp.org/HOWTO/Program-Library-HOWTO/shared-libraries.html).

On Linux this is done with `sudo ldconfig`.
