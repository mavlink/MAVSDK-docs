# mavsdk::Telemetry Class Reference
`#include: telemetry.h`

----


Allow users to get vehicle telemetry and state information (e.g. battery, GPS, RC connection, flight mode etc.) and set telemetry update rates. 


## Data Structures


struct [AccelerationFrd](structmavsdk_1_1_telemetry_1_1_acceleration_frd.md)

struct [ActuatorControlTarget](structmavsdk_1_1_telemetry_1_1_actuator_control_target.md)

struct [ActuatorOutputStatus](structmavsdk_1_1_telemetry_1_1_actuator_output_status.md)

struct [AngularVelocityBody](structmavsdk_1_1_telemetry_1_1_angular_velocity_body.md)

struct [AngularVelocityFrd](structmavsdk_1_1_telemetry_1_1_angular_velocity_frd.md)

struct [Battery](structmavsdk_1_1_telemetry_1_1_battery.md)

struct [Covariance](structmavsdk_1_1_telemetry_1_1_covariance.md)

struct [DistanceSensor](structmavsdk_1_1_telemetry_1_1_distance_sensor.md)

struct [EulerAngle](structmavsdk_1_1_telemetry_1_1_euler_angle.md)

struct [FixedwingMetrics](structmavsdk_1_1_telemetry_1_1_fixedwing_metrics.md)

struct [GpsGlobalOrigin](structmavsdk_1_1_telemetry_1_1_gps_global_origin.md)

struct [GpsInfo](structmavsdk_1_1_telemetry_1_1_gps_info.md)

struct [GroundTruth](structmavsdk_1_1_telemetry_1_1_ground_truth.md)

struct [Heading](structmavsdk_1_1_telemetry_1_1_heading.md)

struct [Health](structmavsdk_1_1_telemetry_1_1_health.md)

struct [Imu](structmavsdk_1_1_telemetry_1_1_imu.md)

struct [MagneticFieldFrd](structmavsdk_1_1_telemetry_1_1_magnetic_field_frd.md)

struct [Odometry](structmavsdk_1_1_telemetry_1_1_odometry.md)

struct [Position](structmavsdk_1_1_telemetry_1_1_position.md)

struct [PositionBody](structmavsdk_1_1_telemetry_1_1_position_body.md)

struct [PositionNed](structmavsdk_1_1_telemetry_1_1_position_ned.md)

struct [PositionVelocityNed](structmavsdk_1_1_telemetry_1_1_position_velocity_ned.md)

struct [Quaternion](structmavsdk_1_1_telemetry_1_1_quaternion.md)

struct [RawGps](structmavsdk_1_1_telemetry_1_1_raw_gps.md)

struct [RcStatus](structmavsdk_1_1_telemetry_1_1_rc_status.md)

struct [ScaledPressure](structmavsdk_1_1_telemetry_1_1_scaled_pressure.md)

struct [StatusText](structmavsdk_1_1_telemetry_1_1_status_text.md)

struct [VelocityBody](structmavsdk_1_1_telemetry_1_1_velocity_body.md)

struct [VelocityNed](structmavsdk_1_1_telemetry_1_1_velocity_ned.md)

## Public Types


Type | Description
--- | ---
enum [FixType](#classmavsdk_1_1_telemetry_1a548213e1b26615d7b6d1b0b3934639de) | GPS fix type.
enum [FlightMode](#classmavsdk_1_1_telemetry_1a8317d953a82a23654db6f14509acb4fe) | Flight modes.
enum [StatusTextType](#classmavsdk_1_1_telemetry_1ada3ebb336abad223a98bc2a625e0e7d8) | Status types.
enum [LandedState](#classmavsdk_1_1_telemetry_1ac6639935bc3b35b1da553cde41e8f046) | Landed State enumeration.
enum [VtolState](#classmavsdk_1_1_telemetry_1a256f951d993aa120c437d989a6e94166) | VTOL State enumeration.
enum [Result](#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75) | Possible results returned for telemetry requests.
std::function< void([Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75))> [ResultCallback](#classmavsdk_1_1_telemetry_1a166e81c6573532978e5940eafdfcec0b) | Callback type for asynchronous [Telemetry](classmavsdk_1_1_telemetry.md) calls.
std::function< void([Position](structmavsdk_1_1_telemetry_1_1_position.md))> [PositionCallback](#classmavsdk_1_1_telemetry_1a978b371d636226e198995462afa63552) | Callback type for subscribe_position.
std::function< void([Position](structmavsdk_1_1_telemetry_1_1_position.md))> [HomeCallback](#classmavsdk_1_1_telemetry_1aaac029969c37a001d43e2788a6abf634) | Callback type for subscribe_home.
std::function< void(bool)> [InAirCallback](#classmavsdk_1_1_telemetry_1af96cca452305dd8f51b42d4663f15a26) | Callback type for subscribe_in_air.
std::function< void([LandedState](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1ac6639935bc3b35b1da553cde41e8f046))> [LandedStateCallback](#classmavsdk_1_1_telemetry_1a0cd8ef17abdd7c3d6a9ee761ccc6ae5e) | Callback type for subscribe_landed_state.
std::function< void(bool)> [ArmedCallback](#classmavsdk_1_1_telemetry_1a9d23a4092d94e50694390e9f41b8c419) | Callback type for subscribe_armed.
std::function< void([VtolState](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a256f951d993aa120c437d989a6e94166))> [VtolStateCallback](#classmavsdk_1_1_telemetry_1abf52126ce4d4efb99560aa8e8e58f20c) | Callback type for subscribe_vtol_state.
std::function< void([Quaternion](structmavsdk_1_1_telemetry_1_1_quaternion.md))> [AttitudeQuaternionCallback](#classmavsdk_1_1_telemetry_1ad16e61245511a99e930d6fdcbd761a30) | Callback type for subscribe_attitude_quaternion.
std::function< void([EulerAngle](structmavsdk_1_1_telemetry_1_1_euler_angle.md))> [AttitudeEulerCallback](#classmavsdk_1_1_telemetry_1a321c7607922369926fbd5f2821986cba) | Callback type for subscribe_attitude_euler.
std::function< void([AngularVelocityBody](structmavsdk_1_1_telemetry_1_1_angular_velocity_body.md))> [AttitudeAngularVelocityBodyCallback](#classmavsdk_1_1_telemetry_1a35ff8def3048faeab7f732153d51085f) | Callback type for subscribe_attitude_angular_velocity_body.
std::function< void([Quaternion](structmavsdk_1_1_telemetry_1_1_quaternion.md))> [CameraAttitudeQuaternionCallback](#classmavsdk_1_1_telemetry_1aa83dafa14e9b5179573a574f6fbdd973) | Callback type for subscribe_camera_attitude_quaternion.
std::function< void([EulerAngle](structmavsdk_1_1_telemetry_1_1_euler_angle.md))> [CameraAttitudeEulerCallback](#classmavsdk_1_1_telemetry_1aa29f9bb0767ba8c384bfe1df69f2fdd9) | Callback type for subscribe_camera_attitude_euler.
std::function< void([VelocityNed](structmavsdk_1_1_telemetry_1_1_velocity_ned.md))> [VelocityNedCallback](#classmavsdk_1_1_telemetry_1ab5859d2f6a9c9bd81282166b3de92342) | Callback type for subscribe_velocity_ned.
std::function< void([GpsInfo](structmavsdk_1_1_telemetry_1_1_gps_info.md))> [GpsInfoCallback](#classmavsdk_1_1_telemetry_1ad8fa90886b2283eace09b4b46708048b) | Callback type for subscribe_gps_info.
std::function< void([RawGps](structmavsdk_1_1_telemetry_1_1_raw_gps.md))> [RawGpsCallback](#classmavsdk_1_1_telemetry_1a915868d562ed445fa30beaa9140ea97c) | Callback type for subscribe_raw_gps.
std::function< void([Battery](structmavsdk_1_1_telemetry_1_1_battery.md))> [BatteryCallback](#classmavsdk_1_1_telemetry_1af4b121c576ef2ae567b1d571b12dff9d) | Callback type for subscribe_battery.
std::function< void([FlightMode](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a8317d953a82a23654db6f14509acb4fe))> [FlightModeCallback](#classmavsdk_1_1_telemetry_1a2d7318d0823771b7a586c40199bdb482) | Callback type for subscribe_flight_mode.
std::function< void([Health](structmavsdk_1_1_telemetry_1_1_health.md))> [HealthCallback](#classmavsdk_1_1_telemetry_1a7a120dd053091c644e0e2e47fdcbeb75) | Callback type for subscribe_health.
std::function< void([RcStatus](structmavsdk_1_1_telemetry_1_1_rc_status.md))> [RcStatusCallback](#classmavsdk_1_1_telemetry_1aafcd706b805898301b574ffa2b909b85) | Callback type for subscribe_rc_status.
std::function< void([StatusText](structmavsdk_1_1_telemetry_1_1_status_text.md))> [StatusTextCallback](#classmavsdk_1_1_telemetry_1a46e51ff90fe779990ed09a593c1c7898) | Callback type for subscribe_status_text.
std::function< void([ActuatorControlTarget](structmavsdk_1_1_telemetry_1_1_actuator_control_target.md))> [ActuatorControlTargetCallback](#classmavsdk_1_1_telemetry_1ada6af3de1b60b93a709345c3a8ede551) | Callback type for subscribe_actuator_control_target.
std::function< void([ActuatorOutputStatus](structmavsdk_1_1_telemetry_1_1_actuator_output_status.md))> [ActuatorOutputStatusCallback](#classmavsdk_1_1_telemetry_1a2b1e800ce1ba6fb776351416340ac8b9) | Callback type for subscribe_actuator_output_status.
std::function< void([Odometry](structmavsdk_1_1_telemetry_1_1_odometry.md))> [OdometryCallback](#classmavsdk_1_1_telemetry_1a8cd23f7364f8f5cb22869155da67c65d) | Callback type for subscribe_odometry.
std::function< void([PositionVelocityNed](structmavsdk_1_1_telemetry_1_1_position_velocity_ned.md))> [PositionVelocityNedCallback](#classmavsdk_1_1_telemetry_1a5a38deb284622ff6926703e1e5c96a74) | Callback type for subscribe_position_velocity_ned.
std::function< void([GroundTruth](structmavsdk_1_1_telemetry_1_1_ground_truth.md))> [GroundTruthCallback](#classmavsdk_1_1_telemetry_1a222aae53852a2c535f6d69ed57221f13) | Callback type for subscribe_ground_truth.
std::function< void([FixedwingMetrics](structmavsdk_1_1_telemetry_1_1_fixedwing_metrics.md))> [FixedwingMetricsCallback](#classmavsdk_1_1_telemetry_1a5b42dbef0ef6d8c1768d503d0437f1e3) | Callback type for subscribe_fixedwing_metrics.
std::function< void([Imu](structmavsdk_1_1_telemetry_1_1_imu.md))> [ImuCallback](#classmavsdk_1_1_telemetry_1a4fbc2ad274fd5a8af077004d2d7bd984) | Callback type for subscribe_imu.
std::function< void([Imu](structmavsdk_1_1_telemetry_1_1_imu.md))> [ScaledImuCallback](#classmavsdk_1_1_telemetry_1a26159a775adcfbc42302234b7108d94f) | Callback type for subscribe_scaled_imu.
std::function< void([Imu](structmavsdk_1_1_telemetry_1_1_imu.md))> [RawImuCallback](#classmavsdk_1_1_telemetry_1a92711da85d343cb58b73561e6b730c76) | Callback type for subscribe_raw_imu.
std::function< void(bool)> [HealthAllOkCallback](#classmavsdk_1_1_telemetry_1a71cdcadfaa988dc14029e0b9fdbe742d) | Callback type for subscribe_health_all_ok.
std::function< void(uint64_t)> [UnixEpochTimeCallback](#classmavsdk_1_1_telemetry_1a321c7d809ae8f56bb8a361d5e5ce6391) | Callback type for subscribe_unix_epoch_time.
std::function< void([DistanceSensor](structmavsdk_1_1_telemetry_1_1_distance_sensor.md))> [DistanceSensorCallback](#classmavsdk_1_1_telemetry_1aacfdb5e2cce7f3f77c68b36f020ed1f2) | Callback type for subscribe_distance_sensor.
std::function< void([ScaledPressure](structmavsdk_1_1_telemetry_1_1_scaled_pressure.md))> [ScaledPressureCallback](#classmavsdk_1_1_telemetry_1ac123edc254bb1874edc08a0f531f82b1) | Callback type for subscribe_scaled_pressure.
std::function< void([Heading](structmavsdk_1_1_telemetry_1_1_heading.md))> [HeadingCallback](#classmavsdk_1_1_telemetry_1aa3bca0adab525a4c733c1e7f5c5dd8b3) | Callback type for subscribe_heading.
std::function< void([Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75), [GpsGlobalOrigin](structmavsdk_1_1_telemetry_1_1_gps_global_origin.md))> [GetGpsGlobalOriginCallback](#classmavsdk_1_1_telemetry_1a350ee89a7e30a691e130e29ace8917ef) | Callback type for get_gps_global_origin_async.

## Public Member Functions


Type | Name | Description
---: | --- | ---
&nbsp; | [Telemetry](#classmavsdk_1_1_telemetry_1a6c8c8ed8759fc8c6e9fd4e7644c63cbe) ([System](classmavsdk_1_1_system.md) & system) | Constructor. Creates the plugin for a specific [System](classmavsdk_1_1_system.md).
&nbsp; | [Telemetry](#classmavsdk_1_1_telemetry_1af78f18fbb117c82d5ffe21e015535067) (std::shared_ptr< [System](classmavsdk_1_1_system.md) > system) | Constructor. Creates the plugin for a specific [System](classmavsdk_1_1_system.md).
&nbsp; | [~Telemetry](#classmavsdk_1_1_telemetry_1a1db31974e0ea6ea9a530d68783566ab1) () | Destructor (internal use only).
&nbsp; | [Telemetry](#classmavsdk_1_1_telemetry_1ad734f199b82a9928c63230676c9789e9) (const [Telemetry](classmavsdk_1_1_telemetry.md) & other) | Copy constructor.
void | [subscribe_position](#classmavsdk_1_1_telemetry_1a61bda57b3ca47000ea7e4758b2a33134) ([PositionCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a978b371d636226e198995462afa63552) callback) | Subscribe to 'position' updates.
[Position](structmavsdk_1_1_telemetry_1_1_position.md) | [position](#classmavsdk_1_1_telemetry_1a2299da1bc63313c429f07ab0fdbe5335) () const | Poll for '[Position](structmavsdk_1_1_telemetry_1_1_position.md)' (blocking).
void | [subscribe_home](#classmavsdk_1_1_telemetry_1a67585989a12de2f099dbc4eb4c41686a) ([HomeCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1aaac029969c37a001d43e2788a6abf634) callback) | Subscribe to 'home position' updates.
[Position](structmavsdk_1_1_telemetry_1_1_position.md) | [home](#classmavsdk_1_1_telemetry_1ad5c239b93aa1923edd1b97494a3fbfe7) () const | Poll for '[Position](structmavsdk_1_1_telemetry_1_1_position.md)' (blocking).
void | [subscribe_in_air](#classmavsdk_1_1_telemetry_1a5ba005827b1ef988ba3f6e81f7469d40) ([InAirCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1af96cca452305dd8f51b42d4663f15a26) callback) | Subscribe to in-air updates.
bool | [in_air](#classmavsdk_1_1_telemetry_1a909738ff2fbe104c6eb4524cc9bf2dd5) () const | Poll for 'bool' (blocking).
void | [subscribe_landed_state](#classmavsdk_1_1_telemetry_1a8eb2d40764b3940e9054c301a6ef5f50) ([LandedStateCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a0cd8ef17abdd7c3d6a9ee761ccc6ae5e) callback) | Subscribe to landed state updates.
[LandedState](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1ac6639935bc3b35b1da553cde41e8f046) | [landed_state](#classmavsdk_1_1_telemetry_1af7d7c385852db38d6320516508ce7465) () const | Poll for 'LandedState' (blocking).
void | [subscribe_armed](#classmavsdk_1_1_telemetry_1a6bada4a3538eb1142fca024bc89ec2d3) ([ArmedCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a9d23a4092d94e50694390e9f41b8c419) callback) | Subscribe to armed updates.
bool | [armed](#classmavsdk_1_1_telemetry_1a6620142adc47f069262e5bf69dbb3876) () const | Poll for 'bool' (blocking).
void | [subscribe_vtol_state](#classmavsdk_1_1_telemetry_1a0ce11e7983ee7ae8693ad8835d70f4f4) ([VtolStateCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1abf52126ce4d4efb99560aa8e8e58f20c) callback) | subscribe to vtol state Updates
[VtolState](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a256f951d993aa120c437d989a6e94166) | [vtol_state](#classmavsdk_1_1_telemetry_1a6d3fd68f3e639a2bf9940e9f38f220c3) () const | Poll for 'VtolState' (blocking).
void | [subscribe_attitude_quaternion](#classmavsdk_1_1_telemetry_1afa6c079d48bc0c0a3287ac095ec290b9) ([AttitudeQuaternionCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1ad16e61245511a99e930d6fdcbd761a30) callback) | Subscribe to 'attitude' updates (quaternion).
[Quaternion](structmavsdk_1_1_telemetry_1_1_quaternion.md) | [attitude_quaternion](#classmavsdk_1_1_telemetry_1aae76890957b33727be72a39807448c88) () const | Poll for '[Quaternion](structmavsdk_1_1_telemetry_1_1_quaternion.md)' (blocking).
void | [subscribe_attitude_euler](#classmavsdk_1_1_telemetry_1ae380f3c65fb5f4d3961101b71ebbd1aa) ([AttitudeEulerCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a321c7607922369926fbd5f2821986cba) callback) | Subscribe to 'attitude' updates (Euler).
[EulerAngle](structmavsdk_1_1_telemetry_1_1_euler_angle.md) | [attitude_euler](#classmavsdk_1_1_telemetry_1a03035bb72324e843372eb69cf7899ce5) () const | Poll for '[EulerAngle](structmavsdk_1_1_telemetry_1_1_euler_angle.md)' (blocking).
void | [subscribe_attitude_angular_velocity_body](#classmavsdk_1_1_telemetry_1a84be21f00d23911ee77cbd7dc6512420) ([AttitudeAngularVelocityBodyCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a35ff8def3048faeab7f732153d51085f) callback) | Subscribe to 'attitude' updates (angular velocity)
[AngularVelocityBody](structmavsdk_1_1_telemetry_1_1_angular_velocity_body.md) | [attitude_angular_velocity_body](#classmavsdk_1_1_telemetry_1a8d9e2489b79c2cdbabaef8b6bb8e2952) () const | Poll for '[AngularVelocityBody](structmavsdk_1_1_telemetry_1_1_angular_velocity_body.md)' (blocking).
void | [subscribe_camera_attitude_quaternion](#classmavsdk_1_1_telemetry_1a6845e2752b535e0ee539f276cfca45d9) ([CameraAttitudeQuaternionCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1aa83dafa14e9b5179573a574f6fbdd973) callback) | Subscribe to 'camera attitude' updates (quaternion).
[Quaternion](structmavsdk_1_1_telemetry_1_1_quaternion.md) | [camera_attitude_quaternion](#classmavsdk_1_1_telemetry_1a3c07447351d3b6195d5e2526e7b128b3) () const | Poll for '[Quaternion](structmavsdk_1_1_telemetry_1_1_quaternion.md)' (blocking).
void | [subscribe_camera_attitude_euler](#classmavsdk_1_1_telemetry_1afaa61016a5319ebea73dc5b1e4cde89c) ([CameraAttitudeEulerCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1aa29f9bb0767ba8c384bfe1df69f2fdd9) callback) | Subscribe to 'camera attitude' updates (Euler).
[EulerAngle](structmavsdk_1_1_telemetry_1_1_euler_angle.md) | [camera_attitude_euler](#classmavsdk_1_1_telemetry_1a635643d955f0cd9a805914501f819796) () const | Poll for '[EulerAngle](structmavsdk_1_1_telemetry_1_1_euler_angle.md)' (blocking).
void | [subscribe_velocity_ned](#classmavsdk_1_1_telemetry_1a0bcbf7a51643c8ca4a93dabd0f4364b5) ([VelocityNedCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1ab5859d2f6a9c9bd81282166b3de92342) callback) | Subscribe to 'ground speed' updates (NED).
[VelocityNed](structmavsdk_1_1_telemetry_1_1_velocity_ned.md) | [velocity_ned](#classmavsdk_1_1_telemetry_1a40a86062c0322d6be7c86d8e15a52f28) () const | Poll for '[VelocityNed](structmavsdk_1_1_telemetry_1_1_velocity_ned.md)' (blocking).
void | [subscribe_gps_info](#classmavsdk_1_1_telemetry_1aa078035ce00505b726dcac4d47796cee) ([GpsInfoCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1ad8fa90886b2283eace09b4b46708048b) callback) | Subscribe to 'GPS info' updates.
[GpsInfo](structmavsdk_1_1_telemetry_1_1_gps_info.md) | [gps_info](#classmavsdk_1_1_telemetry_1a983dabc1aed50745b326072662c419e8) () const | Poll for '[GpsInfo](structmavsdk_1_1_telemetry_1_1_gps_info.md)' (blocking).
void | [subscribe_raw_gps](#classmavsdk_1_1_telemetry_1a7632511f881113f6ecc721c22a17785d) ([RawGpsCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a915868d562ed445fa30beaa9140ea97c) callback) | Subscribe to 'Raw GPS' updates.
[RawGps](structmavsdk_1_1_telemetry_1_1_raw_gps.md) | [raw_gps](#classmavsdk_1_1_telemetry_1ac43c29e435b6c1a6594854adc6a1bf6c) () const | Poll for '[RawGps](structmavsdk_1_1_telemetry_1_1_raw_gps.md)' (blocking).
void | [subscribe_battery](#classmavsdk_1_1_telemetry_1a9a8c5288273b4a6f1e43377a70f47a0e) ([BatteryCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1af4b121c576ef2ae567b1d571b12dff9d) callback) | Subscribe to 'battery' updates.
[Battery](structmavsdk_1_1_telemetry_1_1_battery.md) | [battery](#classmavsdk_1_1_telemetry_1afb3bad3c7a36c14ae97492df3f6bbd54) () const | Poll for '[Battery](structmavsdk_1_1_telemetry_1_1_battery.md)' (blocking).
void | [subscribe_flight_mode](#classmavsdk_1_1_telemetry_1a53db5fb36bf10fbc7ac004a3be9100a4) ([FlightModeCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a2d7318d0823771b7a586c40199bdb482) callback) | Subscribe to 'flight mode' updates.
[FlightMode](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a8317d953a82a23654db6f14509acb4fe) | [flight_mode](#classmavsdk_1_1_telemetry_1a4972a3968e379d565e7700f2f51158dd) () const | Poll for 'FlightMode' (blocking).
void | [subscribe_health](#classmavsdk_1_1_telemetry_1a0c489b33a635adf0610731a42ce5615b) ([HealthCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a7a120dd053091c644e0e2e47fdcbeb75) callback) | Subscribe to 'health' updates.
[Health](structmavsdk_1_1_telemetry_1_1_health.md) | [health](#classmavsdk_1_1_telemetry_1aae4824c9eeb72603b197c864b5cc5df5) () const | Poll for '[Health](structmavsdk_1_1_telemetry_1_1_health.md)' (blocking).
void | [subscribe_rc_status](#classmavsdk_1_1_telemetry_1ae5f894c16564674f7fdaba36ff12dd08) ([RcStatusCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1aafcd706b805898301b574ffa2b909b85) callback) | Subscribe to 'RC status' updates.
[RcStatus](structmavsdk_1_1_telemetry_1_1_rc_status.md) | [rc_status](#classmavsdk_1_1_telemetry_1a59cd497c69f1d32be29a940a2d34a474) () const | Poll for '[RcStatus](structmavsdk_1_1_telemetry_1_1_rc_status.md)' (blocking).
void | [subscribe_status_text](#classmavsdk_1_1_telemetry_1a80106e59b9df76a47a2068b4fb4ecb69) ([StatusTextCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a46e51ff90fe779990ed09a593c1c7898) callback) | Subscribe to 'status text' updates.
[StatusText](structmavsdk_1_1_telemetry_1_1_status_text.md) | [status_text](#classmavsdk_1_1_telemetry_1a2f31c0668ed1ac1bfdfa4b2e9a2023a9) () const | Poll for '[StatusText](structmavsdk_1_1_telemetry_1_1_status_text.md)' (blocking).
void | [subscribe_actuator_control_target](#classmavsdk_1_1_telemetry_1a697c3618245a9886f917431aee59bd2c) ([ActuatorControlTargetCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1ada6af3de1b60b93a709345c3a8ede551) callback) | Subscribe to 'actuator control target' updates.
[ActuatorControlTarget](structmavsdk_1_1_telemetry_1_1_actuator_control_target.md) | [actuator_control_target](#classmavsdk_1_1_telemetry_1af4ffa70ff58c46b50be93a0fbf960f95) () const | Poll for '[ActuatorControlTarget](structmavsdk_1_1_telemetry_1_1_actuator_control_target.md)' (blocking).
void | [subscribe_actuator_output_status](#classmavsdk_1_1_telemetry_1ab5bc6fdb24935f4834cd490d7a085594) ([ActuatorOutputStatusCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a2b1e800ce1ba6fb776351416340ac8b9) callback) | Subscribe to 'actuator output status' updates.
[ActuatorOutputStatus](structmavsdk_1_1_telemetry_1_1_actuator_output_status.md) | [actuator_output_status](#classmavsdk_1_1_telemetry_1a68fa1619dfad0a7cfcc2725025669252) () const | Poll for '[ActuatorOutputStatus](structmavsdk_1_1_telemetry_1_1_actuator_output_status.md)' (blocking).
void | [subscribe_odometry](#classmavsdk_1_1_telemetry_1a1ff5094feae71f009b7cdbab90734b09) ([OdometryCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a8cd23f7364f8f5cb22869155da67c65d) callback) | Subscribe to 'odometry' updates.
[Odometry](structmavsdk_1_1_telemetry_1_1_odometry.md) | [odometry](#classmavsdk_1_1_telemetry_1a715b6e8ba1206059706f08844a0b96d2) () const | Poll for '[Odometry](structmavsdk_1_1_telemetry_1_1_odometry.md)' (blocking).
void | [subscribe_position_velocity_ned](#classmavsdk_1_1_telemetry_1a8e09afe19fe9f2c05a5d647ceb2c8310) ([PositionVelocityNedCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a5a38deb284622ff6926703e1e5c96a74) callback) | Subscribe to 'position velocity' updates.
[PositionVelocityNed](structmavsdk_1_1_telemetry_1_1_position_velocity_ned.md) | [position_velocity_ned](#classmavsdk_1_1_telemetry_1af9b06944ca73ad09caadacd9f4fae950) () const | Poll for '[PositionVelocityNed](structmavsdk_1_1_telemetry_1_1_position_velocity_ned.md)' (blocking).
void | [subscribe_ground_truth](#classmavsdk_1_1_telemetry_1adcc18e7d8801ccdef2cf137a84d53460) ([GroundTruthCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a222aae53852a2c535f6d69ed57221f13) callback) | Subscribe to 'ground truth' updates.
[GroundTruth](structmavsdk_1_1_telemetry_1_1_ground_truth.md) | [ground_truth](#classmavsdk_1_1_telemetry_1a1b5f387edc39e33b86954f2048133f71) () const | Poll for '[GroundTruth](structmavsdk_1_1_telemetry_1_1_ground_truth.md)' (blocking).
void | [subscribe_fixedwing_metrics](#classmavsdk_1_1_telemetry_1a1b32f7cc867f8f21fdcedda49434a22b) ([FixedwingMetricsCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a5b42dbef0ef6d8c1768d503d0437f1e3) callback) | Subscribe to 'fixedwing metrics' updates.
[FixedwingMetrics](structmavsdk_1_1_telemetry_1_1_fixedwing_metrics.md) | [fixedwing_metrics](#classmavsdk_1_1_telemetry_1a2ab8d2a8d017d46e77d49c4f899c7cbf) () const | Poll for '[FixedwingMetrics](structmavsdk_1_1_telemetry_1_1_fixedwing_metrics.md)' (blocking).
void | [subscribe_imu](#classmavsdk_1_1_telemetry_1a35ce2552e8b709e6194481c0fd070a8d) ([ImuCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a4fbc2ad274fd5a8af077004d2d7bd984) callback) | Subscribe to 'IMU' updates (in SI units in NED body frame).
[Imu](structmavsdk_1_1_telemetry_1_1_imu.md) | [imu](#classmavsdk_1_1_telemetry_1a1a4e43b7bdcd988442955d2a5465b977) () const | Poll for '[Imu](structmavsdk_1_1_telemetry_1_1_imu.md)' (blocking).
void | [subscribe_scaled_imu](#classmavsdk_1_1_telemetry_1ac3b293defb52103db936e650212832c1) ([ScaledImuCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a26159a775adcfbc42302234b7108d94f) callback) | Subscribe to 'Scaled IMU' updates.
[Imu](structmavsdk_1_1_telemetry_1_1_imu.md) | [scaled_imu](#classmavsdk_1_1_telemetry_1ab6a515ba85a67bc80e6e1c9a05d1f94d) () const | Poll for '[Imu](structmavsdk_1_1_telemetry_1_1_imu.md)' (blocking).
void | [subscribe_raw_imu](#classmavsdk_1_1_telemetry_1aeaf9d9393300bd61470d6b7bb92b03c2) ([RawImuCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a92711da85d343cb58b73561e6b730c76) callback) | Subscribe to 'Raw IMU' updates.
[Imu](structmavsdk_1_1_telemetry_1_1_imu.md) | [raw_imu](#classmavsdk_1_1_telemetry_1a691464f001ddf8d02b97bcf137f5cf8a) () const | Poll for '[Imu](structmavsdk_1_1_telemetry_1_1_imu.md)' (blocking).
void | [subscribe_health_all_ok](#classmavsdk_1_1_telemetry_1a0f94ea6d707ff314e412367d6681bd8f) ([HealthAllOkCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a71cdcadfaa988dc14029e0b9fdbe742d) callback) | Subscribe to 'HealthAllOk' updates.
bool | [health_all_ok](#classmavsdk_1_1_telemetry_1ad6d833741b5576f07204d268c5cd4d06) () const | Poll for 'bool' (blocking).
void | [subscribe_unix_epoch_time](#classmavsdk_1_1_telemetry_1ad7f04211822f862b580308e3786cdc77) ([UnixEpochTimeCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a321c7d809ae8f56bb8a361d5e5ce6391) callback) | Subscribe to 'unix epoch time' updates.
uint64_t | [unix_epoch_time](#classmavsdk_1_1_telemetry_1ab5ea5f6bb35b5670e34d5697d8c880f4) () const | Poll for 'uint64_t' (blocking).
void | [subscribe_distance_sensor](#classmavsdk_1_1_telemetry_1a74654313a3f588f252012ee6412e9342) ([DistanceSensorCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1aacfdb5e2cce7f3f77c68b36f020ed1f2) callback) | Subscribe to 'Distance Sensor' updates.
[DistanceSensor](structmavsdk_1_1_telemetry_1_1_distance_sensor.md) | [distance_sensor](#classmavsdk_1_1_telemetry_1aa01828c0ffcb4727b884ffeae8fef59a) () const | Poll for '[DistanceSensor](structmavsdk_1_1_telemetry_1_1_distance_sensor.md)' (blocking).
void | [subscribe_scaled_pressure](#classmavsdk_1_1_telemetry_1a2cdca606b62c7fd94c61a47cd06f2245) ([ScaledPressureCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1ac123edc254bb1874edc08a0f531f82b1) callback) | Subscribe to 'Scaled Pressure' updates.
[ScaledPressure](structmavsdk_1_1_telemetry_1_1_scaled_pressure.md) | [scaled_pressure](#classmavsdk_1_1_telemetry_1a825ecb6af46663034f982c3c3d6da022) () const | Poll for '[ScaledPressure](structmavsdk_1_1_telemetry_1_1_scaled_pressure.md)' (blocking).
void | [subscribe_heading](#classmavsdk_1_1_telemetry_1a68c5e62cad1c641a13d0d5c3ae064ce4) ([HeadingCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1aa3bca0adab525a4c733c1e7f5c5dd8b3) callback) | Subscribe to '[Heading](structmavsdk_1_1_telemetry_1_1_heading.md)' updates.
[Heading](structmavsdk_1_1_telemetry_1_1_heading.md) | [heading](#classmavsdk_1_1_telemetry_1a2aec80b167a3076903be4fe52847a4d3) () const | Poll for '[Heading](structmavsdk_1_1_telemetry_1_1_heading.md)' (blocking).
void | [set_rate_position_async](#classmavsdk_1_1_telemetry_1ad7e5b576edb9398c8f5f2f14626b984a) (double rate_hz, const [ResultCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a166e81c6573532978e5940eafdfcec0b) callback) | Set rate to 'position' updates.
[Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75) | [set_rate_position](#classmavsdk_1_1_telemetry_1a665439f3d5f8c58b3ef3dd427cf4782b) (double rate_hz)const | Set rate to 'position' updates.
void | [set_rate_home_async](#classmavsdk_1_1_telemetry_1a098f4c4f50fc3ac2c153ef152208fbbe) (double rate_hz, const [ResultCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a166e81c6573532978e5940eafdfcec0b) callback) | Set rate to 'home position' updates.
[Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75) | [set_rate_home](#classmavsdk_1_1_telemetry_1af90e28ad8a8f05401176c98e427eecfc) (double rate_hz)const | Set rate to 'home position' updates.
void | [set_rate_in_air_async](#classmavsdk_1_1_telemetry_1a9ea77b7ef64acd1e25b05e593e638c70) (double rate_hz, const [ResultCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a166e81c6573532978e5940eafdfcec0b) callback) | Set rate to in-air updates.
[Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75) | [set_rate_in_air](#classmavsdk_1_1_telemetry_1a8f179e8397b395e61a48529ceeba2b14) (double rate_hz)const | Set rate to in-air updates.
void | [set_rate_landed_state_async](#classmavsdk_1_1_telemetry_1a180fff93b120a67c16ad5993f0b38847) (double rate_hz, const [ResultCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a166e81c6573532978e5940eafdfcec0b) callback) | Set rate to landed state updates.
[Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75) | [set_rate_landed_state](#classmavsdk_1_1_telemetry_1a53a3428c602c1f91cfcffdba188a4e51) (double rate_hz)const | Set rate to landed state updates.
void | [set_rate_vtol_state_async](#classmavsdk_1_1_telemetry_1a18f47beba583e6814061f95e68a3851d) (double rate_hz, const [ResultCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a166e81c6573532978e5940eafdfcec0b) callback) | Set rate to VTOL state updates.
[Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75) | [set_rate_vtol_state](#classmavsdk_1_1_telemetry_1a943c2e32a12098a117c4bd4eed7cdc22) (double rate_hz)const | Set rate to VTOL state updates.
void | [set_rate_attitude_async](#classmavsdk_1_1_telemetry_1a2f979321709760a1ad4a8dd09755cd61) (double rate_hz, const [ResultCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a166e81c6573532978e5940eafdfcec0b) callback) | Set rate to 'attitude' updates.
[Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75) | [set_rate_attitude](#classmavsdk_1_1_telemetry_1a163d3960faadad948294f367eaaf52b0) (double rate_hz)const | Set rate to 'attitude' updates.
void | [set_rate_camera_attitude_async](#classmavsdk_1_1_telemetry_1a520f15e42f5f1b3987ca2a9cd94a3d9a) (double rate_hz, const [ResultCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a166e81c6573532978e5940eafdfcec0b) callback) | Set rate of camera attitude updates.
[Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75) | [set_rate_camera_attitude](#classmavsdk_1_1_telemetry_1a427da223d16ce07a61b07d4e5af1ab04) (double rate_hz)const | Set rate of camera attitude updates.
void | [set_rate_velocity_ned_async](#classmavsdk_1_1_telemetry_1a9429ffa784fa56adee69c5017abedee4) (double rate_hz, const [ResultCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a166e81c6573532978e5940eafdfcec0b) callback) | Set rate to 'ground speed' updates (NED).
[Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75) | [set_rate_velocity_ned](#classmavsdk_1_1_telemetry_1ab5cb79fd53f27f245808a6bb9ed3225d) (double rate_hz)const | Set rate to 'ground speed' updates (NED).
void | [set_rate_gps_info_async](#classmavsdk_1_1_telemetry_1ae6ada3cd6d4e9835dd4d1d712f1195e4) (double rate_hz, const [ResultCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a166e81c6573532978e5940eafdfcec0b) callback) | Set rate to 'GPS info' updates.
[Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75) | [set_rate_gps_info](#classmavsdk_1_1_telemetry_1a14510bcb6fe3c31d91653d32d354613f) (double rate_hz)const | Set rate to 'GPS info' updates.
void | [set_rate_battery_async](#classmavsdk_1_1_telemetry_1a5615e21f616997dfca1318c96a7e550e) (double rate_hz, const [ResultCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a166e81c6573532978e5940eafdfcec0b) callback) | Set rate to 'battery' updates.
[Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75) | [set_rate_battery](#classmavsdk_1_1_telemetry_1ae781d2e950a535a465f2bc1575e9f893) (double rate_hz)const | Set rate to 'battery' updates.
void | [set_rate_rc_status_async](#classmavsdk_1_1_telemetry_1a8cf84eaca875626bc53ed03e98d6eb7e) (double rate_hz, const [ResultCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a166e81c6573532978e5940eafdfcec0b) callback) | Set rate to 'RC status' updates.
[Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75) | [set_rate_rc_status](#classmavsdk_1_1_telemetry_1acbfc54792f79c5fd2a9855278981f8ca) (double rate_hz)const | Set rate to 'RC status' updates.
void | [set_rate_actuator_control_target_async](#classmavsdk_1_1_telemetry_1aa44e3a76c482f273a2f1bc1a09bec27c) (double rate_hz, const [ResultCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a166e81c6573532978e5940eafdfcec0b) callback) | Set rate to 'actuator control target' updates.
[Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75) | [set_rate_actuator_control_target](#classmavsdk_1_1_telemetry_1aa43efb510038f1bb95241953ae09c998) (double rate_hz)const | Set rate to 'actuator control target' updates.
void | [set_rate_actuator_output_status_async](#classmavsdk_1_1_telemetry_1a2ad19c1101962ed7cfeec89b7fae0f9c) (double rate_hz, const [ResultCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a166e81c6573532978e5940eafdfcec0b) callback) | Set rate to 'actuator output status' updates.
[Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75) | [set_rate_actuator_output_status](#classmavsdk_1_1_telemetry_1a48b3e3a288ba6a8d38914c4827124006) (double rate_hz)const | Set rate to 'actuator output status' updates.
void | [set_rate_odometry_async](#classmavsdk_1_1_telemetry_1a23e507e1d53c6603479701f5e2af49ce) (double rate_hz, const [ResultCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a166e81c6573532978e5940eafdfcec0b) callback) | Set rate to 'odometry' updates.
[Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75) | [set_rate_odometry](#classmavsdk_1_1_telemetry_1a4368bf825cec3bc9369d57546a45391e) (double rate_hz)const | Set rate to 'odometry' updates.
void | [set_rate_position_velocity_ned_async](#classmavsdk_1_1_telemetry_1a9a4c3b6affa497dd22e464f515ca278c) (double rate_hz, const [ResultCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a166e81c6573532978e5940eafdfcec0b) callback) | Set rate to 'position velocity' updates.
[Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75) | [set_rate_position_velocity_ned](#classmavsdk_1_1_telemetry_1a64fe3457589cd208a9f7bd5dea763da1) (double rate_hz)const | Set rate to 'position velocity' updates.
void | [set_rate_ground_truth_async](#classmavsdk_1_1_telemetry_1a16b28ebdc6d211a5b182bd8d0abb4d2e) (double rate_hz, const [ResultCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a166e81c6573532978e5940eafdfcec0b) callback) | Set rate to 'ground truth' updates.
[Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75) | [set_rate_ground_truth](#classmavsdk_1_1_telemetry_1a23b2962e5b7681ece3fcbc72220d6b48) (double rate_hz)const | Set rate to 'ground truth' updates.
void | [set_rate_fixedwing_metrics_async](#classmavsdk_1_1_telemetry_1a1484ccdcf4ba20a151e380e7bd7b9869) (double rate_hz, const [ResultCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a166e81c6573532978e5940eafdfcec0b) callback) | Set rate to 'fixedwing metrics' updates.
[Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75) | [set_rate_fixedwing_metrics](#classmavsdk_1_1_telemetry_1ab345a5925d132c27e0a5e1ab65a1e2c1) (double rate_hz)const | Set rate to 'fixedwing metrics' updates.
void | [set_rate_imu_async](#classmavsdk_1_1_telemetry_1a7dca435daa0de2db2d2e9d588c6bed99) (double rate_hz, const [ResultCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a166e81c6573532978e5940eafdfcec0b) callback) | Set rate to 'IMU' updates.
[Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75) | [set_rate_imu](#classmavsdk_1_1_telemetry_1a4e0d1dc2350e06f68f472d85dc69d175) (double rate_hz)const | Set rate to 'IMU' updates.
void | [set_rate_scaled_imu_async](#classmavsdk_1_1_telemetry_1aebbf2eb2e5d117d8b40f21075845467c) (double rate_hz, const [ResultCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a166e81c6573532978e5940eafdfcec0b) callback) | Set rate to 'Scaled IMU' updates.
[Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75) | [set_rate_scaled_imu](#classmavsdk_1_1_telemetry_1af8dc4f38bf7cc89f700c985a04e03237) (double rate_hz)const | Set rate to 'Scaled IMU' updates.
void | [set_rate_raw_imu_async](#classmavsdk_1_1_telemetry_1a36d19058a0f71d711de3e50ba718704e) (double rate_hz, const [ResultCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a166e81c6573532978e5940eafdfcec0b) callback) | Set rate to 'Raw IMU' updates.
[Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75) | [set_rate_raw_imu](#classmavsdk_1_1_telemetry_1a020cb8760e6f00b759c8ef564d8801ad) (double rate_hz)const | Set rate to 'Raw IMU' updates.
void | [set_rate_unix_epoch_time_async](#classmavsdk_1_1_telemetry_1a74b18cd8a5faed4d46b244db0a6e3c50) (double rate_hz, const [ResultCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a166e81c6573532978e5940eafdfcec0b) callback) | Set rate to 'unix epoch time' updates.
[Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75) | [set_rate_unix_epoch_time](#classmavsdk_1_1_telemetry_1a340ac34547672ee07131bca34cbbb820) (double rate_hz)const | Set rate to 'unix epoch time' updates.
void | [set_rate_distance_sensor_async](#classmavsdk_1_1_telemetry_1a0371c470866b539b3aa1e254c974aa43) (double rate_hz, const [ResultCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a166e81c6573532978e5940eafdfcec0b) callback) | Set rate to 'Distance Sensor' updates.
[Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75) | [set_rate_distance_sensor](#classmavsdk_1_1_telemetry_1a7f536359536478691d7db980ffe49e49) (double rate_hz)const | Set rate to 'Distance Sensor' updates.
void | [get_gps_global_origin_async](#classmavsdk_1_1_telemetry_1a60cca43e2f87e3fd3a9e170ff2b64e0a) (const [GetGpsGlobalOriginCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a350ee89a7e30a691e130e29ace8917ef) callback) | Get the GPS location of where the estimator has been initialized.
std::pair< [Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75), [Telemetry::GpsGlobalOrigin](structmavsdk_1_1_telemetry_1_1_gps_global_origin.md) > | [get_gps_global_origin](#classmavsdk_1_1_telemetry_1a341b90234b30a27bb25670a31303e0cd) () const | Get the GPS location of where the estimator has been initialized.
const [Telemetry](classmavsdk_1_1_telemetry.md) & | [operator=](#classmavsdk_1_1_telemetry_1ae606a3e3814c773a12035c2674a00c5c) (const [Telemetry](classmavsdk_1_1_telemetry.md) &)=delete | Equality operator (object is not copyable).


## Constructor & Destructor Documentation


### Telemetry() {#classmavsdk_1_1_telemetry_1a6c8c8ed8759fc8c6e9fd4e7644c63cbe}
```cpp
mavsdk::Telemetry::Telemetry(System &system)
```


Constructor. Creates the plugin for a specific [System](classmavsdk_1_1_system.md).

The plugin is typically created as shown below: 

```cpp
auto telemetry = Telemetry(system);
```

**Parameters**

* [System](classmavsdk_1_1_system.md)& **system** - The specific system associated with this plugin.

### Telemetry() {#classmavsdk_1_1_telemetry_1af78f18fbb117c82d5ffe21e015535067}
```cpp
mavsdk::Telemetry::Telemetry(std::shared_ptr< System > system)
```


Constructor. Creates the plugin for a specific [System](classmavsdk_1_1_system.md).

The plugin is typically created as shown below: 

```cpp
auto telemetry = Telemetry(system);
```

**Parameters**

* std::shared_ptr< [System](classmavsdk_1_1_system.md) > **system** - The specific system associated with this plugin.

### ~Telemetry() {#classmavsdk_1_1_telemetry_1a1db31974e0ea6ea9a530d68783566ab1}
```cpp
mavsdk::Telemetry::~Telemetry()
```


Destructor (internal use only).


### Telemetry() {#classmavsdk_1_1_telemetry_1ad734f199b82a9928c63230676c9789e9}
```cpp
mavsdk::Telemetry::Telemetry(const Telemetry &other)
```


Copy constructor.


**Parameters**

* const [Telemetry](classmavsdk_1_1_telemetry.md)& **other** - 

## Member Typdef Documentation


### typedef ResultCallback {#classmavsdk_1_1_telemetry_1a166e81c6573532978e5940eafdfcec0b}

```cpp
using mavsdk::Telemetry::ResultCallback =  std::function<void(Result)>
```


Callback type for asynchronous [Telemetry](classmavsdk_1_1_telemetry.md) calls.


### typedef PositionCallback {#classmavsdk_1_1_telemetry_1a978b371d636226e198995462afa63552}

```cpp
using mavsdk::Telemetry::PositionCallback =  std::function<void(Position)>
```


Callback type for subscribe_position.


### typedef HomeCallback {#classmavsdk_1_1_telemetry_1aaac029969c37a001d43e2788a6abf634}

```cpp
using mavsdk::Telemetry::HomeCallback =  std::function<void(Position)>
```


Callback type for subscribe_home.


### typedef InAirCallback {#classmavsdk_1_1_telemetry_1af96cca452305dd8f51b42d4663f15a26}

```cpp
using mavsdk::Telemetry::InAirCallback =  std::function<void(bool)>
```


Callback type for subscribe_in_air.


### typedef LandedStateCallback {#classmavsdk_1_1_telemetry_1a0cd8ef17abdd7c3d6a9ee761ccc6ae5e}

```cpp
using mavsdk::Telemetry::LandedStateCallback =  std::function<void(LandedState)>
```


Callback type for subscribe_landed_state.


### typedef ArmedCallback {#classmavsdk_1_1_telemetry_1a9d23a4092d94e50694390e9f41b8c419}

```cpp
using mavsdk::Telemetry::ArmedCallback =  std::function<void(bool)>
```


Callback type for subscribe_armed.


### typedef VtolStateCallback {#classmavsdk_1_1_telemetry_1abf52126ce4d4efb99560aa8e8e58f20c}

```cpp
using mavsdk::Telemetry::VtolStateCallback =  std::function<void(VtolState)>
```


Callback type for subscribe_vtol_state.


### typedef AttitudeQuaternionCallback {#classmavsdk_1_1_telemetry_1ad16e61245511a99e930d6fdcbd761a30}

```cpp
using mavsdk::Telemetry::AttitudeQuaternionCallback =  std::function<void(Quaternion)>
```


Callback type for subscribe_attitude_quaternion.


### typedef AttitudeEulerCallback {#classmavsdk_1_1_telemetry_1a321c7607922369926fbd5f2821986cba}

```cpp
using mavsdk::Telemetry::AttitudeEulerCallback =  std::function<void(EulerAngle)>
```


Callback type for subscribe_attitude_euler.


### typedef AttitudeAngularVelocityBodyCallback {#classmavsdk_1_1_telemetry_1a35ff8def3048faeab7f732153d51085f}

```cpp
using mavsdk::Telemetry::AttitudeAngularVelocityBodyCallback =  std::function<void(AngularVelocityBody)>
```


Callback type for subscribe_attitude_angular_velocity_body.


### typedef CameraAttitudeQuaternionCallback {#classmavsdk_1_1_telemetry_1aa83dafa14e9b5179573a574f6fbdd973}

```cpp
using mavsdk::Telemetry::CameraAttitudeQuaternionCallback =  std::function<void(Quaternion)>
```


Callback type for subscribe_camera_attitude_quaternion.


### typedef CameraAttitudeEulerCallback {#classmavsdk_1_1_telemetry_1aa29f9bb0767ba8c384bfe1df69f2fdd9}

```cpp
using mavsdk::Telemetry::CameraAttitudeEulerCallback =  std::function<void(EulerAngle)>
```


Callback type for subscribe_camera_attitude_euler.


### typedef VelocityNedCallback {#classmavsdk_1_1_telemetry_1ab5859d2f6a9c9bd81282166b3de92342}

```cpp
using mavsdk::Telemetry::VelocityNedCallback =  std::function<void(VelocityNed)>
```


Callback type for subscribe_velocity_ned.


### typedef GpsInfoCallback {#classmavsdk_1_1_telemetry_1ad8fa90886b2283eace09b4b46708048b}

```cpp
using mavsdk::Telemetry::GpsInfoCallback =  std::function<void(GpsInfo)>
```


Callback type for subscribe_gps_info.


### typedef RawGpsCallback {#classmavsdk_1_1_telemetry_1a915868d562ed445fa30beaa9140ea97c}

```cpp
using mavsdk::Telemetry::RawGpsCallback =  std::function<void(RawGps)>
```


Callback type for subscribe_raw_gps.


### typedef BatteryCallback {#classmavsdk_1_1_telemetry_1af4b121c576ef2ae567b1d571b12dff9d}

```cpp
using mavsdk::Telemetry::BatteryCallback =  std::function<void(Battery)>
```


Callback type for subscribe_battery.


### typedef FlightModeCallback {#classmavsdk_1_1_telemetry_1a2d7318d0823771b7a586c40199bdb482}

```cpp
using mavsdk::Telemetry::FlightModeCallback =  std::function<void(FlightMode)>
```


Callback type for subscribe_flight_mode.


### typedef HealthCallback {#classmavsdk_1_1_telemetry_1a7a120dd053091c644e0e2e47fdcbeb75}

```cpp
using mavsdk::Telemetry::HealthCallback =  std::function<void(Health)>
```


Callback type for subscribe_health.


### typedef RcStatusCallback {#classmavsdk_1_1_telemetry_1aafcd706b805898301b574ffa2b909b85}

```cpp
using mavsdk::Telemetry::RcStatusCallback =  std::function<void(RcStatus)>
```


Callback type for subscribe_rc_status.


### typedef StatusTextCallback {#classmavsdk_1_1_telemetry_1a46e51ff90fe779990ed09a593c1c7898}

```cpp
using mavsdk::Telemetry::StatusTextCallback =  std::function<void(StatusText)>
```


Callback type for subscribe_status_text.


### typedef ActuatorControlTargetCallback {#classmavsdk_1_1_telemetry_1ada6af3de1b60b93a709345c3a8ede551}

```cpp
using mavsdk::Telemetry::ActuatorControlTargetCallback =  std::function<void(ActuatorControlTarget)>
```


Callback type for subscribe_actuator_control_target.


### typedef ActuatorOutputStatusCallback {#classmavsdk_1_1_telemetry_1a2b1e800ce1ba6fb776351416340ac8b9}

```cpp
using mavsdk::Telemetry::ActuatorOutputStatusCallback =  std::function<void(ActuatorOutputStatus)>
```


Callback type for subscribe_actuator_output_status.


### typedef OdometryCallback {#classmavsdk_1_1_telemetry_1a8cd23f7364f8f5cb22869155da67c65d}

```cpp
using mavsdk::Telemetry::OdometryCallback =  std::function<void(Odometry)>
```


Callback type for subscribe_odometry.


### typedef PositionVelocityNedCallback {#classmavsdk_1_1_telemetry_1a5a38deb284622ff6926703e1e5c96a74}

```cpp
using mavsdk::Telemetry::PositionVelocityNedCallback =  std::function<void(PositionVelocityNed)>
```


Callback type for subscribe_position_velocity_ned.


### typedef GroundTruthCallback {#classmavsdk_1_1_telemetry_1a222aae53852a2c535f6d69ed57221f13}

```cpp
using mavsdk::Telemetry::GroundTruthCallback =  std::function<void(GroundTruth)>
```


Callback type for subscribe_ground_truth.


### typedef FixedwingMetricsCallback {#classmavsdk_1_1_telemetry_1a5b42dbef0ef6d8c1768d503d0437f1e3}

```cpp
using mavsdk::Telemetry::FixedwingMetricsCallback =  std::function<void(FixedwingMetrics)>
```


Callback type for subscribe_fixedwing_metrics.


### typedef ImuCallback {#classmavsdk_1_1_telemetry_1a4fbc2ad274fd5a8af077004d2d7bd984}

```cpp
using mavsdk::Telemetry::ImuCallback =  std::function<void(Imu)>
```


Callback type for subscribe_imu.


### typedef ScaledImuCallback {#classmavsdk_1_1_telemetry_1a26159a775adcfbc42302234b7108d94f}

```cpp
using mavsdk::Telemetry::ScaledImuCallback =  std::function<void(Imu)>
```


Callback type for subscribe_scaled_imu.


### typedef RawImuCallback {#classmavsdk_1_1_telemetry_1a92711da85d343cb58b73561e6b730c76}

```cpp
using mavsdk::Telemetry::RawImuCallback =  std::function<void(Imu)>
```


Callback type for subscribe_raw_imu.


### typedef HealthAllOkCallback {#classmavsdk_1_1_telemetry_1a71cdcadfaa988dc14029e0b9fdbe742d}

```cpp
using mavsdk::Telemetry::HealthAllOkCallback =  std::function<void(bool)>
```


Callback type for subscribe_health_all_ok.


### typedef UnixEpochTimeCallback {#classmavsdk_1_1_telemetry_1a321c7d809ae8f56bb8a361d5e5ce6391}

```cpp
using mavsdk::Telemetry::UnixEpochTimeCallback =  std::function<void(uint64_t)>
```


Callback type for subscribe_unix_epoch_time.


### typedef DistanceSensorCallback {#classmavsdk_1_1_telemetry_1aacfdb5e2cce7f3f77c68b36f020ed1f2}

```cpp
using mavsdk::Telemetry::DistanceSensorCallback =  std::function<void(DistanceSensor)>
```


Callback type for subscribe_distance_sensor.


### typedef ScaledPressureCallback {#classmavsdk_1_1_telemetry_1ac123edc254bb1874edc08a0f531f82b1}

```cpp
using mavsdk::Telemetry::ScaledPressureCallback =  std::function<void(ScaledPressure)>
```


Callback type for subscribe_scaled_pressure.


### typedef HeadingCallback {#classmavsdk_1_1_telemetry_1aa3bca0adab525a4c733c1e7f5c5dd8b3}

```cpp
using mavsdk::Telemetry::HeadingCallback =  std::function<void(Heading)>
```


Callback type for subscribe_heading.


### typedef GetGpsGlobalOriginCallback {#classmavsdk_1_1_telemetry_1a350ee89a7e30a691e130e29ace8917ef}

```cpp
using mavsdk::Telemetry::GetGpsGlobalOriginCallback =  std::function<void(Result, GpsGlobalOrigin)>
```


Callback type for get_gps_global_origin_async.


## Member Enumeration Documentation


### enum FixType {#classmavsdk_1_1_telemetry_1a548213e1b26615d7b6d1b0b3934639de}


GPS fix type.


Value | Description
--- | ---
<span id="classmavsdk_1_1_telemetry_1a548213e1b26615d7b6d1b0b3934639deaeb42b0f27d1fc2ca9bd645212a14c874"></span> `NoGps` | No GPS connected. 
<span id="classmavsdk_1_1_telemetry_1a548213e1b26615d7b6d1b0b3934639dea7458f6cf09e53df9495d3ee0d11868c4"></span> `NoFix` | No position information, GPS is connected. 
<span id="classmavsdk_1_1_telemetry_1a548213e1b26615d7b6d1b0b3934639dead6800eded02a7eaceb638929dbd9ea55"></span> `Fix2D` | 2D position. 
<span id="classmavsdk_1_1_telemetry_1a548213e1b26615d7b6d1b0b3934639dead791aa90d108c9b0c76ec28cd4dfbb0f"></span> `Fix3D` | 3D position. 
<span id="classmavsdk_1_1_telemetry_1a548213e1b26615d7b6d1b0b3934639dea8372860807abaec59412bd6376f51b5f"></span> `FixDgps` | DGPS/SBAS aided 3D position. 
<span id="classmavsdk_1_1_telemetry_1a548213e1b26615d7b6d1b0b3934639dea1eacb557d24c49af2ec6832c5fc32413"></span> `RtkFloat` | RTK float, 3D position. 
<span id="classmavsdk_1_1_telemetry_1a548213e1b26615d7b6d1b0b3934639dea9effa0afed44833d540fec2c57e67426"></span> `RtkFixed` | RTK Fixed, 3D position. 

### enum FlightMode {#classmavsdk_1_1_telemetry_1a8317d953a82a23654db6f14509acb4fe}


Flight modes.

For more information about flight modes, check out [https://docs.px4.io/master/en/config/flight_mode.html](https://docs.px4.io/master/en/config/flight_mode.html).

Value | Description
--- | ---
<span id="classmavsdk_1_1_telemetry_1a8317d953a82a23654db6f14509acb4fea88183b946cc5f0e8c96b2e66e1c74a7e"></span> `Unknown` | Mode not known. 
<span id="classmavsdk_1_1_telemetry_1a8317d953a82a23654db6f14509acb4feae7d31fc0602fb2ede144d18cdffd816b"></span> `Ready` | Armed and ready to take off. 
<span id="classmavsdk_1_1_telemetry_1a8317d953a82a23654db6f14509acb4fea56373a80447c41b9a29e500e62d6884e"></span> `Takeoff` | Taking off. 
<span id="classmavsdk_1_1_telemetry_1a8317d953a82a23654db6f14509acb4feabcd8db575b47c838e5d551e3973db4ac"></span> `Hold` | Holding (hovering in place (or circling for fixed-wing vehicles). 
<span id="classmavsdk_1_1_telemetry_1a8317d953a82a23654db6f14509acb4fea70d529695c253d17e992cb9265abc57f"></span> `Mission` | In mission. 
<span id="classmavsdk_1_1_telemetry_1a8317d953a82a23654db6f14509acb4fea146115c3278581584dcbaac1a77a2588"></span> `ReturnToLaunch` | Returning to launch position (then landing). 
<span id="classmavsdk_1_1_telemetry_1a8317d953a82a23654db6f14509acb4fea512ef7c688a2c8572d5e16f44e17e869"></span> `Land` | Landing. 
<span id="classmavsdk_1_1_telemetry_1a8317d953a82a23654db6f14509acb4feabb085f1e0d3843dda2a4c70437ad1410"></span> `Offboard` | In 'offboard' mode. 
<span id="classmavsdk_1_1_telemetry_1a8317d953a82a23654db6f14509acb4fea08bb3de7dafcf47f05b8c5a9dc0983c0"></span> `FollowMe` | In 'follow-me' mode. 
<span id="classmavsdk_1_1_telemetry_1a8317d953a82a23654db6f14509acb4feae1ba155a9f2e8c3be94020eef32a0301"></span> `Manual` | In 'Manual' mode. 
<span id="classmavsdk_1_1_telemetry_1a8317d953a82a23654db6f14509acb4feaa7a697581399b9be37a545416d4cd2d9"></span> `Altctl` | In 'Altitude Control' mode. 
<span id="classmavsdk_1_1_telemetry_1a8317d953a82a23654db6f14509acb4fea46780e4f8c113481c868da4dd16fcd41"></span> `Posctl` | In '[Position](structmavsdk_1_1_telemetry_1_1_position.md) Control' mode. 
<span id="classmavsdk_1_1_telemetry_1a8317d953a82a23654db6f14509acb4feae10e0f017fee32a9bb2fa9fae53afd70"></span> `Acro` | In 'Acro' mode. 
<span id="classmavsdk_1_1_telemetry_1a8317d953a82a23654db6f14509acb4feafda22026db89cdc5e88b262ad9424b41"></span> `Stabilized` | In 'Stabilize' mode. 
<span id="classmavsdk_1_1_telemetry_1a8317d953a82a23654db6f14509acb4fea1e0c225e976316373c8c08ddc7a154fa"></span> `Rattitude` | In 'Rattitude' mode. 

### enum StatusTextType {#classmavsdk_1_1_telemetry_1ada3ebb336abad223a98bc2a625e0e7d8}


Status types.


Value | Description
--- | ---
<span id="classmavsdk_1_1_telemetry_1ada3ebb336abad223a98bc2a625e0e7d8aa603905470e2a5b8c13e96b579ef0dba"></span> `Debug` | Debug. 
<span id="classmavsdk_1_1_telemetry_1ada3ebb336abad223a98bc2a625e0e7d8a4059b0251f66a18cb56f544728796875"></span> `Info` | Information. 
<span id="classmavsdk_1_1_telemetry_1ada3ebb336abad223a98bc2a625e0e7d8a24efa7ee4511563b16144f39706d594f"></span> `Notice` | Notice. 
<span id="classmavsdk_1_1_telemetry_1ada3ebb336abad223a98bc2a625e0e7d8a0eaadb4fcb48a0a0ed7bc9868be9fbaa"></span> `Warning` | Warning. 
<span id="classmavsdk_1_1_telemetry_1ada3ebb336abad223a98bc2a625e0e7d8a902b0d55fddef6f8d651fe1035b7d4bd"></span> `Error` | Error. 
<span id="classmavsdk_1_1_telemetry_1ada3ebb336abad223a98bc2a625e0e7d8a278d01e5af56273bae1bb99a98b370cd"></span> `Critical` | Critical. 
<span id="classmavsdk_1_1_telemetry_1ada3ebb336abad223a98bc2a625e0e7d8ab92071d61c88498171928745ca53078b"></span> `Alert` | Alert. 
<span id="classmavsdk_1_1_telemetry_1ada3ebb336abad223a98bc2a625e0e7d8aa3fa706f20bc0b7858b7ae6932261940"></span> `Emergency` | Emergency. 

### enum LandedState {#classmavsdk_1_1_telemetry_1ac6639935bc3b35b1da553cde41e8f046}


Landed State enumeration.


Value | Description
--- | ---
<span id="classmavsdk_1_1_telemetry_1ac6639935bc3b35b1da553cde41e8f046a88183b946cc5f0e8c96b2e66e1c74a7e"></span> `Unknown` | Landed state is unknown. 
<span id="classmavsdk_1_1_telemetry_1ac6639935bc3b35b1da553cde41e8f046a2b9beed57034f5727573d7ded76cf777"></span> `OnGround` | The vehicle is on the ground. 
<span id="classmavsdk_1_1_telemetry_1ac6639935bc3b35b1da553cde41e8f046aee4e669a07b061d70b9b79dfed9cb5e7"></span> `InAir` | The vehicle is in the air. 
<span id="classmavsdk_1_1_telemetry_1ac6639935bc3b35b1da553cde41e8f046a85916c5f3400cfa25d988f05b6736a94"></span> `TakingOff` | The vehicle is taking off. 
<span id="classmavsdk_1_1_telemetry_1ac6639935bc3b35b1da553cde41e8f046a41bd61e268fedccfb0d91dd571dd28b2"></span> `Landing` | The vehicle is landing. 

### enum VtolState {#classmavsdk_1_1_telemetry_1a256f951d993aa120c437d989a6e94166}


VTOL State enumeration.


Value | Description
--- | ---
<span id="classmavsdk_1_1_telemetry_1a256f951d993aa120c437d989a6e94166aec0fc0100c4fc1ce4eea230c3dc10360"></span> `Undefined` | MAV is not configured as VTOL. 
<span id="classmavsdk_1_1_telemetry_1a256f951d993aa120c437d989a6e94166a45f439a04f9144adc1dcf5a4fbda0026"></span> `TransitionToFw` | VTOL is in transition from multicopter to fixed-wing. 
<span id="classmavsdk_1_1_telemetry_1a256f951d993aa120c437d989a6e94166af3abadebd9602a0acb33350f64fa7661"></span> `TransitionToMc` | VTOL is in transition from fixed-wing to multicopter. 
<span id="classmavsdk_1_1_telemetry_1a256f951d993aa120c437d989a6e94166aac81adaad0b2a7d6077edd5c319a6048"></span> `Mc` | VTOL is in multicopter state. 
<span id="classmavsdk_1_1_telemetry_1a256f951d993aa120c437d989a6e94166a9b5de99abdffa3a42bd6517ed1a034e4"></span> `Fw` | VTOL is in fixed-wing state. 

### enum Result {#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75}


Possible results returned for telemetry requests.


Value | Description
--- | ---
<span id="classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75a88183b946cc5f0e8c96b2e66e1c74a7e"></span> `Unknown` | Unknown result. 
<span id="classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75a505a83f220c02df2f85c3810cd9ceb38"></span> `Success` | Success: the telemetry command was accepted by the vehicle. 
<span id="classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75a1119faf72ba0dfb23aeea644fed960ad"></span> `NoSystem` | No system connected. 
<span id="classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75a094a6f6b0868122a9dd008cb91c083e4"></span> `ConnectionError` | Connection error. 
<span id="classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75ad8a942ef2b04672adfafef0ad817a407"></span> `Busy` | Vehicle is busy. 
<span id="classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75a3398e12855176d55f43d53e04f472c8a"></span> `CommandDenied` | Command refused by vehicle. 
<span id="classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75ac85a251cc457840f1e032f1b733e9398"></span> `Timeout` | Request timed out. 
<span id="classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75ab4080bdf74febf04d578ff105cce9d3f"></span> `Unsupported` | Request not supported. 

## Member Function Documentation


### subscribe_position() {#classmavsdk_1_1_telemetry_1a61bda57b3ca47000ea7e4758b2a33134}
```cpp
void mavsdk::Telemetry::subscribe_position(PositionCallback callback)
```


Subscribe to 'position' updates.


**Parameters**

* [PositionCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a978b371d636226e198995462afa63552) **callback** - 

### position() {#classmavsdk_1_1_telemetry_1a2299da1bc63313c429f07ab0fdbe5335}
```cpp
Position mavsdk::Telemetry::position() const
```


Poll for '[Position](structmavsdk_1_1_telemetry_1_1_position.md)' (blocking).


**Returns**

&emsp;[Position](structmavsdk_1_1_telemetry_1_1_position.md) - One [Position](structmavsdk_1_1_telemetry_1_1_position.md) update.

### subscribe_home() {#classmavsdk_1_1_telemetry_1a67585989a12de2f099dbc4eb4c41686a}
```cpp
void mavsdk::Telemetry::subscribe_home(HomeCallback callback)
```


Subscribe to 'home position' updates.


**Parameters**

* [HomeCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1aaac029969c37a001d43e2788a6abf634) **callback** - 

### home() {#classmavsdk_1_1_telemetry_1ad5c239b93aa1923edd1b97494a3fbfe7}
```cpp
Position mavsdk::Telemetry::home() const
```


Poll for '[Position](structmavsdk_1_1_telemetry_1_1_position.md)' (blocking).


**Returns**

&emsp;[Position](structmavsdk_1_1_telemetry_1_1_position.md) - One [Position](structmavsdk_1_1_telemetry_1_1_position.md) update.

### subscribe_in_air() {#classmavsdk_1_1_telemetry_1a5ba005827b1ef988ba3f6e81f7469d40}
```cpp
void mavsdk::Telemetry::subscribe_in_air(InAirCallback callback)
```


Subscribe to in-air updates.


**Parameters**

* [InAirCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1af96cca452305dd8f51b42d4663f15a26) **callback** - 

### in_air() {#classmavsdk_1_1_telemetry_1a909738ff2fbe104c6eb4524cc9bf2dd5}
```cpp
bool mavsdk::Telemetry::in_air() const
```


Poll for 'bool' (blocking).


**Returns**

&emsp;bool - One bool update.

### subscribe_landed_state() {#classmavsdk_1_1_telemetry_1a8eb2d40764b3940e9054c301a6ef5f50}
```cpp
void mavsdk::Telemetry::subscribe_landed_state(LandedStateCallback callback)
```


Subscribe to landed state updates.


**Parameters**

* [LandedStateCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a0cd8ef17abdd7c3d6a9ee761ccc6ae5e) **callback** - 

### landed_state() {#classmavsdk_1_1_telemetry_1af7d7c385852db38d6320516508ce7465}
```cpp
LandedState mavsdk::Telemetry::landed_state() const
```


Poll for 'LandedState' (blocking).


**Returns**

&emsp;[LandedState](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1ac6639935bc3b35b1da553cde41e8f046) - One LandedState update.

### subscribe_armed() {#classmavsdk_1_1_telemetry_1a6bada4a3538eb1142fca024bc89ec2d3}
```cpp
void mavsdk::Telemetry::subscribe_armed(ArmedCallback callback)
```


Subscribe to armed updates.


**Parameters**

* [ArmedCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a9d23a4092d94e50694390e9f41b8c419) **callback** - 

### armed() {#classmavsdk_1_1_telemetry_1a6620142adc47f069262e5bf69dbb3876}
```cpp
bool mavsdk::Telemetry::armed() const
```


Poll for 'bool' (blocking).


**Returns**

&emsp;bool - One bool update.

### subscribe_vtol_state() {#classmavsdk_1_1_telemetry_1a0ce11e7983ee7ae8693ad8835d70f4f4}
```cpp
void mavsdk::Telemetry::subscribe_vtol_state(VtolStateCallback callback)
```


subscribe to vtol state Updates


**Parameters**

* [VtolStateCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1abf52126ce4d4efb99560aa8e8e58f20c) **callback** - 

### vtol_state() {#classmavsdk_1_1_telemetry_1a6d3fd68f3e639a2bf9940e9f38f220c3}
```cpp
VtolState mavsdk::Telemetry::vtol_state() const
```


Poll for 'VtolState' (blocking).


**Returns**

&emsp;[VtolState](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a256f951d993aa120c437d989a6e94166) - One VtolState update.

### subscribe_attitude_quaternion() {#classmavsdk_1_1_telemetry_1afa6c079d48bc0c0a3287ac095ec290b9}
```cpp
void mavsdk::Telemetry::subscribe_attitude_quaternion(AttitudeQuaternionCallback callback)
```


Subscribe to 'attitude' updates (quaternion).


**Parameters**

* [AttitudeQuaternionCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1ad16e61245511a99e930d6fdcbd761a30) **callback** - 

### attitude_quaternion() {#classmavsdk_1_1_telemetry_1aae76890957b33727be72a39807448c88}
```cpp
Quaternion mavsdk::Telemetry::attitude_quaternion() const
```


Poll for '[Quaternion](structmavsdk_1_1_telemetry_1_1_quaternion.md)' (blocking).


**Returns**

&emsp;[Quaternion](structmavsdk_1_1_telemetry_1_1_quaternion.md) - One [Quaternion](structmavsdk_1_1_telemetry_1_1_quaternion.md) update.

### subscribe_attitude_euler() {#classmavsdk_1_1_telemetry_1ae380f3c65fb5f4d3961101b71ebbd1aa}
```cpp
void mavsdk::Telemetry::subscribe_attitude_euler(AttitudeEulerCallback callback)
```


Subscribe to 'attitude' updates (Euler).


**Parameters**

* [AttitudeEulerCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a321c7607922369926fbd5f2821986cba) **callback** - 

### attitude_euler() {#classmavsdk_1_1_telemetry_1a03035bb72324e843372eb69cf7899ce5}
```cpp
EulerAngle mavsdk::Telemetry::attitude_euler() const
```


Poll for '[EulerAngle](structmavsdk_1_1_telemetry_1_1_euler_angle.md)' (blocking).


**Returns**

&emsp;[EulerAngle](structmavsdk_1_1_telemetry_1_1_euler_angle.md) - One [EulerAngle](structmavsdk_1_1_telemetry_1_1_euler_angle.md) update.

### subscribe_attitude_angular_velocity_body() {#classmavsdk_1_1_telemetry_1a84be21f00d23911ee77cbd7dc6512420}
```cpp
void mavsdk::Telemetry::subscribe_attitude_angular_velocity_body(AttitudeAngularVelocityBodyCallback callback)
```


Subscribe to 'attitude' updates (angular velocity)


**Parameters**

* [AttitudeAngularVelocityBodyCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a35ff8def3048faeab7f732153d51085f) **callback** - 

### attitude_angular_velocity_body() {#classmavsdk_1_1_telemetry_1a8d9e2489b79c2cdbabaef8b6bb8e2952}
```cpp
AngularVelocityBody mavsdk::Telemetry::attitude_angular_velocity_body() const
```


Poll for '[AngularVelocityBody](structmavsdk_1_1_telemetry_1_1_angular_velocity_body.md)' (blocking).


**Returns**

&emsp;[AngularVelocityBody](structmavsdk_1_1_telemetry_1_1_angular_velocity_body.md) - One [AngularVelocityBody](structmavsdk_1_1_telemetry_1_1_angular_velocity_body.md) update.

### subscribe_camera_attitude_quaternion() {#classmavsdk_1_1_telemetry_1a6845e2752b535e0ee539f276cfca45d9}
```cpp
void mavsdk::Telemetry::subscribe_camera_attitude_quaternion(CameraAttitudeQuaternionCallback callback)
```


Subscribe to 'camera attitude' updates (quaternion).


**Parameters**

* [CameraAttitudeQuaternionCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1aa83dafa14e9b5179573a574f6fbdd973) **callback** - 

### camera_attitude_quaternion() {#classmavsdk_1_1_telemetry_1a3c07447351d3b6195d5e2526e7b128b3}
```cpp
Quaternion mavsdk::Telemetry::camera_attitude_quaternion() const
```


Poll for '[Quaternion](structmavsdk_1_1_telemetry_1_1_quaternion.md)' (blocking).


**Returns**

&emsp;[Quaternion](structmavsdk_1_1_telemetry_1_1_quaternion.md) - One [Quaternion](structmavsdk_1_1_telemetry_1_1_quaternion.md) update.

### subscribe_camera_attitude_euler() {#classmavsdk_1_1_telemetry_1afaa61016a5319ebea73dc5b1e4cde89c}
```cpp
void mavsdk::Telemetry::subscribe_camera_attitude_euler(CameraAttitudeEulerCallback callback)
```


Subscribe to 'camera attitude' updates (Euler).


**Parameters**

* [CameraAttitudeEulerCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1aa29f9bb0767ba8c384bfe1df69f2fdd9) **callback** - 

### camera_attitude_euler() {#classmavsdk_1_1_telemetry_1a635643d955f0cd9a805914501f819796}
```cpp
EulerAngle mavsdk::Telemetry::camera_attitude_euler() const
```


Poll for '[EulerAngle](structmavsdk_1_1_telemetry_1_1_euler_angle.md)' (blocking).


**Returns**

&emsp;[EulerAngle](structmavsdk_1_1_telemetry_1_1_euler_angle.md) - One [EulerAngle](structmavsdk_1_1_telemetry_1_1_euler_angle.md) update.

### subscribe_velocity_ned() {#classmavsdk_1_1_telemetry_1a0bcbf7a51643c8ca4a93dabd0f4364b5}
```cpp
void mavsdk::Telemetry::subscribe_velocity_ned(VelocityNedCallback callback)
```


Subscribe to 'ground speed' updates (NED).


**Parameters**

* [VelocityNedCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1ab5859d2f6a9c9bd81282166b3de92342) **callback** - 

### velocity_ned() {#classmavsdk_1_1_telemetry_1a40a86062c0322d6be7c86d8e15a52f28}
```cpp
VelocityNed mavsdk::Telemetry::velocity_ned() const
```


Poll for '[VelocityNed](structmavsdk_1_1_telemetry_1_1_velocity_ned.md)' (blocking).


**Returns**

&emsp;[VelocityNed](structmavsdk_1_1_telemetry_1_1_velocity_ned.md) - One [VelocityNed](structmavsdk_1_1_telemetry_1_1_velocity_ned.md) update.

### subscribe_gps_info() {#classmavsdk_1_1_telemetry_1aa078035ce00505b726dcac4d47796cee}
```cpp
void mavsdk::Telemetry::subscribe_gps_info(GpsInfoCallback callback)
```


Subscribe to 'GPS info' updates.


**Parameters**

* [GpsInfoCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1ad8fa90886b2283eace09b4b46708048b) **callback** - 

### gps_info() {#classmavsdk_1_1_telemetry_1a983dabc1aed50745b326072662c419e8}
```cpp
GpsInfo mavsdk::Telemetry::gps_info() const
```


Poll for '[GpsInfo](structmavsdk_1_1_telemetry_1_1_gps_info.md)' (blocking).


**Returns**

&emsp;[GpsInfo](structmavsdk_1_1_telemetry_1_1_gps_info.md) - One [GpsInfo](structmavsdk_1_1_telemetry_1_1_gps_info.md) update.

### subscribe_raw_gps() {#classmavsdk_1_1_telemetry_1a7632511f881113f6ecc721c22a17785d}
```cpp
void mavsdk::Telemetry::subscribe_raw_gps(RawGpsCallback callback)
```


Subscribe to 'Raw GPS' updates.


**Parameters**

* [RawGpsCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a915868d562ed445fa30beaa9140ea97c) **callback** - 

### raw_gps() {#classmavsdk_1_1_telemetry_1ac43c29e435b6c1a6594854adc6a1bf6c}
```cpp
RawGps mavsdk::Telemetry::raw_gps() const
```


Poll for '[RawGps](structmavsdk_1_1_telemetry_1_1_raw_gps.md)' (blocking).


**Returns**

&emsp;[RawGps](structmavsdk_1_1_telemetry_1_1_raw_gps.md) - One [RawGps](structmavsdk_1_1_telemetry_1_1_raw_gps.md) update.

### subscribe_battery() {#classmavsdk_1_1_telemetry_1a9a8c5288273b4a6f1e43377a70f47a0e}
```cpp
void mavsdk::Telemetry::subscribe_battery(BatteryCallback callback)
```


Subscribe to 'battery' updates.


**Parameters**

* [BatteryCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1af4b121c576ef2ae567b1d571b12dff9d) **callback** - 

### battery() {#classmavsdk_1_1_telemetry_1afb3bad3c7a36c14ae97492df3f6bbd54}
```cpp
Battery mavsdk::Telemetry::battery() const
```


Poll for '[Battery](structmavsdk_1_1_telemetry_1_1_battery.md)' (blocking).


**Returns**

&emsp;[Battery](structmavsdk_1_1_telemetry_1_1_battery.md) - One [Battery](structmavsdk_1_1_telemetry_1_1_battery.md) update.

### subscribe_flight_mode() {#classmavsdk_1_1_telemetry_1a53db5fb36bf10fbc7ac004a3be9100a4}
```cpp
void mavsdk::Telemetry::subscribe_flight_mode(FlightModeCallback callback)
```


Subscribe to 'flight mode' updates.


**Parameters**

* [FlightModeCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a2d7318d0823771b7a586c40199bdb482) **callback** - 

### flight_mode() {#classmavsdk_1_1_telemetry_1a4972a3968e379d565e7700f2f51158dd}
```cpp
FlightMode mavsdk::Telemetry::flight_mode() const
```


Poll for 'FlightMode' (blocking).


**Returns**

&emsp;[FlightMode](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a8317d953a82a23654db6f14509acb4fe) - One FlightMode update.

### subscribe_health() {#classmavsdk_1_1_telemetry_1a0c489b33a635adf0610731a42ce5615b}
```cpp
void mavsdk::Telemetry::subscribe_health(HealthCallback callback)
```


Subscribe to 'health' updates.


**Parameters**

* [HealthCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a7a120dd053091c644e0e2e47fdcbeb75) **callback** - 

### health() {#classmavsdk_1_1_telemetry_1aae4824c9eeb72603b197c864b5cc5df5}
```cpp
Health mavsdk::Telemetry::health() const
```


Poll for '[Health](structmavsdk_1_1_telemetry_1_1_health.md)' (blocking).


**Returns**

&emsp;[Health](structmavsdk_1_1_telemetry_1_1_health.md) - One [Health](structmavsdk_1_1_telemetry_1_1_health.md) update.

### subscribe_rc_status() {#classmavsdk_1_1_telemetry_1ae5f894c16564674f7fdaba36ff12dd08}
```cpp
void mavsdk::Telemetry::subscribe_rc_status(RcStatusCallback callback)
```


Subscribe to 'RC status' updates.


**Parameters**

* [RcStatusCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1aafcd706b805898301b574ffa2b909b85) **callback** - 

### rc_status() {#classmavsdk_1_1_telemetry_1a59cd497c69f1d32be29a940a2d34a474}
```cpp
RcStatus mavsdk::Telemetry::rc_status() const
```


Poll for '[RcStatus](structmavsdk_1_1_telemetry_1_1_rc_status.md)' (blocking).


**Returns**

&emsp;[RcStatus](structmavsdk_1_1_telemetry_1_1_rc_status.md) - One [RcStatus](structmavsdk_1_1_telemetry_1_1_rc_status.md) update.

### subscribe_status_text() {#classmavsdk_1_1_telemetry_1a80106e59b9df76a47a2068b4fb4ecb69}
```cpp
void mavsdk::Telemetry::subscribe_status_text(StatusTextCallback callback)
```


Subscribe to 'status text' updates.


**Parameters**

* [StatusTextCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a46e51ff90fe779990ed09a593c1c7898) **callback** - 

### status_text() {#classmavsdk_1_1_telemetry_1a2f31c0668ed1ac1bfdfa4b2e9a2023a9}
```cpp
StatusText mavsdk::Telemetry::status_text() const
```


Poll for '[StatusText](structmavsdk_1_1_telemetry_1_1_status_text.md)' (blocking).


**Returns**

&emsp;[StatusText](structmavsdk_1_1_telemetry_1_1_status_text.md) - One [StatusText](structmavsdk_1_1_telemetry_1_1_status_text.md) update.

### subscribe_actuator_control_target() {#classmavsdk_1_1_telemetry_1a697c3618245a9886f917431aee59bd2c}
```cpp
void mavsdk::Telemetry::subscribe_actuator_control_target(ActuatorControlTargetCallback callback)
```


Subscribe to 'actuator control target' updates.


**Parameters**

* [ActuatorControlTargetCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1ada6af3de1b60b93a709345c3a8ede551) **callback** - 

### actuator_control_target() {#classmavsdk_1_1_telemetry_1af4ffa70ff58c46b50be93a0fbf960f95}
```cpp
ActuatorControlTarget mavsdk::Telemetry::actuator_control_target() const
```


Poll for '[ActuatorControlTarget](structmavsdk_1_1_telemetry_1_1_actuator_control_target.md)' (blocking).


**Returns**

&emsp;[ActuatorControlTarget](structmavsdk_1_1_telemetry_1_1_actuator_control_target.md) - One [ActuatorControlTarget](structmavsdk_1_1_telemetry_1_1_actuator_control_target.md) update.

### subscribe_actuator_output_status() {#classmavsdk_1_1_telemetry_1ab5bc6fdb24935f4834cd490d7a085594}
```cpp
void mavsdk::Telemetry::subscribe_actuator_output_status(ActuatorOutputStatusCallback callback)
```


Subscribe to 'actuator output status' updates.


**Parameters**

* [ActuatorOutputStatusCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a2b1e800ce1ba6fb776351416340ac8b9) **callback** - 

### actuator_output_status() {#classmavsdk_1_1_telemetry_1a68fa1619dfad0a7cfcc2725025669252}
```cpp
ActuatorOutputStatus mavsdk::Telemetry::actuator_output_status() const
```


Poll for '[ActuatorOutputStatus](structmavsdk_1_1_telemetry_1_1_actuator_output_status.md)' (blocking).


**Returns**

&emsp;[ActuatorOutputStatus](structmavsdk_1_1_telemetry_1_1_actuator_output_status.md) - One [ActuatorOutputStatus](structmavsdk_1_1_telemetry_1_1_actuator_output_status.md) update.

### subscribe_odometry() {#classmavsdk_1_1_telemetry_1a1ff5094feae71f009b7cdbab90734b09}
```cpp
void mavsdk::Telemetry::subscribe_odometry(OdometryCallback callback)
```


Subscribe to 'odometry' updates.


**Parameters**

* [OdometryCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a8cd23f7364f8f5cb22869155da67c65d) **callback** - 

### odometry() {#classmavsdk_1_1_telemetry_1a715b6e8ba1206059706f08844a0b96d2}
```cpp
Odometry mavsdk::Telemetry::odometry() const
```


Poll for '[Odometry](structmavsdk_1_1_telemetry_1_1_odometry.md)' (blocking).


**Returns**

&emsp;[Odometry](structmavsdk_1_1_telemetry_1_1_odometry.md) - One [Odometry](structmavsdk_1_1_telemetry_1_1_odometry.md) update.

### subscribe_position_velocity_ned() {#classmavsdk_1_1_telemetry_1a8e09afe19fe9f2c05a5d647ceb2c8310}
```cpp
void mavsdk::Telemetry::subscribe_position_velocity_ned(PositionVelocityNedCallback callback)
```


Subscribe to 'position velocity' updates.


**Parameters**

* [PositionVelocityNedCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a5a38deb284622ff6926703e1e5c96a74) **callback** - 

### position_velocity_ned() {#classmavsdk_1_1_telemetry_1af9b06944ca73ad09caadacd9f4fae950}
```cpp
PositionVelocityNed mavsdk::Telemetry::position_velocity_ned() const
```


Poll for '[PositionVelocityNed](structmavsdk_1_1_telemetry_1_1_position_velocity_ned.md)' (blocking).


**Returns**

&emsp;[PositionVelocityNed](structmavsdk_1_1_telemetry_1_1_position_velocity_ned.md) - One [PositionVelocityNed](structmavsdk_1_1_telemetry_1_1_position_velocity_ned.md) update.

### subscribe_ground_truth() {#classmavsdk_1_1_telemetry_1adcc18e7d8801ccdef2cf137a84d53460}
```cpp
void mavsdk::Telemetry::subscribe_ground_truth(GroundTruthCallback callback)
```


Subscribe to 'ground truth' updates.


**Parameters**

* [GroundTruthCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a222aae53852a2c535f6d69ed57221f13) **callback** - 

### ground_truth() {#classmavsdk_1_1_telemetry_1a1b5f387edc39e33b86954f2048133f71}
```cpp
GroundTruth mavsdk::Telemetry::ground_truth() const
```


Poll for '[GroundTruth](structmavsdk_1_1_telemetry_1_1_ground_truth.md)' (blocking).


**Returns**

&emsp;[GroundTruth](structmavsdk_1_1_telemetry_1_1_ground_truth.md) - One [GroundTruth](structmavsdk_1_1_telemetry_1_1_ground_truth.md) update.

### subscribe_fixedwing_metrics() {#classmavsdk_1_1_telemetry_1a1b32f7cc867f8f21fdcedda49434a22b}
```cpp
void mavsdk::Telemetry::subscribe_fixedwing_metrics(FixedwingMetricsCallback callback)
```


Subscribe to 'fixedwing metrics' updates.


**Parameters**

* [FixedwingMetricsCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a5b42dbef0ef6d8c1768d503d0437f1e3) **callback** - 

### fixedwing_metrics() {#classmavsdk_1_1_telemetry_1a2ab8d2a8d017d46e77d49c4f899c7cbf}
```cpp
FixedwingMetrics mavsdk::Telemetry::fixedwing_metrics() const
```


Poll for '[FixedwingMetrics](structmavsdk_1_1_telemetry_1_1_fixedwing_metrics.md)' (blocking).


**Returns**

&emsp;[FixedwingMetrics](structmavsdk_1_1_telemetry_1_1_fixedwing_metrics.md) - One [FixedwingMetrics](structmavsdk_1_1_telemetry_1_1_fixedwing_metrics.md) update.

### subscribe_imu() {#classmavsdk_1_1_telemetry_1a35ce2552e8b709e6194481c0fd070a8d}
```cpp
void mavsdk::Telemetry::subscribe_imu(ImuCallback callback)
```


Subscribe to 'IMU' updates (in SI units in NED body frame).


**Parameters**

* [ImuCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a4fbc2ad274fd5a8af077004d2d7bd984) **callback** - 

### imu() {#classmavsdk_1_1_telemetry_1a1a4e43b7bdcd988442955d2a5465b977}
```cpp
Imu mavsdk::Telemetry::imu() const
```


Poll for '[Imu](structmavsdk_1_1_telemetry_1_1_imu.md)' (blocking).


**Returns**

&emsp;[Imu](structmavsdk_1_1_telemetry_1_1_imu.md) - One [Imu](structmavsdk_1_1_telemetry_1_1_imu.md) update.

### subscribe_scaled_imu() {#classmavsdk_1_1_telemetry_1ac3b293defb52103db936e650212832c1}
```cpp
void mavsdk::Telemetry::subscribe_scaled_imu(ScaledImuCallback callback)
```


Subscribe to 'Scaled IMU' updates.


**Parameters**

* [ScaledImuCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a26159a775adcfbc42302234b7108d94f) **callback** - 

### scaled_imu() {#classmavsdk_1_1_telemetry_1ab6a515ba85a67bc80e6e1c9a05d1f94d}
```cpp
Imu mavsdk::Telemetry::scaled_imu() const
```


Poll for '[Imu](structmavsdk_1_1_telemetry_1_1_imu.md)' (blocking).


**Returns**

&emsp;[Imu](structmavsdk_1_1_telemetry_1_1_imu.md) - One [Imu](structmavsdk_1_1_telemetry_1_1_imu.md) update.

### subscribe_raw_imu() {#classmavsdk_1_1_telemetry_1aeaf9d9393300bd61470d6b7bb92b03c2}
```cpp
void mavsdk::Telemetry::subscribe_raw_imu(RawImuCallback callback)
```


Subscribe to 'Raw IMU' updates.


**Parameters**

* [RawImuCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a92711da85d343cb58b73561e6b730c76) **callback** - 

### raw_imu() {#classmavsdk_1_1_telemetry_1a691464f001ddf8d02b97bcf137f5cf8a}
```cpp
Imu mavsdk::Telemetry::raw_imu() const
```


Poll for '[Imu](structmavsdk_1_1_telemetry_1_1_imu.md)' (blocking).


**Returns**

&emsp;[Imu](structmavsdk_1_1_telemetry_1_1_imu.md) - One [Imu](structmavsdk_1_1_telemetry_1_1_imu.md) update.

### subscribe_health_all_ok() {#classmavsdk_1_1_telemetry_1a0f94ea6d707ff314e412367d6681bd8f}
```cpp
void mavsdk::Telemetry::subscribe_health_all_ok(HealthAllOkCallback callback)
```


Subscribe to 'HealthAllOk' updates.


**Parameters**

* [HealthAllOkCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a71cdcadfaa988dc14029e0b9fdbe742d) **callback** - 

### health_all_ok() {#classmavsdk_1_1_telemetry_1ad6d833741b5576f07204d268c5cd4d06}
```cpp
bool mavsdk::Telemetry::health_all_ok() const
```


Poll for 'bool' (blocking).


**Returns**

&emsp;bool - One bool update.

### subscribe_unix_epoch_time() {#classmavsdk_1_1_telemetry_1ad7f04211822f862b580308e3786cdc77}
```cpp
void mavsdk::Telemetry::subscribe_unix_epoch_time(UnixEpochTimeCallback callback)
```


Subscribe to 'unix epoch time' updates.


**Parameters**

* [UnixEpochTimeCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a321c7d809ae8f56bb8a361d5e5ce6391) **callback** - 

### unix_epoch_time() {#classmavsdk_1_1_telemetry_1ab5ea5f6bb35b5670e34d5697d8c880f4}
```cpp
uint64_t mavsdk::Telemetry::unix_epoch_time() const
```


Poll for 'uint64_t' (blocking).


**Returns**

&emsp;uint64_t - One uint64_t update.

### subscribe_distance_sensor() {#classmavsdk_1_1_telemetry_1a74654313a3f588f252012ee6412e9342}
```cpp
void mavsdk::Telemetry::subscribe_distance_sensor(DistanceSensorCallback callback)
```


Subscribe to 'Distance Sensor' updates.


**Parameters**

* [DistanceSensorCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1aacfdb5e2cce7f3f77c68b36f020ed1f2) **callback** - 

### distance_sensor() {#classmavsdk_1_1_telemetry_1aa01828c0ffcb4727b884ffeae8fef59a}
```cpp
DistanceSensor mavsdk::Telemetry::distance_sensor() const
```


Poll for '[DistanceSensor](structmavsdk_1_1_telemetry_1_1_distance_sensor.md)' (blocking).


**Returns**

&emsp;[DistanceSensor](structmavsdk_1_1_telemetry_1_1_distance_sensor.md) - One [DistanceSensor](structmavsdk_1_1_telemetry_1_1_distance_sensor.md) update.

### subscribe_scaled_pressure() {#classmavsdk_1_1_telemetry_1a2cdca606b62c7fd94c61a47cd06f2245}
```cpp
void mavsdk::Telemetry::subscribe_scaled_pressure(ScaledPressureCallback callback)
```


Subscribe to 'Scaled Pressure' updates.


**Parameters**

* [ScaledPressureCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1ac123edc254bb1874edc08a0f531f82b1) **callback** - 

### scaled_pressure() {#classmavsdk_1_1_telemetry_1a825ecb6af46663034f982c3c3d6da022}
```cpp
ScaledPressure mavsdk::Telemetry::scaled_pressure() const
```


Poll for '[ScaledPressure](structmavsdk_1_1_telemetry_1_1_scaled_pressure.md)' (blocking).


**Returns**

&emsp;[ScaledPressure](structmavsdk_1_1_telemetry_1_1_scaled_pressure.md) - One [ScaledPressure](structmavsdk_1_1_telemetry_1_1_scaled_pressure.md) update.

### subscribe_heading() {#classmavsdk_1_1_telemetry_1a68c5e62cad1c641a13d0d5c3ae064ce4}
```cpp
void mavsdk::Telemetry::subscribe_heading(HeadingCallback callback)
```


Subscribe to '[Heading](structmavsdk_1_1_telemetry_1_1_heading.md)' updates.


**Parameters**

* [HeadingCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1aa3bca0adab525a4c733c1e7f5c5dd8b3) **callback** - 

### heading() {#classmavsdk_1_1_telemetry_1a2aec80b167a3076903be4fe52847a4d3}
```cpp
Heading mavsdk::Telemetry::heading() const
```


Poll for '[Heading](structmavsdk_1_1_telemetry_1_1_heading.md)' (blocking).


**Returns**

&emsp;[Heading](structmavsdk_1_1_telemetry_1_1_heading.md) - One [Heading](structmavsdk_1_1_telemetry_1_1_heading.md) update.

### set_rate_position_async() {#classmavsdk_1_1_telemetry_1ad7e5b576edb9398c8f5f2f14626b984a}
```cpp
void mavsdk::Telemetry::set_rate_position_async(double rate_hz, const ResultCallback callback)
```


Set rate to 'position' updates.

This function is non-blocking. See 'set_rate_position' for the blocking counterpart.

**Parameters**

* double **rate_hz** - 
* const [ResultCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a166e81c6573532978e5940eafdfcec0b) **callback** - 

### set_rate_position() {#classmavsdk_1_1_telemetry_1a665439f3d5f8c58b3ef3dd427cf4782b}
```cpp
Result mavsdk::Telemetry::set_rate_position(double rate_hz) const
```


Set rate to 'position' updates.

This function is blocking. See 'set_rate_position_async' for the non-blocking counterpart.

**Parameters**

* double **rate_hz** - 

**Returns**

&emsp;[Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75) - Result of request.

### set_rate_home_async() {#classmavsdk_1_1_telemetry_1a098f4c4f50fc3ac2c153ef152208fbbe}
```cpp
void mavsdk::Telemetry::set_rate_home_async(double rate_hz, const ResultCallback callback)
```


Set rate to 'home position' updates.

This function is non-blocking. See 'set_rate_home' for the blocking counterpart.

**Parameters**

* double **rate_hz** - 
* const [ResultCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a166e81c6573532978e5940eafdfcec0b) **callback** - 

### set_rate_home() {#classmavsdk_1_1_telemetry_1af90e28ad8a8f05401176c98e427eecfc}
```cpp
Result mavsdk::Telemetry::set_rate_home(double rate_hz) const
```


Set rate to 'home position' updates.

This function is blocking. See 'set_rate_home_async' for the non-blocking counterpart.

**Parameters**

* double **rate_hz** - 

**Returns**

&emsp;[Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75) - Result of request.

### set_rate_in_air_async() {#classmavsdk_1_1_telemetry_1a9ea77b7ef64acd1e25b05e593e638c70}
```cpp
void mavsdk::Telemetry::set_rate_in_air_async(double rate_hz, const ResultCallback callback)
```


Set rate to in-air updates.

This function is non-blocking. See 'set_rate_in_air' for the blocking counterpart.

**Parameters**

* double **rate_hz** - 
* const [ResultCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a166e81c6573532978e5940eafdfcec0b) **callback** - 

### set_rate_in_air() {#classmavsdk_1_1_telemetry_1a8f179e8397b395e61a48529ceeba2b14}
```cpp
Result mavsdk::Telemetry::set_rate_in_air(double rate_hz) const
```


Set rate to in-air updates.

This function is blocking. See 'set_rate_in_air_async' for the non-blocking counterpart.

**Parameters**

* double **rate_hz** - 

**Returns**

&emsp;[Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75) - Result of request.

### set_rate_landed_state_async() {#classmavsdk_1_1_telemetry_1a180fff93b120a67c16ad5993f0b38847}
```cpp
void mavsdk::Telemetry::set_rate_landed_state_async(double rate_hz, const ResultCallback callback)
```


Set rate to landed state updates.

This function is non-blocking. See 'set_rate_landed_state' for the blocking counterpart.

**Parameters**

* double **rate_hz** - 
* const [ResultCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a166e81c6573532978e5940eafdfcec0b) **callback** - 

### set_rate_landed_state() {#classmavsdk_1_1_telemetry_1a53a3428c602c1f91cfcffdba188a4e51}
```cpp
Result mavsdk::Telemetry::set_rate_landed_state(double rate_hz) const
```


Set rate to landed state updates.

This function is blocking. See 'set_rate_landed_state_async' for the non-blocking counterpart.

**Parameters**

* double **rate_hz** - 

**Returns**

&emsp;[Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75) - Result of request.

### set_rate_vtol_state_async() {#classmavsdk_1_1_telemetry_1a18f47beba583e6814061f95e68a3851d}
```cpp
void mavsdk::Telemetry::set_rate_vtol_state_async(double rate_hz, const ResultCallback callback)
```


Set rate to VTOL state updates.

This function is non-blocking. See 'set_rate_vtol_state' for the blocking counterpart.

**Parameters**

* double **rate_hz** - 
* const [ResultCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a166e81c6573532978e5940eafdfcec0b) **callback** - 

### set_rate_vtol_state() {#classmavsdk_1_1_telemetry_1a943c2e32a12098a117c4bd4eed7cdc22}
```cpp
Result mavsdk::Telemetry::set_rate_vtol_state(double rate_hz) const
```


Set rate to VTOL state updates.

This function is blocking. See 'set_rate_vtol_state_async' for the non-blocking counterpart.

**Parameters**

* double **rate_hz** - 

**Returns**

&emsp;[Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75) - Result of request.

### set_rate_attitude_async() {#classmavsdk_1_1_telemetry_1a2f979321709760a1ad4a8dd09755cd61}
```cpp
void mavsdk::Telemetry::set_rate_attitude_async(double rate_hz, const ResultCallback callback)
```


Set rate to 'attitude' updates.

This function is non-blocking. See 'set_rate_attitude' for the blocking counterpart.

**Parameters**

* double **rate_hz** - 
* const [ResultCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a166e81c6573532978e5940eafdfcec0b) **callback** - 

### set_rate_attitude() {#classmavsdk_1_1_telemetry_1a163d3960faadad948294f367eaaf52b0}
```cpp
Result mavsdk::Telemetry::set_rate_attitude(double rate_hz) const
```


Set rate to 'attitude' updates.

This function is blocking. See 'set_rate_attitude_async' for the non-blocking counterpart.

**Parameters**

* double **rate_hz** - 

**Returns**

&emsp;[Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75) - Result of request.

### set_rate_camera_attitude_async() {#classmavsdk_1_1_telemetry_1a520f15e42f5f1b3987ca2a9cd94a3d9a}
```cpp
void mavsdk::Telemetry::set_rate_camera_attitude_async(double rate_hz, const ResultCallback callback)
```


Set rate of camera attitude updates.

This function is non-blocking. See 'set_rate_camera_attitude' for the blocking counterpart.

**Parameters**

* double **rate_hz** - 
* const [ResultCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a166e81c6573532978e5940eafdfcec0b) **callback** - 

### set_rate_camera_attitude() {#classmavsdk_1_1_telemetry_1a427da223d16ce07a61b07d4e5af1ab04}
```cpp
Result mavsdk::Telemetry::set_rate_camera_attitude(double rate_hz) const
```


Set rate of camera attitude updates.

This function is blocking. See 'set_rate_camera_attitude_async' for the non-blocking counterpart.

**Parameters**

* double **rate_hz** - 

**Returns**

&emsp;[Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75) - Result of request.

### set_rate_velocity_ned_async() {#classmavsdk_1_1_telemetry_1a9429ffa784fa56adee69c5017abedee4}
```cpp
void mavsdk::Telemetry::set_rate_velocity_ned_async(double rate_hz, const ResultCallback callback)
```


Set rate to 'ground speed' updates (NED).

This function is non-blocking. See 'set_rate_velocity_ned' for the blocking counterpart.

**Parameters**

* double **rate_hz** - 
* const [ResultCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a166e81c6573532978e5940eafdfcec0b) **callback** - 

### set_rate_velocity_ned() {#classmavsdk_1_1_telemetry_1ab5cb79fd53f27f245808a6bb9ed3225d}
```cpp
Result mavsdk::Telemetry::set_rate_velocity_ned(double rate_hz) const
```


Set rate to 'ground speed' updates (NED).

This function is blocking. See 'set_rate_velocity_ned_async' for the non-blocking counterpart.

**Parameters**

* double **rate_hz** - 

**Returns**

&emsp;[Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75) - Result of request.

### set_rate_gps_info_async() {#classmavsdk_1_1_telemetry_1ae6ada3cd6d4e9835dd4d1d712f1195e4}
```cpp
void mavsdk::Telemetry::set_rate_gps_info_async(double rate_hz, const ResultCallback callback)
```


Set rate to 'GPS info' updates.

This function is non-blocking. See 'set_rate_gps_info' for the blocking counterpart.

**Parameters**

* double **rate_hz** - 
* const [ResultCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a166e81c6573532978e5940eafdfcec0b) **callback** - 

### set_rate_gps_info() {#classmavsdk_1_1_telemetry_1a14510bcb6fe3c31d91653d32d354613f}
```cpp
Result mavsdk::Telemetry::set_rate_gps_info(double rate_hz) const
```


Set rate to 'GPS info' updates.

This function is blocking. See 'set_rate_gps_info_async' for the non-blocking counterpart.

**Parameters**

* double **rate_hz** - 

**Returns**

&emsp;[Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75) - Result of request.

### set_rate_battery_async() {#classmavsdk_1_1_telemetry_1a5615e21f616997dfca1318c96a7e550e}
```cpp
void mavsdk::Telemetry::set_rate_battery_async(double rate_hz, const ResultCallback callback)
```


Set rate to 'battery' updates.

This function is non-blocking. See 'set_rate_battery' for the blocking counterpart.

**Parameters**

* double **rate_hz** - 
* const [ResultCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a166e81c6573532978e5940eafdfcec0b) **callback** - 

### set_rate_battery() {#classmavsdk_1_1_telemetry_1ae781d2e950a535a465f2bc1575e9f893}
```cpp
Result mavsdk::Telemetry::set_rate_battery(double rate_hz) const
```


Set rate to 'battery' updates.

This function is blocking. See 'set_rate_battery_async' for the non-blocking counterpart.

**Parameters**

* double **rate_hz** - 

**Returns**

&emsp;[Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75) - Result of request.

### set_rate_rc_status_async() {#classmavsdk_1_1_telemetry_1a8cf84eaca875626bc53ed03e98d6eb7e}
```cpp
void mavsdk::Telemetry::set_rate_rc_status_async(double rate_hz, const ResultCallback callback)
```


Set rate to 'RC status' updates.

This function is non-blocking. See 'set_rate_rc_status' for the blocking counterpart.

**Parameters**

* double **rate_hz** - 
* const [ResultCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a166e81c6573532978e5940eafdfcec0b) **callback** - 

### set_rate_rc_status() {#classmavsdk_1_1_telemetry_1acbfc54792f79c5fd2a9855278981f8ca}
```cpp
Result mavsdk::Telemetry::set_rate_rc_status(double rate_hz) const
```


Set rate to 'RC status' updates.

This function is blocking. See 'set_rate_rc_status_async' for the non-blocking counterpart.

**Parameters**

* double **rate_hz** - 

**Returns**

&emsp;[Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75) - Result of request.

### set_rate_actuator_control_target_async() {#classmavsdk_1_1_telemetry_1aa44e3a76c482f273a2f1bc1a09bec27c}
```cpp
void mavsdk::Telemetry::set_rate_actuator_control_target_async(double rate_hz, const ResultCallback callback)
```


Set rate to 'actuator control target' updates.

This function is non-blocking. See 'set_rate_actuator_control_target' for the blocking counterpart.

**Parameters**

* double **rate_hz** - 
* const [ResultCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a166e81c6573532978e5940eafdfcec0b) **callback** - 

### set_rate_actuator_control_target() {#classmavsdk_1_1_telemetry_1aa43efb510038f1bb95241953ae09c998}
```cpp
Result mavsdk::Telemetry::set_rate_actuator_control_target(double rate_hz) const
```


Set rate to 'actuator control target' updates.

This function is blocking. See 'set_rate_actuator_control_target_async' for the non-blocking counterpart.

**Parameters**

* double **rate_hz** - 

**Returns**

&emsp;[Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75) - Result of request.

### set_rate_actuator_output_status_async() {#classmavsdk_1_1_telemetry_1a2ad19c1101962ed7cfeec89b7fae0f9c}
```cpp
void mavsdk::Telemetry::set_rate_actuator_output_status_async(double rate_hz, const ResultCallback callback)
```


Set rate to 'actuator output status' updates.

This function is non-blocking. See 'set_rate_actuator_output_status' for the blocking counterpart.

**Parameters**

* double **rate_hz** - 
* const [ResultCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a166e81c6573532978e5940eafdfcec0b) **callback** - 

### set_rate_actuator_output_status() {#classmavsdk_1_1_telemetry_1a48b3e3a288ba6a8d38914c4827124006}
```cpp
Result mavsdk::Telemetry::set_rate_actuator_output_status(double rate_hz) const
```


Set rate to 'actuator output status' updates.

This function is blocking. See 'set_rate_actuator_output_status_async' for the non-blocking counterpart.

**Parameters**

* double **rate_hz** - 

**Returns**

&emsp;[Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75) - Result of request.

### set_rate_odometry_async() {#classmavsdk_1_1_telemetry_1a23e507e1d53c6603479701f5e2af49ce}
```cpp
void mavsdk::Telemetry::set_rate_odometry_async(double rate_hz, const ResultCallback callback)
```


Set rate to 'odometry' updates.

This function is non-blocking. See 'set_rate_odometry' for the blocking counterpart.

**Parameters**

* double **rate_hz** - 
* const [ResultCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a166e81c6573532978e5940eafdfcec0b) **callback** - 

### set_rate_odometry() {#classmavsdk_1_1_telemetry_1a4368bf825cec3bc9369d57546a45391e}
```cpp
Result mavsdk::Telemetry::set_rate_odometry(double rate_hz) const
```


Set rate to 'odometry' updates.

This function is blocking. See 'set_rate_odometry_async' for the non-blocking counterpart.

**Parameters**

* double **rate_hz** - 

**Returns**

&emsp;[Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75) - Result of request.

### set_rate_position_velocity_ned_async() {#classmavsdk_1_1_telemetry_1a9a4c3b6affa497dd22e464f515ca278c}
```cpp
void mavsdk::Telemetry::set_rate_position_velocity_ned_async(double rate_hz, const ResultCallback callback)
```


Set rate to 'position velocity' updates.

This function is non-blocking. See 'set_rate_position_velocity_ned' for the blocking counterpart.

**Parameters**

* double **rate_hz** - 
* const [ResultCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a166e81c6573532978e5940eafdfcec0b) **callback** - 

### set_rate_position_velocity_ned() {#classmavsdk_1_1_telemetry_1a64fe3457589cd208a9f7bd5dea763da1}
```cpp
Result mavsdk::Telemetry::set_rate_position_velocity_ned(double rate_hz) const
```


Set rate to 'position velocity' updates.

This function is blocking. See 'set_rate_position_velocity_ned_async' for the non-blocking counterpart.

**Parameters**

* double **rate_hz** - 

**Returns**

&emsp;[Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75) - Result of request.

### set_rate_ground_truth_async() {#classmavsdk_1_1_telemetry_1a16b28ebdc6d211a5b182bd8d0abb4d2e}
```cpp
void mavsdk::Telemetry::set_rate_ground_truth_async(double rate_hz, const ResultCallback callback)
```


Set rate to 'ground truth' updates.

This function is non-blocking. See 'set_rate_ground_truth' for the blocking counterpart.

**Parameters**

* double **rate_hz** - 
* const [ResultCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a166e81c6573532978e5940eafdfcec0b) **callback** - 

### set_rate_ground_truth() {#classmavsdk_1_1_telemetry_1a23b2962e5b7681ece3fcbc72220d6b48}
```cpp
Result mavsdk::Telemetry::set_rate_ground_truth(double rate_hz) const
```


Set rate to 'ground truth' updates.

This function is blocking. See 'set_rate_ground_truth_async' for the non-blocking counterpart.

**Parameters**

* double **rate_hz** - 

**Returns**

&emsp;[Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75) - Result of request.

### set_rate_fixedwing_metrics_async() {#classmavsdk_1_1_telemetry_1a1484ccdcf4ba20a151e380e7bd7b9869}
```cpp
void mavsdk::Telemetry::set_rate_fixedwing_metrics_async(double rate_hz, const ResultCallback callback)
```


Set rate to 'fixedwing metrics' updates.

This function is non-blocking. See 'set_rate_fixedwing_metrics' for the blocking counterpart.

**Parameters**

* double **rate_hz** - 
* const [ResultCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a166e81c6573532978e5940eafdfcec0b) **callback** - 

### set_rate_fixedwing_metrics() {#classmavsdk_1_1_telemetry_1ab345a5925d132c27e0a5e1ab65a1e2c1}
```cpp
Result mavsdk::Telemetry::set_rate_fixedwing_metrics(double rate_hz) const
```


Set rate to 'fixedwing metrics' updates.

This function is blocking. See 'set_rate_fixedwing_metrics_async' for the non-blocking counterpart.

**Parameters**

* double **rate_hz** - 

**Returns**

&emsp;[Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75) - Result of request.

### set_rate_imu_async() {#classmavsdk_1_1_telemetry_1a7dca435daa0de2db2d2e9d588c6bed99}
```cpp
void mavsdk::Telemetry::set_rate_imu_async(double rate_hz, const ResultCallback callback)
```


Set rate to 'IMU' updates.

This function is non-blocking. See 'set_rate_imu' for the blocking counterpart.

**Parameters**

* double **rate_hz** - 
* const [ResultCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a166e81c6573532978e5940eafdfcec0b) **callback** - 

### set_rate_imu() {#classmavsdk_1_1_telemetry_1a4e0d1dc2350e06f68f472d85dc69d175}
```cpp
Result mavsdk::Telemetry::set_rate_imu(double rate_hz) const
```


Set rate to 'IMU' updates.

This function is blocking. See 'set_rate_imu_async' for the non-blocking counterpart.

**Parameters**

* double **rate_hz** - 

**Returns**

&emsp;[Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75) - Result of request.

### set_rate_scaled_imu_async() {#classmavsdk_1_1_telemetry_1aebbf2eb2e5d117d8b40f21075845467c}
```cpp
void mavsdk::Telemetry::set_rate_scaled_imu_async(double rate_hz, const ResultCallback callback)
```


Set rate to 'Scaled IMU' updates.

This function is non-blocking. See 'set_rate_scaled_imu' for the blocking counterpart.

**Parameters**

* double **rate_hz** - 
* const [ResultCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a166e81c6573532978e5940eafdfcec0b) **callback** - 

### set_rate_scaled_imu() {#classmavsdk_1_1_telemetry_1af8dc4f38bf7cc89f700c985a04e03237}
```cpp
Result mavsdk::Telemetry::set_rate_scaled_imu(double rate_hz) const
```


Set rate to 'Scaled IMU' updates.

This function is blocking. See 'set_rate_scaled_imu_async' for the non-blocking counterpart.

**Parameters**

* double **rate_hz** - 

**Returns**

&emsp;[Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75) - Result of request.

### set_rate_raw_imu_async() {#classmavsdk_1_1_telemetry_1a36d19058a0f71d711de3e50ba718704e}
```cpp
void mavsdk::Telemetry::set_rate_raw_imu_async(double rate_hz, const ResultCallback callback)
```


Set rate to 'Raw IMU' updates.

This function is non-blocking. See 'set_rate_raw_imu' for the blocking counterpart.

**Parameters**

* double **rate_hz** - 
* const [ResultCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a166e81c6573532978e5940eafdfcec0b) **callback** - 

### set_rate_raw_imu() {#classmavsdk_1_1_telemetry_1a020cb8760e6f00b759c8ef564d8801ad}
```cpp
Result mavsdk::Telemetry::set_rate_raw_imu(double rate_hz) const
```


Set rate to 'Raw IMU' updates.

This function is blocking. See 'set_rate_raw_imu_async' for the non-blocking counterpart.

**Parameters**

* double **rate_hz** - 

**Returns**

&emsp;[Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75) - Result of request.

### set_rate_unix_epoch_time_async() {#classmavsdk_1_1_telemetry_1a74b18cd8a5faed4d46b244db0a6e3c50}
```cpp
void mavsdk::Telemetry::set_rate_unix_epoch_time_async(double rate_hz, const ResultCallback callback)
```


Set rate to 'unix epoch time' updates.

This function is non-blocking. See 'set_rate_unix_epoch_time' for the blocking counterpart.

**Parameters**

* double **rate_hz** - 
* const [ResultCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a166e81c6573532978e5940eafdfcec0b) **callback** - 

### set_rate_unix_epoch_time() {#classmavsdk_1_1_telemetry_1a340ac34547672ee07131bca34cbbb820}
```cpp
Result mavsdk::Telemetry::set_rate_unix_epoch_time(double rate_hz) const
```


Set rate to 'unix epoch time' updates.

This function is blocking. See 'set_rate_unix_epoch_time_async' for the non-blocking counterpart.

**Parameters**

* double **rate_hz** - 

**Returns**

&emsp;[Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75) - Result of request.

### set_rate_distance_sensor_async() {#classmavsdk_1_1_telemetry_1a0371c470866b539b3aa1e254c974aa43}
```cpp
void mavsdk::Telemetry::set_rate_distance_sensor_async(double rate_hz, const ResultCallback callback)
```


Set rate to 'Distance Sensor' updates.

This function is non-blocking. See 'set_rate_distance_sensor' for the blocking counterpart.

**Parameters**

* double **rate_hz** - 
* const [ResultCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a166e81c6573532978e5940eafdfcec0b) **callback** - 

### set_rate_distance_sensor() {#classmavsdk_1_1_telemetry_1a7f536359536478691d7db980ffe49e49}
```cpp
Result mavsdk::Telemetry::set_rate_distance_sensor(double rate_hz) const
```


Set rate to 'Distance Sensor' updates.

This function is blocking. See 'set_rate_distance_sensor_async' for the non-blocking counterpart.

**Parameters**

* double **rate_hz** - 

**Returns**

&emsp;[Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75) - Result of request.

### get_gps_global_origin_async() {#classmavsdk_1_1_telemetry_1a60cca43e2f87e3fd3a9e170ff2b64e0a}
```cpp
void mavsdk::Telemetry::get_gps_global_origin_async(const GetGpsGlobalOriginCallback callback)
```


Get the GPS location of where the estimator has been initialized.

This function is non-blocking. See 'get_gps_global_origin' for the blocking counterpart.

**Parameters**

* const [GetGpsGlobalOriginCallback](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a350ee89a7e30a691e130e29ace8917ef) **callback** - 

### get_gps_global_origin() {#classmavsdk_1_1_telemetry_1a341b90234b30a27bb25670a31303e0cd}
```cpp
std::pair< Result, Telemetry::GpsGlobalOrigin > mavsdk::Telemetry::get_gps_global_origin() const
```


Get the GPS location of where the estimator has been initialized.

This function is blocking. See 'get_gps_global_origin_async' for the non-blocking counterpart.

**Returns**

&emsp;std::pair< [Result](classmavsdk_1_1_telemetry.md#classmavsdk_1_1_telemetry_1a241427df9a06234df2d3020fb524db75), [Telemetry::GpsGlobalOrigin](structmavsdk_1_1_telemetry_1_1_gps_global_origin.md) > - Result of request.

### operator=() {#classmavsdk_1_1_telemetry_1ae606a3e3814c773a12035c2674a00c5c}
```cpp
const Telemetry & mavsdk::Telemetry::operator=(const Telemetry &)=delete
```


Equality operator (object is not copyable).


**Parameters**

* const [Telemetry](classmavsdk_1_1_telemetry.md)&  - 

**Returns**

&emsp;const [Telemetry](classmavsdk_1_1_telemetry.md) & - 