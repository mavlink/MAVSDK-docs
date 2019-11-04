# mavsdk::Shell::ShellMessage Struct Reference
`#include: shell.h`

----


[Shell](classmavsdk_1_1_shell.md) Message type. 


## Data Fields


bool [need_response](#structmavsdk_1_1_shell_1_1_shell_message_1a42aa30f0f1706d51648c0d54c5769813)  - Set if wants the receiver to send a response.

uint16_t [timeout](#structmavsdk_1_1_shell_1_1_shell_message_1a17fb510fbc5c994c808e9d6bd0b7aba3)  - Timeout for reply data in ms.

std::string [data](#structmavsdk_1_1_shell_1_1_shell_message_1ae2fcb66971e20c13d91c3ce2089e79f3)  - Serial data.


## Field Documentation


### need_response {#structmavsdk_1_1_shell_1_1_shell_message_1a42aa30f0f1706d51648c0d54c5769813}

```cpp
bool mavsdk::Shell::ShellMessage::need_response
```


Set if wants the receiver to send a response.


### timeout {#structmavsdk_1_1_shell_1_1_shell_message_1a17fb510fbc5c994c808e9d6bd0b7aba3}

```cpp
uint16_t mavsdk::Shell::ShellMessage::timeout
```


Timeout for reply data in ms.


### data {#structmavsdk_1_1_shell_1_1_shell_message_1ae2fcb66971e20c13d91c3ce2089e79f3}

```cpp
std::string mavsdk::Shell::ShellMessage::data
```


Serial data.

