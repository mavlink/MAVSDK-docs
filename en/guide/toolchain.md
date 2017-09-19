# Building C++ DroneCore Apps

DroneCore C++ apps are written in standard C++ (c++11) and can be built using your preferred build system, compiler and linker toolchain. The only requirements are:
- The build system must be able to locate the DroneCore headers and libraries (installed as described [here](../contributing/build.md#install-artifacts)).
- When using DroneCore you need to link to a thread library (e.g. *pthread* on a POSIX system). 

DroneCore itself uses the [cmake](https://cmake.org/) build system, and we recommend that you do too. CMake is an open-source, cross-platform toolchain that allows you to build your examples on Mac OS, Linux and Windows using the same build file definition.

Below we explain how to set up a minimal build setup (**CMakeLists.txt**) file for your application.


## Build Definition File - CMakeLists.txt

*Cmake* uses a definition file named **CMakeLists.txt** to define the project. This specifies the name of the project, compiler flags for different platforms and targets, where to find dependencies (libraries and header files), source files to build, and the name of the generated binary. **CMakeLists.txt** is typically stored in the root directory of your app project.

The sections below show how you can set up the file for when DroneCore is installed system-wide or locally.


### DroneCore Installed System-wide

> **Warning** System-wide install is not (yet) supported on Windows (if you're a Windows guru, we'd [love your help](../README.md#getting-help) to implement this). You will have to use install locally as shown in the following section. 

A "template" **CMakeLists.txt** is shown below. Almost all of the above file is boilerplate - the only things you need to change are *your_project_name*, *your_executable_name* and *your_source_file*. 

```cmake
cmake_minimum_required(VERSION 2.8.12)
project(your_project_name)

# Add platform/compiler specific flags
if(NOT MSVC)
    add_definitions("-std=c++11 -Wall -Wextra -Werror")
else()
    add_definitions("-std=c++11 -WX -W2")
    set(platform_libs "Ws2_32.lib")
endif()

# Add DEBUG define for Debug target
set(CMAKE_CXX_FLAGS_DEBUG "-DDEBUG")

# This finds thread libs on Linux, Mac, and Windows.
find_package(Threads REQUIRED)

# Specify your binary name, and list of source files used to create it.
add_executable(your_executable_name
    your_source_file.cpp
)

target_link_libraries(your_executable_name
    dronecore  # Link against library named dronecore in standard install location
    ${CMAKE_THREAD_LIBS_INIT}  # Link against thread library found using find_package() 
    ${platform_libs}  # Variable containing all libraries that to link against for this platform (e.g. pthread).
)
```

> **Tip** The make file can be so minimal because the `target_link_libraries()` function has the `dronecore` line, which tells *cmake* that DroneCore's library and headers are in the standard location.

We'll explain some of it in the next section.


### DroneCore Installed Locally

The **CMakeLists.txt** is more complicated when DroneCore is installed locally, because you need to specify where the build should find both headers and library files. 

The new lines are marked up using `# >>> ADDED` comments below.  You have to change the same information as before: *your_project_name*, *your_executable_name* and *your_source_file*. You may also need to change the location of the headers/library files, depending on where your application is hosted relative to the **DroneCore** project root directory (this example assumes that your application is nested two levels deep, just like our example code).

```cmake
cmake_minimum_required(VERSION 2.8.12)
project(your_project_name)

# Add platform/compiler specific flags
if(NOT MSVC)
    add_definitions("-std=c++11 -Wall -Wextra -Werror")
else()
    add_definitions("-std=c++11 -WX -W2")
    set(platform_libs "Ws2_32.lib")
endif()

# Add DEBUG define for Debug target
set(CMAKE_CXX_FLAGS_DEBUG "-DDEBUG")

# This finds thread libs on Linux, Mac, and Windows.
find_package(Threads REQUIRED)

# >>> ADDED
# Specify include directories
include_directories(
    # Not needed if installed system-wide
    ${CMAKE_SOURCE_DIR}/../../install/include
)
# <<< 

# Specify your binary name, and list of source files used to create it.
add_executable(your_executable_name
    your_source_file.cpp
)

# >>> ADDED
# Specify variable 'dronecore_lib' containing location of DroneCore library.
if(WINDOWS)
    set(dronecore_lib "${CMAKE_SOURCE_DIR}/../../install/lib/dronecore.lib")
else()
    set(dronecore_lib "${CMAKE_SOURCE_DIR}/../../install/lib/libdronecore.a")
endif()
# <<< 

target_link_libraries(your_executable_name
# >>> ADDED
    # Add  'dronecore_lib' variable defining where the dronecore library can be found. 
    ${dronecore_lib}
    # dronecore # Link against library named dronecore in standard install location
# <<< 
    ${CMAKE_THREAD_LIBS_INIT}  # Link against thread library found using find_package() 
    ${platform_libs}  # Variable containing all libraries that to link against for this platform (e.g. pthread).
)
```


The main elements of the file are described below:

1. The first two lines of the file should specify the minimum compatible version of *cmake* and *your* project's name.
   ```cmake
   cmake_minimum_required(VERSION 2.8.12)
   project(your_project_name)
   ```
1. The [add_definitions()](https://cmake.org/cmake/help/latest/command/add_definitions.html) and [set()](https://cmake.org/cmake/help/latest/command/set.html) are used to the define flags that are used in compilation on different platforms. In this case we enable strict handling of warnings and an MSVC specific library.
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
1. The [find_package()](https://cmake.org/cmake/help/latest/command/find_package.html) command tells *cmake* to find a thread library on Linux, Mac, and Windows. Further down we add the found package to the libraries built into the project (see `${CMAKE_THREAD_LIBS_INIT}`):
   ```cmake
   find_package(Threads REQUIRED)
   ```
   This is required in order to use DroneCore!

1. The [include_directories()](https://cmake.org/cmake/help/latest/command/include_directories.html) tells *cmake* where to find locally installed header files (if DroneCore is installed globally this is not required). 
   ```cmake
   include_directories(
       # Not needed if installed system-wide
       ${CMAKE_SOURCE_DIR}/../../install/include
   )
   ```

   > **Note** `CMAKE_SOURCE_DIR` is the directory in which **CMakeLists.txt** is stored, and provides a useful way of defining relative paths to the header files. This example assumes that your application is nested two levels deep, in order to access the include files installed locally to: **/Dronecore/install/include**.
1. The [add_executable()](https://cmake.org/cmake/help/latest/command/add_executable.html) command specifies the name for your generated executable and your source file(s). 
   ```cmake
   add_executable(your_executable_name
       your_source_file.cpp
   )
  ```
1. Here we define a variable for the location of the DroneCore library, depending on platform. As for the include files, this requires a relative path (to **DroneCore/install/lib/*). This is then used in the next step.
   ```cmake
   if(WINDOWS)
       set(dronecore_lib "${CMAKE_SOURCE_DIR}/../../install/lib/dronecore.lib")
   else()
       set(dronecore_lib "${CMAKE_SOURCE_DIR}/../../install/lib/libdronecore.a")
   endif()
   ```
1. The [target_link_libraries()](https://cmake.org/cmake/help/latest/command/target_link_libraries.html) command defines the libraries that your executable (`your_executable_name`) will link against. Here we use the `${dronecore_lib}` variable defined above. We comment out the `dronecore`, because the two definitions for libraries conflict.
```cmake
target_link_libraries(your_executable_name
    ${dronecore_lib}
    # If installed system-wide:
    # dronecore
    ${CMAKE_THREAD_LIBS_INIT}  # Link against thread library found using find_package() 
    ${platform_libs}  # Variable containing all libraries that to link against for this platform (e.g. pthread).
)
```


## Building the App

This section assumes that you have already [built and installed the DroneCore C++ Library](../contributing/build.md) and that your example has a **CMakeLists.txt** in its root directory. 

To create and run the app:
1. First create a build directory and run *cmake*: 
   ```bash 
   cd /path/to/your/application/   # Open a prompt and navigate to your application 
   mkdir build && cd build   # Create a build directory and navigate into it
   cmake ..   # Create make files for your current platform
   ```
1. Build the project
   * Linux/Mac:
     ```bash 
     make -j8
     ``` 
   * Windows:
     ```bash 
     cmake --build .
     ``` 
1. Execute the file (in your build directory):
     ```bash 
     ./your_executable_name  # Run your new executable
     ```


## Useful Links

We only show a small fraction of what *Cmake* is capable of! Check out the links below for more information and examples.

* [cmake resources page](https://cmake.org/documentation/)
* [cmake documentation](https://cmake.org/cmake/help/latest/) (latest)
* [cmake commands](https://cmake.org/cmake/help/latest/manual/cmake-commands.7.html)


  
