# Building C++ Apps

Dronecode SDK C++ apps are written in standard C++ (c++11) and can be built using your preferred build system, compiler and linker toolchain. 
The only requirement is that the build system must be able to locate the SDK C++ headers and libraries (installed as described [here](../contributing/build.md#install-artifacts)).

The SDK itself uses the [cmake](https://cmake.org/) build system, and we recommend that you do too. 
*CMake* is an open-source, cross-platform toolchain that allows you to build your examples on macOS, Linux and Windows using the same build file definition.

Below we explain how to set up a minimal build setup (**CMakeLists.txt**) file for your application.


## Build Definition File - CMakeLists.txt

*Cmake* uses a definition file named **CMakeLists.txt** to define the project. This specifies the name of the project, compiler flags for different platforms and targets, where to find dependencies (libraries and header files), source files to build, and the name of the generated binary. **CMakeLists.txt** is typically stored in the root directory of your app project.

The sections below show how you can set up the file for when the SDK is [installed system wide](../contributing/build.md#sdk_system_wide_install) (the default) or [locally](../contributing/build.md#sdk_local_install).

> **Warning** SDK system-wide installation is not supported on Windows (see [#155](https://github.com/dronecore/DroneCore/issues/155)). 
>  Instead build the app using a [local SDK installation](#sdk_local_install).
>
>  Windows gurus, we'd [love your help](../README.md#getting-help) to implement this).


### SDK Installed System-wide {#sdk_installed_system_wide}

A "template" **CMakeLists.txt** is shown below. Most of file is boilerplate - the main things you need to change are *your_project_name*, *your_executable_name* and *your_source_file*. You should also make sure that any plugins used by your app are listed in the `target_link_libraries` section.

```cmake
cmake_minimum_required(VERSION 2.8.12)

## Specify your project's name
project(your_project_name)

# Enable strict handling of warnings
if(NOT MSVC)
    add_definitions("-std=c++11 -Wall -Wextra -Werror")
else()
    add_definitions("-std=c++11 -WX -W2")
    include_directories(${CMAKE_SOURCE_DIR}/../../install/include)
    link_directories(${CMAKE_SOURCE_DIR}/../../install/lib)
endif()

# Specify your app's executable name, and list of source files used to create it.
add_executable(your_executable_name
    your_source_file.cpp
    # ... any other source files
)

# Specify your app's executable name and a list of linked libraries
target_link_libraries(your_executable_name
    dronecore  #All apps link against dronecore library
    dronecore_action  # If action plugin used by app ...
    dronecore_telemetry If telemetry plugin used by app ...
    # ... Any other linked libraries
)
```

> **Note** The file format and required modifications are self-explanatory. 
> If additional information is required see the [cmake documentation](https://cmake.org/cmake/help/latest/manual/cmake-commands.7.html).


### SDK Installed Locally {#sdk_local_install}

> **Tip** Where possible install the SDK [system wide](../contributing/build.md#sdk_system_wide_install) and follow the instructions in the [previous section](#sdk_installed_system_wide). 
You will need to install locally on Windows.

**CMakeLists.txt** is more complicated when the SDK is [installed locally](../contributing/build.md#sdk_local_install), 
because you need to specify where the build should find both headers and library files *relative to your current directory*. 

The changes to the file (with respect to the previous version) are shown below. 
You have to change the same information as before: *your_project_name*, *your_executable_name* and *your_source_file*. 

> **Note** The example file below assumes that the SDK was installed locally into the directory **DroneCore/install/** and that the application is nested two levels deep (at the same level as the SDK example code).

```cmake
cmake_minimum_required(VERSION 2.8.12)

## Specify your project's name
project(your_project_name)

# Enable strict handling of warnings
if(NOT MSVC)
    add_definitions("-std=c++11 -Wall -Wextra -Werror")
else()
    add_definitions("-std=c++11 -WX -W2")
endif()

# Specify your app's executable name, and list of source files used to create it.
add_executable(your_executable_name
    your_source_file.cpp
    # ... any other source files
)
```
Remove/comment this section (Not using "system wide" SDK)
```cmake
#target_link_libraries(your_executable_name
#    dronecore  #All apps link against dronecore library
    # ... any other linked libraries
#)
```
Add section specifying local path to include directories and the SDK library.
```cmake
# Specify include directories
include_directories(
    ${CMAKE_SOURCE_DIR}/../../install/include
)

# Specify variable 'dronecore_lib' containing location of DroneCore library.
if(MSVC)
    set(dronecore_lib "${CMAKE_SOURCE_DIR}/../../install/lib/dronecore.lib")
else()
    set(dronecore_lib "${CMAKE_SOURCE_DIR}/../../install/lib/libdronecore.so")
endif()

# Specify your app's executable name and a list of linked libraries
target_link_libraries(your_executable_name
    # Add  'dronecore_lib' variable defining where the DroneCore library can be found. 
    ${dronecore_lib}
    # dronecore # Link against library named dronecore in standard install location
    # ... any other linked libraries
)
```


## Building the App

This section assumes that you have already [built and installed the DroneCore C++ Library](../contributing/build.md) and that your example has a **CMakeLists.txt** in its root directory. 

### Linux/macOS

To create and run the app on Linux/macOS:
1. First create a build directory and run *cmake*: 
   ```bash 
   cd /path/to/your/application/   # Open a prompt and navigate to your application 
   mkdir build && cd build   # Create a build directory and navigate into it
   cmake ..   # Create make files for your current platform
   ```
   > **Tip** Make files for release binaries are created by default. Use the flag `-DCMAKE_BUILD_TYPE=Debug` to build debug binaries:
   ```
   cmake -DCMAKE_BUILD_TYPE=Debug ..
   ```
1. Build the project
   ```bash 
   make
   ```
1. Execute the file (in your build directory):
   ```bash 
   ./your_executable_name  # Run your new executable
   ```

### Windows

To create and run the app on Windows:
1. Open the *VS2017 x64 Native Tools Command Prompt*.
1. Navigate to the app source directory and enter the commands as shown below:
   ```bash 
   cd /path/to/your/application/   # Open a prompt and navigate to your application 
   mkdir build && cd build   # Create a build directory and navigate into it
   cmake .. -G "Visual Studio 15 2017 Win64" # Create make files for your current platform
   cmake --build .  # Build the file 
   .\Debug\your_executable_name.exe  # Run your new executable
   ```


## Useful Links

We only show a small fraction of what *Cmake* is capable of! Check out the links below for more information and examples.

* [cmake resources page](https://cmake.org/documentation/)
* [cmake documentation](https://cmake.org/cmake/help/latest/) (latest)
* [cmake commands](https://cmake.org/cmake/help/latest/manual/cmake-commands.7.html)


  
