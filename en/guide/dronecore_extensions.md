# DroneCore Extensions

DroneCore can be extended with [plugins](../contributing/plugins.md) and [tests](../contributing/test.md) that are defined "out of tree".
This enables developers to manage custom code in a separate repository (reducing *git* conflicts). 
The extensions are built into the DroneCore library at compile time.

> **Note** Extensions are defined in a parallel tree that *mirrors* the DroneCore structure. 
> Extension plugins and tests are *exactly the same* as "standard" DroneCore plugins and tests.

## Folder Structure

The extension folder *mirrors* DroneCore, and **must** contain the folders **integration_tests** and **plugins**.
The *plugin* folder contains appropriately named sub-folders for each plugin (along with its unit test code).

A simplified view of a "typical" extension directory is shown below (in this case named "DroneCore_Extensions"). 

```
├── DroneCore
│   ├── core
│   ├── integration_tests
│   └── plugins
│       ├── action
│       ├── ...
│       └── telemetry
├── DroneCore_Extensions
│   ├── integration_tests
│   └── plugins
│       ├── camera
│       ├── another_plugin
│       └── etc.
```

## Create a DroneCore Extension Library

To create a new C++ DroneCore Extension Library, first copy [DroneCore/external_example](https://github.com/dronecore/DroneCore/tree/master/external_example) to the same folder level as the DroneCore directory.
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

Plugins in extension libraries are exactly the same as "normal" DroneCore plugins 
(except that they are located in the extension rather than under DroneCore). 

[Writing Plugins](../contributing/plugins.md) explains how to write or modify plugins.

> **Tip** To create a new plugin you can either copy and modify an existing DroneCore plugin
> or start from the example plugin shown above.


## Testing

Tests in extension libraries are written and run exactly the same as "normal" DroneCore plugin tests.

[Testing](../contributing/test.md) explains how to run (and write) unit and integration tests.


## Building 

To build *DroneCore* so that it includes the extension library, specify the top level directory `EXTERNAL_DIR` in the `make` command 
(only one external directory can be specified). 
The line below shows how this is done for the [external_example](https://github.com/dronecore/DroneCore/tree/master/external_example) directory.

```
make clean  # This is required!
make EXTERNAL_DIR=external_example
```

To build a parallel *DroneCore_Extensions* folder (from within the DroneCore directory) you would enter:

```
make clean   # This is required!
make EXTERNAL_DIR=../DroneCore_Extensions
```


<!-- 
## Additional Functionality

### Locking/Unlocking the SDK

Functionality to deliver in: https://github.com/dronecore/DroneCore/pull/139
-->
