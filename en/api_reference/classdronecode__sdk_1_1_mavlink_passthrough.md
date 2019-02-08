# dronecode_sdk::MavlinkPassthrough Class Reference
`#include: mavlink_passthrough.h`

----


The [MavlinkPassthrough](classdronecode__sdk_1_1_mavlink_passthrough.md) class provides direct MAVLink access. 


"With great power comes great responsibility." - This plugin allows you to send and receive MAVLink messages. There is no checking or safe-guards, you're on your own, and you have been warned.


> **Note** This plugin is not included in the build by default. To add it `make ENABLE_MAVLINK_PASSTHROUGH=1` is required.


## Public Types


Type | Description
--- | ---
enum [Result](#classdronecode__sdk_1_1_mavlink_passthrough_1ac3b371385d42e196ca58fd961adedcd5) | Possible results returned for requests.

## Public Member Functions


Type | Name | Description
---: | --- | ---
&nbsp; | [MavlinkPassthrough](#classdronecode__sdk_1_1_mavlink_passthrough_1a74901cc6ceb1a0b6f0100ff2c68a1b36) ([System](classdronecode__sdk_1_1_system.md) & system) | Constructor. Creates the plugin for a specific [System](classdronecode__sdk_1_1_system.md).
&nbsp; | [~MavlinkPassthrough](#classdronecode__sdk_1_1_mavlink_passthrough_1a90b903cb8589736ecaa8c239ca06143f) () | Destructor (internal use only).
&nbsp; | [MavlinkPassthrough](#classdronecode__sdk_1_1_mavlink_passthrough_1aa1424b68ca4b1692ed6b04fb574be152) (const [MavlinkPassthrough](classdronecode__sdk_1_1_mavlink_passthrough.md) &)=delete | Copy Constructor (object is not copyable).
std::string | [result_str](#classdronecode__sdk_1_1_mavlink_passthrough_1a6f6a37b8c03eee9ad5b47a11d0948991) ([Result](classdronecode__sdk_1_1_mavlink_passthrough.md#classdronecode__sdk_1_1_mavlink_passthrough_1ac3b371385d42e196ca58fd961adedcd5) result) | Returns a human-readable English string for [MavlinkPassthrough::Result](classdronecode__sdk_1_1_mavlink_passthrough.md#classdronecode__sdk_1_1_mavlink_passthrough_1ac3b371385d42e196ca58fd961adedcd5).
[Result](classdronecode__sdk_1_1_mavlink_passthrough.md#classdronecode__sdk_1_1_mavlink_passthrough_1ac3b371385d42e196ca58fd961adedcd5) | [send_message](#classdronecode__sdk_1_1_mavlink_passthrough_1a7f2011579844046bb8a66feab4210633) (mavlink_message_t & message) | Send message.
void | [subscribe_message_async](#classdronecode__sdk_1_1_mavlink_passthrough_1ac9fc1dd9b79c28a2d5ef032a5ceccebf) (uint16_t message_id, std::function< void(const mavlink_message_t &)> callback) | Subscribe to messages using message ID.
uint8_t | [get_our_sysid](#classdronecode__sdk_1_1_mavlink_passthrough_1a83495068807dd261e6d4169a125a7182) () const | Get our own system ID.
uint8_t | [get_our_compid](#classdronecode__sdk_1_1_mavlink_passthrough_1aa412d4e919557532dabee7cc11e45030) () const | Get our own component ID.
uint8_t | [get_target_sysid](#classdronecode__sdk_1_1_mavlink_passthrough_1abb0ee535513138251e738ef96d8798f9) () const | Get system ID of target.
uint8_t | [get_target_compid](#classdronecode__sdk_1_1_mavlink_passthrough_1a5295ac481c6df05126def0e5c9e184e2) () const | Get target component ID.
void | [intercept_incoming_messages_async](#classdronecode__sdk_1_1_mavlink_passthrough_1ab59ea4e649dfe6bb8c4caaf866985a72) (std::function< bool(mavlink_message_t &)> callback) | Intercept incoming messages.
void | [intercept_outgoing_messages_async](#classdronecode__sdk_1_1_mavlink_passthrough_1aa135ef8b2083d4d0b3f30f6f4125a360) (std::function< bool(mavlink_message_t &)> callback) | Intercept outgoing messages.
const [MavlinkPassthrough](classdronecode__sdk_1_1_mavlink_passthrough.md) & | [operator=](#classdronecode__sdk_1_1_mavlink_passthrough_1a77a73209d5891446455b43a90bac4523) (const [MavlinkPassthrough](classdronecode__sdk_1_1_mavlink_passthrough.md) &)=delete | Equality operator (object is not copyable).


## Constructor & Destructor Documentation


### MavlinkPassthrough() {#classdronecode__sdk_1_1_mavlink_passthrough_1a74901cc6ceb1a0b6f0100ff2c68a1b36}
```cpp
dronecode_sdk::MavlinkPassthrough::MavlinkPassthrough(System &system)
```


Constructor. Creates the plugin for a specific [System](classdronecode__sdk_1_1_system.md).

The plugin is typically created as shown below: 

```cpp
auto mavlink_passthrough = std::make_shared<MavlinkPassthrough>(system);
```

**Parameters**

* [System](classdronecode__sdk_1_1_system.md)& **system** - The specific system associated with this plugin.

### ~MavlinkPassthrough() {#classdronecode__sdk_1_1_mavlink_passthrough_1a90b903cb8589736ecaa8c239ca06143f}
```cpp
dronecode_sdk::MavlinkPassthrough::~MavlinkPassthrough()
```


Destructor (internal use only).


### MavlinkPassthrough() {#classdronecode__sdk_1_1_mavlink_passthrough_1aa1424b68ca4b1692ed6b04fb574be152}
```cpp
dronecode_sdk::MavlinkPassthrough::MavlinkPassthrough(const MavlinkPassthrough &)=delete
```


Copy Constructor (object is not copyable).


**Parameters**

* const [MavlinkPassthrough](classdronecode__sdk_1_1_mavlink_passthrough.md)&  - 

## Member Enumeration Documentation


### enum Result {#classdronecode__sdk_1_1_mavlink_passthrough_1ac3b371385d42e196ca58fd961adedcd5}


Possible results returned for requests.


Value | Description
--- | ---
<span id="classdronecode__sdk_1_1_mavlink_passthrough_1ac3b371385d42e196ca58fd961adedcd5a696b031073e74bf2cb98e5ef201d4aa3"></span> `UNKNOWN` | Unknown error. 
<span id="classdronecode__sdk_1_1_mavlink_passthrough_1ac3b371385d42e196ca58fd961adedcd5ad0749aaba8b833466dfcbb0428e4f89c"></span> `SUCCESS` | Success. 
<span id="classdronecode__sdk_1_1_mavlink_passthrough_1ac3b371385d42e196ca58fd961adedcd5ac77f1f09dab2c0c9980fca7cfae02518"></span> `CONNECTION_ERROR` | Connection error. 

## Member Function Documentation


### result_str() {#classdronecode__sdk_1_1_mavlink_passthrough_1a6f6a37b8c03eee9ad5b47a11d0948991}
```cpp
std::string dronecode_sdk::MavlinkPassthrough::result_str(Result result)
```


Returns a human-readable English string for [MavlinkPassthrough::Result](classdronecode__sdk_1_1_mavlink_passthrough.md#classdronecode__sdk_1_1_mavlink_passthrough_1ac3b371385d42e196ca58fd961adedcd5).


**Parameters**

* [Result](classdronecode__sdk_1_1_mavlink_passthrough.md#classdronecode__sdk_1_1_mavlink_passthrough_1ac3b371385d42e196ca58fd961adedcd5) **result** - The enum value for which a human readable string is required.

**Returns**

&emsp;std::string - Human readable string for the [MavlinkPassthrough::Result](classdronecode__sdk_1_1_mavlink_passthrough.md#classdronecode__sdk_1_1_mavlink_passthrough_1ac3b371385d42e196ca58fd961adedcd5).

### send_message() {#classdronecode__sdk_1_1_mavlink_passthrough_1a7f2011579844046bb8a66feab4210633}
```cpp
Result dronecode_sdk::MavlinkPassthrough::send_message(mavlink_message_t &message)
```


Send message.


**Parameters**

* mavlink_message_t& **message** - 

**Returns**

&emsp;[Result](classdronecode__sdk_1_1_mavlink_passthrough.md#classdronecode__sdk_1_1_mavlink_passthrough_1ac3b371385d42e196ca58fd961adedcd5) - result of the request.

### subscribe_message_async() {#classdronecode__sdk_1_1_mavlink_passthrough_1ac9fc1dd9b79c28a2d5ef032a5ceccebf}
```cpp
void dronecode_sdk::MavlinkPassthrough::subscribe_message_async(uint16_t message_id, std::function< void(const mavlink_message_t &)> callback)
```


Subscribe to messages using message ID.

This means that all future messages being received will trigger the callback to be called. To stop the subscription, call this method with `nullptr` as the argument.

**Parameters**

* uint16_t **message_id** - The MAVLink message ID.
* std::function< void(const mavlink_message_t &)> **callback** - Callback to be called for message subscription.

### get_our_sysid() {#classdronecode__sdk_1_1_mavlink_passthrough_1a83495068807dd261e6d4169a125a7182}
```cpp
uint8_t dronecode_sdk::MavlinkPassthrough::get_our_sysid() const
```


Get our own system ID.


**Returns**

&emsp;uint8_t - our own system ID.

### get_our_compid() {#classdronecode__sdk_1_1_mavlink_passthrough_1aa412d4e919557532dabee7cc11e45030}
```cpp
uint8_t dronecode_sdk::MavlinkPassthrough::get_our_compid() const
```


Get our own component ID.


**Returns**

&emsp;uint8_t - our own component ID.

### get_target_sysid() {#classdronecode__sdk_1_1_mavlink_passthrough_1abb0ee535513138251e738ef96d8798f9}
```cpp
uint8_t dronecode_sdk::MavlinkPassthrough::get_target_sysid() const
```


Get system ID of target.


**Returns**

&emsp;uint8_t - system ID of target.

### get_target_compid() {#classdronecode__sdk_1_1_mavlink_passthrough_1a5295ac481c6df05126def0e5c9e184e2}
```cpp
uint8_t dronecode_sdk::MavlinkPassthrough::get_target_compid() const
```


Get target component ID.

This defaults to the component ID of the autopilot (1) if available and otherwise to all components (0).

**Returns**

&emsp;uint8_t - component ID of target.

### intercept_incoming_messages_async() {#classdronecode__sdk_1_1_mavlink_passthrough_1ab59ea4e649dfe6bb8c4caaf866985a72}
```cpp
void dronecode_sdk::MavlinkPassthrough::intercept_incoming_messages_async(std::function< bool(mavlink_message_t &)> callback)
```


Intercept incoming messages.

This is a hook which allows to change or drop MAVLink messages as they are received before they get forwarded to the core and the other plugins.


> **Note** This functioniality is provided primarily for testing in order to simulate packet drops or actors not adhering to the MAVLink protocols.

**Parameters**

* std::function< bool(mavlink_message_t &)> **callback** - Callback to be called for each incoming message. To drop a message, return 'false' from the callback.

### intercept_outgoing_messages_async() {#classdronecode__sdk_1_1_mavlink_passthrough_1aa135ef8b2083d4d0b3f30f6f4125a360}
```cpp
void dronecode_sdk::MavlinkPassthrough::intercept_outgoing_messages_async(std::function< bool(mavlink_message_t &)> callback)
```


Intercept outgoing messages.

This is a hook which allows to change or drop MAVLink messages before they are sent.


> **Note** This functioniality is provided primarily for testing in order to simulate packet drops or actors not adhering to the MAVLink protocols.

**Parameters**

* std::function< bool(mavlink_message_t &)> **callback** - Callback to be called for each outgoing message. To drop a message, return 'false' from the callback.

### operator=() {#classdronecode__sdk_1_1_mavlink_passthrough_1a77a73209d5891446455b43a90bac4523}
```cpp
const MavlinkPassthrough& dronecode_sdk::MavlinkPassthrough::operator=(const MavlinkPassthrough &)=delete
```


Equality operator (object is not copyable).


**Parameters**

* const [MavlinkPassthrough](classdronecode__sdk_1_1_mavlink_passthrough.md)&  - 

**Returns**

&emsp;const [MavlinkPassthrough](classdronecode__sdk_1_1_mavlink_passthrough.md) & - 