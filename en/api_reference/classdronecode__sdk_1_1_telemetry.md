# dronecode_sdk::Telemetry Class Reference
`#include: telemetry.h`

----


This class allows users to get vehicle telemetry and state information (e.g. battery, GPS, RC connection, flight mode etc.) and set telemetry update rates. 


## Data Structures


struct [Battery](structdronecode__sdk_1_1_telemetry_1_1_battery.md)

struct [EulerAngle](structdronecode__sdk_1_1_telemetry_1_1_euler_angle.md)

struct [GPSInfo](structdronecode__sdk_1_1_telemetry_1_1_g_p_s_info.md)

struct [GroundSpeedNED](structdronecode__sdk_1_1_telemetry_1_1_ground_speed_n_e_d.md)

struct [Health](structdronecode__sdk_1_1_telemetry_1_1_health.md)

struct [Position](structdronecode__sdk_1_1_telemetry_1_1_position.md)

struct [PositionNED](structdronecode__sdk_1_1_telemetry_1_1_position_n_e_d.md)

struct [PositionVelocityNED](structdronecode__sdk_1_1_telemetry_1_1_position_velocity_n_e_d.md)

struct [Quaternion](structdronecode__sdk_1_1_telemetry_1_1_quaternion.md)

struct [RCStatus](structdronecode__sdk_1_1_telemetry_1_1_r_c_status.md)

struct [StatusText](structdronecode__sdk_1_1_telemetry_1_1_status_text.md)

struct [VelocityNED](structdronecode__sdk_1_1_telemetry_1_1_velocity_n_e_d.md)

## Public Types


Type | Description
--- | ---
enum [FlightMode](#classdronecode__sdk_1_1_telemetry_1a7e503d87f48fabb8549b4af7acb77f8f) | Flight modes.
enum [Result](#classdronecode__sdk_1_1_telemetry_1ae5e3509344edb0faea3d44b786c16b3e) | Results enum for telemetry requests.
std::function< void([Result](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1ae5e3509344edb0faea3d44b786c16b3e))> [result_callback_t](#classdronecode__sdk_1_1_telemetry_1af338eea395337c8940231ad690fe57e7) | Callback type for telemetry requests.
std::function< void([PositionVelocityNED](structdronecode__sdk_1_1_telemetry_1_1_position_velocity_n_e_d.md))> [position_velocity_ned_callback_t](#classdronecode__sdk_1_1_telemetry_1a6a584ef033a162eb56cf8c45589a8ffd) | Callback type for kinematic (position and velocity) updates.
std::function< void([Position](structdronecode__sdk_1_1_telemetry_1_1_position.md))> [position_callback_t](#classdronecode__sdk_1_1_telemetry_1a325501dc02e5c85cc7ad74ef233b3ff6) | Callback type for position updates.
std::function< void(bool [in_air](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1a2f22522ddfde00b97dbfad84864a1730))> [in_air_callback_t](#classdronecode__sdk_1_1_telemetry_1af64278aec30c32f4b8db9d427ba9c48c) | Callback type for in-air updates.
std::function< void([StatusText](structdronecode__sdk_1_1_telemetry_1_1_status_text.md) [status_text](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1ae97f81f4f564b02ffd2c0ef241f9feee))> [status_text_callback_t](#classdronecode__sdk_1_1_telemetry_1abd606e783a8ca44b9b87d7eb82a9b980) | Callback for mavlink status text updates.
std::function< void(bool [armed](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1a76b05cc86c9152eabbda6b0051b8605d))> [armed_callback_t](#classdronecode__sdk_1_1_telemetry_1ad4be5f2c17988fa53b0c59affb64e9a2) | Callback type for armed updates (asynchronous).
std::function< void([Quaternion](structdronecode__sdk_1_1_telemetry_1_1_quaternion.md) quaternion)> [attitude_quaternion_callback_t](#classdronecode__sdk_1_1_telemetry_1a4fe1cb6af59d7ecabb26563f6c33079d) | Callback type for attitude updates in quaternion.
std::function< void([EulerAngle](structdronecode__sdk_1_1_telemetry_1_1_euler_angle.md) euler_angle)> [attitude_euler_angle_callback_t](#classdronecode__sdk_1_1_telemetry_1a0db7573bc74c00231c96cb87a5711e96) | Callback type for attitude updates in Euler angles.
std::function< void([GroundSpeedNED](structdronecode__sdk_1_1_telemetry_1_1_ground_speed_n_e_d.md) [ground_speed_ned](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1a970b406d06b7ebd5f762e2d3b8d6021e))> [ground_speed_ned_callback_t](#classdronecode__sdk_1_1_telemetry_1a0ef2162b9ce267e0e59757712bbc8326) | Callback type for ground speed (NED) updates.
std::function< void([GPSInfo](structdronecode__sdk_1_1_telemetry_1_1_g_p_s_info.md) [gps_info](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1a22ca23272aa13e3cce9d4fabe025e467))> [gps_info_callback_t](#classdronecode__sdk_1_1_telemetry_1a2111571572b3898de7c1296eb3c8f547) | Callback type for GPS information updates.
std::function< void([Battery](structdronecode__sdk_1_1_telemetry_1_1_battery.md) [battery](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1a7c50637603fbde0f0ded0cbc24182d59))> [battery_callback_t](#classdronecode__sdk_1_1_telemetry_1ac13b14156d710aad87b113584a75af16) | Callback type for battery status updates.
std::function< void([FlightMode](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1a7e503d87f48fabb8549b4af7acb77f8f) [flight_mode](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1a8b108f9368e4f8f06b613d8571ad4e1e))> [flight_mode_callback_t](#classdronecode__sdk_1_1_telemetry_1a2d667183c1d2640c7248e9c438c01191) | Callback type for flight mode updates.
std::function< void([Health](structdronecode__sdk_1_1_telemetry_1_1_health.md) [health](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1a4f1b6620fa890b8ceb5599a9fc26a898))> [health_callback_t](#classdronecode__sdk_1_1_telemetry_1a58fdb6d9cb7dc8124182556630a0135c) | Callback type for health status updates.
std::function< void(bool [health_all_ok](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1acb0cdb02b7368179ca0193a111904a64))> [health_all_ok_callback_t](#classdronecode__sdk_1_1_telemetry_1aabf06480ae9a9ab85412b749030534df) | Callback type for health status updates.
std::function< void([RCStatus](structdronecode__sdk_1_1_telemetry_1_1_r_c_status.md) [rc_status](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1a0d7d1a6b8c73723c71ef3f147971d81d))> [rc_status_callback_t](#classdronecode__sdk_1_1_telemetry_1a1441a3aa4b0865ebb62f5e4f6d1cbdee) | Callback type for RC status updates.

## Public Member Functions


Type | Name | Description
---: | --- | ---
&nbsp; | [Telemetry](#classdronecode__sdk_1_1_telemetry_1aa75415e52318dd791c66a0b6c8ff2a14) ([System](classdronecode__sdk_1_1_system.md) & system) | Constructor. Creates the plugin for a specific [System](classdronecode__sdk_1_1_system.md).
&nbsp; | [~Telemetry](#classdronecode__sdk_1_1_telemetry_1a9f730bedfb635985ca1807efe605564b) () | Destructor (internal use only).
&nbsp; | [Telemetry](#classdronecode__sdk_1_1_telemetry_1ae813b39df956463080d31688138b96d4) (const [Telemetry](classdronecode__sdk_1_1_telemetry.md) &)=delete | Copy constructor (object is not copyable).
[Result](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1ae5e3509344edb0faea3d44b786c16b3e) | [set_rate_position_velocity_ned](#classdronecode__sdk_1_1_telemetry_1aa1e4ac8be67dd73f144ff2e404beb081) (double rate_hz) | Set rate of kinematic (position and velocity) updates (synchronous).
[Result](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1ae5e3509344edb0faea3d44b786c16b3e) | [set_rate_position](#classdronecode__sdk_1_1_telemetry_1a84833a8b1b30347c9cd5b98bed889472) (double rate_hz) | Set rate of position updates (synchronous).
[Result](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1ae5e3509344edb0faea3d44b786c16b3e) | [set_rate_home_position](#classdronecode__sdk_1_1_telemetry_1affff08e268b116a27280bedafc27df6a) (double rate_hz) | Set rate of home position updates (synchronous).
[Result](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1ae5e3509344edb0faea3d44b786c16b3e) | [set_rate_in_air](#classdronecode__sdk_1_1_telemetry_1ac2f9fd9e44696b7af0a24669f2f140bb) (double rate_hz) | Set rate of in-air status updates (synchronous).
[Result](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1ae5e3509344edb0faea3d44b786c16b3e) | [set_rate_attitude](#classdronecode__sdk_1_1_telemetry_1a2005067a7b24f376be97bf562bbb4a8d) (double rate_hz) | Set rate of attitude updates (synchronous).
[Result](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1ae5e3509344edb0faea3d44b786c16b3e) | [set_rate_camera_attitude](#classdronecode__sdk_1_1_telemetry_1a4ade0a9e9b6b80f35607e7944fbc0dc7) (double rate_hz) | Set rate of camera attitude updates (synchronous).
[Result](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1ae5e3509344edb0faea3d44b786c16b3e) | [set_rate_ground_speed_ned](#classdronecode__sdk_1_1_telemetry_1a02db719c2dfd8b035f59e0253bdb8be8) (double rate_hz) | Set rate of ground speed (NED) updates (synchronous).
[Result](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1ae5e3509344edb0faea3d44b786c16b3e) | [set_rate_gps_info](#classdronecode__sdk_1_1_telemetry_1abca93bc1dca4bfb6b647ee4284cd3d60) (double rate_hz) | Set rate of GPS information updates (synchronous).
[Result](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1ae5e3509344edb0faea3d44b786c16b3e) | [set_rate_battery](#classdronecode__sdk_1_1_telemetry_1aa100035f60c4c97eb4aa2b0a16239297) (double rate_hz) | Set rate of battery status updates (synchronous).
[Result](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1ae5e3509344edb0faea3d44b786c16b3e) | [set_rate_rc_status](#classdronecode__sdk_1_1_telemetry_1a0c68f4260c89ab51ab1d1dc0b9a47852) (double rate_hz) | Set rate of RC status updates (synchronous).
void | [set_rate_position_velocity_ned_async](#classdronecode__sdk_1_1_telemetry_1a4d4425908644763435a34ec72e9650e0) (double rate_hz, [result_callback_t](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1af338eea395337c8940231ad690fe57e7) callback) | Set rate of kinematic (position and velocity) updates (asynchronous).
void | [set_rate_position_async](#classdronecode__sdk_1_1_telemetry_1a7dc380a3f7c653fe54561e5b48ff5995) (double rate_hz, [result_callback_t](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1af338eea395337c8940231ad690fe57e7) callback) | Set rate of position updates (asynchronous).
void | [set_rate_home_position_async](#classdronecode__sdk_1_1_telemetry_1ade7ca559607ff70293f9bb955765abcf) (double rate_hz, [result_callback_t](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1af338eea395337c8940231ad690fe57e7) callback) | Set rate of home position updates (asynchronous).
void | [set_rate_in_air_async](#classdronecode__sdk_1_1_telemetry_1af6d992febca0f79c7c4fb3e5fb97c06a) (double rate_hz, [result_callback_t](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1af338eea395337c8940231ad690fe57e7) callback) | Set rate of in-air status updates (asynchronous).
void | [set_rate_attitude_async](#classdronecode__sdk_1_1_telemetry_1a75fe9809222c9ac0bf6707037d6a5869) (double rate_hz, [result_callback_t](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1af338eea395337c8940231ad690fe57e7) callback) | Set rate of attitude updates (asynchronous).
void | [set_rate_camera_attitude_async](#classdronecode__sdk_1_1_telemetry_1ae1cd4b0135ed4ce0e1ecff3a60856d7b) (double rate_hz, [result_callback_t](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1af338eea395337c8940231ad690fe57e7) callback) | Set rate of camera attitude updates (asynchronous).
void | [set_rate_ground_speed_ned_async](#classdronecode__sdk_1_1_telemetry_1af230d9fc89b5a3c833314fa953360b17) (double rate_hz, [result_callback_t](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1af338eea395337c8940231ad690fe57e7) callback) | Set rate of ground speed (NED) updates (asynchronous).
void | [set_rate_gps_info_async](#classdronecode__sdk_1_1_telemetry_1ad459a78b1dfa0ef3a4d0d222267e1fbd) (double rate_hz, [result_callback_t](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1af338eea395337c8940231ad690fe57e7) callback) | Set rate of GPS information updates (asynchronous).
void | [set_rate_battery_async](#classdronecode__sdk_1_1_telemetry_1aedc178582ac703bf467f4defc7efe450) (double rate_hz, [result_callback_t](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1af338eea395337c8940231ad690fe57e7) callback) | Set rate of battery status updates (asynchronous).
void | [set_rate_rc_status_async](#classdronecode__sdk_1_1_telemetry_1a3984dea260db91d37f8d99161aa2c3ba) (double rate_hz, [result_callback_t](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1af338eea395337c8940231ad690fe57e7) callback) | Set rate of RC status updates (asynchronous).
[PositionVelocityNED](structdronecode__sdk_1_1_telemetry_1_1_position_velocity_n_e_d.md) | [position_velocity_ned](#classdronecode__sdk_1_1_telemetry_1a21b0683af83e65884fdd460a45eb85d8) () const | Get the current kinematic (position and velocity) in NED frame (synchronous).
[Position](structdronecode__sdk_1_1_telemetry_1_1_position.md) | [position](#classdronecode__sdk_1_1_telemetry_1ae1d845b0f461a5e50f425939c1efccd2) () const | Get the current position (synchronous).
[Position](structdronecode__sdk_1_1_telemetry_1_1_position.md) | [home_position](#classdronecode__sdk_1_1_telemetry_1a76ad20dab72e02523b5637900aaab9da) () const | Get the home position (synchronous).
[StatusText](structdronecode__sdk_1_1_telemetry_1_1_status_text.md) | [status_text](#classdronecode__sdk_1_1_telemetry_1ae97f81f4f564b02ffd2c0ef241f9feee) () const | Get status text (synchronous).
bool | [in_air](#classdronecode__sdk_1_1_telemetry_1a2f22522ddfde00b97dbfad84864a1730) () const | Get the in-air status (synchronous).
bool | [armed](#classdronecode__sdk_1_1_telemetry_1a76b05cc86c9152eabbda6b0051b8605d) () const | Get the arming status (synchronous).
[Quaternion](structdronecode__sdk_1_1_telemetry_1_1_quaternion.md) | [attitude_quaternion](#classdronecode__sdk_1_1_telemetry_1a2e05a480489c3b5a9b1f825b62d3434b) () const | Get the current attitude in quaternions (synchronous).
[EulerAngle](structdronecode__sdk_1_1_telemetry_1_1_euler_angle.md) | [attitude_euler_angle](#classdronecode__sdk_1_1_telemetry_1a7044fd16df994d84791f0a2434cf0060) () const | Get the current attitude in Euler angles (synchronous).
[Quaternion](structdronecode__sdk_1_1_telemetry_1_1_quaternion.md) | [camera_attitude_quaternion](#classdronecode__sdk_1_1_telemetry_1a60695c414ae2e520fc69932db272c646) () const | Get the camera's attitude in quaternions (synchronous).
[EulerAngle](structdronecode__sdk_1_1_telemetry_1_1_euler_angle.md) | [camera_attitude_euler_angle](#classdronecode__sdk_1_1_telemetry_1a513fe94561cbf33d3d20db2a513c7ae3) () const | Get the camera's attitude in Euler angles (synchronous).
[GroundSpeedNED](structdronecode__sdk_1_1_telemetry_1_1_ground_speed_n_e_d.md) | [ground_speed_ned](#classdronecode__sdk_1_1_telemetry_1a970b406d06b7ebd5f762e2d3b8d6021e) () const | Get the current ground speed (NED) (synchronous).
[GPSInfo](structdronecode__sdk_1_1_telemetry_1_1_g_p_s_info.md) | [gps_info](#classdronecode__sdk_1_1_telemetry_1a22ca23272aa13e3cce9d4fabe025e467) () const | Get the current GPS information (synchronous).
[Battery](structdronecode__sdk_1_1_telemetry_1_1_battery.md) | [battery](#classdronecode__sdk_1_1_telemetry_1a7c50637603fbde0f0ded0cbc24182d59) () const | Get the current battery status (synchronous).
[FlightMode](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1a7e503d87f48fabb8549b4af7acb77f8f) | [flight_mode](#classdronecode__sdk_1_1_telemetry_1a8b108f9368e4f8f06b613d8571ad4e1e) () const | Get the current flight mode (synchronous).
[Health](structdronecode__sdk_1_1_telemetry_1_1_health.md) | [health](#classdronecode__sdk_1_1_telemetry_1a4f1b6620fa890b8ceb5599a9fc26a898) () const | Get the current health status (synchronous).
bool | [health_all_ok](#classdronecode__sdk_1_1_telemetry_1acb0cdb02b7368179ca0193a111904a64) () const | Returns true if the overall health is ok (synchronous).
[RCStatus](structdronecode__sdk_1_1_telemetry_1_1_r_c_status.md) | [rc_status](#classdronecode__sdk_1_1_telemetry_1a0d7d1a6b8c73723c71ef3f147971d81d) () const | Get the RC status (synchronous).
void | [position_velocity_ned_async](#classdronecode__sdk_1_1_telemetry_1a2d910e16336263522afa871ab01ee555) ([position_velocity_ned_callback_t](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1a6a584ef033a162eb56cf8c45589a8ffd) callback) | Subscribe to kinematic (position and velocity) updates (asynchronous).
void | [position_async](#classdronecode__sdk_1_1_telemetry_1a2a19fb93315e33a2dad6720b36ec9389) ([position_callback_t](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1a325501dc02e5c85cc7ad74ef233b3ff6) callback) | Subscribe to position updates (asynchronous).
void | [home_position_async](#classdronecode__sdk_1_1_telemetry_1ad94dbcc5ed4ebb8f377d11a2ea72f6fc) ([position_callback_t](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1a325501dc02e5c85cc7ad74ef233b3ff6) callback) | Subscribe to home position updates (asynchronous).
void | [in_air_async](#classdronecode__sdk_1_1_telemetry_1a1027180f38628306ddfd1d6e66ae067b) ([in_air_callback_t](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1af64278aec30c32f4b8db9d427ba9c48c) callback) | Subscribe to in-air updates (asynchronous).
void | [status_text_async](#classdronecode__sdk_1_1_telemetry_1aecc39d5aab5500a94c6516c9fcc6bc9a) ([status_text_callback_t](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1abd606e783a8ca44b9b87d7eb82a9b980) callback) | Subscribe to status text updates (asynchronous).
void | [armed_async](#classdronecode__sdk_1_1_telemetry_1a9382a19ea66f1d99f3780fa88abea3fd) ([armed_callback_t](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1ad4be5f2c17988fa53b0c59affb64e9a2) callback) | Subscribe to armed updates (asynchronous).
void | [attitude_quaternion_async](#classdronecode__sdk_1_1_telemetry_1ac9633b72e0a38f5d5ec7f98d63ff1944) ([attitude_quaternion_callback_t](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1a4fe1cb6af59d7ecabb26563f6c33079d) callback) | Subscribe to attitude updates in quaternion (asynchronous).
void | [attitude_euler_angle_async](#classdronecode__sdk_1_1_telemetry_1a6da4a219d31fffcbf2223f80bfa063f4) ([attitude_euler_angle_callback_t](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1a0db7573bc74c00231c96cb87a5711e96) callback) | Subscribe to attitude updates in Euler angles (asynchronous).
void | [camera_attitude_quaternion_async](#classdronecode__sdk_1_1_telemetry_1a8188574203ab3f916bfece2feaee62e2) ([attitude_quaternion_callback_t](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1a4fe1cb6af59d7ecabb26563f6c33079d) callback) | Subscribe to camera attitude updates in quaternion (asynchronous).
void | [camera_attitude_euler_angle_async](#classdronecode__sdk_1_1_telemetry_1aa40c2f8da4cdbe812187854d23a31e6a) ([attitude_euler_angle_callback_t](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1a0db7573bc74c00231c96cb87a5711e96) callback) | Subscribe to camera attitude updates in Euler angles (asynchronous).
void | [ground_speed_ned_async](#classdronecode__sdk_1_1_telemetry_1a652cf6fcec470ae65c39d22f934f6bc3) ([ground_speed_ned_callback_t](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1a0ef2162b9ce267e0e59757712bbc8326) callback) | Subscribe to ground speed (NED) updates (asynchronous).
void | [gps_info_async](#classdronecode__sdk_1_1_telemetry_1afbc16838d115ca2bc43901be1e5637ff) ([gps_info_callback_t](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1a2111571572b3898de7c1296eb3c8f547) callback) | Subscribe to GPS information updates (asynchronous).
void | [battery_async](#classdronecode__sdk_1_1_telemetry_1a7988874d093cc514c31ec737568010b1) ([battery_callback_t](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1ac13b14156d710aad87b113584a75af16) callback) | Subscribe to battery status updates (asynchronous).
void | [flight_mode_async](#classdronecode__sdk_1_1_telemetry_1a29494b6f0ed34be913e3f5c4bbfdf4cd) ([flight_mode_callback_t](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1a2d667183c1d2640c7248e9c438c01191) callback) | Subscribe to flight mode updates (asynchronous).
void | [health_async](#classdronecode__sdk_1_1_telemetry_1ad6f8b300630350000db7c44ce6976ab0) ([health_callback_t](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1a58fdb6d9cb7dc8124182556630a0135c) callback) | Subscribe to health status updates (asynchronous).
void | [health_all_ok_async](#classdronecode__sdk_1_1_telemetry_1ad3eb60db8b4dc72fd55d8689d849c9ae) ([health_all_ok_callback_t](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1aabf06480ae9a9ab85412b749030534df) callback) | Subscribe to overall health status updates (asynchronous).
void | [rc_status_async](#classdronecode__sdk_1_1_telemetry_1a9c08927e8693588dfc7a8d33d3df2423) ([rc_status_callback_t](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1a1441a3aa4b0865ebb62f5e4f6d1cbdee) callback) | Subscribe to RC status updates (asynchronous).
const [Telemetry](classdronecode__sdk_1_1_telemetry.md) & | [operator=](#classdronecode__sdk_1_1_telemetry_1a029b8fc4c241e4c20d26ff1a4e601ef7) (const [Telemetry](classdronecode__sdk_1_1_telemetry.md) &)=delete | Equality operator (object is not copyable).

## Static Public Member Functions


Type | Name | Description
---: | --- | ---
std::string | [flight_mode_str](#classdronecode__sdk_1_1_telemetry_1ac35c44d286d50e649b5e192730a756e7) ([FlightMode](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1a7e503d87f48fabb8549b4af7acb77f8f) flight_mode) | Get a human readable English string for a flight mode.
const char * | [result_str](#classdronecode__sdk_1_1_telemetry_1a046457e28886493a677fe7d35627bacc) ([Result](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1ae5e3509344edb0faea3d44b786c16b3e) result) | Get human-readable English string for [Telemetry::Result](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1ae5e3509344edb0faea3d44b786c16b3e).


## Constructor & Destructor Documentation


### Telemetry() {#classdronecode__sdk_1_1_telemetry_1aa75415e52318dd791c66a0b6c8ff2a14}
```cpp
dronecode_sdk::Telemetry::Telemetry(System &system)
```


Constructor. Creates the plugin for a specific [System](classdronecode__sdk_1_1_system.md).

The plugin is typically created as shown below: 

```cpp
auto telemetry = std::make_shared<Telemetry>(system);
```

**Parameters**

* [System](classdronecode__sdk_1_1_system.md)& **system** - The specific system associated with this plugin.

### ~Telemetry() {#classdronecode__sdk_1_1_telemetry_1a9f730bedfb635985ca1807efe605564b}
```cpp
dronecode_sdk::Telemetry::~Telemetry()
```


Destructor (internal use only).


### Telemetry() {#classdronecode__sdk_1_1_telemetry_1ae813b39df956463080d31688138b96d4}
```cpp
dronecode_sdk::Telemetry::Telemetry(const Telemetry &)=delete
```


Copy constructor (object is not copyable).


**Parameters**

* const [Telemetry](classdronecode__sdk_1_1_telemetry.md)&  - 

## Member Typdef Documentation


### typedef result_callback_t {#classdronecode__sdk_1_1_telemetry_1af338eea395337c8940231ad690fe57e7}

```cpp
typedef std::function<void(Result)> dronecode_sdk::Telemetry::result_callback_t
```


Callback type for telemetry requests.


### typedef position_velocity_ned_callback_t {#classdronecode__sdk_1_1_telemetry_1a6a584ef033a162eb56cf8c45589a8ffd}

```cpp
typedef std::function<void(PositionVelocityNED)> dronecode_sdk::Telemetry::position_velocity_ned_callback_t
```


Callback type for kinematic (position and velocity) updates.


### typedef position_callback_t {#classdronecode__sdk_1_1_telemetry_1a325501dc02e5c85cc7ad74ef233b3ff6}

```cpp
typedef std::function<void(Position)> dronecode_sdk::Telemetry::position_callback_t
```


Callback type for position updates.


### typedef in_air_callback_t {#classdronecode__sdk_1_1_telemetry_1af64278aec30c32f4b8db9d427ba9c48c}

```cpp
typedef std::function<void(bool in_air)> dronecode_sdk::Telemetry::in_air_callback_t
```


Callback type for in-air updates.


**Parameters**

* **in_air** - true if in-air (flying) and not on-ground (landed).

### typedef status_text_callback_t {#classdronecode__sdk_1_1_telemetry_1abd606e783a8ca44b9b87d7eb82a9b980}

```cpp
typedef std::function<void(StatusText status_text)> dronecode_sdk::Telemetry::status_text_callback_t
```


Callback for mavlink status text updates.


**Parameters**

* **status** - text with message type and text.

### typedef armed_callback_t {#classdronecode__sdk_1_1_telemetry_1ad4be5f2c17988fa53b0c59affb64e9a2}

```cpp
typedef std::function<void(bool armed)> dronecode_sdk::Telemetry::armed_callback_t
```


Callback type for armed updates (asynchronous).


**Parameters**

* **armed** - true if armed (motors spinning).

### typedef attitude_quaternion_callback_t {#classdronecode__sdk_1_1_telemetry_1a4fe1cb6af59d7ecabb26563f6c33079d}

```cpp
typedef std::function<void(Quaternion quaternion)> dronecode_sdk::Telemetry::attitude_quaternion_callback_t
```


Callback type for attitude updates in quaternion.


**Parameters**

* **quaternion** - Attitude quaternion.

### typedef attitude_euler_angle_callback_t {#classdronecode__sdk_1_1_telemetry_1a0db7573bc74c00231c96cb87a5711e96}

```cpp
typedef std::function<void(EulerAngle euler_angle)> dronecode_sdk::Telemetry::attitude_euler_angle_callback_t
```


Callback type for attitude updates in Euler angles.


**Parameters**

* **euler_angle** - Attitude Euler angle.

### typedef ground_speed_ned_callback_t {#classdronecode__sdk_1_1_telemetry_1a0ef2162b9ce267e0e59757712bbc8326}

```cpp
typedef std::function<void(GroundSpeedNED ground_speed_ned)> dronecode_sdk::Telemetry::ground_speed_ned_callback_t
```


Callback type for ground speed (NED) updates.


**Parameters**

* **ground_speed_ned** - Ground speed (NED).

### typedef gps_info_callback_t {#classdronecode__sdk_1_1_telemetry_1a2111571572b3898de7c1296eb3c8f547}

```cpp
typedef std::function<void(GPSInfo gps_info)> dronecode_sdk::Telemetry::gps_info_callback_t
```


Callback type for GPS information updates.


**Parameters**

* **gps_info** - GPS information.

### typedef battery_callback_t {#classdronecode__sdk_1_1_telemetry_1ac13b14156d710aad87b113584a75af16}

```cpp
typedef std::function<void(Battery battery)> dronecode_sdk::Telemetry::battery_callback_t
```


Callback type for battery status updates.


**Parameters**

* **battery** - [Battery](structdronecode__sdk_1_1_telemetry_1_1_battery.md) status.

### typedef flight_mode_callback_t {#classdronecode__sdk_1_1_telemetry_1a2d667183c1d2640c7248e9c438c01191}

```cpp
typedef std::function<void(FlightMode flight_mode)> dronecode_sdk::Telemetry::flight_mode_callback_t
```


Callback type for flight mode updates.


**Parameters**

* **flight_mode** - Flight mode.

### typedef health_callback_t {#classdronecode__sdk_1_1_telemetry_1a58fdb6d9cb7dc8124182556630a0135c}

```cpp
typedef std::function<void(Health health)> dronecode_sdk::Telemetry::health_callback_t
```


Callback type for health status updates.


**Parameters**

* **health** - health flags.

### typedef health_all_ok_callback_t {#classdronecode__sdk_1_1_telemetry_1aabf06480ae9a9ab85412b749030534df}

```cpp
typedef std::function<void(bool health_all_ok)> dronecode_sdk::Telemetry::health_all_ok_callback_t
```


Callback type for health status updates.


**Parameters**

* **health_all_ok** - If all health flags are ok.

### typedef rc_status_callback_t {#classdronecode__sdk_1_1_telemetry_1a1441a3aa4b0865ebb62f5e4f6d1cbdee}

```cpp
typedef std::function<void(RCStatus rc_status)> dronecode_sdk::Telemetry::rc_status_callback_t
```


Callback type for RC status updates.


**Parameters**

* **rc_status** - RC status.

## Member Enumeration Documentation


### enum FlightMode {#classdronecode__sdk_1_1_telemetry_1a7e503d87f48fabb8549b4af7acb77f8f}


Flight modes.

For more information about flight modes, check out [https://docs.px4.io/en/config/flight_mode.html](https://docs.px4.io/en/config/flight_mode.html).

Value | Description
--- | ---
<span id="classdronecode__sdk_1_1_telemetry_1a7e503d87f48fabb8549b4af7acb77f8fa2baa69eafc7204f3bd8648eba580c489"></span> `READY` | Armed and ready to take off. 
<span id="classdronecode__sdk_1_1_telemetry_1a7e503d87f48fabb8549b4af7acb77f8fa8fabc74a4ed0781d663336cbf8c9c53d"></span> `TAKEOFF` | Taking off. 
<span id="classdronecode__sdk_1_1_telemetry_1a7e503d87f48fabb8549b4af7acb77f8fa0c6d9dfb485b43c6fba87439f9f73ac4"></span> `HOLD` | Hold mode (hovering in place (or circling for fixed-wing vehicles). 
<span id="classdronecode__sdk_1_1_telemetry_1a7e503d87f48fabb8549b4af7acb77f8faa46075d70b9612df685b11436d195196"></span> `MISSION` | [Mission](classdronecode__sdk_1_1_mission.md) mode. 
<span id="classdronecode__sdk_1_1_telemetry_1a7e503d87f48fabb8549b4af7acb77f8fa0d4a147a2cf60f0761f239bf3ee2745e"></span> `RETURN_TO_LAUNCH` | Returning to launch position (then landing). 
<span id="classdronecode__sdk_1_1_telemetry_1a7e503d87f48fabb8549b4af7acb77f8fa479a809c0b6eaaefd3b1df16f976df06"></span> `LAND` | Landing. 
<span id="classdronecode__sdk_1_1_telemetry_1a7e503d87f48fabb8549b4af7acb77f8fa6687898e86a83f245901f96d313930b1"></span> `OFFBOARD` | [Offboard](classdronecode__sdk_1_1_offboard.md) mode. 
<span id="classdronecode__sdk_1_1_telemetry_1a7e503d87f48fabb8549b4af7acb77f8fac4099cf323b2f571c3d4917db6b1a20d"></span> `FOLLOW_ME` | [FollowMe](classdronecode__sdk_1_1_follow_me.md) mode. 
<span id="classdronecode__sdk_1_1_telemetry_1a7e503d87f48fabb8549b4af7acb77f8fa696b031073e74bf2cb98e5ef201d4aa3"></span> `UNKNOWN` | Mode not known. 

### enum Result {#classdronecode__sdk_1_1_telemetry_1ae5e3509344edb0faea3d44b786c16b3e}


Results enum for telemetry requests.


Value | Description
--- | ---
<span id="classdronecode__sdk_1_1_telemetry_1ae5e3509344edb0faea3d44b786c16b3ead0749aaba8b833466dfcbb0428e4f89c"></span> `SUCCESS` | Request succeeded. 
<span id="classdronecode__sdk_1_1_telemetry_1ae5e3509344edb0faea3d44b786c16b3eafeae72a3a2feec3c92c2a79a30d31186"></span> `NO_SYSTEM` | No system connected. 
<span id="classdronecode__sdk_1_1_telemetry_1ae5e3509344edb0faea3d44b786c16b3eac77f1f09dab2c0c9980fca7cfae02518"></span> `CONNECTION_ERROR` | Connection error. 
<span id="classdronecode__sdk_1_1_telemetry_1ae5e3509344edb0faea3d44b786c16b3ea802706a9238e2928077f97736854bad4"></span> `BUSY` | [System](classdronecode__sdk_1_1_system.md) busy. 
<span id="classdronecode__sdk_1_1_telemetry_1ae5e3509344edb0faea3d44b786c16b3ea6fa4dbf368cea972db8d9156799d5dbe"></span> `COMMAND_DENIED` | Command denied. 
<span id="classdronecode__sdk_1_1_telemetry_1ae5e3509344edb0faea3d44b786c16b3ea070a0fb40f6c308ab544b227660aadff"></span> `TIMEOUT` | Request timeout. 
<span id="classdronecode__sdk_1_1_telemetry_1ae5e3509344edb0faea3d44b786c16b3ea696b031073e74bf2cb98e5ef201d4aa3"></span> `UNKNOWN` | Unknown error. 

## Member Function Documentation


### set_rate_position_velocity_ned() {#classdronecode__sdk_1_1_telemetry_1aa1e4ac8be67dd73f144ff2e404beb081}
```cpp
Result dronecode_sdk::Telemetry::set_rate_position_velocity_ned(double rate_hz)
```


Set rate of kinematic (position and velocity) updates (synchronous).


**Parameters**

* double **rate_hz** - Rate in Hz.

**Returns**

&emsp;[Result](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1ae5e3509344edb0faea3d44b786c16b3e) - Result of request.

**See Also:**
- [PositionVelocityNED](structdronecode__sdk_1_1_telemetry_1_1_position_velocity_n_e_d.md)


### set_rate_position() {#classdronecode__sdk_1_1_telemetry_1a84833a8b1b30347c9cd5b98bed889472}
```cpp
Result dronecode_sdk::Telemetry::set_rate_position(double rate_hz)
```


Set rate of position updates (synchronous).


**Parameters**

* double **rate_hz** - Rate in Hz.

**Returns**

&emsp;[Result](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1ae5e3509344edb0faea3d44b786c16b3e) - Result of request.

### set_rate_home_position() {#classdronecode__sdk_1_1_telemetry_1affff08e268b116a27280bedafc27df6a}
```cpp
Result dronecode_sdk::Telemetry::set_rate_home_position(double rate_hz)
```


Set rate of home position updates (synchronous).


**Parameters**

* double **rate_hz** - Rate in Hz.

**Returns**

&emsp;[Result](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1ae5e3509344edb0faea3d44b786c16b3e) - Result of request.

### set_rate_in_air() {#classdronecode__sdk_1_1_telemetry_1ac2f9fd9e44696b7af0a24669f2f140bb}
```cpp
Result dronecode_sdk::Telemetry::set_rate_in_air(double rate_hz)
```


Set rate of in-air status updates (synchronous).


**Parameters**

* double **rate_hz** - Rate in Hz.

**Returns**

&emsp;[Result](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1ae5e3509344edb0faea3d44b786c16b3e) - Result of request.

### set_rate_attitude() {#classdronecode__sdk_1_1_telemetry_1a2005067a7b24f376be97bf562bbb4a8d}
```cpp
Result dronecode_sdk::Telemetry::set_rate_attitude(double rate_hz)
```


Set rate of attitude updates (synchronous).


**Parameters**

* double **rate_hz** - Rate in Hz.

**Returns**

&emsp;[Result](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1ae5e3509344edb0faea3d44b786c16b3e) - Result of request.

### set_rate_camera_attitude() {#classdronecode__sdk_1_1_telemetry_1a4ade0a9e9b6b80f35607e7944fbc0dc7}
```cpp
Result dronecode_sdk::Telemetry::set_rate_camera_attitude(double rate_hz)
```


Set rate of camera attitude updates (synchronous).


**Parameters**

* double **rate_hz** - Rate in Hz.

**Returns**

&emsp;[Result](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1ae5e3509344edb0faea3d44b786c16b3e) - Result of request.

### set_rate_ground_speed_ned() {#classdronecode__sdk_1_1_telemetry_1a02db719c2dfd8b035f59e0253bdb8be8}
```cpp
Result dronecode_sdk::Telemetry::set_rate_ground_speed_ned(double rate_hz)
```


Set rate of ground speed (NED) updates (synchronous).


**Parameters**

* double **rate_hz** - Rate in Hz.

**Returns**

&emsp;[Result](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1ae5e3509344edb0faea3d44b786c16b3e) - Result of request.

### set_rate_gps_info() {#classdronecode__sdk_1_1_telemetry_1abca93bc1dca4bfb6b647ee4284cd3d60}
```cpp
Result dronecode_sdk::Telemetry::set_rate_gps_info(double rate_hz)
```


Set rate of GPS information updates (synchronous).


**Parameters**

* double **rate_hz** - Rate in Hz.

**Returns**

&emsp;[Result](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1ae5e3509344edb0faea3d44b786c16b3e) - Result of request.

### set_rate_battery() {#classdronecode__sdk_1_1_telemetry_1aa100035f60c4c97eb4aa2b0a16239297}
```cpp
Result dronecode_sdk::Telemetry::set_rate_battery(double rate_hz)
```


Set rate of battery status updates (synchronous).


**Parameters**

* double **rate_hz** - Rate in Hz.

**Returns**

&emsp;[Result](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1ae5e3509344edb0faea3d44b786c16b3e) - Result of request.

### set_rate_rc_status() {#classdronecode__sdk_1_1_telemetry_1a0c68f4260c89ab51ab1d1dc0b9a47852}
```cpp
Result dronecode_sdk::Telemetry::set_rate_rc_status(double rate_hz)
```


Set rate of RC status updates (synchronous).


**Parameters**

* double **rate_hz** - Rate in Hz.

**Returns**

&emsp;[Result](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1ae5e3509344edb0faea3d44b786c16b3e) - Result of request.

### set_rate_position_velocity_ned_async() {#classdronecode__sdk_1_1_telemetry_1a4d4425908644763435a34ec72e9650e0}
```cpp
void dronecode_sdk::Telemetry::set_rate_position_velocity_ned_async(double rate_hz, result_callback_t callback)
```


Set rate of kinematic (position and velocity) updates (asynchronous).


**Parameters**

* double **rate_hz** - Rate in Hz.
* [result_callback_t](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1af338eea395337c8940231ad690fe57e7) **callback** - Callback to receive request result.

**See Also:**
- [PositionVelocityNED](structdronecode__sdk_1_1_telemetry_1_1_position_velocity_n_e_d.md)


### set_rate_position_async() {#classdronecode__sdk_1_1_telemetry_1a7dc380a3f7c653fe54561e5b48ff5995}
```cpp
void dronecode_sdk::Telemetry::set_rate_position_async(double rate_hz, result_callback_t callback)
```


Set rate of position updates (asynchronous).


**Parameters**

* double **rate_hz** - Rate in Hz.
* [result_callback_t](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1af338eea395337c8940231ad690fe57e7) **callback** - Callback to receive request result.

### set_rate_home_position_async() {#classdronecode__sdk_1_1_telemetry_1ade7ca559607ff70293f9bb955765abcf}
```cpp
void dronecode_sdk::Telemetry::set_rate_home_position_async(double rate_hz, result_callback_t callback)
```


Set rate of home position updates (asynchronous).


**Parameters**

* double **rate_hz** - Rate in Hz.
* [result_callback_t](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1af338eea395337c8940231ad690fe57e7) **callback** - Callback to receive request result.

### set_rate_in_air_async() {#classdronecode__sdk_1_1_telemetry_1af6d992febca0f79c7c4fb3e5fb97c06a}
```cpp
void dronecode_sdk::Telemetry::set_rate_in_air_async(double rate_hz, result_callback_t callback)
```


Set rate of in-air status updates (asynchronous).


**Parameters**

* double **rate_hz** - Rate in Hz.
* [result_callback_t](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1af338eea395337c8940231ad690fe57e7) **callback** - Callback to receive request result.

### set_rate_attitude_async() {#classdronecode__sdk_1_1_telemetry_1a75fe9809222c9ac0bf6707037d6a5869}
```cpp
void dronecode_sdk::Telemetry::set_rate_attitude_async(double rate_hz, result_callback_t callback)
```


Set rate of attitude updates (asynchronous).


**Parameters**

* double **rate_hz** - Rate in Hz.
* [result_callback_t](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1af338eea395337c8940231ad690fe57e7) **callback** - Callback to receive request result.

### set_rate_camera_attitude_async() {#classdronecode__sdk_1_1_telemetry_1ae1cd4b0135ed4ce0e1ecff3a60856d7b}
```cpp
void dronecode_sdk::Telemetry::set_rate_camera_attitude_async(double rate_hz, result_callback_t callback)
```


Set rate of camera attitude updates (asynchronous).


**Parameters**

* double **rate_hz** - Rate in Hz.
* [result_callback_t](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1af338eea395337c8940231ad690fe57e7) **callback** - Callback to receive request result.

### set_rate_ground_speed_ned_async() {#classdronecode__sdk_1_1_telemetry_1af230d9fc89b5a3c833314fa953360b17}
```cpp
void dronecode_sdk::Telemetry::set_rate_ground_speed_ned_async(double rate_hz, result_callback_t callback)
```


Set rate of ground speed (NED) updates (asynchronous).


**Parameters**

* double **rate_hz** - Rate in Hz.
* [result_callback_t](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1af338eea395337c8940231ad690fe57e7) **callback** - Callback to receive request result.

### set_rate_gps_info_async() {#classdronecode__sdk_1_1_telemetry_1ad459a78b1dfa0ef3a4d0d222267e1fbd}
```cpp
void dronecode_sdk::Telemetry::set_rate_gps_info_async(double rate_hz, result_callback_t callback)
```


Set rate of GPS information updates (asynchronous).


**Parameters**

* double **rate_hz** - Rate in Hz.
* [result_callback_t](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1af338eea395337c8940231ad690fe57e7) **callback** - Callback to receive request result.

### set_rate_battery_async() {#classdronecode__sdk_1_1_telemetry_1aedc178582ac703bf467f4defc7efe450}
```cpp
void dronecode_sdk::Telemetry::set_rate_battery_async(double rate_hz, result_callback_t callback)
```


Set rate of battery status updates (asynchronous).


**Parameters**

* double **rate_hz** - Rate in Hz.
* [result_callback_t](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1af338eea395337c8940231ad690fe57e7) **callback** - Callback to receive request result.

### set_rate_rc_status_async() {#classdronecode__sdk_1_1_telemetry_1a3984dea260db91d37f8d99161aa2c3ba}
```cpp
void dronecode_sdk::Telemetry::set_rate_rc_status_async(double rate_hz, result_callback_t callback)
```


Set rate of RC status updates (asynchronous).


**Parameters**

* double **rate_hz** - Rate in Hz.
* [result_callback_t](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1af338eea395337c8940231ad690fe57e7) **callback** - Callback to receive request result.

### position_velocity_ned() {#classdronecode__sdk_1_1_telemetry_1a21b0683af83e65884fdd460a45eb85d8}
```cpp
PositionVelocityNED dronecode_sdk::Telemetry::position_velocity_ned() const
```


Get the current kinematic (position and velocity) in NED frame (synchronous).


**Returns**

&emsp;[PositionVelocityNED](structdronecode__sdk_1_1_telemetry_1_1_position_velocity_n_e_d.md) - [PositionVelocityNED](structdronecode__sdk_1_1_telemetry_1_1_position_velocity_n_e_d.md).

### position() {#classdronecode__sdk_1_1_telemetry_1ae1d845b0f461a5e50f425939c1efccd2}
```cpp
Position dronecode_sdk::Telemetry::position() const
```


Get the current position (synchronous).


**Returns**

&emsp;[Position](structdronecode__sdk_1_1_telemetry_1_1_position.md) - [Position](structdronecode__sdk_1_1_telemetry_1_1_position.md).

### home_position() {#classdronecode__sdk_1_1_telemetry_1a76ad20dab72e02523b5637900aaab9da}
```cpp
Position dronecode_sdk::Telemetry::home_position() const
```


Get the home position (synchronous).


**Returns**

&emsp;[Position](structdronecode__sdk_1_1_telemetry_1_1_position.md) - Home position.

### status_text() {#classdronecode__sdk_1_1_telemetry_1ae97f81f4f564b02ffd2c0ef241f9feee}
```cpp
StatusText dronecode_sdk::Telemetry::status_text() const
```


Get status text (synchronous).


**Returns**

&emsp;[StatusText](structdronecode__sdk_1_1_telemetry_1_1_status_text.md) - Status text.

### in_air() {#classdronecode__sdk_1_1_telemetry_1a2f22522ddfde00b97dbfad84864a1730}
```cpp
bool dronecode_sdk::Telemetry::in_air() const
```


Get the in-air status (synchronous).


**Returns**

&emsp;bool - true if in-air (flying) and not on-ground (landed).

### armed() {#classdronecode__sdk_1_1_telemetry_1a76b05cc86c9152eabbda6b0051b8605d}
```cpp
bool dronecode_sdk::Telemetry::armed() const
```


Get the arming status (synchronous).


**Returns**

&emsp;bool - true if armed (propellers spinning).

### attitude_quaternion() {#classdronecode__sdk_1_1_telemetry_1a2e05a480489c3b5a9b1f825b62d3434b}
```cpp
Quaternion dronecode_sdk::Telemetry::attitude_quaternion() const
```


Get the current attitude in quaternions (synchronous).


**Returns**

&emsp;[Quaternion](structdronecode__sdk_1_1_telemetry_1_1_quaternion.md) - Attitude as quaternion.

### attitude_euler_angle() {#classdronecode__sdk_1_1_telemetry_1a7044fd16df994d84791f0a2434cf0060}
```cpp
EulerAngle dronecode_sdk::Telemetry::attitude_euler_angle() const
```


Get the current attitude in Euler angles (synchronous).


**Returns**

&emsp;[EulerAngle](structdronecode__sdk_1_1_telemetry_1_1_euler_angle.md) - Attitude as Euler angle.

### camera_attitude_quaternion() {#classdronecode__sdk_1_1_telemetry_1a60695c414ae2e520fc69932db272c646}
```cpp
Quaternion dronecode_sdk::Telemetry::camera_attitude_quaternion() const
```


Get the camera's attitude in quaternions (synchronous).

Note that the yaw component of attitude is relative to North (absolute frame).

**Returns**

&emsp;[Quaternion](structdronecode__sdk_1_1_telemetry_1_1_quaternion.md) - [Camera](classdronecode__sdk_1_1_camera.md)'s attitude as quaternion.

### camera_attitude_euler_angle() {#classdronecode__sdk_1_1_telemetry_1a513fe94561cbf33d3d20db2a513c7ae3}
```cpp
EulerAngle dronecode_sdk::Telemetry::camera_attitude_euler_angle() const
```


Get the camera's attitude in Euler angles (synchronous).

Note that the yaw component of attitude is relative to North (absolute frame).

**Returns**

&emsp;[EulerAngle](structdronecode__sdk_1_1_telemetry_1_1_euler_angle.md) - [Camera](classdronecode__sdk_1_1_camera.md)'s attitude as Euler angle.

### ground_speed_ned() {#classdronecode__sdk_1_1_telemetry_1a970b406d06b7ebd5f762e2d3b8d6021e}
```cpp
GroundSpeedNED dronecode_sdk::Telemetry::ground_speed_ned() const
```


Get the current ground speed (NED) (synchronous).


**Returns**

&emsp;[GroundSpeedNED](structdronecode__sdk_1_1_telemetry_1_1_ground_speed_n_e_d.md) - Ground speed in NED.

### gps_info() {#classdronecode__sdk_1_1_telemetry_1a22ca23272aa13e3cce9d4fabe025e467}
```cpp
GPSInfo dronecode_sdk::Telemetry::gps_info() const
```


Get the current GPS information (synchronous).


**Returns**

&emsp;[GPSInfo](structdronecode__sdk_1_1_telemetry_1_1_g_p_s_info.md) - GPS information.

### battery() {#classdronecode__sdk_1_1_telemetry_1a7c50637603fbde0f0ded0cbc24182d59}
```cpp
Battery dronecode_sdk::Telemetry::battery() const
```


Get the current battery status (synchronous).


**Returns**

&emsp;[Battery](structdronecode__sdk_1_1_telemetry_1_1_battery.md) - 

### flight_mode() {#classdronecode__sdk_1_1_telemetry_1a8b108f9368e4f8f06b613d8571ad4e1e}
```cpp
FlightMode dronecode_sdk::Telemetry::flight_mode() const
```


Get the current flight mode (synchronous).


**Returns**

&emsp;[FlightMode](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1a7e503d87f48fabb8549b4af7acb77f8f) - Flight mode.

### health() {#classdronecode__sdk_1_1_telemetry_1a4f1b6620fa890b8ceb5599a9fc26a898}
```cpp
Health dronecode_sdk::Telemetry::health() const
```


Get the current health status (synchronous).


**Returns**

&emsp;[Health](structdronecode__sdk_1_1_telemetry_1_1_health.md) - [Health](structdronecode__sdk_1_1_telemetry_1_1_health.md) status.

### health_all_ok() {#classdronecode__sdk_1_1_telemetry_1acb0cdb02b7368179ca0193a111904a64}
```cpp
bool dronecode_sdk::Telemetry::health_all_ok() const
```


Returns true if the overall health is ok (synchronous).


**Returns**

&emsp;bool - True if all health flags are OK.

### rc_status() {#classdronecode__sdk_1_1_telemetry_1a0d7d1a6b8c73723c71ef3f147971d81d}
```cpp
RCStatus dronecode_sdk::Telemetry::rc_status() const
```


Get the RC status (synchronous).


**Returns**

&emsp;[RCStatus](structdronecode__sdk_1_1_telemetry_1_1_r_c_status.md) - RC status.

### position_velocity_ned_async() {#classdronecode__sdk_1_1_telemetry_1a2d910e16336263522afa871ab01ee555}
```cpp
void dronecode_sdk::Telemetry::position_velocity_ned_async(position_velocity_ned_callback_t callback)
```


Subscribe to kinematic (position and velocity) updates (asynchronous).


**Parameters**

* [position_velocity_ned_callback_t](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1a6a584ef033a162eb56cf8c45589a8ffd) **callback** - Function to call with updates.

### position_async() {#classdronecode__sdk_1_1_telemetry_1a2a19fb93315e33a2dad6720b36ec9389}
```cpp
void dronecode_sdk::Telemetry::position_async(position_callback_t callback)
```


Subscribe to position updates (asynchronous).


**Parameters**

* [position_callback_t](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1a325501dc02e5c85cc7ad74ef233b3ff6) **callback** - Function to call with updates.

### home_position_async() {#classdronecode__sdk_1_1_telemetry_1ad94dbcc5ed4ebb8f377d11a2ea72f6fc}
```cpp
void dronecode_sdk::Telemetry::home_position_async(position_callback_t callback)
```


Subscribe to home position updates (asynchronous).


**Parameters**

* [position_callback_t](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1a325501dc02e5c85cc7ad74ef233b3ff6) **callback** - Function to call with updates.

### in_air_async() {#classdronecode__sdk_1_1_telemetry_1a1027180f38628306ddfd1d6e66ae067b}
```cpp
void dronecode_sdk::Telemetry::in_air_async(in_air_callback_t callback)
```


Subscribe to in-air updates (asynchronous).


**Parameters**

* [in_air_callback_t](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1af64278aec30c32f4b8db9d427ba9c48c) **callback** - Function to call with updates.

### status_text_async() {#classdronecode__sdk_1_1_telemetry_1aecc39d5aab5500a94c6516c9fcc6bc9a}
```cpp
void dronecode_sdk::Telemetry::status_text_async(status_text_callback_t callback)
```


Subscribe to status text updates (asynchronous).


**Parameters**

* [status_text_callback_t](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1abd606e783a8ca44b9b87d7eb82a9b980) **callback** - Function to call with updates.

### armed_async() {#classdronecode__sdk_1_1_telemetry_1a9382a19ea66f1d99f3780fa88abea3fd}
```cpp
void dronecode_sdk::Telemetry::armed_async(armed_callback_t callback)
```


Subscribe to armed updates (asynchronous).

Note that armed updates are limited to 1Hz.

**Parameters**

* [armed_callback_t](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1ad4be5f2c17988fa53b0c59affb64e9a2) **callback** - Function to call with updates.

### attitude_quaternion_async() {#classdronecode__sdk_1_1_telemetry_1ac9633b72e0a38f5d5ec7f98d63ff1944}
```cpp
void dronecode_sdk::Telemetry::attitude_quaternion_async(attitude_quaternion_callback_t callback)
```


Subscribe to attitude updates in quaternion (asynchronous).


**Parameters**

* [attitude_quaternion_callback_t](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1a4fe1cb6af59d7ecabb26563f6c33079d) **callback** - Function to call with updates.

### attitude_euler_angle_async() {#classdronecode__sdk_1_1_telemetry_1a6da4a219d31fffcbf2223f80bfa063f4}
```cpp
void dronecode_sdk::Telemetry::attitude_euler_angle_async(attitude_euler_angle_callback_t callback)
```


Subscribe to attitude updates in Euler angles (asynchronous).


**Parameters**

* [attitude_euler_angle_callback_t](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1a0db7573bc74c00231c96cb87a5711e96) **callback** - Function to call with updates.

### camera_attitude_quaternion_async() {#classdronecode__sdk_1_1_telemetry_1a8188574203ab3f916bfece2feaee62e2}
```cpp
void dronecode_sdk::Telemetry::camera_attitude_quaternion_async(attitude_quaternion_callback_t callback)
```


Subscribe to camera attitude updates in quaternion (asynchronous).


**Parameters**

* [attitude_quaternion_callback_t](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1a4fe1cb6af59d7ecabb26563f6c33079d) **callback** - Function to call with updates.

### camera_attitude_euler_angle_async() {#classdronecode__sdk_1_1_telemetry_1aa40c2f8da4cdbe812187854d23a31e6a}
```cpp
void dronecode_sdk::Telemetry::camera_attitude_euler_angle_async(attitude_euler_angle_callback_t callback)
```


Subscribe to camera attitude updates in Euler angles (asynchronous).


**Parameters**

* [attitude_euler_angle_callback_t](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1a0db7573bc74c00231c96cb87a5711e96) **callback** - Function to call with updates.

### ground_speed_ned_async() {#classdronecode__sdk_1_1_telemetry_1a652cf6fcec470ae65c39d22f934f6bc3}
```cpp
void dronecode_sdk::Telemetry::ground_speed_ned_async(ground_speed_ned_callback_t callback)
```


Subscribe to ground speed (NED) updates (asynchronous).


**Parameters**

* [ground_speed_ned_callback_t](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1a0ef2162b9ce267e0e59757712bbc8326) **callback** - Function to call with updates.

### gps_info_async() {#classdronecode__sdk_1_1_telemetry_1afbc16838d115ca2bc43901be1e5637ff}
```cpp
void dronecode_sdk::Telemetry::gps_info_async(gps_info_callback_t callback)
```


Subscribe to GPS information updates (asynchronous).


**Parameters**

* [gps_info_callback_t](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1a2111571572b3898de7c1296eb3c8f547) **callback** - Function to call with updates.

### battery_async() {#classdronecode__sdk_1_1_telemetry_1a7988874d093cc514c31ec737568010b1}
```cpp
void dronecode_sdk::Telemetry::battery_async(battery_callback_t callback)
```


Subscribe to battery status updates (asynchronous).


**Parameters**

* [battery_callback_t](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1ac13b14156d710aad87b113584a75af16) **callback** - Function to call with updates.

### flight_mode_async() {#classdronecode__sdk_1_1_telemetry_1a29494b6f0ed34be913e3f5c4bbfdf4cd}
```cpp
void dronecode_sdk::Telemetry::flight_mode_async(flight_mode_callback_t callback)
```


Subscribe to flight mode updates (asynchronous).

Note that flight mode updates are limited to 1Hz.

**Parameters**

* [flight_mode_callback_t](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1a2d667183c1d2640c7248e9c438c01191) **callback** - Function to call with updates.

### health_async() {#classdronecode__sdk_1_1_telemetry_1ad6f8b300630350000db7c44ce6976ab0}
```cpp
void dronecode_sdk::Telemetry::health_async(health_callback_t callback)
```


Subscribe to health status updates (asynchronous).

Note that health status updates are limited to 1Hz.

**Parameters**

* [health_callback_t](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1a58fdb6d9cb7dc8124182556630a0135c) **callback** - Function to call with updates.

### health_all_ok_async() {#classdronecode__sdk_1_1_telemetry_1ad3eb60db8b4dc72fd55d8689d849c9ae}
```cpp
void dronecode_sdk::Telemetry::health_all_ok_async(health_all_ok_callback_t callback)
```


Subscribe to overall health status updates (asynchronous).

Note that overall health status updates are limited to 1Hz.

**Parameters**

* [health_all_ok_callback_t](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1aabf06480ae9a9ab85412b749030534df) **callback** - Function to call with updates.

### rc_status_async() {#classdronecode__sdk_1_1_telemetry_1a9c08927e8693588dfc7a8d33d3df2423}
```cpp
void dronecode_sdk::Telemetry::rc_status_async(rc_status_callback_t callback)
```


Subscribe to RC status updates (asynchronous).


**Parameters**

* [rc_status_callback_t](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1a1441a3aa4b0865ebb62f5e4f6d1cbdee) **callback** - Function to call with updates.

### operator=() {#classdronecode__sdk_1_1_telemetry_1a029b8fc4c241e4c20d26ff1a4e601ef7}
```cpp
const Telemetry& dronecode_sdk::Telemetry::operator=(const Telemetry &)=delete
```


Equality operator (object is not copyable).


**Parameters**

* const [Telemetry](classdronecode__sdk_1_1_telemetry.md)&  - 

**Returns**

&emsp;const [Telemetry](classdronecode__sdk_1_1_telemetry.md) & - 

### flight_mode_str() {#classdronecode__sdk_1_1_telemetry_1ac35c44d286d50e649b5e192730a756e7}
```cpp
static std::string dronecode_sdk::Telemetry::flight_mode_str(FlightMode flight_mode)
```


Get a human readable English string for a flight mode.


**Parameters**

* [FlightMode](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1a7e503d87f48fabb8549b4af7acb77f8f) **flight_mode** - 

**Returns**

&emsp;std::string - 

### result_str() {#classdronecode__sdk_1_1_telemetry_1a046457e28886493a677fe7d35627bacc}
```cpp
static const char* dronecode_sdk::Telemetry::result_str(Result result)
```


Get human-readable English string for [Telemetry::Result](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1ae5e3509344edb0faea3d44b786c16b3e).


**Parameters**

* [Result](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1ae5e3509344edb0faea3d44b786c16b3e) **result** - The enum value for which string is needed.

**Returns**

&emsp;const char * - Human readable string for the [Telemetry::Result](classdronecode__sdk_1_1_telemetry.md#classdronecode__sdk_1_1_telemetry_1ae5e3509344edb0faea3d44b786c16b3e).