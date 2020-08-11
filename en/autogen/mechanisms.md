# Autogeneration mechanisms

The autogeneration is made of multiple parts:

* [`protoc-gen-mavsdk`](https://github.com/mavlink/MAVSDK-Proto/tree/master/pb_plugins), which is a `protoc` custom plugin generating MAVSDK's code.
* [The API definition](https://github.com/mavlink/MAVSDK-Proto/tree/master/protos), in the form of proto files.
* Template files (per language, see e.g. the [python templates](https://github.com/mavlink/MAVSDK-Python/tree/master/other/templates/py) or the [C++ templates](https://github.com/mavlink/MAVSDK/tree/develop/templates)).

![Autogeneration pipeline](../../assets/autogen/autogen_overview.png)

`protoc` takes the custom plugin (`protoc-gen-mavsdk`) and the template files as inputs, and generate source code out of it. The way it currently works is that it generates one source file out of each `*.proto` file. For instance, `action.proto` becomes `Action.java` in MAVSDK-Java.

In some languages (typically C++), we need to generate multiple source files out of one proto definition file, and this is the reason why the C++ generation script runs protoc [in](https://github.com/mavlink/MAVSDK/blob/develop/tools/generate_from_protos.sh#L72-L74) [multiple](https://github.com/mavlink/MAVSDK/blob/develop/tools/generate_from_protos.sh#L76-L77) [passes](https://github.com/mavlink/MAVSDK/blob/develop/tools/generate_from_protos.sh#L79-L81), once [for each template](https://github.com/mavlink/MAVSDK/blob/develop/tools/generate_from_protos.sh#L79-L81) (e.g. "templates/plugin_h" defines the templates to generate `action.h`, `telemetry.h`, ..., and "templates/plugin_cpp" is responsible for `action.cpp`, `telemetry.cpp`, ...).

All the MAVSDK repositories contain some kind of `generate_from_proto.sh` file, and a `templates/` directory:

* MAVSDK-C++: [script](https://github.com/mavlink/MAVSDK/blob/develop/tools/generate_from_protos.sh), [templates](https://github.com/mavlink/MAVSDK/tree/develop/templates)
* MAVSDK-Python: [script](https://github.com/mavlink/MAVSDK-Python/blob/master/other/tools/run_protoc.sh), [templates](https://github.com/mavlink/MAVSDK-Python/tree/master/other/templates/py)
* MAVSDK-Swift: [script](https://github.com/mavlink/MAVSDK-Swift/blob/master/tools/generate_from_protos.bash), [templates](https://github.com/mavlink/MAVSDK-Swift/tree/master/templates)
* MAVSDK-Java: [script](https://github.com/mavlink/MAVSDK-Java/blob/master/sdk/build.gradle#L54-L73), [templates](https://github.com/mavlink/MAVSDK-Java/tree/master/sdk/templates)
* MAVSDK-C#: [script](https://github.com/mavlink/MAVSDK-CSharp/blob/master/MAVSDK-CSharp/MAVSDK/MAVSDK.csproj#L18-L31), [templates](https://github.com/mavlink/MAVSDK-CSharp/tree/master/MAVSDK-CSharp/MAVSDK/templates)
* MAVSDK-Go: [script](https://github.com/mavlink/MAVSDK-Go/blob/master/tools/generate_from_protos.bash), [templates](https://github.com/mavlink/MAVSDK-Go/tree/master/templates)
