# mavsdk::MavlinkPassthrough Class Reference
`#include: mavlink_passthrough.h`

----


The [MavlinkPassthrough](classmavsdk_1_1_mavlink_passthrough.md) class provides direct MAVLink access. 


"With great power comes great responsibility." - This plugin allows you to send and receive MAVLink messages. There is no checking or safe-guards, you're on your own, and you have been warned.


> **Note** This plugin is not included in the build by default. To add it `make ENABLE_MAVLINK_PASSTHROUGH=1` is required.


## Public Types


Type | Description
--- | ---
enum [Result](#classmavsdk_1_1_mavlink_passthrough_1a265eacaeea064a31de3fe16d1e357793) | Possible results returned for requests.

## Public Member Functions


Type | Name | Description
---: | --- | ---
&nbsp; | [MavlinkPassthrough](#classmavsdk_1_1_mavlink_passthrough_1ad17fc20d2b7c5c6996e0841aaabccb56) ([System](classmavsdk_1_1_system.md) & system) | Constructor. Creates the plugin for a specific [System](classmavsdk_1_1_system.md).
&nbsp; | [~MavlinkPassthrough](#classmavsdk_1_1_mavlink_passthrough_1a890faef9ad80c3e79e0b785fd07106c8) () | Destructor (internal use only).
&nbsp; | [MavlinkPassthrough](#classmavsdk_1_1_mavlink_passthrough_1ae4b30f9c2c5e938ab965729e27f50ce5) (const [MavlinkPassthrough](classmavsdk_1_1_mavlink_passthrough.md) &)=delete | Copy Constructor (object is not copyable).
std::string | [result_str](#classmavsdk_1_1_mavlink_passthrough_1ad9f3ba62746ee389638e29b2f75c6020) ([Result](classmavsdk_1_1_mavlink_passthrough.md#classmavsdk_1_1_mavlink_passthrough_1a265eacaeea064a31de3fe16d1e357793) result) | Returns a human-readable English string for [MavlinkPassthrough::Result](classmavsdk_1_1_mavlink_passthrough.md#classmavsdk_1_1_mavlink_passthrough_1a265eacaeea064a31de3fe16d1e357793).
[Result](classmavsdk_1_1_mavlink_passthrough.md#classmavsdk_1_1_mavlink_passthrough_1a265eacaeea064a31de3fe16d1e357793) | [send_message](#classmavsdk_1_1_mavlink_passthrough_1ac66d092318fa6d80c5bffea449f4bbaa) (mavlink_message_t & message) | Send message.
void | [subscribe_message_async](#classmavsdk_1_1_mavlink_passthrough_1a6dfb4fedba830dff881deb2e375da571) (uint16_t message_id, std::function< void(const mavlink_message_t &)> callback) | Subscribe to messages using message ID.
uint8_t | [get_our_sysid](#classmavsdk_1_1_mavlink_passthrough_1a985b269c1b78ec3e4e9d9468e46e19be) () const | Get our own system ID.
uint8_t | [get_our_compid](#classmavsdk_1_1_mavlink_passthrough_1a85ddd016ab35d5f3f487b1362723d3cf) () const | Get our own component ID.
uint8_t | [get_target_sysid](#classmavsdk_1_1_mavlink_passthrough_1a2867d1f37649d62e757bbac0a73b3ebd) () const | Get system ID of target.
uint8_t | [get_target_compid](#classmavsdk_1_1_mavlink_passthrough_1a22ecab3905237a2f227f77bbab9afd17) () const | Get target component ID.
void | [intercept_incoming_messages_async](#classmavsdk_1_1_mavlink_passthrough_1a06f6c1d181f966bc9d67c4a69e4aae7a) (std::function< bool(mavlink_message_t &)> callback) | Intercept incoming messages.
void | [intercept_outgoing_messages_async](#classmavsdk_1_1_mavlink_passthrough_1ad06c4f286f8b785a2fc09ee18dfb43c3) (std::function< bool(mavlink_message_t &)> callback) | Intercept outgoing messages.
const [MavlinkPassthrough](classmavsdk_1_1_mavlink_passthrough.md) & | [operator=](#classmavsdk_1_1_mavlink_passthrough_1aa7f49a131a8facf4d05449ec03ce3643) (const [MavlinkPassthrough](classmavsdk_1_1_mavlink_passthrough.md) &)=delete | Equality operator (object is not copyable).


## Constructor & Destructor Documentation


### MavlinkPassthrough() {#classmavsdk_1_1_mavlink_passthrough_1ad17fc20d2b7c5c6996e0841aaabccb56}
```cpp
mavsdk::MavlinkPassthrough::MavlinkPassthrough(System &system)
```


Constructor. Creates the plugin for a specific [System](classmavsdk_1_1_system.md).

The plugin is typically created as shown below: 

```cpp
auto mavlink_passthrough = std::make_shared<MavlinkPassthrough>(system);
```

**Parameters**

* [System](classmavsdk_1_1_system.md)& **system** - The specific system associated with this plugin.

### ~MavlinkPassthrough() {#classmavsdk_1_1_mavlink_passthrough_1a890faef9ad80c3e79e0b785fd07106c8}
```cpp
mavsdk::MavlinkPassthrough::~MavlinkPassthrough()
```


Destructor (internal use only).


### MavlinkPassthrough() {#classmavsdk_1_1_mavlink_passthrough_1ae4b30f9c2c5e938ab965729e27f50ce5}
```cpp
mavsdk::MavlinkPassthrough::MavlinkPassthrough(const MavlinkPassthrough &)=delete
```


Copy Constructor (object is not copyable).


**Parameters**

* const [MavlinkPassthrough](classmavsdk_1_1_mavlink_passthrough.md)&  - 

## Member Enumeration Documentation


### enum Result {#classmavsdk_1_1_mavlink_passthrough_1a265eacaeea064a31de3fe16d1e357793}


Possible results returned for requests.


Value | Description
--- | ---
<span id="classmavsdk_1_1_mavlink_passthrough_1a265eacaeea064a31de3fe16d1e357793a696b031073e74bf2cb98e5ef201d4aa3"></span> `UNKNOWN` | Unknown error. 
<span id="classmavsdk_1_1_mavlink_passthrough_1a265eacaeea064a31de3fe16d1e357793ad0749aaba8b833466dfcbb0428e4f89c"></span> `SUCCESS` | Success. 
<span id="classmavsdk_1_1_mavlink_passthrough_1a265eacaeea064a31de3fe16d1e357793ac77f1f09dab2c0c9980fca7cfae02518"></span> `CONNECTION_ERROR` | Connection error. 

## Member Function Documentation


### result_str() {#classmavsdk_1_1_mavlink_passthrough_1ad9f3ba62746ee389638e29b2f75c6020}
```cpp
std::string mavsdk::MavlinkPassthrough::result_str(Result result)
```


Returns a human-readable English string for [MavlinkPassthrough::Result](classmavsdk_1_1_mavlink_passthrough.md#classmavsdk_1_1_mavlink_passthrough_1a265eacaeea064a31de3fe16d1e357793).


**Parameters**

* [Result](classmavsdk_1_1_mavlink_passthrough.md#classmavsdk_1_1_mavlink_passthrough_1a265eacaeea064a31de3fe16d1e357793) **result** - The enum value for which a human readable string is required.

**Returns**

&emsp;std::string - Human readable string for the [MavlinkPassthrough::Result](classmavsdk_1_1_mavlink_passthrough.md#classmavsdk_1_1_mavlink_passthrough_1a265eacaeea064a31de3fe16d1e357793).

### send_message() {#classmavsdk_1_1_mavlink_passthrough_1ac66d092318fa6d80c5bffea449f4bbaa}
```cpp
Result mavsdk::MavlinkPassthrough::send_message(mavlink_message_t &message)
```


Send message.


**Parameters**

* mavlink_message_t& **message** - 

**Returns**

&emsp;[Result](classmavsdk_1_1_mavlink_passthrough.md#classmavsdk_1_1_mavlink_passthrough_1a265eacaeea064a31de3fe16d1e357793) - result of the request.

### subscribe_message_async() {#classmavsdk_1_1_mavlink_passthrough_1a6dfb4fedba830dff881deb2e375da571}
```cpp
void mavsdk::MavlinkPassthrough::subscribe_message_async(uint16_t message_id, std::function< void(const mavlink_message_t &)> callback)
```


Subscribe to messages using message ID.

This means that all future messages being received will trigger the callback to be called. To stop the subscription, call this method with `nullptr` as the argument.

**Parameters**

* uint16_t **message_id** - The MAVLink message ID.
* std::function< void(const mavlink_message_t &)> **callback** - Callback to be called for message subscription.

### get_our_sysid() {#classmavsdk_1_1_mavlink_passthrough_1a985b269c1b78ec3e4e9d9468e46e19be}
```cpp
uint8_t mavsdk::MavlinkPassthrough::get_our_sysid() const
```


Get our own system ID.


**Returns**

&emsp;uint8_t - our own system ID.

### get_our_compid() {#classmavsdk_1_1_mavlink_passthrough_1a85ddd016ab35d5f3f487b1362723d3cf}
```cpp
uint8_t mavsdk::MavlinkPassthrough::get_our_compid() const
```


Get our own component ID.


**Returns**

&emsp;uint8_t - our own component ID.

### get_target_sysid() {#classmavsdk_1_1_mavlink_passthrough_1a2867d1f37649d62e757bbac0a73b3ebd}
```cpp
uint8_t mavsdk::MavlinkPassthrough::get_target_sysid() const
```


Get system ID of target.


**Returns**

&emsp;uint8_t - system ID of target.

### get_target_compid() {#classmavsdk_1_1_mavlink_passthrough_1a22ecab3905237a2f227f77bbab9afd17}
```cpp
uint8_t mavsdk::MavlinkPassthrough::get_target_compid() const
```


Get target component ID.

This defaults to the component ID of the autopilot (1) if available and otherwise to all components (0).

**Returns**

&emsp;uint8_t - component ID of target.

### intercept_incoming_messages_async() {#classmavsdk_1_1_mavlink_passthrough_1a06f6c1d181f966bc9d67c4a69e4aae7a}
```cpp
void mavsdk::MavlinkPassthrough::intercept_incoming_messages_async(std::function< bool(mavlink_message_t &)> callback)
```


Intercept incoming messages.

This is a hook which allows to change or drop MAVLink messages as they are received before they get forwarded to the core and the other plugins.


> **Note** This functioniality is provided primarily for testing in order to simulate packet drops or actors not adhering to the MAVLink protocols.

**Parameters**

* std::function< bool(mavlink_message_t &)> **callback** - Callback to be called for each incoming message. To drop a message, return 'false' from the callback.

### intercept_outgoing_messages_async() {#classmavsdk_1_1_mavlink_passthrough_1ad06c4f286f8b785a2fc09ee18dfb43c3}
```cpp
void mavsdk::MavlinkPassthrough::intercept_outgoing_messages_async(std::function< bool(mavlink_message_t &)> callback)
```


Intercept outgoing messages.

This is a hook which allows to change or drop MAVLink messages before they are sent.


> **Note** This functioniality is provided primarily for testing in order to simulate packet drops or actors not adhering to the MAVLink protocols.

**Parameters**

* std::function< bool(mavlink_message_t &)> **callback** - Callback to be called for each outgoing message. To drop a message, return 'false' from the callback.

### operator=() {#classmavsdk_1_1_mavlink_passthrough_1aa7f49a131a8facf4d05449ec03ce3643}
```cpp
const MavlinkPassthrough& mavsdk::MavlinkPassthrough::operator=(const MavlinkPassthrough &)=delete
```


Equality operator (object is not copyable).


**Parameters**

* const [MavlinkPassthrough](classmavsdk_1_1_mavlink_passthrough.md)&  - 

**Returns**

&emsp;const [MavlinkPassthrough](classmavsdk_1_1_mavlink_passthrough.md) & - 