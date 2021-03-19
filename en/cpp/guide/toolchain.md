# Building C++ Apps

The MAVSDK core C++ library is written in C++17 and exposes C++11 interfaces such as `std::function`. Therefore, applications using the library need to be C++11 or later as well.

Applications can be built using your preferred build system, compiler and linker toolchain. The only requirement is that the build system must be able to locate the MAVSDK C++ headers and libraries (installed as described [here](../contributing/build.md#install-artifacts)).

MAVSDK itself uses the [cmake](https://cmake.org/) build system, and we recommend that you do too.
*CMake* is an open-source, cross-platform toolchain that allows you to build your examples on macOS, Linux and Windows using the same build file definition.

Below we explain how to set up a minimal build setup (**CMakeLists.txt**) file for your application.


## Build Definition File - CMakeLists.txt

*Cmake* uses a definition file named **CMakeLists.txt** to define the project. This specifies the name of the project, compiler flags for different platforms and targets, where to find dependencies (libraries and header files), source files to build, and the name of the generated binary. **CMakeLists.txt** is typically stored in the root directory of your app project.

The sections below show how you can set up the file for when the SDK is [installed system wide](../contributing/build.md#sdk_system_wide_install) (the default) or [locally](../contributing/build.md#sdk_local_install).

> **Warning** MAVSDK system-wide installation is not supported on Windows (see [#155](https://github.com/mavlink/MAVSDK/issues/155)).
>  Instead build the app using a [local SDK installation](#sdk_local_install).
>
>  Windows gurus, we'd [love your help](../README.md#getting-help) to implement this).


### MAVSDK Installed System-wide {#sdk_installed_system_wide}

A "template" **CMakeLists.txt** is shown below.
Most of file is boilerplate - the main things you need to change are *your_project_name*, *your_executable_name* and *your_source_file*. You should also make sure that any plugins used by your app are listed in the `target_link_libraries` section.

```cmake
cmake_minimum_required(VERSION 3.10.2)

# Specify your project's name
project(your_project_name)

# Specify at least C++11, better C++17
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Enable strict handling of warnings
add_definitions("-Wall -Wextra -Werror")

# Finds MAVSDK when installed system wide.
find_package(MAVSDK REQUIRED)

# Specify your app's executable name, and list of source files used to create it.
add_executable(your_executable_name
    your_source_file.cpp
    # ... any other source files
)

# Specify your app's executable name and a list of linked libraries
target_link_libraries(your_executable_name
    MAVSDK::mavsdk             #All apps link against mavsdk library
    MAVSDK::mavsdk_action      # If action plugin used by app ...
    MAVSDK::mavsdk_telemetry   #If telemetry plugin used by app ...
    # ... Any other linked libraries
)
```

> **Note** The file format and required modifications are self-explanatory.
> If additional information is required see the [cmake documentation](https://cmake.org/cmake/help/latest/manual/cmake-commands.7.html).


### MAVSDK Installed Locally {#sdk_local_install}

> **Tip** Where possible install MAVSDK [system wide](../contributing/build.md#sdk_system_wide_install) and follow the instructions in the [previous section](#sdk_installed_system_wide).
You will need to install locally on Windows.

In order to specify a local path, you need to pass the location of MAVSDK like this:
```
FILL IN
```

## Building the App

This section assumes that you have already [built and installed the MAVSDK C++ Library](../contributing/build.md) and that your example has a **CMakeLists.txt** in its root directory.

### Linux/macOS

To create and run the app on Linux/macOS:
1. First create a build directory and run *cmake*:
   ```bash
   cd /path/to/your/application/ # Open a prompt and navigate to your application
   cmake -Bbuild -H.             # Create make files for your current platform
   ```
   > **Tip** The cmake default is "Debug" build. Use the flag `-DCMAKE_BUILD_TYPE=Release` to build release binaries:
   ```
   cmake -Bbuild -DCMAKE_BUILD_TYPE=Release -H.
   ```
1. Build the project (using 8 threads)
   ```bash
   cmake --build build -j8
   ```
1. Execute the file (in your build directory):
   ```bash
   build/your_executable_name  # Run your new executable
   ```

### Windows

To create and run the app on Windows:
1. Open the *VS2019 x64 Native Tools Command Prompt*.
1. Navigate to the app source directory and enter the commands as shown below:
   ```bash
   cd /path/to/your/application/   # Open a prompt and navigate to your application
   cmake -Bbuild -G "Visual Studio 16 2019" -H. # Create make files for your current platform
   cmake --build .  # Build the file
   build\Debug\your_executable_name.exe  # Run your new executable
   ```

## Useful Links

We only show a small fraction of what *Cmake* is capable of! Check out the links below for more information and examples.

* [cmake resources page](https://cmake.org/documentation/)
* [cmake documentation](https://cmake.org/cmake/help/latest/) (latest)
* [cmake commands](https://cmake.org/cmake/help/latest/manual/cmake-commands.7.html)
