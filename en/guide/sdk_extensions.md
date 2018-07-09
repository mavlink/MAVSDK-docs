# SDK Extensions

The *DroneCode SDK* can be extended with [plugins](../contributing/plugins.md) and [tests](../contributing/test.md) that are defined "out of tree".
This enables developers to manage custom code in a separate repository (reducing *git* conflicts). 

> **Note** Extensions are defined in a parallel tree that *mirrors* the SDK source code structure. 
> Extension plugins and tests are *exactly the same* as "standard" SDK plugins and tests.

## Folder Structure

The extension folder *mirrors* the SDK source tree, and **must** contain the folders **integration_tests** and **plugins**.
The *plugin* folder contains appropriately named sub-folders for each plugin (along with its unit test code).

A simplified view of a "typical" extension directory is shown below (in this case named "SDK_Extensions"). 

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

## Create a DroneCore Extension Library

To create a new C++ Dronecode SDK Extension Library, first copy [DroneCore/external_example](https://github.com/dronecore/DroneCore/tree/{{ book.github_branch }}/external_example) to the same folder level as the DroneCore directory.
Then rename the top level folder as desired.

The *external_example* contains a single integration test (**hello_world.cpp**) and a single plugin (**/example**) 
with a separate implementation file and a stub unit test file. 
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

Plugins in extension libraries are exactly the same as "normal" SDK plugins 
(except that they are located in the extension "plugins" folder rather than under DroneCore). 

[Writing Plugins](../contributing/plugins.md) explains how to write or modify plugins.

> **Tip** To create a new plugin you can either copy and modify an existing DroneCore plugin
> or start from the example plugin shown above.


## Testing

Tests in extension libraries are written in exactly the same as "normal" SDK plugin tests.

The only difference is that all external tests should be compiled into their own "test runner". 
The test runner for the "external example" is defined in 
[/integration_tests/CMakeLists.txt]( https://github.com/dronecore/DroneCore/blob/{{ book.github_branch }}/external_example/integration_tests/CMakeLists.txt) (named `external_example_integration_tests_runner`).

[Testing](../contributing/test.md) explains how to run (and write) unit and integration tests.


## Building 

To build the *Dronecode SDK* so that it includes the extension library, specify the top level directory `EXTERNAL_DIR` in the `make` command 
(only one external directory can be specified). 

To build and install a parallel folder named *SDK_Extensions* (from within the DroneCore directory) you would enter:

```
make clean   # This is required!
make default EXTERNAL_DIR=../SDK_Extensions
sudo make default install   # sudo needed to install files into system directories. 
```

> **Tip** You can test this by copying the [DroneCore/external_example](https://github.com/dronecore/DroneCore/tree/{{ book.github_branch }}/external_example) directory as a peer of **DroneCore** and renaming it to *DroneCore_Extensions*.


<!-- 
## Additional Functionality

### Locking/Unlocking the SDK

Functionality delivered in: https://github.com/dronecore/DroneCore/pull/139
This is somewhat internal.
-->
