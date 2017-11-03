# DroneCore SDKs

DroneCore allows SDK Vendors to create independent plugin libraries, along with integration and unit tests, and 
build them into DroneCore at compile time. <!-- It also provides other functionality that is useful for SDK developers,
including the ability to lock down custom versions of DroneCore to authorised developers. -->

> **Note** This topic only covers the (very minor) differences between SDK plugins/testing and "vanilla" DroneCore.
> SDK authors should review the topics [Writing Plugins](../contributing/plugins.md) and 
> [Testing](../contributing/test.md).


## SDK Architecture

SDK extensions are defined in a separate/parallel folder to DroneCore. 
The extension folder *mirrors* DroneCore, and **must** contain the folders **integration_tests** and **plugins**.
The *plugin* folder contains appropriately named sub-folders for each plugin (along with its unit test code).

A simplified view of a "typical" DroneCore SDK is shown below (with extension directory: *SDK_Extensions*). 

```
├── DroneCore
│   ├── core
│   ├── integration_tests
│   └── plugins
│       ├── action
│       ├── ...
│       └── telemetry
├── SDK_Extensions
│   ├── integration_tests
│   └── plugins
│       ├── camera
│       ├── another_plugin
│       └── etc.
```


## Create an SDK Extension Library

To create a new C++ SDK Extension Library, first copy the [DroneCore/external_example](https://github.com/dronecore/DroneCore/tree/master/external_example) 
alongside DroneCore. 

The *external_example* contains a single integration test (**hello_world.cpp**) and a single plugin (**/example**) 
with a separate implementation file and a stub unit test file. Adapt it first by renaming the top level folder.
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

## Adding/Modifying Plugins

The extension library can contain as many plugins as needed, provided they are subfolders of **/plugins**, 
and have an appropriately formatted **CMakeLists.txt** make file. You can therefore duplicate and modify 
the "example" plugin as required by the SDK.

Modify the example plugin as needed and update its [CMakeLists.txt](https://github.com/dronecore/DroneCore/blob/master/external_example/plugins/example/CMakeLists.txt) as appropriate:
* Add additional libraries using the variable `additional_libs`:
  ```
  set(additional_libs "library_name" PARENT_SCOPE)
  ```
* Add required includes with `additional_includes`:
  ```
  set(additional_includes "include_dir" PARENT_SCOPE)
  ```
* You can also add tests with `unittest_source_files`, as discussed in the following section.
 
Plugins are otherwise written exactly as discussed in [Writing Plugins](../contributing/plugins.md). 


## Testing

SDK Extension tests are the same as those for the default plugins. 
The only (slight) difference is how the tests are included into the `unit_tests_runner` and
`integration_tests_runner` test programs.

> **Tip** See [Testing](../contributing/test.md) for general guidance on writing tests.

Once included in a build, the tests are run in exactly the same way as those for the default plugins.
For example to run the external_example hello world integration test, do:
```
build/default/integration_tests_runner --gtest_filter="ExternalExampleHello"
```
 
### Unit Tests

Unit tests are stored in the same folder as their associated plugin source code. 
The test file name(s) are added to the `$unittest_source_files` variable in the 
plugin **CMakeLists.txt** file (you can add multiple files).

> **Note** The DroneCore toolchain then does everything else necessary to
> add the tests to the `unit_tests_runner` program when the extension library
> is compiled with DroneCore.

The example plugin adds the **example_impl_test.cpp** unit test as shown below:

```cmake
set(unittest_source_files
    # Add unit test file(s) for plugin
    example_impl_test.cpp
    PARENT_SCOPE
)
```

### Integration Tests

Integration tests for SDKs/External plugins are placed in the SDK/Extension directory's **integration_tests** folder:

```
external_example       ## The (example) SDK/external plugin directory.
├── integration_tests
│   ├── CMakeLists.txt
│   └── hello_world.cpp
```

The tests are added to the test runner by appending them to the **CMakeLists.txt** file:

```cmake
list(APPEND integration_tests
    # Add the cpp file for each integration test on its own line
    hello_world
)
```

> **Note** The DroneCore toolchain then does everything else necessary to
> add the tests to the `integration_tests_runner` program when the extension library
> is compiled with DroneCore.


## Building 

To build *DroneCore* so that it includes the SDK/External plugins, specify the top level directory `EXTERNAL_DIR` in the `make` command. 
The line below shows how this is done for the [external_example](https://github.com/dronecore/DroneCore/tree/master/external_example) directory.

```
make EXTERNAL_DIR=external_example
```

Only one external directory can be specified.

<!-- 
## Additional Functionality

### Locking/Unlocking the SDK

Functionality to deliver in: https://github.com/dronecore/DroneCore/pull/139
-->
