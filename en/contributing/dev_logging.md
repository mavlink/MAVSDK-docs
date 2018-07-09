# Plugin/Test Logging

The *Dronecode SDK* provides an API that developers can use for console logging in plugins and integration tests. 
Basic [message logging](#message_logging) can be enabled by building with a specific `#define`.


## Plugin Log API

The API methods display a custom message, prepending a timestamp and the type of log message (e.g. debug) and appending the origin of the message (file and line number).

> **Tip** The API should be considered "internal". It is not exported, or intended, for use in SDK apps (and we do not commit to maintaining compatibility in future versions).

### Usage

The API is defined in [core/log.h](https://github.com/Dronecode/DronecodeSDK/blob/{{ book.github_branch }}/core/log.h) (and made available to integration tests via [core/integration_test_helper.h](https://github.com/Dronecode/DronecodeSDK/blob/{{ book.github_branch }}/core/integration_test_helper.h)). 

The API methods are called as shown below for `LogDebug()`, with the left shift operator (`<<`) used to append the message-specific text.

```cpp
#include "../path-to/core/log.h"
...
LogDebug() << "command unsupported (" << something.mavlink_command << ").";
```

### Log Methods

Function | Description | Example
--- | --- | ---
`LogDebug()` | Debug messages.<br> For reporting internal progress/state.<br>*Not displayed in RELEASE builds.* | <code style="color:green;">[04:55:08&#124;Error]</code> `This is a debug message (test_file.cpp:26)`
`LogInfo()` | Information messages.<br>For reporting progress and status. | <code style="color:#006fb8;">[04:55:08&#124;Error]</code> `This is an information message (test_file.cpp:26)`
`LogWarn()` | Warning messages.<br>For reporting when vehicle not acting as commanded (e.g. rejecting commands). | <code style="color:#ffc706;">[04:55:08&#124;Error]</code> `This is a warning message (test_file.cpp:26)`
`LogErr()` | Error messages.<br>For reporting errors in SDK behaviour (e.g. communication link issues/retry failures). | <code style="color:red;">[04:55:08&#124;Error]</code> `This is an error message (test_file.cpp:26)`


## Message Logging {#message_logging}

Basic logging is defined in source for both incoming (handled/ignored) and sent MAVLink messages.

This functionality is disabled by default, and available only in debug builds. 
To enable the logs, set `#define MESSAGE_DEBUGGING 1` in [core/system.cpp](https://github.com/Dronecode/DronecodeSDK/blob/{{ book.github_branch }}/core/system.cpp)

<!-- Added: https://github.com/Dronecode/DronecodeSDK/pull/194 -->