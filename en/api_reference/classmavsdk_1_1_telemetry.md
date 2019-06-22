# mavsdk::Telemetry Class Reference
`#include: telemetry.h`

----


This class allows users to get vehicle telemetry and state information (e.g. battery, GPS, RC connection, flight mode etc.) and set telemetry update rates. 


## Data Structures


struct [Battery](structmavsdk_1_1_telemetry_1_1_battery.md)

struct [EulerAngle](structmavsdk_1_1_telemetry_1_1_euler_angle.md)

struct [GPSInfo](structmavsdk_1_1_telemetry_1_1_g_p_s_info.md)

struct [GroundSpeedNED](structmavsdk_1_1_telemetry_1_1_ground_speed_n_e_d.md)

struct [Health](structmavsdk_1_1_telemetry_1_1_health.md)

struct [Position](structmavsdk_1_1_telemetry_1_1_position.md)

struct [PositionNED](structmavsdk_1_1_telemetry_1_1_position_n_e_d.md)

struct [PositionVelocityNED](structmavsdk_1_1_telemetry_1_1_position_velocity_n_e_d.md)

struct [Quaternion](structmavsdk_1_1_telemetry_1_1_quaternion.md)

struct [RCStatus](structmavsdk_1_1_telemetry_1_1_r_c_status.md)

struct [StatusText](structmavsdk_1_1_telemetry_1_1_status_text.md)

struct [VelocityNED](structmavsdk_1_1_telemetry_1_1_velocity_n_e_d.md)

## Public Types


Type | Description
--- | ---
enum [FlightMode](#classmavsdk_1_1_telemetry_1a8317d953a82a23654db6f14509acb4fe) | Flight modes.
enum [Result](#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75) | Results enum for telemetry requests.
std::function< void([Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75))> [result_callback_t](#classmavsdk_1_1_telemetry_1a1e9e3db79bb18a5e144c3aad4dfe57e7) | Callback type for telemetry requests.
std::function< void([PositionVelocityNED](structmavsdk_1_1_telemetry_1_1_position_velocity_n_e_d.md))> [position_velocity_ned_callback_t](#classmavsdk_1_1_telemetry_1adc89dbb35eb82768c59656519a69d6ba) | Callback type for kinematic (position and velocity) updates.
std::function< void([Position](structmavsdk_1_1_telemetry_1_1_position.md))> [position_callback_t](#classmavsdk_1_1_telemetry_1aadcd5ce9f12b7de8f44b32aff9bc766f) | Callback type for position updates.
std::function< void(bool [in_air](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a909738ff2fbe104c6eb4524cc9bf2dd5))> [in_air_callback_t](#classmavsdk_1_1_telemetry_1a5c89acce93f9c8b4379ed0dd002ee68c) | Callback type for in-air updates.
std::function< void([StatusText](structmavsdk_1_1_telemetry_1_1_status_text.md) [status_text](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a2f31c0668ed1ac1bfdfa4b2e9a2023a9))> [status_text_callback_t](#classmavsdk_1_1_telemetry_1ab6bfd92d95e534b04ed98f09bf3a1e7a) | Callback for mavlink status text updates.
std::function< void(bool [armed](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a6620142adc47f069262e5bf69dbb3876))> [armed_callback_t](#classmavsdk_1_1_telemetry_1a795e5848a43b29f5009d91e6c87b37d0) | Callback type for armed updates (asynchronous).
std::function< void([Quaternion](structmavsdk_1_1_telemetry_1_1_quaternion.md) quaternion)> [attitude_quaternion_callback_t](#classmavsdk_1_1_telemetry_1a8f1fb6e5bfb5c5bdd0c6469f0870775c) | Callback type for attitude updates in quaternion.
std::function< void([EulerAngle](structmavsdk_1_1_telemetry_1_1_euler_angle.md) euler_angle)> [attitude_euler_angle_callback_t](#classmavsdk_1_1_telemetry_1ab2076cee92c4714482d83a2be7526b9c) | Callback type for attitude updates in Euler angles.
std::function< void([GroundSpeedNED](structmavsdk_1_1_telemetry_1_1_ground_speed_n_e_d.md) [ground_speed_ned](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1afd68d9d29f14023ffdcb7d86a4b47f04))> [ground_speed_ned_callback_t](#classmavsdk_1_1_telemetry_1a0b58b0ef625a1eaf864d3a4890cb2a23) | Callback type for ground speed (NED) updates.
std::function< void([GPSInfo](structmavsdk_1_1_telemetry_1_1_g_p_s_info.md) [gps_info](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a76a4e21380d03dd2112fdc0e9c3c44b7))> [gps_info_callback_t](#classmavsdk_1_1_telemetry_1af34942b21fde18d723b300ebe6c40421) | Callback type for GPS information updates.
std::function< void([Battery](structmavsdk_1_1_telemetry_1_1_battery.md) [battery](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1afb3bad3c7a36c14ae97492df3f6bbd54))> [battery_callback_t](#classmavsdk_1_1_telemetry_1ab7582939b706b1eea718c94433a1e5de) | Callback type for battery status updates.
std::function< void([FlightMode](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a8317d953a82a23654db6f14509acb4fe) [flight_mode](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a4972a3968e379d565e7700f2f51158dd))> [flight_mode_callback_t](#classmavsdk_1_1_telemetry_1ad8cfe203cf88b457ed3593eb82d3ff77) | Callback type for flight mode updates.
std::function< void([Health](structmavsdk_1_1_telemetry_1_1_health.md) [health](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1aae4824c9eeb72603b197c864b5cc5df5))> [health_callback_t](#classmavsdk_1_1_telemetry_1abadf7c5be3e650809402115c1810a8d7) | Callback type for health status updates.
std::function< void(bool [health_all_ok](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1ad6d833741b5576f07204d268c5cd4d06))> [health_all_ok_callback_t](#classmavsdk_1_1_telemetry_1a8fe09456f509c93e2110fb45996bd927) | Callback type for health status updates.
std::function< void([RCStatus](structmavsdk_1_1_telemetry_1_1_r_c_status.md) [rc_status](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1aa8301c58483148b9e211d2f27f9c3140))> [rc_status_callback_t](#classmavsdk_1_1_telemetry_1ade4c432133b83aa9612528117a2cd6d6) | Callback type for RC status updates.

## Public Member Functions


Type | Name | Description
---: | --- | ---
&nbsp; | [Telemetry](#classmavsdk_1_1_telemetry_1a6c8c8ed8759fc8c6e9fd4e7644c63cbe) ([System](classmavsdk_1_1_system.md) & system) | Constructor. Creates the plugin for a specific [System](classmavsdk_1_1_system.md).
&nbsp; | [~Telemetry](#classmavsdk_1_1_telemetry_1a1db31974e0ea6ea9a530d68783566ab1) () | Destructor (internal use only).
&nbsp; | [Telemetry](#classmavsdk_1_1_telemetry_1ad2bbcfbf06add4067bdc42bf239b6ecb) (const [Telemetry](classmavsdk_1_1_telemetry.md) &)=delete | Copy constructor (object is not copyable).
[Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75) | [set_rate_position_velocity_ned](#classmavsdk_1_1_telemetry_1a7cb04951523d210ccd1d68911d58f23e) (double rate_hz) | Set rate of kinematic (position and velocity) updates (synchronous).
[Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75) | [set_rate_position](#classmavsdk_1_1_telemetry_1a7bb2f0ad795108ea857cbd6b9f802ee2) (double rate_hz) | Set rate of position updates (synchronous).
[Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75) | [set_rate_home_position](#classmavsdk_1_1_telemetry_1a3ea9fc72cfdd86136f59701c57c46f9b) (double rate_hz) | Set rate of home position updates (synchronous).
[Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75) | [set_rate_in_air](#classmavsdk_1_1_telemetry_1ab2a3a7172e83982525353d6a5c6cb929) (double rate_hz) | Set rate of in-air status updates (synchronous).
[Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75) | [set_rate_attitude](#classmavsdk_1_1_telemetry_1a948a58cb3756134dee7fd60191911493) (double rate_hz) | Set rate of attitude updates (synchronous).
[Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75) | [set_rate_camera_attitude](#classmavsdk_1_1_telemetry_1a60caa6177503040d9926eb75249c12af) (double rate_hz) | Set rate of camera attitude updates (synchronous).
[Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75) | [set_rate_ground_speed_ned](#classmavsdk_1_1_telemetry_1a229bfcf87a09f98ede59522817f8911c) (double rate_hz) | Set rate of ground speed (NED) updates (synchronous).
[Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75) | [set_rate_gps_info](#classmavsdk_1_1_telemetry_1aaf3270f4688f586c65daa29f712df04b) (double rate_hz) | Set rate of GPS information updates (synchronous).
[Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75) | [set_rate_battery](#classmavsdk_1_1_telemetry_1a58135427b4f862bc41db8888cc328d08) (double rate_hz) | Set rate of battery status updates (synchronous).
[Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75) | [set_rate_rc_status](#classmavsdk_1_1_telemetry_1a5ab00a099c7a7052433e652ed19466fd) (double rate_hz) | Set rate of RC status updates (synchronous).
void | [set_rate_position_velocity_ned_async](#classmavsdk_1_1_telemetry_1a618da18fabb0c13f07f1eb0c3e1e3395) (double rate_hz, [result_callback_t](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a1e9e3db79bb18a5e144c3aad4dfe57e7) callback) | Set rate of kinematic (position and velocity) updates (asynchronous).
void | [set_rate_position_async](#classmavsdk_1_1_telemetry_1aa8d3e034d11fccb1533d1a782618f4a4) (double rate_hz, [result_callback_t](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a1e9e3db79bb18a5e144c3aad4dfe57e7) callback) | Set rate of position updates (asynchronous).
void | [set_rate_home_position_async](#classmavsdk_1_1_telemetry_1a3b9a4de97101c11420b29f6ff010b164) (double rate_hz, [result_callback_t](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a1e9e3db79bb18a5e144c3aad4dfe57e7) callback) | Set rate of home position updates (asynchronous).
void | [set_rate_in_air_async](#classmavsdk_1_1_telemetry_1aa11598e99766e395309d3899211191aa) (double rate_hz, [result_callback_t](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a1e9e3db79bb18a5e144c3aad4dfe57e7) callback) | Set rate of in-air status updates (asynchronous).
void | [set_rate_attitude_async](#classmavsdk_1_1_telemetry_1ae16699eb5a558b663b5666b6788c483f) (double rate_hz, [result_callback_t](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a1e9e3db79bb18a5e144c3aad4dfe57e7) callback) | Set rate of attitude updates (asynchronous).
void | [set_rate_camera_attitude_async](#classmavsdk_1_1_telemetry_1a7f73b3bb2119a426b01af4370a90c9b9) (double rate_hz, [result_callback_t](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a1e9e3db79bb18a5e144c3aad4dfe57e7) callback) | Set rate of camera attitude updates (asynchronous).
void | [set_rate_ground_speed_ned_async](#classmavsdk_1_1_telemetry_1a813e26ab74c7200e09e8ad8c8ecb597a) (double rate_hz, [result_callback_t](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a1e9e3db79bb18a5e144c3aad4dfe57e7) callback) | Set rate of ground speed (NED) updates (asynchronous).
void | [set_rate_gps_info_async](#classmavsdk_1_1_telemetry_1a09d9232f3fc83de09e1b97fbde9edd27) (double rate_hz, [result_callback_t](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a1e9e3db79bb18a5e144c3aad4dfe57e7) callback) | Set rate of GPS information updates (asynchronous).
void | [set_rate_battery_async](#classmavsdk_1_1_telemetry_1aa0c57683779b276c196543d1b11b4794) (double rate_hz, [result_callback_t](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a1e9e3db79bb18a5e144c3aad4dfe57e7) callback) | Set rate of battery status updates (asynchronous).
void | [set_rate_rc_status_async](#classmavsdk_1_1_telemetry_1ab293eac4daab1b8628e3adce311312ec) (double rate_hz, [result_callback_t](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a1e9e3db79bb18a5e144c3aad4dfe57e7) callback) | Set rate of RC status updates (asynchronous).
[PositionVelocityNED](structmavsdk_1_1_telemetry_1_1_position_velocity_n_e_d.md) | [position_velocity_ned](#classmavsdk_1_1_telemetry_1abb053c00761eb67b07816d9e01427f37) () const | Get the current kinematic (position and velocity) in NED frame (synchronous).
[Position](structmavsdk_1_1_telemetry_1_1_position.md) | [position](#classmavsdk_1_1_telemetry_1a2299da1bc63313c429f07ab0fdbe5335) () const | Get the current position (synchronous).
[Position](structmavsdk_1_1_telemetry_1_1_position.md) | [home_position](#classmavsdk_1_1_telemetry_1ad4e079b3067a79da8b3b2f3067dc4178) () const | Get the home position (synchronous).
[StatusText](structmavsdk_1_1_telemetry_1_1_status_text.md) | [status_text](#classmavsdk_1_1_telemetry_1a2f31c0668ed1ac1bfdfa4b2e9a2023a9) () const | Get status text (synchronous).
bool | [in_air](#classmavsdk_1_1_telemetry_1a909738ff2fbe104c6eb4524cc9bf2dd5) () const | Get the in-air status (synchronous).
bool | [armed](#classmavsdk_1_1_telemetry_1a6620142adc47f069262e5bf69dbb3876) () const | Get the arming status (synchronous).
[Quaternion](structmavsdk_1_1_telemetry_1_1_quaternion.md) | [attitude_quaternion](#classmavsdk_1_1_telemetry_1aae76890957b33727be72a39807448c88) () const | Get the current attitude in quaternions (synchronous).
[EulerAngle](structmavsdk_1_1_telemetry_1_1_euler_angle.md) | [attitude_euler_angle](#classmavsdk_1_1_telemetry_1af57a6e448b22f1126e34c3031d7f4af9) () const | Get the current attitude in Euler angles (synchronous).
[Quaternion](structmavsdk_1_1_telemetry_1_1_quaternion.md) | [camera_attitude_quaternion](#classmavsdk_1_1_telemetry_1a3c07447351d3b6195d5e2526e7b128b3) () const | Get the camera's attitude in quaternions (synchronous).
[EulerAngle](structmavsdk_1_1_telemetry_1_1_euler_angle.md) | [camera_attitude_euler_angle](#classmavsdk_1_1_telemetry_1a4e17866a65077bb3db474e6437848fce) () const | Get the camera's attitude in Euler angles (synchronous).
[GroundSpeedNED](structmavsdk_1_1_telemetry_1_1_ground_speed_n_e_d.md) | [ground_speed_ned](#classmavsdk_1_1_telemetry_1afd68d9d29f14023ffdcb7d86a4b47f04) () const | Get the current ground speed (NED) (synchronous).
[GPSInfo](structmavsdk_1_1_telemetry_1_1_g_p_s_info.md) | [gps_info](#classmavsdk_1_1_telemetry_1a76a4e21380d03dd2112fdc0e9c3c44b7) () const | Get the current GPS information (synchronous).
[Battery](structmavsdk_1_1_telemetry_1_1_battery.md) | [battery](#classmavsdk_1_1_telemetry_1afb3bad3c7a36c14ae97492df3f6bbd54) () const | Get the current battery status (synchronous).
[FlightMode](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a8317d953a82a23654db6f14509acb4fe) | [flight_mode](#classmavsdk_1_1_telemetry_1a4972a3968e379d565e7700f2f51158dd) () const | Get the current flight mode (synchronous).
[Health](structmavsdk_1_1_telemetry_1_1_health.md) | [health](#classmavsdk_1_1_telemetry_1aae4824c9eeb72603b197c864b5cc5df5) () const | Get the current health status (synchronous).
bool | [health_all_ok](#classmavsdk_1_1_telemetry_1ad6d833741b5576f07204d268c5cd4d06) () const | Returns true if the overall health is ok (synchronous).
[RCStatus](structmavsdk_1_1_telemetry_1_1_r_c_status.md) | [rc_status](#classmavsdk_1_1_telemetry_1aa8301c58483148b9e211d2f27f9c3140) () const | Get the RC status (synchronous).
void | [position_velocity_ned_async](#classmavsdk_1_1_telemetry_1ab966373bd9975304132ac81f0f8dcd97) ([position_velocity_ned_callback_t](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1adc89dbb35eb82768c59656519a69d6ba) callback) | Subscribe to kinematic (position and velocity) updates (asynchronous).
void | [position_async](#classmavsdk_1_1_telemetry_1a36c873a346ec80ffa6440191e57e440a) ([position_callback_t](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1aadcd5ce9f12b7de8f44b32aff9bc766f) callback) | Subscribe to position updates (asynchronous).
void | [home_position_async](#classmavsdk_1_1_telemetry_1ad732889dfb7e0b6e8607d04e1a0d379a) ([position_callback_t](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1aadcd5ce9f12b7de8f44b32aff9bc766f) callback) | Subscribe to home position updates (asynchronous).
void | [in_air_async](#classmavsdk_1_1_telemetry_1ab7872779d80172a8c3ec1f381995613c) ([in_air_callback_t](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a5c89acce93f9c8b4379ed0dd002ee68c) callback) | Subscribe to in-air updates (asynchronous).
void | [status_text_async](#classmavsdk_1_1_telemetry_1a3dafc5195525739b84f6ae9774484450) ([status_text_callback_t](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1ab6bfd92d95e534b04ed98f09bf3a1e7a) callback) | Subscribe to status text updates (asynchronous).
void | [armed_async](#classmavsdk_1_1_telemetry_1ae73fc84556a85ecc07de33f5b1f8f8cc) ([armed_callback_t](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a795e5848a43b29f5009d91e6c87b37d0) callback) | Subscribe to armed updates (asynchronous).
void | [attitude_quaternion_async](#classmavsdk_1_1_telemetry_1a73c1f4f96fd2ac08e8a6eae6bba00098) ([attitude_quaternion_callback_t](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a8f1fb6e5bfb5c5bdd0c6469f0870775c) callback) | Subscribe to attitude updates in quaternion (asynchronous).
void | [attitude_euler_angle_async](#classmavsdk_1_1_telemetry_1ab7dba6f0da6bd624ae3ce7f2da5d50cd) ([attitude_euler_angle_callback_t](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1ab2076cee92c4714482d83a2be7526b9c) callback) | Subscribe to attitude updates in Euler angles (asynchronous).
void | [camera_attitude_quaternion_async](#classmavsdk_1_1_telemetry_1ae39f1c1769189fbd7e21fb216da7cfd2) ([attitude_quaternion_callback_t](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a8f1fb6e5bfb5c5bdd0c6469f0870775c) callback) | Subscribe to camera attitude updates in quaternion (asynchronous).
void | [camera_attitude_euler_angle_async](#classmavsdk_1_1_telemetry_1adb78b9cb7d918970a19222e1a8101706) ([attitude_euler_angle_callback_t](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1ab2076cee92c4714482d83a2be7526b9c) callback) | Subscribe to camera attitude updates in Euler angles (asynchronous).
void | [ground_speed_ned_async](#classmavsdk_1_1_telemetry_1a3eb3256f1a4708a6cf19ac28bc6e3568) ([ground_speed_ned_callback_t](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a0b58b0ef625a1eaf864d3a4890cb2a23) callback) | Subscribe to ground speed (NED) updates (asynchronous).
void | [gps_info_async](#classmavsdk_1_1_telemetry_1a2ba72a9a7b24c9d16fa39482077ccfac) ([gps_info_callback_t](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1af34942b21fde18d723b300ebe6c40421) callback) | Subscribe to GPS information updates (asynchronous).
void | [battery_async](#classmavsdk_1_1_telemetry_1aabb419112c981a837cee2f498b96c2c5) ([battery_callback_t](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1ab7582939b706b1eea718c94433a1e5de) callback) | Subscribe to battery status updates (asynchronous).
void | [flight_mode_async](#classmavsdk_1_1_telemetry_1adede4202304e53466b4df41367a75878) ([flight_mode_callback_t](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1ad8cfe203cf88b457ed3593eb82d3ff77) callback) | Subscribe to flight mode updates (asynchronous).
void | [health_async](#classmavsdk_1_1_telemetry_1aceb2a5a458cafd2171720424652c8e39) ([health_callback_t](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1abadf7c5be3e650809402115c1810a8d7) callback) | Subscribe to health status updates (asynchronous).
void | [health_all_ok_async](#classmavsdk_1_1_telemetry_1ae1a2f05a126a88b19e78078ef5f552f4) ([health_all_ok_callback_t](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a8fe09456f509c93e2110fb45996bd927) callback) | Subscribe to overall health status updates (asynchronous).
void | [rc_status_async](#classmavsdk_1_1_telemetry_1a5c1cba91eb65f738470c51da4d74aecc) ([rc_status_callback_t](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1ade4c432133b83aa9612528117a2cd6d6) callback) | Subscribe to RC status updates (asynchronous).
const [Telemetry](classmavsdk_1_1_telemetry.md) & | [operator=](#classmavsdk_1_1_telemetry_1a703ac978c925be8806921925cf16aca9) (const [Telemetry](classmavsdk_1_1_telemetry.md) &)=delete | Equality operator (object is not copyable).

## Static Public Member Functions


Type | Name | Description
---: | --- | ---
std::string | [flight_mode_str](#classmavsdk_1_1_telemetry_1a25933c37dd05e5c3b7b4e9d52507cca7) ([FlightMode](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a8317d953a82a23654db6f14509acb4fe) flight_mode) | Get a human readable English string for a flight mode.
const char * | [result_str](#classmavsdk_1_1_telemetry_1a20bff42d7bb42c002ef7217cf98990e8) ([Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75) result) | Get human-readable English string for [Telemetry::Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75).


## Constructor & Destructor Documentation


### Telemetry() {#classmavsdk_1_1_telemetry_1a6c8c8ed8759fc8c6e9fd4e7644c63cbe}
```cpp
mavsdk::Telemetry::Telemetry(System &system)
```


Constructor. Creates the plugin for a specific [System](classmavsdk_1_1_system.md).

The plugin is typically created as shown below: 

```cpp
auto telemetry = std::make_shared<Telemetry>(system);
```

**Parameters**

* [System](classmavsdk_1_1_system.md)& **system** - The specific system associated with this plugin.

### ~Telemetry() {#classmavsdk_1_1_telemetry_1a1db31974e0ea6ea9a530d68783566ab1}
```cpp
mavsdk::Telemetry::~Telemetry()
```


Destructor (internal use only).


### Telemetry() {#classmavsdk_1_1_telemetry_1ad2bbcfbf06add4067bdc42bf239b6ecb}
```cpp
mavsdk::Telemetry::Telemetry(const Telemetry &)=delete
```


Copy constructor (object is not copyable).


**Parameters**

* const [Telemetry](classmavsdk_1_1_telemetry.md)&  - 

## Member Typdef Documentation


### typedef result_callback_t {#classmavsdk_1_1_telemetry_1a1e9e3db79bb18a5e144c3aad4dfe57e7}

```cpp
typedef std::function<void(Result)> mavsdk::Telemetry::result_callback_t
```


Callback type for telemetry requests.


### typedef position_velocity_ned_callback_t {#classmavsdk_1_1_telemetry_1adc89dbb35eb82768c59656519a69d6ba}

```cpp
typedef std::function<void(PositionVelocityNED)> mavsdk::Telemetry::position_velocity_ned_callback_t
```


Callback type for kinematic (position and velocity) updates.


### typedef position_callback_t {#classmavsdk_1_1_telemetry_1aadcd5ce9f12b7de8f44b32aff9bc766f}

```cpp
typedef std::function<void(Position)> mavsdk::Telemetry::position_callback_t
```


Callback type for position updates.


### typedef in_air_callback_t {#classmavsdk_1_1_telemetry_1a5c89acce93f9c8b4379ed0dd002ee68c}

```cpp
typedef std::function<void(bool in_air)> mavsdk::Telemetry::in_air_callback_t
```


Callback type for in-air updates.


**Parameters**

* **in_air** - true if in-air (flying) and not on-ground (landed).

### typedef status_text_callback_t {#classmavsdk_1_1_telemetry_1ab6bfd92d95e534b04ed98f09bf3a1e7a}

```cpp
typedef std::function<void(StatusText status_text)> mavsdk::Telemetry::status_text_callback_t
```


Callback for mavlink status text updates.


**Parameters**

* **status** - text with message type and text.

### typedef armed_callback_t {#classmavsdk_1_1_telemetry_1a795e5848a43b29f5009d91e6c87b37d0}

```cpp
typedef std::function<void(bool armed)> mavsdk::Telemetry::armed_callback_t
```


Callback type for armed updates (asynchronous).


**Parameters**

* **armed** - true if armed (motors spinning).

### typedef attitude_quaternion_callback_t {#classmavsdk_1_1_telemetry_1a8f1fb6e5bfb5c5bdd0c6469f0870775c}

```cpp
typedef std::function<void(Quaternion quaternion)> mavsdk::Telemetry::attitude_quaternion_callback_t
```


Callback type for attitude updates in quaternion.


**Parameters**

* **quaternion** - Attitude quaternion.

### typedef attitude_euler_angle_callback_t {#classmavsdk_1_1_telemetry_1ab2076cee92c4714482d83a2be7526b9c}

```cpp
typedef std::function<void(EulerAngle euler_angle)> mavsdk::Telemetry::attitude_euler_angle_callback_t
```


Callback type for attitude updates in Euler angles.


**Parameters**

* **euler_angle** - Attitude Euler angle.

### typedef ground_speed_ned_callback_t {#classmavsdk_1_1_telemetry_1a0b58b0ef625a1eaf864d3a4890cb2a23}

```cpp
typedef std::function<void(GroundSpeedNED ground_speed_ned)> mavsdk::Telemetry::ground_speed_ned_callback_t
```


Callback type for ground speed (NED) updates.


**Parameters**

* **ground_speed_ned** - Ground speed (NED).

### typedef gps_info_callback_t {#classmavsdk_1_1_telemetry_1af34942b21fde18d723b300ebe6c40421}

```cpp
typedef std::function<void(GPSInfo gps_info)> mavsdk::Telemetry::gps_info_callback_t
```


Callback type for GPS information updates.


**Parameters**

* **gps_info** - GPS information.

### typedef battery_callback_t {#classmavsdk_1_1_telemetry_1ab7582939b706b1eea718c94433a1e5de}

```cpp
typedef std::function<void(Battery battery)> mavsdk::Telemetry::battery_callback_t
```


Callback type for battery status updates.


**Parameters**

* **battery** - [Battery](structmavsdk_1_1_telemetry_1_1_battery.md) status.

### typedef flight_mode_callback_t {#classmavsdk_1_1_telemetry_1ad8cfe203cf88b457ed3593eb82d3ff77}

```cpp
typedef std::function<void(FlightMode flight_mode)> mavsdk::Telemetry::flight_mode_callback_t
```


Callback type for flight mode updates.


**Parameters**

* **flight_mode** - Flight mode.

### typedef health_callback_t {#classmavsdk_1_1_telemetry_1abadf7c5be3e650809402115c1810a8d7}

```cpp
typedef std::function<void(Health health)> mavsdk::Telemetry::health_callback_t
```


Callback type for health status updates.


**Parameters**

* **health** - health flags.

### typedef health_all_ok_callback_t {#classmavsdk_1_1_telemetry_1a8fe09456f509c93e2110fb45996bd927}

```cpp
typedef std::function<void(bool health_all_ok)> mavsdk::Telemetry::health_all_ok_callback_t
```


Callback type for health status updates.


**Parameters**

* **health_all_ok** - If all health flags are ok.

### typedef rc_status_callback_t {#classmavsdk_1_1_telemetry_1ade4c432133b83aa9612528117a2cd6d6}

```cpp
typedef std::function<void(RCStatus rc_status)> mavsdk::Telemetry::rc_status_callback_t
```


Callback type for RC status updates.


**Parameters**

* **rc_status** - RC status.

## Member Enumeration Documentation


### enum FlightMode {#classmavsdk_1_1_telemetry_1a8317d953a82a23654db6f14509acb4fe}


Flight modes.

For more information about flight modes, check out [https://docs.px4.io/en/config/flight_mode.html](https://docs.px4.io/en/config/flight_mode.html).

Value | Description
--- | ---
<span id="classmavsdk_1_1_telemetry_1a8317d953a82a23654db6f14509acb4fea2baa69eafc7204f3bd8648eba580c489"></span> `READY` | Armed and ready to take off. 
<span id="classmavsdk_1_1_telemetry_1a8317d953a82a23654db6f14509acb4fea8fabc74a4ed0781d663336cbf8c9c53d"></span> `TAKEOFF` | Taking off. 
<span id="classmavsdk_1_1_telemetry_1a8317d953a82a23654db6f14509acb4fea0c6d9dfb485b43c6fba87439f9f73ac4"></span> `HOLD` | Hold mode (hovering in place (or circling for fixed-wing vehicles). 
<span id="classmavsdk_1_1_telemetry_1a8317d953a82a23654db6f14509acb4feaa46075d70b9612df685b11436d195196"></span> `MISSION` | [Mission](classmavsdk_1_1_mission.md) mode. 
<span id="classmavsdk_1_1_telemetry_1a8317d953a82a23654db6f14509acb4fea0d4a147a2cf60f0761f239bf3ee2745e"></span> `RETURN_TO_LAUNCH` | Returning to launch position (then landing). 
<span id="classmavsdk_1_1_telemetry_1a8317d953a82a23654db6f14509acb4fea479a809c0b6eaaefd3b1df16f976df06"></span> `LAND` | Landing. 
<span id="classmavsdk_1_1_telemetry_1a8317d953a82a23654db6f14509acb4fea6687898e86a83f245901f96d313930b1"></span> `OFFBOARD` | [Offboard](classmavsdk_1_1_offboard.md) mode. 
<span id="classmavsdk_1_1_telemetry_1a8317d953a82a23654db6f14509acb4feac4099cf323b2f571c3d4917db6b1a20d"></span> `FOLLOW_ME` | [FollowMe](classmavsdk_1_1_follow_me.md) mode. 
<span id="classmavsdk_1_1_telemetry_1a8317d953a82a23654db6f14509acb4fea696b031073e74bf2cb98e5ef201d4aa3"></span> `UNKNOWN` | Mode not known. 

### enum Result {#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75}


Results enum for telemetry requests.


Value | Description
--- | ---
<span id="classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75ad0749aaba8b833466dfcbb0428e4f89c"></span> `SUCCESS` | Request succeeded. 
<span id="classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75afeae72a3a2feec3c92c2a79a30d31186"></span> `NO_SYSTEM` | No system connected. 
<span id="classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75ac77f1f09dab2c0c9980fca7cfae02518"></span> `CONNECTION_ERROR` | Connection error. 
<span id="classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75a802706a9238e2928077f97736854bad4"></span> `BUSY` | [System](classmavsdk_1_1_system.md) busy. 
<span id="classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75a6fa4dbf368cea972db8d9156799d5dbe"></span> `COMMAND_DENIED` | Command denied. 
<span id="classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75a070a0fb40f6c308ab544b227660aadff"></span> `TIMEOUT` | Request timeout. 
<span id="classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75a696b031073e74bf2cb98e5ef201d4aa3"></span> `UNKNOWN` | Unknown error. 

## Member Function Documentation


### set_rate_position_velocity_ned() {#classmavsdk_1_1_telemetry_1a7cb04951523d210ccd1d68911d58f23e}
```cpp
Result mavsdk::Telemetry::set_rate_position_velocity_ned(double rate_hz)
```


Set rate of kinematic (position and velocity) updates (synchronous).


**Parameters**

* double **rate_hz** - Rate in Hz.

**Returns**

&emsp;[Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75) - Result of request.

**See Also:**
- [PositionVelocityNED](structmavsdk_1_1_telemetry_1_1_position_velocity_n_e_d.md)


### set_rate_position() {#classmavsdk_1_1_telemetry_1a7bb2f0ad795108ea857cbd6b9f802ee2}
```cpp
Result mavsdk::Telemetry::set_rate_position(double rate_hz)
```


Set rate of position updates (synchronous).


**Parameters**

* double **rate_hz** - Rate in Hz.

**Returns**

&emsp;[Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75) - Result of request.

### set_rate_home_position() {#classmavsdk_1_1_telemetry_1a3ea9fc72cfdd86136f59701c57c46f9b}
```cpp
Result mavsdk::Telemetry::set_rate_home_position(double rate_hz)
```


Set rate of home position updates (synchronous).


**Parameters**

* double **rate_hz** - Rate in Hz.

**Returns**

&emsp;[Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75) - Result of request.

### set_rate_in_air() {#classmavsdk_1_1_telemetry_1ab2a3a7172e83982525353d6a5c6cb929}
```cpp
Result mavsdk::Telemetry::set_rate_in_air(double rate_hz)
```


Set rate of in-air status updates (synchronous).


**Parameters**

* double **rate_hz** - Rate in Hz.

**Returns**

&emsp;[Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75) - Result of request.

### set_rate_attitude() {#classmavsdk_1_1_telemetry_1a948a58cb3756134dee7fd60191911493}
```cpp
Result mavsdk::Telemetry::set_rate_attitude(double rate_hz)
```


Set rate of attitude updates (synchronous).


**Parameters**

* double **rate_hz** - Rate in Hz.

**Returns**

&emsp;[Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75) - Result of request.

### set_rate_camera_attitude() {#classmavsdk_1_1_telemetry_1a60caa6177503040d9926eb75249c12af}
```cpp
Result mavsdk::Telemetry::set_rate_camera_attitude(double rate_hz)
```


Set rate of camera attitude updates (synchronous).


**Parameters**

* double **rate_hz** - Rate in Hz.

**Returns**

&emsp;[Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75) - Result of request.

### set_rate_ground_speed_ned() {#classmavsdk_1_1_telemetry_1a229bfcf87a09f98ede59522817f8911c}
```cpp
Result mavsdk::Telemetry::set_rate_ground_speed_ned(double rate_hz)
```


Set rate of ground speed (NED) updates (synchronous).


**Parameters**

* double **rate_hz** - Rate in Hz.

**Returns**

&emsp;[Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75) - Result of request.

### set_rate_gps_info() {#classmavsdk_1_1_telemetry_1aaf3270f4688f586c65daa29f712df04b}
```cpp
Result mavsdk::Telemetry::set_rate_gps_info(double rate_hz)
```


Set rate of GPS information updates (synchronous).


**Parameters**

* double **rate_hz** - Rate in Hz.

**Returns**

&emsp;[Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75) - Result of request.

### set_rate_battery() {#classmavsdk_1_1_telemetry_1a58135427b4f862bc41db8888cc328d08}
```cpp
Result mavsdk::Telemetry::set_rate_battery(double rate_hz)
```


Set rate of battery status updates (synchronous).


**Parameters**

* double **rate_hz** - Rate in Hz.

**Returns**

&emsp;[Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75) - Result of request.

### set_rate_rc_status() {#classmavsdk_1_1_telemetry_1a5ab00a099c7a7052433e652ed19466fd}
```cpp
Result mavsdk::Telemetry::set_rate_rc_status(double rate_hz)
```


Set rate of RC status updates (synchronous).


**Parameters**

* double **rate_hz** - Rate in Hz.

**Returns**

&emsp;[Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75) - Result of request.

### set_rate_position_velocity_ned_async() {#classmavsdk_1_1_telemetry_1a618da18fabb0c13f07f1eb0c3e1e3395}
```cpp
void mavsdk::Telemetry::set_rate_position_velocity_ned_async(double rate_hz, result_callback_t callback)
```


Set rate of kinematic (position and velocity) updates (asynchronous).


**Parameters**

* double **rate_hz** - Rate in Hz.
* [result_callback_t](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a1e9e3db79bb18a5e144c3aad4dfe57e7) **callback** - Callback to receive request result.

**See Also:**
- [PositionVelocityNED](structmavsdk_1_1_telemetry_1_1_position_velocity_n_e_d.md)


### set_rate_position_async() {#classmavsdk_1_1_telemetry_1aa8d3e034d11fccb1533d1a782618f4a4}
```cpp
void mavsdk::Telemetry::set_rate_position_async(double rate_hz, result_callback_t callback)
```


Set rate of position updates (asynchronous).


**Parameters**

* double **rate_hz** - Rate in Hz.
* [result_callback_t](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a1e9e3db79bb18a5e144c3aad4dfe57e7) **callback** - Callback to receive request result.

### set_rate_home_position_async() {#classmavsdk_1_1_telemetry_1a3b9a4de97101c11420b29f6ff010b164}
```cpp
void mavsdk::Telemetry::set_rate_home_position_async(double rate_hz, result_callback_t callback)
```


Set rate of home position updates (asynchronous).


**Parameters**

* double **rate_hz** - Rate in Hz.
* [result_callback_t](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a1e9e3db79bb18a5e144c3aad4dfe57e7) **callback** - Callback to receive request result.

### set_rate_in_air_async() {#classmavsdk_1_1_telemetry_1aa11598e99766e395309d3899211191aa}
```cpp
void mavsdk::Telemetry::set_rate_in_air_async(double rate_hz, result_callback_t callback)
```


Set rate of in-air status updates (asynchronous).


**Parameters**

* double **rate_hz** - Rate in Hz.
* [result_callback_t](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a1e9e3db79bb18a5e144c3aad4dfe57e7) **callback** - Callback to receive request result.

### set_rate_attitude_async() {#classmavsdk_1_1_telemetry_1ae16699eb5a558b663b5666b6788c483f}
```cpp
void mavsdk::Telemetry::set_rate_attitude_async(double rate_hz, result_callback_t callback)
```


Set rate of attitude updates (asynchronous).


**Parameters**

* double **rate_hz** - Rate in Hz.
* [result_callback_t](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a1e9e3db79bb18a5e144c3aad4dfe57e7) **callback** - Callback to receive request result.

### set_rate_camera_attitude_async() {#classmavsdk_1_1_telemetry_1a7f73b3bb2119a426b01af4370a90c9b9}
```cpp
void mavsdk::Telemetry::set_rate_camera_attitude_async(double rate_hz, result_callback_t callback)
```


Set rate of camera attitude updates (asynchronous).


**Parameters**

* double **rate_hz** - Rate in Hz.
* [result_callback_t](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a1e9e3db79bb18a5e144c3aad4dfe57e7) **callback** - Callback to receive request result.

### set_rate_ground_speed_ned_async() {#classmavsdk_1_1_telemetry_1a813e26ab74c7200e09e8ad8c8ecb597a}
```cpp
void mavsdk::Telemetry::set_rate_ground_speed_ned_async(double rate_hz, result_callback_t callback)
```


Set rate of ground speed (NED) updates (asynchronous).


**Parameters**

* double **rate_hz** - Rate in Hz.
* [result_callback_t](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a1e9e3db79bb18a5e144c3aad4dfe57e7) **callback** - Callback to receive request result.

### set_rate_gps_info_async() {#classmavsdk_1_1_telemetry_1a09d9232f3fc83de09e1b97fbde9edd27}
```cpp
void mavsdk::Telemetry::set_rate_gps_info_async(double rate_hz, result_callback_t callback)
```


Set rate of GPS information updates (asynchronous).


**Parameters**

* double **rate_hz** - Rate in Hz.
* [result_callback_t](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a1e9e3db79bb18a5e144c3aad4dfe57e7) **callback** - Callback to receive request result.

### set_rate_battery_async() {#classmavsdk_1_1_telemetry_1aa0c57683779b276c196543d1b11b4794}
```cpp
void mavsdk::Telemetry::set_rate_battery_async(double rate_hz, result_callback_t callback)
```


Set rate of battery status updates (asynchronous).


**Parameters**

* double **rate_hz** - Rate in Hz.
* [result_callback_t](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a1e9e3db79bb18a5e144c3aad4dfe57e7) **callback** - Callback to receive request result.

### set_rate_rc_status_async() {#classmavsdk_1_1_telemetry_1ab293eac4daab1b8628e3adce311312ec}
```cpp
void mavsdk::Telemetry::set_rate_rc_status_async(double rate_hz, result_callback_t callback)
```


Set rate of RC status updates (asynchronous).


**Parameters**

* double **rate_hz** - Rate in Hz.
* [result_callback_t](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a1e9e3db79bb18a5e144c3aad4dfe57e7) **callback** - Callback to receive request result.

### position_velocity_ned() {#classmavsdk_1_1_telemetry_1abb053c00761eb67b07816d9e01427f37}
```cpp
PositionVelocityNED mavsdk::Telemetry::position_velocity_ned() const
```


Get the current kinematic (position and velocity) in NED frame (synchronous).


**Returns**

&emsp;[PositionVelocityNED](structmavsdk_1_1_telemetry_1_1_position_velocity_n_e_d.md) - [PositionVelocityNED](structmavsdk_1_1_telemetry_1_1_position_velocity_n_e_d.md).

### position() {#classmavsdk_1_1_telemetry_1a2299da1bc63313c429f07ab0fdbe5335}
```cpp
Position mavsdk::Telemetry::position() const
```


Get the current position (synchronous).


**Returns**

&emsp;[Position](structmavsdk_1_1_telemetry_1_1_position.md) - [Position](structmavsdk_1_1_telemetry_1_1_position.md).

### home_position() {#classmavsdk_1_1_telemetry_1ad4e079b3067a79da8b3b2f3067dc4178}
```cpp
Position mavsdk::Telemetry::home_position() const
```


Get the home position (synchronous).


**Returns**

&emsp;[Position](structmavsdk_1_1_telemetry_1_1_position.md) - Home position.

### status_text() {#classmavsdk_1_1_telemetry_1a2f31c0668ed1ac1bfdfa4b2e9a2023a9}
```cpp
StatusText mavsdk::Telemetry::status_text() const
```


Get status text (synchronous).


**Returns**

&emsp;[StatusText](structmavsdk_1_1_telemetry_1_1_status_text.md) - Status text.

### in_air() {#classmavsdk_1_1_telemetry_1a909738ff2fbe104c6eb4524cc9bf2dd5}
```cpp
bool mavsdk::Telemetry::in_air() const
```


Get the in-air status (synchronous).


**Returns**

&emsp;bool - true if in-air (flying) and not on-ground (landed).

### armed() {#classmavsdk_1_1_telemetry_1a6620142adc47f069262e5bf69dbb3876}
```cpp
bool mavsdk::Telemetry::armed() const
```


Get the arming status (synchronous).


**Returns**

&emsp;bool - true if armed (propellers spinning).

### attitude_quaternion() {#classmavsdk_1_1_telemetry_1aae76890957b33727be72a39807448c88}
```cpp
Quaternion mavsdk::Telemetry::attitude_quaternion() const
```


Get the current attitude in quaternions (synchronous).


**Returns**

&emsp;[Quaternion](structmavsdk_1_1_telemetry_1_1_quaternion.md) - Attitude as quaternion.

### attitude_euler_angle() {#classmavsdk_1_1_telemetry_1af57a6e448b22f1126e34c3031d7f4af9}
```cpp
EulerAngle mavsdk::Telemetry::attitude_euler_angle() const
```


Get the current attitude in Euler angles (synchronous).


**Returns**

&emsp;[EulerAngle](structmavsdk_1_1_telemetry_1_1_euler_angle.md) - Attitude as Euler angle.

### camera_attitude_quaternion() {#classmavsdk_1_1_telemetry_1a3c07447351d3b6195d5e2526e7b128b3}
```cpp
Quaternion mavsdk::Telemetry::camera_attitude_quaternion() const
```


Get the camera's attitude in quaternions (synchronous).

Note that the yaw component of attitude is relative to North (absolute frame).

**Returns**

&emsp;[Quaternion](structmavsdk_1_1_telemetry_1_1_quaternion.md) - [Camera](classmavsdk_1_1_camera.md)'s attitude as quaternion.

### camera_attitude_euler_angle() {#classmavsdk_1_1_telemetry_1a4e17866a65077bb3db474e6437848fce}
```cpp
EulerAngle mavsdk::Telemetry::camera_attitude_euler_angle() const
```


Get the camera's attitude in Euler angles (synchronous).

Note that the yaw component of attitude is relative to North (absolute frame).

**Returns**

&emsp;[EulerAngle](structmavsdk_1_1_telemetry_1_1_euler_angle.md) - [Camera](classmavsdk_1_1_camera.md)'s attitude as Euler angle.

### ground_speed_ned() {#classmavsdk_1_1_telemetry_1afd68d9d29f14023ffdcb7d86a4b47f04}
```cpp
GroundSpeedNED mavsdk::Telemetry::ground_speed_ned() const
```


Get the current ground speed (NED) (synchronous).


**Returns**

&emsp;[GroundSpeedNED](structmavsdk_1_1_telemetry_1_1_ground_speed_n_e_d.md) - Ground speed in NED.

### gps_info() {#classmavsdk_1_1_telemetry_1a76a4e21380d03dd2112fdc0e9c3c44b7}
```cpp
GPSInfo mavsdk::Telemetry::gps_info() const
```


Get the current GPS information (synchronous).


**Returns**

&emsp;[GPSInfo](structmavsdk_1_1_telemetry_1_1_g_p_s_info.md) - GPS information.

### battery() {#classmavsdk_1_1_telemetry_1afb3bad3c7a36c14ae97492df3f6bbd54}
```cpp
Battery mavsdk::Telemetry::battery() const
```


Get the current battery status (synchronous).


**Returns**

&emsp;[Battery](structmavsdk_1_1_telemetry_1_1_battery.md) - 

### flight_mode() {#classmavsdk_1_1_telemetry_1a4972a3968e379d565e7700f2f51158dd}
```cpp
FlightMode mavsdk::Telemetry::flight_mode() const
```


Get the current flight mode (synchronous).


**Returns**

&emsp;[FlightMode](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a8317d953a82a23654db6f14509acb4fe) - Flight mode.

### health() {#classmavsdk_1_1_telemetry_1aae4824c9eeb72603b197c864b5cc5df5}
```cpp
Health mavsdk::Telemetry::health() const
```


Get the current health status (synchronous).


**Returns**

&emsp;[Health](structmavsdk_1_1_telemetry_1_1_health.md) - [Health](structmavsdk_1_1_telemetry_1_1_health.md) status.

### health_all_ok() {#classmavsdk_1_1_telemetry_1ad6d833741b5576f07204d268c5cd4d06}
```cpp
bool mavsdk::Telemetry::health_all_ok() const
```


Returns true if the overall health is ok (synchronous).


**Returns**

&emsp;bool - True if all health flags are OK.

### rc_status() {#classmavsdk_1_1_telemetry_1aa8301c58483148b9e211d2f27f9c3140}
```cpp
RCStatus mavsdk::Telemetry::rc_status() const
```


Get the RC status (synchronous).


**Returns**

&emsp;[RCStatus](structmavsdk_1_1_telemetry_1_1_r_c_status.md) - RC status.

### position_velocity_ned_async() {#classmavsdk_1_1_telemetry_1ab966373bd9975304132ac81f0f8dcd97}
```cpp
void mavsdk::Telemetry::position_velocity_ned_async(position_velocity_ned_callback_t callback)
```


Subscribe to kinematic (position and velocity) updates (asynchronous).


**Parameters**

* [position_velocity_ned_callback_t](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1adc89dbb35eb82768c59656519a69d6ba) **callback** - Function to call with updates.

### position_async() {#classmavsdk_1_1_telemetry_1a36c873a346ec80ffa6440191e57e440a}
```cpp
void mavsdk::Telemetry::position_async(position_callback_t callback)
```


Subscribe to position updates (asynchronous).


**Parameters**

* [position_callback_t](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1aadcd5ce9f12b7de8f44b32aff9bc766f) **callback** - Function to call with updates.

### home_position_async() {#classmavsdk_1_1_telemetry_1ad732889dfb7e0b6e8607d04e1a0d379a}
```cpp
void mavsdk::Telemetry::home_position_async(position_callback_t callback)
```


Subscribe to home position updates (asynchronous).


**Parameters**

* [position_callback_t](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1aadcd5ce9f12b7de8f44b32aff9bc766f) **callback** - Function to call with updates.

### in_air_async() {#classmavsdk_1_1_telemetry_1ab7872779d80172a8c3ec1f381995613c}
```cpp
void mavsdk::Telemetry::in_air_async(in_air_callback_t callback)
```


Subscribe to in-air updates (asynchronous).


**Parameters**

* [in_air_callback_t](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a5c89acce93f9c8b4379ed0dd002ee68c) **callback** - Function to call with updates.

### status_text_async() {#classmavsdk_1_1_telemetry_1a3dafc5195525739b84f6ae9774484450}
```cpp
void mavsdk::Telemetry::status_text_async(status_text_callback_t callback)
```


Subscribe to status text updates (asynchronous).


**Parameters**

* [status_text_callback_t](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1ab6bfd92d95e534b04ed98f09bf3a1e7a) **callback** - Function to call with updates.

### armed_async() {#classmavsdk_1_1_telemetry_1ae73fc84556a85ecc07de33f5b1f8f8cc}
```cpp
void mavsdk::Telemetry::armed_async(armed_callback_t callback)
```


Subscribe to armed updates (asynchronous).

Note that armed updates are limited to 1Hz.

**Parameters**

* [armed_callback_t](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a795e5848a43b29f5009d91e6c87b37d0) **callback** - Function to call with updates.

### attitude_quaternion_async() {#classmavsdk_1_1_telemetry_1a73c1f4f96fd2ac08e8a6eae6bba00098}
```cpp
void mavsdk::Telemetry::attitude_quaternion_async(attitude_quaternion_callback_t callback)
```


Subscribe to attitude updates in quaternion (asynchronous).


**Parameters**

* [attitude_quaternion_callback_t](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a8f1fb6e5bfb5c5bdd0c6469f0870775c) **callback** - Function to call with updates.

### attitude_euler_angle_async() {#classmavsdk_1_1_telemetry_1ab7dba6f0da6bd624ae3ce7f2da5d50cd}
```cpp
void mavsdk::Telemetry::attitude_euler_angle_async(attitude_euler_angle_callback_t callback)
```


Subscribe to attitude updates in Euler angles (asynchronous).


**Parameters**

* [attitude_euler_angle_callback_t](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1ab2076cee92c4714482d83a2be7526b9c) **callback** - Function to call with updates.

### camera_attitude_quaternion_async() {#classmavsdk_1_1_telemetry_1ae39f1c1769189fbd7e21fb216da7cfd2}
```cpp
void mavsdk::Telemetry::camera_attitude_quaternion_async(attitude_quaternion_callback_t callback)
```


Subscribe to camera attitude updates in quaternion (asynchronous).


**Parameters**

* [attitude_quaternion_callback_t](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a8f1fb6e5bfb5c5bdd0c6469f0870775c) **callback** - Function to call with updates.

### camera_attitude_euler_angle_async() {#classmavsdk_1_1_telemetry_1adb78b9cb7d918970a19222e1a8101706}
```cpp
void mavsdk::Telemetry::camera_attitude_euler_angle_async(attitude_euler_angle_callback_t callback)
```


Subscribe to camera attitude updates in Euler angles (asynchronous).


**Parameters**

* [attitude_euler_angle_callback_t](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1ab2076cee92c4714482d83a2be7526b9c) **callback** - Function to call with updates.

### ground_speed_ned_async() {#classmavsdk_1_1_telemetry_1a3eb3256f1a4708a6cf19ac28bc6e3568}
```cpp
void mavsdk::Telemetry::ground_speed_ned_async(ground_speed_ned_callback_t callback)
```


Subscribe to ground speed (NED) updates (asynchronous).


**Parameters**

* [ground_speed_ned_callback_t](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a0b58b0ef625a1eaf864d3a4890cb2a23) **callback** - Function to call with updates.

### gps_info_async() {#classmavsdk_1_1_telemetry_1a2ba72a9a7b24c9d16fa39482077ccfac}
```cpp
void mavsdk::Telemetry::gps_info_async(gps_info_callback_t callback)
```


Subscribe to GPS information updates (asynchronous).


**Parameters**

* [gps_info_callback_t](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1af34942b21fde18d723b300ebe6c40421) **callback** - Function to call with updates.

### battery_async() {#classmavsdk_1_1_telemetry_1aabb419112c981a837cee2f498b96c2c5}
```cpp
void mavsdk::Telemetry::battery_async(battery_callback_t callback)
```


Subscribe to battery status updates (asynchronous).


**Parameters**

* [battery_callback_t](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1ab7582939b706b1eea718c94433a1e5de) **callback** - Function to call with updates.

### flight_mode_async() {#classmavsdk_1_1_telemetry_1adede4202304e53466b4df41367a75878}
```cpp
void mavsdk::Telemetry::flight_mode_async(flight_mode_callback_t callback)
```


Subscribe to flight mode updates (asynchronous).

Note that flight mode updates are limited to 1Hz.

**Parameters**

* [flight_mode_callback_t](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1ad8cfe203cf88b457ed3593eb82d3ff77) **callback** - Function to call with updates.

### health_async() {#classmavsdk_1_1_telemetry_1aceb2a5a458cafd2171720424652c8e39}
```cpp
void mavsdk::Telemetry::health_async(health_callback_t callback)
```


Subscribe to health status updates (asynchronous).

Note that health status updates are limited to 1Hz.

**Parameters**

* [health_callback_t](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1abadf7c5be3e650809402115c1810a8d7) **callback** - Function to call with updates.

### health_all_ok_async() {#classmavsdk_1_1_telemetry_1ae1a2f05a126a88b19e78078ef5f552f4}
```cpp
void mavsdk::Telemetry::health_all_ok_async(health_all_ok_callback_t callback)
```


Subscribe to overall health status updates (asynchronous).

Note that overall health status updates are limited to 1Hz.

**Parameters**

* [health_all_ok_callback_t](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a8fe09456f509c93e2110fb45996bd927) **callback** - Function to call with updates.

### rc_status_async() {#classmavsdk_1_1_telemetry_1a5c1cba91eb65f738470c51da4d74aecc}
```cpp
void mavsdk::Telemetry::rc_status_async(rc_status_callback_t callback)
```


Subscribe to RC status updates (asynchronous).


**Parameters**

* [rc_status_callback_t](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1ade4c432133b83aa9612528117a2cd6d6) **callback** - Function to call with updates.

### operator=() {#classmavsdk_1_1_telemetry_1a703ac978c925be8806921925cf16aca9}
```cpp
const Telemetry& mavsdk::Telemetry::operator=(const Telemetry &)=delete
```


Equality operator (object is not copyable).


**Parameters**

* const [Telemetry](classmavsdk_1_1_telemetry.md)&  - 

**Returns**

&emsp;const [Telemetry](classmavsdk_1_1_telemetry.md) & - 

### flight_mode_str() {#classmavsdk_1_1_telemetry_1a25933c37dd05e5c3b7b4e9d52507cca7}
```cpp
static std::string mavsdk::Telemetry::flight_mode_str(FlightMode flight_mode)
```


Get a human readable English string for a flight mode.


**Parameters**

* [FlightMode](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a8317d953a82a23654db6f14509acb4fe) **flight_mode** - 

**Returns**

&emsp;std::string - 

### result_str() {#classmavsdk_1_1_telemetry_1a20bff42d7bb42c002ef7217cf98990e8}
```cpp
static const char* mavsdk::Telemetry::result_str(Result result)
```


Get human-readable English string for [Telemetry::Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75).


**Parameters**

* [Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75) **result** - The enum value for which string is needed.

**Returns**

&emsp;const char * - Human readable string for the [Telemetry::Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75).