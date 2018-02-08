# dronecore::Telemetry Class Reference
`#include: telemetry.h`

----


This class allows users to get vehicle telemetry and state information (e.g. battery, GPS, RC connection, flight mode etc.) and set telemetry update rates. 


## Data Structures


struct [Battery](structdronecore_1_1_telemetry_1_1_battery.md)

struct [EulerAngle](structdronecore_1_1_telemetry_1_1_euler_angle.md)

struct [GPSInfo](structdronecore_1_1_telemetry_1_1_g_p_s_info.md)

struct [GroundSpeedNED](structdronecore_1_1_telemetry_1_1_ground_speed_n_e_d.md)

struct [Health](structdronecore_1_1_telemetry_1_1_health.md)

struct [Position](structdronecore_1_1_telemetry_1_1_position.md)

struct [Quaternion](structdronecore_1_1_telemetry_1_1_quaternion.md)

struct [RCStatus](structdronecore_1_1_telemetry_1_1_r_c_status.md)

## Public Types


Type | Description
--- | ---
enum [FlightMode](#classdronecore_1_1_telemetry_1a881d44b3a1522ea14bff8834edd4145a) | Flight modes.
enum [Result](#classdronecore_1_1_telemetry_1a5bfab85edb7c160e156133a9643964bc) | Results enum for telemetry requests.
std::function< void([Result](classdronecore_1_1_telemetry.md#classdronecore_1_1_telemetry_1a5bfab85edb7c160e156133a9643964bc))> [result_callback_t](#classdronecore_1_1_telemetry_1a0375deb06bf63988c664a319a5d67fdf) | Callback type for telemetry requests.
std::function< void([Position](structdronecore_1_1_telemetry_1_1_position.md))> [position_callback_t](#classdronecore_1_1_telemetry_1a0b6f61942324aa2cb56e4c6cc97f41c3) | Callback type for position updates.
std::function< void(bool [in_air](classdronecore_1_1_telemetry.md#classdronecore_1_1_telemetry_1ae6cc80856eb3e57b9598dbea4b0a4a78))> [in_air_callback_t](#classdronecore_1_1_telemetry_1a99189e3b07a193d756ceaeaa1a91d833) | Callback type for in-air updates.
std::function< void(bool [armed](classdronecore_1_1_telemetry.md#classdronecore_1_1_telemetry_1a0ca7da7922c22509ce6d55d4ad19bcf7))> [armed_callback_t](#classdronecore_1_1_telemetry_1a832876c9db780e356bc365d3efb33655) | Callback type for armed updates (asynchronous).
std::function< void([Quaternion](structdronecore_1_1_telemetry_1_1_quaternion.md) quaternion)> [attitude_quaternion_callback_t](#classdronecore_1_1_telemetry_1a86295814a8130e61b0daea84cd8a325d) | Callback type for attitude updates in quaternion.
std::function< void([EulerAngle](structdronecore_1_1_telemetry_1_1_euler_angle.md) euler_angle)> [attitude_euler_angle_callback_t](#classdronecore_1_1_telemetry_1a8e907cdfef9c7692b01bf9369e3cccc1) | Callback type for attitude updates in Euler angles.
std::function< void([GroundSpeedNED](structdronecore_1_1_telemetry_1_1_ground_speed_n_e_d.md) [ground_speed_ned](classdronecore_1_1_telemetry.md#classdronecore_1_1_telemetry_1ae0a0fc17033ef5dc92618a027f813da2))> [ground_speed_ned_callback_t](#classdronecore_1_1_telemetry_1adfa7b9abb80fcb835b6f369e432086eb) | Callback type for ground speed (NED) updates.
std::function< void([GPSInfo](structdronecore_1_1_telemetry_1_1_g_p_s_info.md) [gps_info](classdronecore_1_1_telemetry.md#classdronecore_1_1_telemetry_1aab62cc7225f40082acbd16f2fdbb8a7e))> [gps_info_callback_t](#classdronecore_1_1_telemetry_1a4fee2a4394b618b9425fc2436709dd7c) | Callback type for GPS information updates.
std::function< void([Battery](structdronecore_1_1_telemetry_1_1_battery.md) [battery](classdronecore_1_1_telemetry.md#classdronecore_1_1_telemetry_1a28f1adb3a672c4fd15bbf1489f76e2fa))> [battery_callback_t](#classdronecore_1_1_telemetry_1addeb9f37391d82c73ceada70a654952e) | Callback type for battery status updates.
std::function< void([FlightMode](classdronecore_1_1_telemetry.md#classdronecore_1_1_telemetry_1a881d44b3a1522ea14bff8834edd4145a) [flight_mode](classdronecore_1_1_telemetry.md#classdronecore_1_1_telemetry_1ac2da43d7afc47da36a6c9d010bac22f0))> [flight_mode_callback_t](#classdronecore_1_1_telemetry_1a71d15a014fb64cf25033bf8d2917bfb2) | Callback type for flight mode updates.
std::function< void([Health](structdronecore_1_1_telemetry_1_1_health.md) [health](classdronecore_1_1_telemetry.md#classdronecore_1_1_telemetry_1a17ba227e4324b7033d0175ecab3d64bc))> [health_callback_t](#classdronecore_1_1_telemetry_1a49377fd508ff337929dd930b769bb033) | Callback type for health status updates.
std::function< void(bool [health_all_ok](classdronecore_1_1_telemetry.md#classdronecore_1_1_telemetry_1a630c91d8067e4084c4f303513a0aeb29))> [health_all_ok_callback_t](#classdronecore_1_1_telemetry_1a9d1d2b101bf57ebc838b4280641d1334) | Callback type for health status updates.
std::function< void([RCStatus](structdronecore_1_1_telemetry_1_1_r_c_status.md) [rc_status](classdronecore_1_1_telemetry.md#classdronecore_1_1_telemetry_1a1f60325b7b4b31c5c02baafd025e7bf0))> [rc_status_callback_t](#classdronecore_1_1_telemetry_1a7bbe1360883d5d1f124096e94576e4c3) | Callback type for RC status updates.

## Public Member Functions


Type | Name | Description
---: | --- | ---
| [Telemetry](#classdronecore_1_1_telemetry_1ad0cb6dd62c12af390870f8b5cb5bde55) (Device *device) | Constructor. Creates the plugin for a specific [Device](classdronecore_1_1_device.md).
| [~Telemetry](#classdronecore_1_1_telemetry_1ade5f44873d1fd5a5ec63037307920095) () | Destructor (internal use only).
| [Telemetry](#classdronecore_1_1_telemetry_1a91a3319d9040bd89d241be3d8b2e9a5e) (const Telemetry &)=delete | Copy constructor (object is not copyable).
[Result](classdronecore_1_1_telemetry.md#classdronecore_1_1_telemetry_1a5bfab85edb7c160e156133a9643964bc) | [set_rate_position](#classdronecore_1_1_telemetry_1ae7a6e1313b1508fef7163287aa77a6da) (double rate_hz) | Set rate of position updates (synchronous).
[Result](classdronecore_1_1_telemetry.md#classdronecore_1_1_telemetry_1a5bfab85edb7c160e156133a9643964bc) | [set_rate_home_position](#classdronecore_1_1_telemetry_1a9d89866f6672fbe3b88047e7ba295bf9) (double rate_hz) | Set rate of home position updates (synchronous).
[Result](classdronecore_1_1_telemetry.md#classdronecore_1_1_telemetry_1a5bfab85edb7c160e156133a9643964bc) | [set_rate_in_air](#classdronecore_1_1_telemetry_1aed902b38ff4380a8927340c291e183f5) (double rate_hz) | Set rate of in-air status updates (synchronous).
[Result](classdronecore_1_1_telemetry.md#classdronecore_1_1_telemetry_1a5bfab85edb7c160e156133a9643964bc) | [set_rate_attitude](#classdronecore_1_1_telemetry_1a2471afa3ebcc9df677e4369f9788c272) (double rate_hz) | Set rate of attitude updates (synchronous).
[Result](classdronecore_1_1_telemetry.md#classdronecore_1_1_telemetry_1a5bfab85edb7c160e156133a9643964bc) | [set_rate_camera_attitude](#classdronecore_1_1_telemetry_1ad04dcac5e40d592c04a46631350b99fd) (double rate_hz) | Set rate of camera attitude updates (synchronous).
[Result](classdronecore_1_1_telemetry.md#classdronecore_1_1_telemetry_1a5bfab85edb7c160e156133a9643964bc) | [set_rate_ground_speed_ned](#classdronecore_1_1_telemetry_1a3d3db4ee1fc2060f5f21e36bd3afe0b3) (double rate_hz) | Set rate of ground speed (NED) updates (synchronous).
[Result](classdronecore_1_1_telemetry.md#classdronecore_1_1_telemetry_1a5bfab85edb7c160e156133a9643964bc) | [set_rate_gps_info](#classdronecore_1_1_telemetry_1a7b31a3bafe6bfa4c3a9698d06fdb226d) (double rate_hz) | Set rate of GPS information updates (synchronous).
[Result](classdronecore_1_1_telemetry.md#classdronecore_1_1_telemetry_1a5bfab85edb7c160e156133a9643964bc) | [set_rate_battery](#classdronecore_1_1_telemetry_1a004c386df5e28c458a9ac56fa45f7dfe) (double rate_hz) | Set rate of battery status updates (synchronous).
[Result](classdronecore_1_1_telemetry.md#classdronecore_1_1_telemetry_1a5bfab85edb7c160e156133a9643964bc) | [set_rate_rc_status](#classdronecore_1_1_telemetry_1a9fe7d6275bf8a330673f9890481d5b4a) (double rate_hz) | Set rate of RC status updates (synchronous).
void | [set_rate_position_async](#classdronecore_1_1_telemetry_1aeac791b919a172f96b9b3e6ecb07e288) (double rate_hz, result_callback_t callback) | Set rate of position updates (asynchronous).
void | [set_rate_home_position_async](#classdronecore_1_1_telemetry_1a2540af7d324392aa7d3749568c74c140) (double rate_hz, result_callback_t callback) | Set rate of home position updates (asynchronous).
void | [set_rate_in_air_async](#classdronecore_1_1_telemetry_1aac06f897f6eff775f458ea3979f2ae68) (double rate_hz, result_callback_t callback) | Set rate of in-air status updates (asynchronous).
void | [set_rate_attitude_async](#classdronecore_1_1_telemetry_1ac219c4f150a31c38606e18a94d969a2c) (double rate_hz, result_callback_t callback) | Set rate of attitude updates (asynchronous).
void | [set_rate_camera_attitude_async](#classdronecore_1_1_telemetry_1a4afd29de2fef5eecd709252d70548eb1) (double rate_hz, result_callback_t callback) | Set rate of camera attitude updates (asynchronous).
void | [set_rate_ground_speed_ned_async](#classdronecore_1_1_telemetry_1adeff5606c33c24cece7afc2ae1247c46) (double rate_hz, result_callback_t callback) | Set rate of ground speed (NED) updates (asynchronous).
void | [set_rate_gps_info_async](#classdronecore_1_1_telemetry_1a8e65a2cf6a47faeca762866e06ee581f) (double rate_hz, result_callback_t callback) | Set rate of GPS information updates (asynchronous).
void | [set_rate_battery_async](#classdronecore_1_1_telemetry_1a52d686b80c498d8ecb66e8a59de12e3d) (double rate_hz, result_callback_t callback) | Set rate of battery status updates (asynchronous).
void | [set_rate_rc_status_async](#classdronecore_1_1_telemetry_1a931cdcb687aca9253ed6c183a977986f) (double rate_hz, result_callback_t callback) | Set rate of RC status updates (asynchronous).
[Position](structdronecore_1_1_telemetry_1_1_position.md) | [position](#classdronecore_1_1_telemetry_1aa272d9fb09a850b815c78cbdf47311e1) () const | Get the current position (synchronous).
[Position](structdronecore_1_1_telemetry_1_1_position.md) | [home_position](#classdronecore_1_1_telemetry_1a48c7bfa911ac4ecbc3dd7c374dc2ac74) () const | Get the home position (synchronous).
bool | [in_air](#classdronecore_1_1_telemetry_1ae6cc80856eb3e57b9598dbea4b0a4a78) () const | Get the in-air status (synchronous).
bool | [armed](#classdronecore_1_1_telemetry_1a0ca7da7922c22509ce6d55d4ad19bcf7) () const | Get the arming status (synchronous).
[Quaternion](structdronecore_1_1_telemetry_1_1_quaternion.md) | [attitude_quaternion](#classdronecore_1_1_telemetry_1a960a63afbe464b51267c7dbd562aa4eb) () const | Get the current attitude in quaternions (synchronous).
[EulerAngle](structdronecore_1_1_telemetry_1_1_euler_angle.md) | [attitude_euler_angle](#classdronecore_1_1_telemetry_1a2bab57f8e73e25354f7f3d7d6ac663c0) () const | Get the current attitude in Euler angles (synchronous).
[Quaternion](structdronecore_1_1_telemetry_1_1_quaternion.md) | [camera_attitude_quaternion](#classdronecore_1_1_telemetry_1acf85f5bf7a50c1e397a60e7b12dfe495) () const | Get the camera's attitude in quaternions (synchronous).
[EulerAngle](structdronecore_1_1_telemetry_1_1_euler_angle.md) | [camera_attitude_euler_angle](#classdronecore_1_1_telemetry_1a12ef129a12fcbae32b7a60008b4b135c) () const | Get the camera's attitude in Euler angles (synchronous).
[GroundSpeedNED](structdronecore_1_1_telemetry_1_1_ground_speed_n_e_d.md) | [ground_speed_ned](#classdronecore_1_1_telemetry_1ae0a0fc17033ef5dc92618a027f813da2) () const | Get the current ground speed (NED) (synchronous).
[GPSInfo](structdronecore_1_1_telemetry_1_1_g_p_s_info.md) | [gps_info](#classdronecore_1_1_telemetry_1aab62cc7225f40082acbd16f2fdbb8a7e) () const | Get the current GPS information (synchronous).
[Battery](structdronecore_1_1_telemetry_1_1_battery.md) | [battery](#classdronecore_1_1_telemetry_1a28f1adb3a672c4fd15bbf1489f76e2fa) () const | Get the current battery status (synchronous).
[FlightMode](classdronecore_1_1_telemetry.md#classdronecore_1_1_telemetry_1a881d44b3a1522ea14bff8834edd4145a) | [flight_mode](#classdronecore_1_1_telemetry_1ac2da43d7afc47da36a6c9d010bac22f0) () const | Get the current flight mode (synchronous).
[Health](structdronecore_1_1_telemetry_1_1_health.md) | [health](#classdronecore_1_1_telemetry_1a17ba227e4324b7033d0175ecab3d64bc) () const | Get the current health status (synchronous).
bool | [health_all_ok](#classdronecore_1_1_telemetry_1a630c91d8067e4084c4f303513a0aeb29) () const | Returns true if the overall health is ok (synchronous).
[RCStatus](structdronecore_1_1_telemetry_1_1_r_c_status.md) | [rc_status](#classdronecore_1_1_telemetry_1a1f60325b7b4b31c5c02baafd025e7bf0) () const | Get the RC status (synchronous).
void | [position_async](#classdronecore_1_1_telemetry_1ac4a01ef44f175ef9a84a984268708722) (position_callback_t callback) | Subscribe to position updates (asynchronous).
void | [home_position_async](#classdronecore_1_1_telemetry_1a3a90030b4259e8cf6979883d3271b0e3) (position_callback_t callback) | Subscribe to home position updates (asynchronous).
void | [in_air_async](#classdronecore_1_1_telemetry_1a0f97d0730c7f1481e82355944a99a5cf) (in_air_callback_t callback) | Subscribe to in-air updates (asynchronous).
void | [armed_async](#classdronecore_1_1_telemetry_1a5bc58c1183bc8d149b67f944740c28ca) (armed_callback_t callback) | Subscribe to armed updates (asynchronous).
void | [attitude_quaternion_async](#classdronecore_1_1_telemetry_1a5efba6a7d3eee0c0ed7fbf32d736591c) (attitude_quaternion_callback_t callback) | Subscribe to attitude updates in quaternion (asynchronous).
void | [attitude_euler_angle_async](#classdronecore_1_1_telemetry_1a4db3470f055b7a76485ec27eebee8c59) (attitude_euler_angle_callback_t callback) | Subscribe to attitude updates in Euler angles (asynchronous).
void | [camera_attitude_quaternion_async](#classdronecore_1_1_telemetry_1aa1a49c8d37499314f6050dfc4bb145ad) (attitude_quaternion_callback_t callback) | Subscribe to camera attitude updates in quaternion (asynchronous).
void | [camera_attitude_euler_angle_async](#classdronecore_1_1_telemetry_1a35b0534671564e763621f516e0197449) (attitude_euler_angle_callback_t callback) | Subscribe to camera attitude updates in Euler angles (asynchronous).
void | [ground_speed_ned_async](#classdronecore_1_1_telemetry_1a954e95659c2890e0277664910fce9c34) (ground_speed_ned_callback_t callback) | Subscribe to ground speed (NED) updates (asynchronous).
void | [gps_info_async](#classdronecore_1_1_telemetry_1afa05293d3d370ef90c5a291a22036a6e) (gps_info_callback_t callback) | Subscribe to GPS information updates (asynchronous).
void | [battery_async](#classdronecore_1_1_telemetry_1a58bf2de73fbd609460398157dc8ffdd5) (battery_callback_t callback) | Subscribe to battery status updates (asynchronous).
void | [flight_mode_async](#classdronecore_1_1_telemetry_1ac8842dec06db4bd54c8c2ba2deb0d34a) (flight_mode_callback_t callback) | Subscribe to flight mode updates (asynchronous).
void | [health_async](#classdronecore_1_1_telemetry_1a69675f46ba188d07d2e7edc110fbd2e9) (health_callback_t callback) | Subscribe to health status updates (asynchronous).
void | [health_all_ok_async](#classdronecore_1_1_telemetry_1a83b384cd04b2ed17db805cfad8bafab5) (health_all_ok_callback_t callback) | Subscribe to overall health status updates (asynchronous).
void | [rc_status_async](#classdronecore_1_1_telemetry_1a8f49537ae4c176a3e952247d60e82cd9) (rc_status_callback_t callback) | Subscribe to RC status updates (asynchronous).
const [Telemetry](classdronecore_1_1_telemetry.md) & | [operator=](#classdronecore_1_1_telemetry_1a9f46a41e835ab0beed894e49ab61515f) (const Telemetry &)=delete | Equality operator (object is not copyable).

## Static Public Member Functions


Type | Name | Description
---: | --- | ---
std::string | [flight_mode_str](#classdronecore_1_1_telemetry_1a84a33ee3ce1a95a97dd66c66d821b512) (FlightMode flight_mode) | Get a human readable English string for a flight mode.
const char * | [result_str](#classdronecore_1_1_telemetry_1a05c6355b7f8743250b2a7a611ea5fb4a) (Result result) | Get human-readable English string for [Telemetry::Result](classdronecore_1_1_telemetry.md#classdronecore_1_1_telemetry_1a5bfab85edb7c160e156133a9643964bc).


## Constructor & Destructor Documentation


### Telemetry() {#classdronecore_1_1_telemetry_1ad0cb6dd62c12af390870f8b5cb5bde55}
```cpp
dronecore::Telemetry::Telemetry(Device *device)
```


Constructor. Creates the plugin for a specific [Device](classdronecore_1_1_device.md).

The plugin is typically created as shown below: 

```cpp
auto telemetry = std::make_shared<Telemetry>(&device);
```

**Parameters**

* [Device](classdronecore_1_1_device.md) * **device** - The specific device associated with this plugin.

### ~Telemetry() {#classdronecore_1_1_telemetry_1ade5f44873d1fd5a5ec63037307920095}
```cpp
dronecore::Telemetry::~Telemetry()
```


Destructor (internal use only).


### Telemetry() {#classdronecore_1_1_telemetry_1a91a3319d9040bd89d241be3d8b2e9a5e}
```cpp
dronecore::Telemetry::Telemetry(const Telemetry &)=delete
```


Copy constructor (object is not copyable).


**Parameters**

* const [Telemetry](classdronecore_1_1_telemetry.md) & - 

## Member Typdef Documentation


### typedef result_callback_t {#classdronecore_1_1_telemetry_1a0375deb06bf63988c664a319a5d67fdf}

```cpp
typedef std::function<void(Result)> dronecore::Telemetry::result_callback_t
```


Callback type for telemetry requests.


### typedef position_callback_t {#classdronecore_1_1_telemetry_1a0b6f61942324aa2cb56e4c6cc97f41c3}

```cpp
typedef std::function<void(Position)> dronecore::Telemetry::position_callback_t
```


Callback type for position updates.


### typedef in_air_callback_t {#classdronecore_1_1_telemetry_1a99189e3b07a193d756ceaeaa1a91d833}

```cpp
typedef std::function<void(bool in_air)> dronecore::Telemetry::in_air_callback_t
```


Callback type for in-air updates.


**Parameters**

* **in_air** - true if in-air (flying) and not on-ground (landed).

### typedef armed_callback_t {#classdronecore_1_1_telemetry_1a832876c9db780e356bc365d3efb33655}

```cpp
typedef std::function<void(bool armed)> dronecore::Telemetry::armed_callback_t
```


Callback type for armed updates (asynchronous).


**Parameters**

* **armed** - true if armed (motors spinning).

### typedef attitude_quaternion_callback_t {#classdronecore_1_1_telemetry_1a86295814a8130e61b0daea84cd8a325d}

```cpp
typedef std::function<void(Quaternion quaternion)> dronecore::Telemetry::attitude_quaternion_callback_t
```


Callback type for attitude updates in quaternion.


**Parameters**

* **quaternion** - Attitude quaternion.

### typedef attitude_euler_angle_callback_t {#classdronecore_1_1_telemetry_1a8e907cdfef9c7692b01bf9369e3cccc1}

```cpp
typedef std::function<void(EulerAngle euler_angle)> dronecore::Telemetry::attitude_euler_angle_callback_t
```


Callback type for attitude updates in Euler angles.


**Parameters**

* **euler_angle** - Attitude Euler angle.

### typedef ground_speed_ned_callback_t {#classdronecore_1_1_telemetry_1adfa7b9abb80fcb835b6f369e432086eb}

```cpp
typedef std::function<void(GroundSpeedNED ground_speed_ned)> dronecore::Telemetry::ground_speed_ned_callback_t
```


Callback type for ground speed (NED) updates.


**Parameters**

* **ground_speed_ned** - Ground speed (NED).

### typedef gps_info_callback_t {#classdronecore_1_1_telemetry_1a4fee2a4394b618b9425fc2436709dd7c}

```cpp
typedef std::function<void(GPSInfo gps_info)> dronecore::Telemetry::gps_info_callback_t
```


Callback type for GPS information updates.


**Parameters**

* **gps_info** - GPS information.

### typedef battery_callback_t {#classdronecore_1_1_telemetry_1addeb9f37391d82c73ceada70a654952e}

```cpp
typedef std::function<void(Battery battery)> dronecore::Telemetry::battery_callback_t
```


Callback type for battery status updates.


**Parameters**

* **battery** - [Battery](structdronecore_1_1_telemetry_1_1_battery.md) status.

### typedef flight_mode_callback_t {#classdronecore_1_1_telemetry_1a71d15a014fb64cf25033bf8d2917bfb2}

```cpp
typedef std::function<void(FlightMode flight_mode)> dronecore::Telemetry::flight_mode_callback_t
```


Callback type for flight mode updates.


**Parameters**

* **flight_mode** - Flight mode.

### typedef health_callback_t {#classdronecore_1_1_telemetry_1a49377fd508ff337929dd930b769bb033}

```cpp
typedef std::function<void(Health health)> dronecore::Telemetry::health_callback_t
```


Callback type for health status updates.


**Parameters**

* **health** - health flags.

### typedef health_all_ok_callback_t {#classdronecore_1_1_telemetry_1a9d1d2b101bf57ebc838b4280641d1334}

```cpp
typedef std::function<void(bool health_all_ok)> dronecore::Telemetry::health_all_ok_callback_t
```


Callback type for health status updates.


**Parameters**

* **health_all_ok** - If all health flags are ok.

### typedef rc_status_callback_t {#classdronecore_1_1_telemetry_1a7bbe1360883d5d1f124096e94576e4c3}

```cpp
typedef std::function<void(RCStatus rc_status)> dronecore::Telemetry::rc_status_callback_t
```


Callback type for RC status updates.


**Parameters**

* **rc_status** - RC status.

## Member Enumeration Documentation


### enum FlightMode {#classdronecore_1_1_telemetry_1a881d44b3a1522ea14bff8834edd4145a}


Flight modes.

For more information about flight modes, check out [https://docs.px4.io/en/config/flight_mode.html](https://docs.px4.io/en/config/flight_mode.html).

Value | Description
--- | ---
<span id="classdronecore_1_1_telemetry_1a881d44b3a1522ea14bff8834edd4145aa2baa69eafc7204f3bd8648eba580c489"></span> `READY` | Armed and ready to take off. 
<span id="classdronecore_1_1_telemetry_1a881d44b3a1522ea14bff8834edd4145aa8fabc74a4ed0781d663336cbf8c9c53d"></span> `TAKEOFF` | Taking off. 
<span id="classdronecore_1_1_telemetry_1a881d44b3a1522ea14bff8834edd4145aa0c6d9dfb485b43c6fba87439f9f73ac4"></span> `HOLD` | Hold mode (hovering in place (or circling for fixed-wing vehicles). 
<span id="classdronecore_1_1_telemetry_1a881d44b3a1522ea14bff8834edd4145aaa46075d70b9612df685b11436d195196"></span> `MISSION` | [Mission](classdronecore_1_1_mission.md) mode. 
<span id="classdronecore_1_1_telemetry_1a881d44b3a1522ea14bff8834edd4145aa0d4a147a2cf60f0761f239bf3ee2745e"></span> `RETURN_TO_LAUNCH` | Returning to launch position (then landing). 
<span id="classdronecore_1_1_telemetry_1a881d44b3a1522ea14bff8834edd4145aa479a809c0b6eaaefd3b1df16f976df06"></span> `LAND` | Landing. 
<span id="classdronecore_1_1_telemetry_1a881d44b3a1522ea14bff8834edd4145aa6687898e86a83f245901f96d313930b1"></span> `OFFBOARD` | [Offboard](classdronecore_1_1_offboard.md) mode. 
<span id="classdronecore_1_1_telemetry_1a881d44b3a1522ea14bff8834edd4145aac4099cf323b2f571c3d4917db6b1a20d"></span> `FOLLOW_ME` | [FollowMe](classdronecore_1_1_follow_me.md) mode. 
<span id="classdronecore_1_1_telemetry_1a881d44b3a1522ea14bff8834edd4145aa696b031073e74bf2cb98e5ef201d4aa3"></span> `UNKNOWN` | Mode not known. 

### enum Result {#classdronecore_1_1_telemetry_1a5bfab85edb7c160e156133a9643964bc}


Results enum for telemetry requests.


Value | Description
--- | ---
<span id="classdronecore_1_1_telemetry_1a5bfab85edb7c160e156133a9643964bcad0749aaba8b833466dfcbb0428e4f89c"></span> `SUCCESS` | Request succeeded. 
<span id="classdronecore_1_1_telemetry_1a5bfab85edb7c160e156133a9643964bca23514014e50da2b2583cae24ab1ecd88"></span> `NO_DEVICE` | No device connected. 
<span id="classdronecore_1_1_telemetry_1a5bfab85edb7c160e156133a9643964bcac77f1f09dab2c0c9980fca7cfae02518"></span> `CONNECTION_ERROR` | Connection error. 
<span id="classdronecore_1_1_telemetry_1a5bfab85edb7c160e156133a9643964bca802706a9238e2928077f97736854bad4"></span> `BUSY` | [Device](classdronecore_1_1_device.md) busy. 
<span id="classdronecore_1_1_telemetry_1a5bfab85edb7c160e156133a9643964bca6fa4dbf368cea972db8d9156799d5dbe"></span> `COMMAND_DENIED` | Command denied. 
<span id="classdronecore_1_1_telemetry_1a5bfab85edb7c160e156133a9643964bca070a0fb40f6c308ab544b227660aadff"></span> `TIMEOUT` | Request timeout. 
<span id="classdronecore_1_1_telemetry_1a5bfab85edb7c160e156133a9643964bca696b031073e74bf2cb98e5ef201d4aa3"></span> `UNKNOWN` | Unknown error. 

## Member Function Documentation


### set_rate_position() {#classdronecore_1_1_telemetry_1ae7a6e1313b1508fef7163287aa77a6da}
```cpp
Result dronecore::Telemetry::set_rate_position(double rate_hz)
```


Set rate of position updates (synchronous).


**Parameters**

* double **rate_hz** - Rate in Hz.

**Returns**

&emsp;[Result](classdronecore_1_1_telemetry.md#classdronecore_1_1_telemetry_1a5bfab85edb7c160e156133a9643964bc) - Result of request.

### set_rate_home_position() {#classdronecore_1_1_telemetry_1a9d89866f6672fbe3b88047e7ba295bf9}
```cpp
Result dronecore::Telemetry::set_rate_home_position(double rate_hz)
```


Set rate of home position updates (synchronous).


**Parameters**

* double **rate_hz** - Rate in Hz.

**Returns**

&emsp;[Result](classdronecore_1_1_telemetry.md#classdronecore_1_1_telemetry_1a5bfab85edb7c160e156133a9643964bc) - Result of request.

### set_rate_in_air() {#classdronecore_1_1_telemetry_1aed902b38ff4380a8927340c291e183f5}
```cpp
Result dronecore::Telemetry::set_rate_in_air(double rate_hz)
```


Set rate of in-air status updates (synchronous).


**Parameters**

* double **rate_hz** - Rate in Hz.

**Returns**

&emsp;[Result](classdronecore_1_1_telemetry.md#classdronecore_1_1_telemetry_1a5bfab85edb7c160e156133a9643964bc) - Result of request.

### set_rate_attitude() {#classdronecore_1_1_telemetry_1a2471afa3ebcc9df677e4369f9788c272}
```cpp
Result dronecore::Telemetry::set_rate_attitude(double rate_hz)
```


Set rate of attitude updates (synchronous).


**Parameters**

* double **rate_hz** - Rate in Hz.

**Returns**

&emsp;[Result](classdronecore_1_1_telemetry.md#classdronecore_1_1_telemetry_1a5bfab85edb7c160e156133a9643964bc) - Result of request.

### set_rate_camera_attitude() {#classdronecore_1_1_telemetry_1ad04dcac5e40d592c04a46631350b99fd}
```cpp
Result dronecore::Telemetry::set_rate_camera_attitude(double rate_hz)
```


Set rate of camera attitude updates (synchronous).


**Parameters**

* double **rate_hz** - Rate in Hz.

**Returns**

&emsp;[Result](classdronecore_1_1_telemetry.md#classdronecore_1_1_telemetry_1a5bfab85edb7c160e156133a9643964bc) - Result of request.

### set_rate_ground_speed_ned() {#classdronecore_1_1_telemetry_1a3d3db4ee1fc2060f5f21e36bd3afe0b3}
```cpp
Result dronecore::Telemetry::set_rate_ground_speed_ned(double rate_hz)
```


Set rate of ground speed (NED) updates (synchronous).


**Parameters**

* double **rate_hz** - Rate in Hz.

**Returns**

&emsp;[Result](classdronecore_1_1_telemetry.md#classdronecore_1_1_telemetry_1a5bfab85edb7c160e156133a9643964bc) - Result of request.

### set_rate_gps_info() {#classdronecore_1_1_telemetry_1a7b31a3bafe6bfa4c3a9698d06fdb226d}
```cpp
Result dronecore::Telemetry::set_rate_gps_info(double rate_hz)
```


Set rate of GPS information updates (synchronous).


**Parameters**

* double **rate_hz** - Rate in Hz.

**Returns**

&emsp;[Result](classdronecore_1_1_telemetry.md#classdronecore_1_1_telemetry_1a5bfab85edb7c160e156133a9643964bc) - Result of request.

### set_rate_battery() {#classdronecore_1_1_telemetry_1a004c386df5e28c458a9ac56fa45f7dfe}
```cpp
Result dronecore::Telemetry::set_rate_battery(double rate_hz)
```


Set rate of battery status updates (synchronous).


**Parameters**

* double **rate_hz** - Rate in Hz.

**Returns**

&emsp;[Result](classdronecore_1_1_telemetry.md#classdronecore_1_1_telemetry_1a5bfab85edb7c160e156133a9643964bc) - Result of request.

### set_rate_rc_status() {#classdronecore_1_1_telemetry_1a9fe7d6275bf8a330673f9890481d5b4a}
```cpp
Result dronecore::Telemetry::set_rate_rc_status(double rate_hz)
```


Set rate of RC status updates (synchronous).


**Parameters**

* double **rate_hz** - Rate in Hz.

**Returns**

&emsp;[Result](classdronecore_1_1_telemetry.md#classdronecore_1_1_telemetry_1a5bfab85edb7c160e156133a9643964bc) - Result of request.

### set_rate_position_async() {#classdronecore_1_1_telemetry_1aeac791b919a172f96b9b3e6ecb07e288}
```cpp
void dronecore::Telemetry::set_rate_position_async(double rate_hz, result_callback_t callback)
```


Set rate of position updates (asynchronous).


**Parameters**

* double **rate_hz** - Rate in Hz.
* [result_callback_t](classdronecore_1_1_telemetry.md#classdronecore_1_1_telemetry_1a0375deb06bf63988c664a319a5d67fdf) **callback** - Callback to receive request result.

### set_rate_home_position_async() {#classdronecore_1_1_telemetry_1a2540af7d324392aa7d3749568c74c140}
```cpp
void dronecore::Telemetry::set_rate_home_position_async(double rate_hz, result_callback_t callback)
```


Set rate of home position updates (asynchronous).


**Parameters**

* double **rate_hz** - Rate in Hz.
* [result_callback_t](classdronecore_1_1_telemetry.md#classdronecore_1_1_telemetry_1a0375deb06bf63988c664a319a5d67fdf) **callback** - Callback to receive request result.

### set_rate_in_air_async() {#classdronecore_1_1_telemetry_1aac06f897f6eff775f458ea3979f2ae68}
```cpp
void dronecore::Telemetry::set_rate_in_air_async(double rate_hz, result_callback_t callback)
```


Set rate of in-air status updates (asynchronous).


**Parameters**

* double **rate_hz** - Rate in Hz.
* [result_callback_t](classdronecore_1_1_telemetry.md#classdronecore_1_1_telemetry_1a0375deb06bf63988c664a319a5d67fdf) **callback** - Callback to receive request result.

### set_rate_attitude_async() {#classdronecore_1_1_telemetry_1ac219c4f150a31c38606e18a94d969a2c}
```cpp
void dronecore::Telemetry::set_rate_attitude_async(double rate_hz, result_callback_t callback)
```


Set rate of attitude updates (asynchronous).


**Parameters**

* double **rate_hz** - Rate in Hz.
* [result_callback_t](classdronecore_1_1_telemetry.md#classdronecore_1_1_telemetry_1a0375deb06bf63988c664a319a5d67fdf) **callback** - Callback to receive request result.

### set_rate_camera_attitude_async() {#classdronecore_1_1_telemetry_1a4afd29de2fef5eecd709252d70548eb1}
```cpp
void dronecore::Telemetry::set_rate_camera_attitude_async(double rate_hz, result_callback_t callback)
```


Set rate of camera attitude updates (asynchronous).


**Parameters**

* double **rate_hz** - Rate in Hz.
* [result_callback_t](classdronecore_1_1_telemetry.md#classdronecore_1_1_telemetry_1a0375deb06bf63988c664a319a5d67fdf) **callback** - Callback to receive request result.

### set_rate_ground_speed_ned_async() {#classdronecore_1_1_telemetry_1adeff5606c33c24cece7afc2ae1247c46}
```cpp
void dronecore::Telemetry::set_rate_ground_speed_ned_async(double rate_hz, result_callback_t callback)
```


Set rate of ground speed (NED) updates (asynchronous).


**Parameters**

* double **rate_hz** - Rate in Hz.
* [result_callback_t](classdronecore_1_1_telemetry.md#classdronecore_1_1_telemetry_1a0375deb06bf63988c664a319a5d67fdf) **callback** - Callback to receive request result.

### set_rate_gps_info_async() {#classdronecore_1_1_telemetry_1a8e65a2cf6a47faeca762866e06ee581f}
```cpp
void dronecore::Telemetry::set_rate_gps_info_async(double rate_hz, result_callback_t callback)
```


Set rate of GPS information updates (asynchronous).


**Parameters**

* double **rate_hz** - Rate in Hz.
* [result_callback_t](classdronecore_1_1_telemetry.md#classdronecore_1_1_telemetry_1a0375deb06bf63988c664a319a5d67fdf) **callback** - Callback to receive request result.

### set_rate_battery_async() {#classdronecore_1_1_telemetry_1a52d686b80c498d8ecb66e8a59de12e3d}
```cpp
void dronecore::Telemetry::set_rate_battery_async(double rate_hz, result_callback_t callback)
```


Set rate of battery status updates (asynchronous).


**Parameters**

* double **rate_hz** - Rate in Hz.
* [result_callback_t](classdronecore_1_1_telemetry.md#classdronecore_1_1_telemetry_1a0375deb06bf63988c664a319a5d67fdf) **callback** - Callback to receive request result.

### set_rate_rc_status_async() {#classdronecore_1_1_telemetry_1a931cdcb687aca9253ed6c183a977986f}
```cpp
void dronecore::Telemetry::set_rate_rc_status_async(double rate_hz, result_callback_t callback)
```


Set rate of RC status updates (asynchronous).


**Parameters**

* double **rate_hz** - Rate in Hz.
* [result_callback_t](classdronecore_1_1_telemetry.md#classdronecore_1_1_telemetry_1a0375deb06bf63988c664a319a5d67fdf) **callback** - Callback to receive request result.

### position() {#classdronecore_1_1_telemetry_1aa272d9fb09a850b815c78cbdf47311e1}
```cpp
Position dronecore::Telemetry::position() const
```


Get the current position (synchronous).


**Returns**

&emsp;[Position](structdronecore_1_1_telemetry_1_1_position.md) - [Position](structdronecore_1_1_telemetry_1_1_position.md).

### home_position() {#classdronecore_1_1_telemetry_1a48c7bfa911ac4ecbc3dd7c374dc2ac74}
```cpp
Position dronecore::Telemetry::home_position() const
```


Get the home position (synchronous).


**Returns**

&emsp;[Position](structdronecore_1_1_telemetry_1_1_position.md) - Home position.

### in_air() {#classdronecore_1_1_telemetry_1ae6cc80856eb3e57b9598dbea4b0a4a78}
```cpp
bool dronecore::Telemetry::in_air() const
```


Get the in-air status (synchronous).


**Returns**

&emsp;bool - true if in-air (flying) and not on-ground (landed).

### armed() {#classdronecore_1_1_telemetry_1a0ca7da7922c22509ce6d55d4ad19bcf7}
```cpp
bool dronecore::Telemetry::armed() const
```


Get the arming status (synchronous).


**Returns**

&emsp;bool - true if armed (propellers spinning).

### attitude_quaternion() {#classdronecore_1_1_telemetry_1a960a63afbe464b51267c7dbd562aa4eb}
```cpp
Quaternion dronecore::Telemetry::attitude_quaternion() const
```


Get the current attitude in quaternions (synchronous).


**Returns**

&emsp;[Quaternion](structdronecore_1_1_telemetry_1_1_quaternion.md) - Attitude as quaternion.

### attitude_euler_angle() {#classdronecore_1_1_telemetry_1a2bab57f8e73e25354f7f3d7d6ac663c0}
```cpp
EulerAngle dronecore::Telemetry::attitude_euler_angle() const
```


Get the current attitude in Euler angles (synchronous).


**Returns**

&emsp;[EulerAngle](structdronecore_1_1_telemetry_1_1_euler_angle.md) - Attitude as Euler angle.

### camera_attitude_quaternion() {#classdronecore_1_1_telemetry_1acf85f5bf7a50c1e397a60e7b12dfe495}
```cpp
Quaternion dronecore::Telemetry::camera_attitude_quaternion() const
```


Get the camera's attitude in quaternions (synchronous).


**Returns**

&emsp;[Quaternion](structdronecore_1_1_telemetry_1_1_quaternion.md) - Camera's attitude as quaternion.

### camera_attitude_euler_angle() {#classdronecore_1_1_telemetry_1a12ef129a12fcbae32b7a60008b4b135c}
```cpp
EulerAngle dronecore::Telemetry::camera_attitude_euler_angle() const
```


Get the camera's attitude in Euler angles (synchronous).


**Returns**

&emsp;[EulerAngle](structdronecore_1_1_telemetry_1_1_euler_angle.md) - Camera's attitude as Euler angle.

### ground_speed_ned() {#classdronecore_1_1_telemetry_1ae0a0fc17033ef5dc92618a027f813da2}
```cpp
GroundSpeedNED dronecore::Telemetry::ground_speed_ned() const
```


Get the current ground speed (NED) (synchronous).


**Returns**

&emsp;[GroundSpeedNED](structdronecore_1_1_telemetry_1_1_ground_speed_n_e_d.md) - Ground speed in NED.

### gps_info() {#classdronecore_1_1_telemetry_1aab62cc7225f40082acbd16f2fdbb8a7e}
```cpp
GPSInfo dronecore::Telemetry::gps_info() const
```


Get the current GPS information (synchronous).


**Returns**

&emsp;[GPSInfo](structdronecore_1_1_telemetry_1_1_g_p_s_info.md) - GPS information.

### battery() {#classdronecore_1_1_telemetry_1a28f1adb3a672c4fd15bbf1489f76e2fa}
```cpp
Battery dronecore::Telemetry::battery() const
```


Get the current battery status (synchronous).


**Returns**

&emsp;[Battery](structdronecore_1_1_telemetry_1_1_battery.md) - 

### flight_mode() {#classdronecore_1_1_telemetry_1ac2da43d7afc47da36a6c9d010bac22f0}
```cpp
FlightMode dronecore::Telemetry::flight_mode() const
```


Get the current flight mode (synchronous).


**Returns**

&emsp;[FlightMode](classdronecore_1_1_telemetry.md#classdronecore_1_1_telemetry_1a881d44b3a1522ea14bff8834edd4145a) - Flight mode.

### health() {#classdronecore_1_1_telemetry_1a17ba227e4324b7033d0175ecab3d64bc}
```cpp
Health dronecore::Telemetry::health() const
```


Get the current health status (synchronous).


**Returns**

&emsp;[Health](structdronecore_1_1_telemetry_1_1_health.md) - [Health](structdronecore_1_1_telemetry_1_1_health.md) status.

### health_all_ok() {#classdronecore_1_1_telemetry_1a630c91d8067e4084c4f303513a0aeb29}
```cpp
bool dronecore::Telemetry::health_all_ok() const
```


Returns true if the overall health is ok (synchronous).


**Returns**

&emsp;bool - True if all health flags are OK.

### rc_status() {#classdronecore_1_1_telemetry_1a1f60325b7b4b31c5c02baafd025e7bf0}
```cpp
RCStatus dronecore::Telemetry::rc_status() const
```


Get the RC status (synchronous).


**Returns**

&emsp;[RCStatus](structdronecore_1_1_telemetry_1_1_r_c_status.md) - RC status.

### position_async() {#classdronecore_1_1_telemetry_1ac4a01ef44f175ef9a84a984268708722}
```cpp
void dronecore::Telemetry::position_async(position_callback_t callback)
```


Subscribe to position updates (asynchronous).


**Parameters**

* [position_callback_t](classdronecore_1_1_telemetry.md#classdronecore_1_1_telemetry_1a0b6f61942324aa2cb56e4c6cc97f41c3) **callback** - Function to call with updates.

### home_position_async() {#classdronecore_1_1_telemetry_1a3a90030b4259e8cf6979883d3271b0e3}
```cpp
void dronecore::Telemetry::home_position_async(position_callback_t callback)
```


Subscribe to home position updates (asynchronous).


**Parameters**

* [position_callback_t](classdronecore_1_1_telemetry.md#classdronecore_1_1_telemetry_1a0b6f61942324aa2cb56e4c6cc97f41c3) **callback** - Function to call with updates.

### in_air_async() {#classdronecore_1_1_telemetry_1a0f97d0730c7f1481e82355944a99a5cf}
```cpp
void dronecore::Telemetry::in_air_async(in_air_callback_t callback)
```


Subscribe to in-air updates (asynchronous).


**Parameters**

* [in_air_callback_t](classdronecore_1_1_telemetry.md#classdronecore_1_1_telemetry_1a99189e3b07a193d756ceaeaa1a91d833) **callback** - Function to call with updates.

### armed_async() {#classdronecore_1_1_telemetry_1a5bc58c1183bc8d149b67f944740c28ca}
```cpp
void dronecore::Telemetry::armed_async(armed_callback_t callback)
```


Subscribe to armed updates (asynchronous).

Note that armed updates are limited to 1Hz.

**Parameters**

* [armed_callback_t](classdronecore_1_1_telemetry.md#classdronecore_1_1_telemetry_1a832876c9db780e356bc365d3efb33655) **callback** - Function to call with updates.

### attitude_quaternion_async() {#classdronecore_1_1_telemetry_1a5efba6a7d3eee0c0ed7fbf32d736591c}
```cpp
void dronecore::Telemetry::attitude_quaternion_async(attitude_quaternion_callback_t callback)
```


Subscribe to attitude updates in quaternion (asynchronous).


**Parameters**

* [attitude_quaternion_callback_t](classdronecore_1_1_telemetry.md#classdronecore_1_1_telemetry_1a86295814a8130e61b0daea84cd8a325d) **callback** - Function to call with updates.

### attitude_euler_angle_async() {#classdronecore_1_1_telemetry_1a4db3470f055b7a76485ec27eebee8c59}
```cpp
void dronecore::Telemetry::attitude_euler_angle_async(attitude_euler_angle_callback_t callback)
```


Subscribe to attitude updates in Euler angles (asynchronous).


**Parameters**

* [attitude_euler_angle_callback_t](classdronecore_1_1_telemetry.md#classdronecore_1_1_telemetry_1a8e907cdfef9c7692b01bf9369e3cccc1) **callback** - Function to call with updates.

### camera_attitude_quaternion_async() {#classdronecore_1_1_telemetry_1aa1a49c8d37499314f6050dfc4bb145ad}
```cpp
void dronecore::Telemetry::camera_attitude_quaternion_async(attitude_quaternion_callback_t callback)
```


Subscribe to camera attitude updates in quaternion (asynchronous).


**Parameters**

* [attitude_quaternion_callback_t](classdronecore_1_1_telemetry.md#classdronecore_1_1_telemetry_1a86295814a8130e61b0daea84cd8a325d) **callback** - Function to call with updates.

### camera_attitude_euler_angle_async() {#classdronecore_1_1_telemetry_1a35b0534671564e763621f516e0197449}
```cpp
void dronecore::Telemetry::camera_attitude_euler_angle_async(attitude_euler_angle_callback_t callback)
```


Subscribe to camera attitude updates in Euler angles (asynchronous).


**Parameters**

* [attitude_euler_angle_callback_t](classdronecore_1_1_telemetry.md#classdronecore_1_1_telemetry_1a8e907cdfef9c7692b01bf9369e3cccc1) **callback** - Function to call with updates.

### ground_speed_ned_async() {#classdronecore_1_1_telemetry_1a954e95659c2890e0277664910fce9c34}
```cpp
void dronecore::Telemetry::ground_speed_ned_async(ground_speed_ned_callback_t callback)
```


Subscribe to ground speed (NED) updates (asynchronous).


**Parameters**

* [ground_speed_ned_callback_t](classdronecore_1_1_telemetry.md#classdronecore_1_1_telemetry_1adfa7b9abb80fcb835b6f369e432086eb) **callback** - Function to call with updates.

### gps_info_async() {#classdronecore_1_1_telemetry_1afa05293d3d370ef90c5a291a22036a6e}
```cpp
void dronecore::Telemetry::gps_info_async(gps_info_callback_t callback)
```


Subscribe to GPS information updates (asynchronous).


**Parameters**

* [gps_info_callback_t](classdronecore_1_1_telemetry.md#classdronecore_1_1_telemetry_1a4fee2a4394b618b9425fc2436709dd7c) **callback** - Function to call with updates.

### battery_async() {#classdronecore_1_1_telemetry_1a58bf2de73fbd609460398157dc8ffdd5}
```cpp
void dronecore::Telemetry::battery_async(battery_callback_t callback)
```


Subscribe to battery status updates (asynchronous).


**Parameters**

* [battery_callback_t](classdronecore_1_1_telemetry.md#classdronecore_1_1_telemetry_1addeb9f37391d82c73ceada70a654952e) **callback** - Function to call with updates.

### flight_mode_async() {#classdronecore_1_1_telemetry_1ac8842dec06db4bd54c8c2ba2deb0d34a}
```cpp
void dronecore::Telemetry::flight_mode_async(flight_mode_callback_t callback)
```


Subscribe to flight mode updates (asynchronous).

Note that flight mode updates are limited to 1Hz.

**Parameters**

* [flight_mode_callback_t](classdronecore_1_1_telemetry.md#classdronecore_1_1_telemetry_1a71d15a014fb64cf25033bf8d2917bfb2) **callback** - Function to call with updates.

### health_async() {#classdronecore_1_1_telemetry_1a69675f46ba188d07d2e7edc110fbd2e9}
```cpp
void dronecore::Telemetry::health_async(health_callback_t callback)
```


Subscribe to health status updates (asynchronous).

Note that health status updates are limited to 1Hz.

**Parameters**

* [health_callback_t](classdronecore_1_1_telemetry.md#classdronecore_1_1_telemetry_1a49377fd508ff337929dd930b769bb033) **callback** - Function to call with updates.

### health_all_ok_async() {#classdronecore_1_1_telemetry_1a83b384cd04b2ed17db805cfad8bafab5}
```cpp
void dronecore::Telemetry::health_all_ok_async(health_all_ok_callback_t callback)
```


Subscribe to overall health status updates (asynchronous).

Note that overall health status updates are limited to 1Hz.

**Parameters**

* [health_all_ok_callback_t](classdronecore_1_1_telemetry.md#classdronecore_1_1_telemetry_1a9d1d2b101bf57ebc838b4280641d1334) **callback** - Function to call with updates.

### rc_status_async() {#classdronecore_1_1_telemetry_1a8f49537ae4c176a3e952247d60e82cd9}
```cpp
void dronecore::Telemetry::rc_status_async(rc_status_callback_t callback)
```


Subscribe to RC status updates (asynchronous).


**Parameters**

* [rc_status_callback_t](classdronecore_1_1_telemetry.md#classdronecore_1_1_telemetry_1a7bbe1360883d5d1f124096e94576e4c3) **callback** - Function to call with updates.

### operator=() {#classdronecore_1_1_telemetry_1a9f46a41e835ab0beed894e49ab61515f}
```cpp
const Telemetry& dronecore::Telemetry::operator=(const Telemetry &)=delete
```


Equality operator (object is not copyable).


**Parameters**

* const [Telemetry](classdronecore_1_1_telemetry.md) & - 

**Returns**

&emsp;const [Telemetry](classdronecore_1_1_telemetry.md) & - 

### flight_mode_str() {#classdronecore_1_1_telemetry_1a84a33ee3ce1a95a97dd66c66d821b512}
```cpp
static std::string dronecore::Telemetry::flight_mode_str(FlightMode flight_mode)
```


Get a human readable English string for a flight mode.


**Parameters**

* [FlightMode](classdronecore_1_1_telemetry.md#classdronecore_1_1_telemetry_1a881d44b3a1522ea14bff8834edd4145a) **flight_mode** - 

**Returns**

&emsp;std::string - 

### result_str() {#classdronecore_1_1_telemetry_1a05c6355b7f8743250b2a7a611ea5fb4a}
```cpp
static const char* dronecore::Telemetry::result_str(Result result)
```


Get human-readable English string for [Telemetry::Result](classdronecore_1_1_telemetry.md#classdronecore_1_1_telemetry_1a5bfab85edb7c160e156133a9643964bc).


**Parameters**

* [Result](classdronecore_1_1_telemetry.md#classdronecore_1_1_telemetry_1a5bfab85edb7c160e156133a9643964bc) **result** - The enum value for which string is needed.

**Returns**

&emsp;const char * - Human readable string for the [Telemetry::Result](classdronecore_1_1_telemetry.md#classdronecore_1_1_telemetry_1a5bfab85edb7c160e156133a9643964bc).