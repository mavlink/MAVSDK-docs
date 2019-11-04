# mavsdk::Mocap Class Reference
`#include: mocap.h`

----


This class allows users to get vehicle mocap and state information (e.g. battery, GPS, RC connection, flight mode etc.) and set mocap update rates. 


## Data Structures


struct [AngleBody](structmavsdk_1_1_mocap_1_1_angle_body.md)

struct [AngularVelocityBody](structmavsdk_1_1_mocap_1_1_angular_velocity_body.md)

struct [AttitudePositionMocap](structmavsdk_1_1_mocap_1_1_attitude_position_mocap.md)

struct [Odometry](structmavsdk_1_1_mocap_1_1_odometry.md)

struct [PositionBody](structmavsdk_1_1_mocap_1_1_position_body.md)

struct [Quaternion](structmavsdk_1_1_mocap_1_1_quaternion.md)

struct [SpeedBody](structmavsdk_1_1_mocap_1_1_speed_body.md)

struct [VisionPositionEstimate](structmavsdk_1_1_mocap_1_1_vision_position_estimate.md)

## Public Types


Type | Description
--- | ---
enum [Result](#classmavsdk_1_1_mocap_1a3af8c27b8ad9a4567feb1045e82884d5) | Results enum for mocap requests.
std::array< float, 21 > [Covariance](#classmavsdk_1_1_mocap_1a558daf6f193660cda5539a042ae91beb) | Covariance type.

## Public Member Functions


Type | Name | Description
---: | --- | ---
&nbsp; | [Mocap](#classmavsdk_1_1_mocap_1a993147a5f0ae4c8a4ddf8be4258690cc) ([System](classmavsdk_1_1_system.md) & system) | Constructor. Creates the plugin for a specific [System](classmavsdk_1_1_system.md).
&nbsp; | [~Mocap](#classmavsdk_1_1_mocap_1a0c065d15483fd1b121ac4d7046f7ea17) () | Destructor (internal use only).
&nbsp; | [Mocap](#classmavsdk_1_1_mocap_1a92d664be23f96b000e74f7c51d55a297) (const [Mocap](classmavsdk_1_1_mocap.md) &)=delete | Copy constructor (object is not copyable).
[Result](classmavsdk_1_1_mocap.md#classmavsdk_1_1_mocap_1a3af8c27b8ad9a4567feb1045e82884d5) | [set_vision_position_estimate](#classmavsdk_1_1_mocap_1a219c8fd11ff4367446315302e3e6a391) ([VisionPositionEstimate](structmavsdk_1_1_mocap_1_1_vision_position_estimate.md) vision_position_estimate) | Set the vision position.
[Result](classmavsdk_1_1_mocap.md#classmavsdk_1_1_mocap_1a3af8c27b8ad9a4567feb1045e82884d5) | [set_attitude_position_mocap](#classmavsdk_1_1_mocap_1aa053a77ec7f2fd563845cc569a7192b0) ([AttitudePositionMocap](structmavsdk_1_1_mocap_1_1_attitude_position_mocap.md) attitude_position_mocap) | Set the motion capture attitude and position.
[Result](classmavsdk_1_1_mocap.md#classmavsdk_1_1_mocap_1a3af8c27b8ad9a4567feb1045e82884d5) | [set_odometry](#classmavsdk_1_1_mocap_1af0b8da6f2d1fab36306f2874caa9c879) (const [Odometry](structmavsdk_1_1_mocap_1_1_odometry.md) & odometry) | Set the [Odometry](structmavsdk_1_1_mocap_1_1_odometry.md) information.
const [Mocap](classmavsdk_1_1_mocap.md) & | [operator=](#classmavsdk_1_1_mocap_1adf2f33e3befbec23f43e066946050eab) (const [Mocap](classmavsdk_1_1_mocap.md) &)=delete | Equality operator (object is not copyable).

## Static Public Member Functions


Type | Name | Description
---: | --- | ---
const char * | [result_str](#classmavsdk_1_1_mocap_1a016bd92c16cc6a47b183d89925922ffb) ([Result](classmavsdk_1_1_mocap.md#classmavsdk_1_1_mocap_1a3af8c27b8ad9a4567feb1045e82884d5) result) | Get human-readable English string for [Mocap::Result](classmavsdk_1_1_mocap.md#classmavsdk_1_1_mocap_1a3af8c27b8ad9a4567feb1045e82884d5).


## Constructor & Destructor Documentation


### Mocap() {#classmavsdk_1_1_mocap_1a993147a5f0ae4c8a4ddf8be4258690cc}
```cpp
mavsdk::Mocap::Mocap(System &system)
```


Constructor. Creates the plugin for a specific [System](classmavsdk_1_1_system.md).

The plugin is typically created as shown below: 

```cpp
auto mocap = std::make_shared<Mocap>(system);
```

**Parameters**

* [System](classmavsdk_1_1_system.md)& **system** - The specific system associated with this plugin.

### ~Mocap() {#classmavsdk_1_1_mocap_1a0c065d15483fd1b121ac4d7046f7ea17}
```cpp
mavsdk::Mocap::~Mocap()
```


Destructor (internal use only).


### Mocap() {#classmavsdk_1_1_mocap_1a92d664be23f96b000e74f7c51d55a297}
```cpp
mavsdk::Mocap::Mocap(const Mocap &)=delete
```


Copy constructor (object is not copyable).


**Parameters**

* const [Mocap](classmavsdk_1_1_mocap.md)&  - 

## Member Typdef Documentation


### typedef Covariance {#classmavsdk_1_1_mocap_1a558daf6f193660cda5539a042ae91beb}

```cpp
typedef std::array<float, 21> mavsdk::Mocap::Covariance
```


Covariance type.


## Member Enumeration Documentation


### enum Result {#classmavsdk_1_1_mocap_1a3af8c27b8ad9a4567feb1045e82884d5}


Results enum for mocap requests.


Value | Description
--- | ---
<span id="classmavsdk_1_1_mocap_1a3af8c27b8ad9a4567feb1045e82884d5a696b031073e74bf2cb98e5ef201d4aa3"></span> `UNKNOWN` | Unknown error. 
<span id="classmavsdk_1_1_mocap_1a3af8c27b8ad9a4567feb1045e82884d5ad0749aaba8b833466dfcbb0428e4f89c"></span> `SUCCESS` | Request succeeded. 
<span id="classmavsdk_1_1_mocap_1a3af8c27b8ad9a4567feb1045e82884d5afeae72a3a2feec3c92c2a79a30d31186"></span> `NO_SYSTEM` | No system connected. 
<span id="classmavsdk_1_1_mocap_1a3af8c27b8ad9a4567feb1045e82884d5ac77f1f09dab2c0c9980fca7cfae02518"></span> `CONNECTION_ERROR` | Connection error. 
<span id="classmavsdk_1_1_mocap_1a3af8c27b8ad9a4567feb1045e82884d5afe10e2f51d885b5e852db2b6a766c8d2"></span> `INVALID_REQUEST_DATA` | Invalid request data. 

## Member Function Documentation


### set_vision_position_estimate() {#classmavsdk_1_1_mocap_1a219c8fd11ff4367446315302e3e6a391}
```cpp
Result mavsdk::Mocap::set_vision_position_estimate(VisionPositionEstimate vision_position_estimate)
```


Set the vision position.


**Parameters**

* [VisionPositionEstimate](structmavsdk_1_1_mocap_1_1_vision_position_estimate.md) **vision_position_estimate** - Position `struct`. Set time_usec to 0 to use internal timestamp.

**Returns**

&emsp;[Result](classmavsdk_1_1_mocap.md#classmavsdk_1_1_mocap_1a3af8c27b8ad9a4567feb1045e82884d5) - 

### set_attitude_position_mocap() {#classmavsdk_1_1_mocap_1aa053a77ec7f2fd563845cc569a7192b0}
```cpp
Result mavsdk::Mocap::set_attitude_position_mocap(AttitudePositionMocap attitude_position_mocap)
```


Set the motion capture attitude and position.


**Parameters**

* [AttitudePositionMocap](structmavsdk_1_1_mocap_1_1_attitude_position_mocap.md) **attitude_position_mocap** - Position `struct`. Set time_usec to 0 to use internal timestamp.

**Returns**

&emsp;[Result](classmavsdk_1_1_mocap.md#classmavsdk_1_1_mocap_1a3af8c27b8ad9a4567feb1045e82884d5) - 

### set_odometry() {#classmavsdk_1_1_mocap_1af0b8da6f2d1fab36306f2874caa9c879}
```cpp
Result mavsdk::Mocap::set_odometry(const Odometry &odometry)
```


Set the [Odometry](structmavsdk_1_1_mocap_1_1_odometry.md) information.


**Parameters**

* const [Odometry](structmavsdk_1_1_mocap_1_1_odometry.md)& **odometry** - [Odometry](structmavsdk_1_1_mocap_1_1_odometry.md) `struct`. Set time_usec to 0 to use internal timestamp.

**Returns**

&emsp;[Result](classmavsdk_1_1_mocap.md#classmavsdk_1_1_mocap_1a3af8c27b8ad9a4567feb1045e82884d5) - 

### operator=() {#classmavsdk_1_1_mocap_1adf2f33e3befbec23f43e066946050eab}
```cpp
const Mocap& mavsdk::Mocap::operator=(const Mocap &)=delete
```


Equality operator (object is not copyable).


**Parameters**

* const [Mocap](classmavsdk_1_1_mocap.md)&  - 

**Returns**

&emsp;const [Mocap](classmavsdk_1_1_mocap.md) & - 

### result_str() {#classmavsdk_1_1_mocap_1a016bd92c16cc6a47b183d89925922ffb}
```cpp
static const char* mavsdk::Mocap::result_str(Result result)
```


Get human-readable English string for [Mocap::Result](classmavsdk_1_1_mocap.md#classmavsdk_1_1_mocap_1a3af8c27b8ad9a4567feb1045e82884d5).


**Parameters**

* [Result](classmavsdk_1_1_mocap.md#classmavsdk_1_1_mocap_1a3af8c27b8ad9a4567feb1045e82884d5) **result** - The enum value for which string is needed.

**Returns**

&emsp;const char * - Human readable string for the [Mocap::Result](classmavsdk_1_1_mocap.md#classmavsdk_1_1_mocap_1a3af8c27b8ad9a4567feb1045e82884d5).