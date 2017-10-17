# Plugin/Test Logging

DroneCore provides an API that developers can use for console logging in plugins and integration tests. 

The API methods display a custom message, prepending a timestamp and the type of log message (e.g. debug) and appending the origin of the message (file and line number).

> **Tip** The API should be considered "internal". It is not exported, or intended, for use in Dronecore apps (and we do not commit to maintaining compatibility in future versions).


## Usage

The API is defined in [core/log.h](https://github.com/dronecore/DroneCore/blob/master/core/log.h) (and made available to integration tests via [core/integration_test_helper.h](https://github.com/dronecore/DroneCore/blob/master/core/integration_test_helper.h)). 

The API methods are called as shown below for `LogDebug()`, with the left shift operator (`<<`) used to append the message-specific text.

```cpp
#include "../path-to/core/log.h"
...
LogDebug() << "command unsupported (" << something.mavlink_command << ").";
```

## Log Methods

Function | Description | Example
--- | --- | ---
`LogDebug()` | Debug messages showing progress and internal state.<br>Debug messages. *These are not displayed in RELEASE builds*. | <code style="color:white; background-color:black;">[04:55:08&#124;Error] This is a debug message (test_file.cpp:26)</code>
`LogInfo()` | Information messages. For reporting progress and status. | <code style="color:#006fb8;">[04:55:08&#124;Error] This is an information message (test_file.cpp:26)</code>
`LogWarn()` | Warning messages. For reporting when the vehicle isn't acting as commanded (e.g. rejecting commands). |  <code style="color:#ffc706;">[04:55:08&#124;Error] This is a warning message (test_file.cpp:26)</code>
`LogErr()` | Error messages. For reporting errors in DroneCore behaviour (e.g. communication link issues/retry failures). | <code style="color:red;">[04:55:08&#124;Error] This is an error message (test_file.cpp:26)</code>
