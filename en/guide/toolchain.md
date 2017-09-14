# Building C++ DroneCore Apps

DroneCore C++ apps are written in standard C++ (c++11) and can be built using your preferred build system, compiler and linker toolchain. The only requirements are:
- The build system must be able to locate the DroneCore headers and libraries (installed as described [here](../contributing/build.html#install-artifacts)).
- When using the library **libdronecore.a**, you need to link to a thread library such as *pthread* on a POSIX system (*pthread* is not included in the static library because it is included in *glibc*). 

DroneCore itself uses [cmake](https://cmake.org/), and we recommend that you do too. CMake is an open-source, cross-platform toolchain that allows you to build your examples on Mac OS, Linux and Windows using the same build file definition.

Below we explain how to set up a minimal make file for your application.

> **Tip** You can also kick off your application by copying modifying our existing [example code](https://github.com/dronecore/DroneCore/blob/master/example/takeoff_land/). Note that if you move your new application outside of the example directory you will need to update the (relative) paths to the locally installed DroneCore library.


## Build Definition File - CMakeLists.txt

*Cmake* uses a definition file named **CMakeLists.txt** to define the project. This specifies the name of the project, compiler flags for different platforms and targets, where to find dependencies (libraries and header files), source files to build, and the name of the generated binary. **CMakeLists.txt** is typically stored in the root directory of your app project.

The first two lines of the file should specify the minimum compatible version of *cmake* and *your* project's name. 
```cmake
cmake_minimum_required(VERSION 2.8.12)
project(your_project_name)
```

Next add the define flags that are used in compilation on different platforms 
(you can treat this as boilerplate - it enables relatively strict handling of warnings).
```cmake
if(NOT MSVC)
    add_definitions("-std=c++11 -Wall -Wextra -Werror")
else()
    add_definitions("-std=c++11 -WX -W2")
    set(platform_libs "Ws2_32.lib")
endif()

# Add DEBUG define for Debug target
set(CMAKE_CXX_FLAGS_DEBUG "-DDEBUG")
```

Add the line below to find a thread library on Linux, Mac, and Windows. This is required in order to use DroneCore!
```cmake
find_package(Threads REQUIRED)
```

The `include_directories()` command tells *cmake* where to find locally installed header files (if DroneCore is installed globally this is not required). 

```cmake
include_directories(
    # Not needed if installed system-wide
    ${CMAKE_SOURCE_DIR}/../../install/include
)
```

> **Note** The fragment above is taken from one of the DroneCore examples, and specifies a relative path from an example sub-directory to where DroneCore exports the header files by default. 
> If you have installed DroneCore locally and your application is not located alongside the DroneCore examples you will need to change this. 
>
>  Note that `CMAKE_SOURCE_DIR` is the directory in which **CMakeLists.txt** is stored, and provides a useful way of defining relative paths to the header files.

Then use `add_executable()` to specify the name for your generated executable and your source files. 
```cmake
add_executable(your_executable_name
    your_source_file.cpp
)
```

The final sections of the file defines the libraries to link against. 
The first part is used if DroneCore is installed locally, and will have to be modified depending on the relative path from your code to the **DroneCore/install/** directory.
```cmake
if(WINDOWS)
    set(dronecore_lib "${CMAKE_SOURCE_DIR}/../../install/lib/dronecore.lib")
else()
    set(dronecore_lib "${CMAKE_SOURCE_DIR}/../../install/lib/libdronecore.a")
endif()
```

The final section of the file defines the libraries to link against if DroneCore is installed globally.
```cmake
target_link_libraries(takeoff_and_land
    ${dronecore_lib}
    # If installed system-wide:
    # dronecore
    ${CMAKE_THREAD_LIBS_INIT}
    ${platform_libs}
)
```

> **Tip** Getting relative paths right can be difficult. You can use [message()](https://cmake.org/cmake/help/v3.9/command/message.html) to print out debug information in your build:
```bash
# Get the location of your CMakeLists.txt file
message(${CMAKE_SOURCE_DIR})
```

## Building the App

This section assumes that you have already [built and installed the DroneCore C++ Library](../contributing/build.md) and that your example has a **CMakeLists.txt** in its root directory. 

All we need to do is create a build directory (to keep all our build files in one place) and run the build from there. 

```bash 
cd /path/to/your/example/  # Open a prompt and navigate to your example 
mkdir build && cd build   # Create a build directory and navigate into it
cmake --build .  # Build the current directory
./your_executable_name  # Run your new executable
```


## Useful Links

We only show a small fraction of what *Cmake* is capable of! Check out the links below for more information and examples.

* [cmake resources page](https://cmake.org/documentation/)
* [cmake documentation](https://cmake.org/cmake/help/latest/) (latest)
* [cmake commands](https://cmake.org/cmake/help/latest/manual/cmake-commands.7.html) (used in this example):
  * [cmake_minimum_required()](https://cmake.org/cmake/help/latest/command/cmake_minimum_required.html) - Minimum compatible version of cmake
  * [project()](https://cmake.org/cmake/help/latest/command/project.html) - Set a name for project (and optionally version, languages, etc.)
  * [add_definitions()](https://cmake.org/cmake/help/latest/command/add_definitions.html) - Adds -D define flags to the compilation of source files
  * [set()](https://cmake.org/cmake/help/latest/command/set.html) - Set a normal, cache, or environment variable to a given value
  * [find_package()](https://cmake.org/cmake/help/latest/command/find_package.html) - Load settings for an external project.
  * [include_directories()](https://cmake.org/cmake/help/latest/command/include_directories.html)
  * [add_executable()](https://cmake.org/cmake/help/latest/command/add_executable.html) - Specify executable to be created and set of source files to use
  * [target_link_libraries()](https://cmake.org/cmake/help/latest/command/target_link_libraries.html) - Specify libraries to use when linking
  * [message()](https://cmake.org/cmake/help/v3.9/command/message.html) - Display a message to the user
  
