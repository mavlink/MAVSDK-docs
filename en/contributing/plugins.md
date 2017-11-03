# Writing Plugins

DroneCore is split into a [core](https://github.com/dronecore/DroneCore/tree/master/core) and [plugins](https://github.com/dronecore/DroneCore/tree/master/plugins).

Plugins that are located in the correct location (a subfolder of **/plugins**) and have the correct structure are included at compile time. The *cmake* script [autogenerate_plugin_container.cmake](https://github.com/dronecore/DroneCore/blob/master/autogenerate_plugin_container.cmake) takes care of including the plugin folders and integration tests.

> **Note** Plugins can also be defined as part of an SDK/Extension Library (see [SDK Creation](../guide/sdk.md)).

## Plugin Architecture

Plugins should be written so that they are independent of each other (allowing them to be removed/replaced as needed).
They will still need to be dependent on the core source, and there will be some duplicated functionality across the plugin modules.

The code for each plugin and its unit test (if defined) is stored in a sub-folder of the **plugins** directory. Integration tests for all plugins are stored in **integration_tests**. 
A simplified view of the folder structure is shown below: 

```
├── DroneCore
│   ├── core
│   ├── integration_tests
│   └── plugins
│       ├── action
│       ├── ...
│       └── telemetry
```
Drilling down, each plugin should have the same structure as shown for the "example" plugin below.
```
└── plugins
    └── example 
        ├── CMakeLists.txt
        ├── example.cpp
        ├── example.h
        ├── example_impl.cpp
        ├── example_impl.h
        └── example_impl_test.cpp  ##optional
```

## Create a Plugin

To create a new C++ plugin, copy the [example](https://github.com/dronecore/DroneCore/tree/master/external_example/plugins/example/) plugin from the "external_example" into the DroneCore **plugins** directory.

> **Tip** Plugins are defined/written in the same way whether declared in DroneCore or 
as part of an [SDK](../guide/sdk.md). The only difference is how they are included in the build.

Modify the plugin as needed and update its [CMakeLists.txt](https://github.com/dronecore/DroneCore/blob/master/external_example/plugins/example/CMakeLists.txt) as appropriate:
* Add additional libraries using the variable `additional_libs`:
  ```
  set(additional_libs "library_name" PARENT_SCOPE)
  ```
* Add required includes with `additional_includes`:
  ```
  set(additional_includes "include_dir" PARENT_SCOPE)
  ```
<!-- * You can also add tests with `unittest_source_files`, as discussed in the following section. -->

The [standard plugins](https://github.com/dronecore/DroneCore/tree/master/plugins) can be reviewed for guidance on
how to send and process MAVLink messages.

## Test Code

[Integration tests](../contributing/test.md#writing_tests) must be created for all new and updated plugin code. 
The tests should be exhaustive, and cover all aspects of using the plugin API.

> **Note** All unit and integrations tests are run prior to accepting new code into the project.


## Example Code

> **Note** It is quicker and easier to write and modify [integration tests](#test-code) than examples. 
> Do not write example code until the plugin has been accepted!

A simple example should be written that demonstrates basic usage of its API by 3rd parties. 
The example need not cover all functionality, but should demonstrate enough that developers 
can see how it is used and how the example might be extended.

Where possible examples should demonstrate realistic use cases such that the code
can usefully be copied and reused by external developers.

The plugin example should be documented in markdown following the same pattern as the existing [examples](../examples/README.md). 


## Documentation

### In-Source Comments

The public API must be fully documented using [Doxygen](https://www.stack.nl/~dimitri/doxygen/manual/docblocks.html) markup.
All items should minimally have a brief description (preceded by the `@brief` tag).

> **Tip** The in-source comments will be compiled to markdown and included in the [API Reference](../api_reference/README.md).
> The process is outlined in [Documentation > API Reference](../contributing/documentation.md#api-reference).

Internal/implementation classes need not be documented, but should be written so that their use can be inferred.

### Guide Documentation

Ideally, [guide](../guide/README.md) documentation should be created. This should be based on example code.

The purpose of the guide is to:
* Show how different parts of the API can be used together
* Highlight usage patterns and limitations that may not be obvious from API reference
* Provide code fragments that can easily be reused

