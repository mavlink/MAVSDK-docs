# mavsdk Namespace Reference

----

Namespace for all mavsdk types.


## Data Structures

* [mavsdk::Action](classmavsdk_1_1_action.md)
* [mavsdk::Calibration](classmavsdk_1_1_calibration.md)
* [mavsdk::Camera](classmavsdk_1_1_camera.md)
* [mavsdk::FollowMe](classmavsdk_1_1_follow_me.md)
* [mavsdk::Geofence](classmavsdk_1_1_geofence.md)
* [mavsdk::Gimbal](classmavsdk_1_1_gimbal.md)
* [mavsdk::Info](classmavsdk_1_1_info.md)
* [mavsdk::LogFiles](classmavsdk_1_1_log_files.md)
* [mavsdk::MavlinkPassthrough](classmavsdk_1_1_mavlink_passthrough.md)
* [mavsdk::Mavsdk](classmavsdk_1_1_mavsdk.md)
* [mavsdk::Mission](classmavsdk_1_1_mission.md)
* [mavsdk::MissionItem](classmavsdk_1_1_mission_item.md)
* [mavsdk::MissionRaw](classmavsdk_1_1_mission_raw.md)
* [mavsdk::Offboard](classmavsdk_1_1_offboard.md)
* [mavsdk::Param](classmavsdk_1_1_param.md)
* [mavsdk::PluginBase](classmavsdk_1_1_plugin_base.md)
* [mavsdk::System](classmavsdk_1_1_system.md)
* [mavsdk::Telemetry](classmavsdk_1_1_telemetry.md)

## Enumerations

Type | Description
--- | ---
enum [ConnectionResult](#namespacemavsdk_1a0bad93f6d037051ac3906a0bcc09f992) | Result type returned when adding a connection.
enum [ComponentType](#namespacemavsdk_1a20fe7f7c8312779a187017111bf33d12) | Component Types.

## Functions

Type | Name | Description
--- | --- | ---
const char * | [connection_result_str](#namespacemavsdk_1a59e8a165c1edafab6ab0c04df2c83679) (const [ConnectionResult](namespacemavsdk.md#namespacemavsdk_1a0bad93f6d037051ac3906a0bcc09f992) result) | Returns a human-readable English string for a ConnectionResult.
bool | [operator==](#namespacemavsdk_1a4b91fa858984dd10b4f745169a7c815a) (const [Camera::VideoStreamSettings](structmavsdk_1_1_camera_1_1_video_stream_settings.md) & lhs, const [Camera::VideoStreamSettings](structmavsdk_1_1_camera_1_1_video_stream_settings.md) & rhs) | Equal operator to compare two [Camera::VideoStreamSettings](structmavsdk_1_1_camera_1_1_video_stream_settings.md) objects.
std::ostream & | [operator<<](#namespacemavsdk_1a53ab7b39303999b5a1b5895cad3d670c) (std::ostream & str, [Camera::VideoStreamSettings](structmavsdk_1_1_camera_1_1_video_stream_settings.md) const & video_stream_settings) | Stream operator to print information about a [Camera::VideoStreamSettings](structmavsdk_1_1_camera_1_1_video_stream_settings.md).
bool | [operator==](#namespacemavsdk_1ae99c2da0ad5c58644f33e42183c0d6de) (const [Camera::VideoStreamInfo](structmavsdk_1_1_camera_1_1_video_stream_info.md) & lhs, const [Camera::VideoStreamInfo](structmavsdk_1_1_camera_1_1_video_stream_info.md) & rhs) | Equal operator to compare two [Camera::VideoStreamInfo](structmavsdk_1_1_camera_1_1_video_stream_info.md) objects.
std::ostream & | [operator<<](#namespacemavsdk_1a65e3a42fd4080dbf56b41327744c632f) (std::ostream & str, [Camera::VideoStreamInfo](structmavsdk_1_1_camera_1_1_video_stream_info.md) const & video_stream_info) | Stream operator to print information about a [Camera::VideoStreamInfo](structmavsdk_1_1_camera_1_1_video_stream_info.md).
std::ostream & | [operator<<](#namespacemavsdk_1ab725cd17112ca709dbfcdaec51d2a00e) (std::ostream & str, [Camera::VideoStreamInfo::Status](structmavsdk_1_1_camera_1_1_video_stream_info.md#structmavsdk_1_1_camera_1_1_video_stream_info_1a429e643fccbc559bc193dc8e2ae66ed7) const & video_stream_info_status) | Stream operator to print information about a [Camera::VideoStreamInfo::Status](structmavsdk_1_1_camera_1_1_video_stream_info.md#structmavsdk_1_1_camera_1_1_video_stream_info_1a429e643fccbc559bc193dc8e2ae66ed7).
bool | [operator==](#namespacemavsdk_1a6b1958328b5898997e3d86b8239ffccc) (const [Camera::CaptureInfo](structmavsdk_1_1_camera_1_1_capture_info.md) & lhs, const [Camera::CaptureInfo](structmavsdk_1_1_camera_1_1_capture_info.md) & rhs) | Equal operator to compare two [Camera::CaptureInfo](structmavsdk_1_1_camera_1_1_capture_info.md) objects.
std::ostream & | [operator<<](#namespacemavsdk_1ac09a7c2eb9ffff7432bd521380f74a26) (std::ostream & str, [Camera::CaptureInfo](structmavsdk_1_1_camera_1_1_capture_info.md) const & capture_info) | Stream operator to print information about a [Camera::CaptureInfo](structmavsdk_1_1_camera_1_1_capture_info.md).
bool | [operator==](#namespacemavsdk_1a173eabf041f819202fde27bbed651f5b) (const [Camera::CaptureInfo::Position](structmavsdk_1_1_camera_1_1_capture_info_1_1_position.md) & lhs, const [Camera::CaptureInfo::Position](structmavsdk_1_1_camera_1_1_capture_info_1_1_position.md) & rhs) | Equal operator to compare two [Camera::CaptureInfo::Position](structmavsdk_1_1_camera_1_1_capture_info_1_1_position.md) objects.
std::ostream & | [operator<<](#namespacemavsdk_1a4b54951b60e8f76bf0b5e636f6762853) (std::ostream & str, [Camera::CaptureInfo::Position](structmavsdk_1_1_camera_1_1_capture_info_1_1_position.md) const & position) | Stream operator to print information about a [Camera::CaptureInfo::Position](structmavsdk_1_1_camera_1_1_capture_info_1_1_position.md).
bool | [operator==](#namespacemavsdk_1a028cbcdf7965efa24296995727b3ba53) (const [Camera::CaptureInfo::Quaternion](structmavsdk_1_1_camera_1_1_capture_info_1_1_quaternion.md) & lhs, const [Camera::CaptureInfo::Quaternion](structmavsdk_1_1_camera_1_1_capture_info_1_1_quaternion.md) & rhs) | Equal operator to compare two [Camera::CaptureInfo::Quaternion](structmavsdk_1_1_camera_1_1_capture_info_1_1_quaternion.md) objects.
std::ostream & | [operator<<](#namespacemavsdk_1a65d6ae0f4fc11653e6670fc0c294d75c) (std::ostream & str, [Camera::CaptureInfo::Quaternion](structmavsdk_1_1_camera_1_1_capture_info_1_1_quaternion.md) const & quaternion) | Stream operator to print information about a [Camera::CaptureInfo::Quaternion](structmavsdk_1_1_camera_1_1_capture_info_1_1_quaternion.md).
bool | [operator==](#namespacemavsdk_1ade64639544aa662ca2b24e197f06fb5c) (const [Camera::CaptureInfo::EulerAngle](structmavsdk_1_1_camera_1_1_capture_info_1_1_euler_angle.md) & lhs, const [Camera::CaptureInfo::EulerAngle](structmavsdk_1_1_camera_1_1_capture_info_1_1_euler_angle.md) & rhs) | Equal operator to compare two [Camera::CaptureInfo::EulerAngle](structmavsdk_1_1_camera_1_1_capture_info_1_1_euler_angle.md) objects.
std::ostream & | [operator<<](#namespacemavsdk_1a7a7a978fe79c8f328c7d4952905da2cd) (std::ostream & str, [Camera::CaptureInfo::EulerAngle](structmavsdk_1_1_camera_1_1_capture_info_1_1_euler_angle.md) const & euler_angle) | Stream operator to print information about a [Camera::CaptureInfo::EulerAngle](structmavsdk_1_1_camera_1_1_capture_info_1_1_euler_angle.md).
bool | [operator==](#namespacemavsdk_1aea27aec45756fe4063540f6ae50f768d) (const [Camera::Status](structmavsdk_1_1_camera_1_1_status.md) & lhs, const [Camera::Status](structmavsdk_1_1_camera_1_1_status.md) & rhs) | Equal operator to compare two [Camera::Status](structmavsdk_1_1_camera_1_1_status.md) objects.
std::ostream & | [operator<<](#namespacemavsdk_1ac574bad245c49c3de6647d66f1bedbbe) (std::ostream & str, [Camera::Status](structmavsdk_1_1_camera_1_1_status.md) const & status) | Stream operator to print information about a [Camera::Status](structmavsdk_1_1_camera_1_1_status.md).
std::ostream & | [operator<<](#namespacemavsdk_1a8c0335660bfac6111e208b2cc16434fa) (std::ostream & str, [Camera::Status::StorageStatus](structmavsdk_1_1_camera_1_1_status.md#structmavsdk_1_1_camera_1_1_status_1ae4e4a1e5622e75cce5813ffdf2ffcc52) const & storage_status) | Stream operator to print information about a [Camera::Status::StorageStatus](structmavsdk_1_1_camera_1_1_status.md#structmavsdk_1_1_camera_1_1_status_1ae4e4a1e5622e75cce5813ffdf2ffcc52).
bool | [operator==](#namespacemavsdk_1a82f7289502d74b0821660aa7077ae59f) (const [Camera::Setting](structmavsdk_1_1_camera_1_1_setting.md) & lhs, const [Camera::Setting](structmavsdk_1_1_camera_1_1_setting.md) & rhs) | Equal operator to compare two [Camera::Setting](structmavsdk_1_1_camera_1_1_setting.md) objects.
std::ostream & | [operator<<](#namespacemavsdk_1adbff21782b5c2d9435b345bc527be581) (std::ostream & str, [Camera::Setting](structmavsdk_1_1_camera_1_1_setting.md) const & setting) | Stream operator to print information about a [Camera::Setting](structmavsdk_1_1_camera_1_1_setting.md).
bool | [operator==](#namespacemavsdk_1aba0b44fe6b7c2a7ca2fe705987f7cfc8) (const [Camera::Option](structmavsdk_1_1_camera_1_1_option.md) & lhs, const [Camera::Option](structmavsdk_1_1_camera_1_1_option.md) & rhs) | Equal operator to compare two [Camera::Option](structmavsdk_1_1_camera_1_1_option.md) objects.
std::ostream & | [operator<<](#namespacemavsdk_1ab05ee57d67e64f502927b48488009b5e) (std::ostream & str, [Camera::Option](structmavsdk_1_1_camera_1_1_option.md) const & option) | Stream operator to print information about a [Camera::Option](structmavsdk_1_1_camera_1_1_option.md).
bool | [operator==](#namespacemavsdk_1ac22e24d381007660cbcf5deb3ff4e81c) (const [Camera::SettingOptions](structmavsdk_1_1_camera_1_1_setting_options.md) & lhs, const [Camera::SettingOptions](structmavsdk_1_1_camera_1_1_setting_options.md) & rhs) | Equal operator to compare two [Camera::SettingOptions](structmavsdk_1_1_camera_1_1_setting_options.md) objects.
std::ostream & | [operator<<](#namespacemavsdk_1a56a292413ed3441ae4ab74c998b61686) (std::ostream & str, [Camera::SettingOptions](structmavsdk_1_1_camera_1_1_setting_options.md) const & setting_options) | Stream operator to print information about a [Camera::Option](structmavsdk_1_1_camera_1_1_option.md).
bool | [operator==](#namespacemavsdk_1a7dd59dabb4ce1a28a4b28d033415e00d) (const [MissionItem](classmavsdk_1_1_mission_item.md) & lhs, const [MissionItem](classmavsdk_1_1_mission_item.md) & rhs) | Equal operator to compare two [MissionItem](classmavsdk_1_1_mission_item.md) objects.
std::ostream & | [operator<<](#namespacemavsdk_1a285b7c8eee38fd978aea94f48d31b549) (std::ostream & str, [MissionItem](classmavsdk_1_1_mission_item.md) const & mission_item) | Stream operator to print infos about a [MissionItem](classmavsdk_1_1_mission_item.md).
std::ostream & | [operator<<](#namespacemavsdk_1ae2ef3a70228f55484d7cdb99b6f1d951) (std::ostream & str, [MissionItem::CameraAction](classmavsdk_1_1_mission_item.md#classmavsdk_1_1_mission_item_1a132fb8fb01a95f7da406d6691a699b33) const & camera_action) | Stream operator to print infos about a [MissionItem::CameraAction](classmavsdk_1_1_mission_item.md#classmavsdk_1_1_mission_item_1a132fb8fb01a95f7da406d6691a699b33).
bool | [operator==](#namespacemavsdk_1a8fffe4f649d09ed4e0bddb93aa760927) (const [Offboard::Attitude](structmavsdk_1_1_offboard_1_1_attitude.md) & lhs, const [Offboard::Attitude](structmavsdk_1_1_offboard_1_1_attitude.md) & rhs) | Equal operator to compare two [Offboard::Attitude](structmavsdk_1_1_offboard_1_1_attitude.md) objects.
bool | [operator==](#namespacemavsdk_1aa855b987ed2db4e060173cc7e56e99ac) (const [Offboard::AttitudeRate](structmavsdk_1_1_offboard_1_1_attitude_rate.md) & lhs, const [Offboard::AttitudeRate](structmavsdk_1_1_offboard_1_1_attitude_rate.md) & rhs) | Equal operator to compare two [Offboard::AttitudeRate](structmavsdk_1_1_offboard_1_1_attitude_rate.md) objects.
std::ostream & | [operator<<](#namespacemavsdk_1a3d762a768e0f21786e38305b9f7ef655) (std::ostream & str, [Offboard::Attitude](structmavsdk_1_1_offboard_1_1_attitude.md) const & attitude) | Stream operator to print information about a [Offboard::Attitude](structmavsdk_1_1_offboard_1_1_attitude.md).
std::ostream & | [operator<<](#namespacemavsdk_1af08833298b8e9d03a1fc1018573b4e23) (std::ostream & str, [Offboard::AttitudeRate](structmavsdk_1_1_offboard_1_1_attitude_rate.md) const & attitude_rate) | Stream operator to print information about a [Offboard::AttitudeRate](structmavsdk_1_1_offboard_1_1_attitude_rate.md).
bool | [operator==](#namespacemavsdk_1a2598ec5e427ecd3408b53636ac4cbafa) (const [Offboard::PositionNEDYaw](structmavsdk_1_1_offboard_1_1_position_n_e_d_yaw.md) & lhs, const [Offboard::PositionNEDYaw](structmavsdk_1_1_offboard_1_1_position_n_e_d_yaw.md) & rhs) | Equal operator to compare two [Offboard::PositionNEDYaw](structmavsdk_1_1_offboard_1_1_position_n_e_d_yaw.md) objects.
std::ostream & | [operator<<](#namespacemavsdk_1af53d7336622d62bacc686d4523a0e73c) (std::ostream & str, [Offboard::PositionNEDYaw](structmavsdk_1_1_offboard_1_1_position_n_e_d_yaw.md) const & position_ned_yaw) | Stream operator to print information about a [Offboard::PositionNEDYaw](structmavsdk_1_1_offboard_1_1_position_n_e_d_yaw.md).
bool | [operator==](#namespacemavsdk_1ab9227f4d8cdcc151ef5402a3cdbf435f) (const [Offboard::VelocityBodyYawspeed](structmavsdk_1_1_offboard_1_1_velocity_body_yawspeed.md) & lhs, const [Offboard::VelocityBodyYawspeed](structmavsdk_1_1_offboard_1_1_velocity_body_yawspeed.md) & rhs) | Equal operator to compare two [Offboard::VelocityBodyYawspeed](structmavsdk_1_1_offboard_1_1_velocity_body_yawspeed.md) objects.
std::ostream & | [operator<<](#namespacemavsdk_1abf2d76a08000245b4ea66aa0486c17f8) (std::ostream & str, [Offboard::VelocityBodyYawspeed](structmavsdk_1_1_offboard_1_1_velocity_body_yawspeed.md) const & velocity_body_yawspeed) | Stream operator to print information about a [Offboard::VelocityBodyYawspeed](structmavsdk_1_1_offboard_1_1_velocity_body_yawspeed.md).
bool | [operator==](#namespacemavsdk_1ab2170a8ed79eea8749c794dba578ec46) (const [Offboard::VelocityNEDYaw](structmavsdk_1_1_offboard_1_1_velocity_n_e_d_yaw.md) & lhs, const [Offboard::VelocityNEDYaw](structmavsdk_1_1_offboard_1_1_velocity_n_e_d_yaw.md) & rhs) | Equal operator to compare two [Offboard::VelocityNEDYaw](structmavsdk_1_1_offboard_1_1_velocity_n_e_d_yaw.md) objects.
std::ostream & | [operator<<](#namespacemavsdk_1a437c3579b70f077f836ffe8fd04c0a6a) (std::ostream & str, [Offboard::VelocityNEDYaw](structmavsdk_1_1_offboard_1_1_velocity_n_e_d_yaw.md) const & velocity_ned_yaw) | Stream operator to print information about a [Offboard::VelocityNEDYaw](structmavsdk_1_1_offboard_1_1_velocity_n_e_d_yaw.md).
bool | [operator==](#namespacemavsdk_1a2f38aaafc84b4b7f46fd33cbbf3b8cba) (const [Telemetry::PositionVelocityNED](structmavsdk_1_1_telemetry_1_1_position_velocity_n_e_d.md) & lhs, const [Telemetry::PositionVelocityNED](structmavsdk_1_1_telemetry_1_1_position_velocity_n_e_d.md) & rhs) | Equal operator to compare two [Telemetry::PositionVelocityNED](structmavsdk_1_1_telemetry_1_1_position_velocity_n_e_d.md) objects.
bool | [operator==](#namespacemavsdk_1a191d2a0c2c6e28c1f49afb4bc4fe9b87) (const [Telemetry::Position](structmavsdk_1_1_telemetry_1_1_position.md) & lhs, const [Telemetry::Position](structmavsdk_1_1_telemetry_1_1_position.md) & rhs) | Equal operator to compare two [Telemetry::Position](structmavsdk_1_1_telemetry_1_1_position.md) objects.
std::ostream & | [operator<<](#namespacemavsdk_1aadeb8f386d025e70f4a029fdac856a43) (std::ostream & str, [Telemetry::Position](structmavsdk_1_1_telemetry_1_1_position.md) const & position) | Stream operator to print information about a [Telemetry::Position](structmavsdk_1_1_telemetry_1_1_position.md).
std::ostream & | [operator<<](#namespacemavsdk_1ada8ebbf818db06d7a7e30190e5118737) (std::ostream & str, [Telemetry::PositionNED](structmavsdk_1_1_telemetry_1_1_position_n_e_d.md) const & position_ned) | Stream operator to print information about a [Telemetry::PositionNED](structmavsdk_1_1_telemetry_1_1_position_n_e_d.md).
std::ostream & | [operator<<](#namespacemavsdk_1acc9e7235b5fedb39afc23011bfb92ced) (std::ostream & str, [Telemetry::VelocityNED](structmavsdk_1_1_telemetry_1_1_velocity_n_e_d.md) const & velocity_ned) | Stream operator to print information about a [Telemetry::VelocityNED](structmavsdk_1_1_telemetry_1_1_velocity_n_e_d.md).
std::ostream & | [operator<<](#namespacemavsdk_1ab7c10218203267a603cf58e0f9df83ab) (std::ostream & str, [Telemetry::PositionVelocityNED](structmavsdk_1_1_telemetry_1_1_position_velocity_n_e_d.md) const & position_velocity_ned) | Stream operator to print information about a [Telemetry::PositionVelocityNED](structmavsdk_1_1_telemetry_1_1_position_velocity_n_e_d.md).
bool | [operator==](#namespacemavsdk_1afa0a77d20c18fc8c406a195ccd8403ce) (const [Telemetry::Health](structmavsdk_1_1_telemetry_1_1_health.md) & lhs, const [Telemetry::Health](structmavsdk_1_1_telemetry_1_1_health.md) & rhs) | Equal operator to compare two [Telemetry::Health](structmavsdk_1_1_telemetry_1_1_health.md) objects.
std::ostream & | [operator<<](#namespacemavsdk_1a1fd300074aa856860f3e34a188c60272) (std::ostream & str, [Telemetry::Health](structmavsdk_1_1_telemetry_1_1_health.md) const & health) | Stream operator to print information about a [Telemetry::Health](structmavsdk_1_1_telemetry_1_1_health.md).
bool | [operator==](#namespacemavsdk_1afb8fd460143b0b2cdd94182756b8ee02) (const [Telemetry::GPSInfo](structmavsdk_1_1_telemetry_1_1_g_p_s_info.md) & lhs, const [Telemetry::GPSInfo](structmavsdk_1_1_telemetry_1_1_g_p_s_info.md) & rhs) | Equal operator to compare two [Telemetry::GPSInfo](structmavsdk_1_1_telemetry_1_1_g_p_s_info.md) objects.
std::ostream & | [operator<<](#namespacemavsdk_1a27f1b3bce30accddfe5c874970853f29) (std::ostream & str, [Telemetry::GPSInfo](structmavsdk_1_1_telemetry_1_1_g_p_s_info.md) const & gps_info) | Stream operator to print information about a [Telemetry::GPSInfo](structmavsdk_1_1_telemetry_1_1_g_p_s_info.md).
bool | [operator==](#namespacemavsdk_1a80896a794103e69c5ca72aa47f4b9011) (const [Telemetry::Battery](structmavsdk_1_1_telemetry_1_1_battery.md) & lhs, const [Telemetry::Battery](structmavsdk_1_1_telemetry_1_1_battery.md) & rhs) | Equal operator to compare two [Telemetry::Battery](structmavsdk_1_1_telemetry_1_1_battery.md) objects.
std::ostream & | [operator<<](#namespacemavsdk_1a3254ebf618e006568cfc724a2969a3a5) (std::ostream & str, [Telemetry::Battery](structmavsdk_1_1_telemetry_1_1_battery.md) const & battery) | Stream operator to print information about a [Telemetry::Battery](structmavsdk_1_1_telemetry_1_1_battery.md).
bool | [operator==](#namespacemavsdk_1ada20caf18bf2781eb8f07117b247412d) (const [Telemetry::Quaternion](structmavsdk_1_1_telemetry_1_1_quaternion.md) & lhs, const [Telemetry::Quaternion](structmavsdk_1_1_telemetry_1_1_quaternion.md) & rhs) | Equal operator to compare two [Telemetry::Quaternion](structmavsdk_1_1_telemetry_1_1_quaternion.md) objects.
std::ostream & | [operator<<](#namespacemavsdk_1a74a1a53d8a08d5518f0b78e050c7fb36) (std::ostream & str, [Telemetry::Quaternion](structmavsdk_1_1_telemetry_1_1_quaternion.md) const & quaternion) | Stream operator to print information about a [Telemetry::Quaternion](structmavsdk_1_1_telemetry_1_1_quaternion.md).
bool | [operator==](#namespacemavsdk_1a1f9d8c8f29bb52e305784093433aedeb) (const [Telemetry::EulerAngle](structmavsdk_1_1_telemetry_1_1_euler_angle.md) & lhs, const [Telemetry::EulerAngle](structmavsdk_1_1_telemetry_1_1_euler_angle.md) & rhs) | Equal operator to compare two [Telemetry::EulerAngle](structmavsdk_1_1_telemetry_1_1_euler_angle.md) objects.
std::ostream & | [operator<<](#namespacemavsdk_1ad12d5557f83f327450850dca95706f9d) (std::ostream & str, [Telemetry::EulerAngle](structmavsdk_1_1_telemetry_1_1_euler_angle.md) const & euler_angle) | Stream operator to print information about a [Telemetry::EulerAngle](structmavsdk_1_1_telemetry_1_1_euler_angle.md).
bool | [operator==](#namespacemavsdk_1a79b26da66253b9ac9a12f672ed9fef51) (const [Telemetry::GroundSpeedNED](structmavsdk_1_1_telemetry_1_1_ground_speed_n_e_d.md) & lhs, const [Telemetry::GroundSpeedNED](structmavsdk_1_1_telemetry_1_1_ground_speed_n_e_d.md) & rhs) | Equal operator to compare two [Telemetry::GroundSpeedNED](structmavsdk_1_1_telemetry_1_1_ground_speed_n_e_d.md) objects.
std::ostream & | [operator<<](#namespacemavsdk_1adbada9caa34e673e1f3b0e58d18a5f7c) (std::ostream & str, [Telemetry::GroundSpeedNED](structmavsdk_1_1_telemetry_1_1_ground_speed_n_e_d.md) const & ground_speed) | Stream operator to print information about a [Telemetry::GroundSpeedNED](structmavsdk_1_1_telemetry_1_1_ground_speed_n_e_d.md).
bool | [operator==](#namespacemavsdk_1aa0d7b6aae3953c3e589ce4b8d5aaa198) (const [Telemetry::RCStatus](structmavsdk_1_1_telemetry_1_1_r_c_status.md) & lhs, const [Telemetry::RCStatus](structmavsdk_1_1_telemetry_1_1_r_c_status.md) & rhs) | Equal operator to compare two [Telemetry::RCStatus](structmavsdk_1_1_telemetry_1_1_r_c_status.md) objects.
std::ostream & | [operator<<](#namespacemavsdk_1a855a444d9281f175fb6d3dcbac6c6b20) (std::ostream & str, [Telemetry::RCStatus](structmavsdk_1_1_telemetry_1_1_r_c_status.md) const & rc_status) | Stream operator to print information about a [Telemetry::RCStatus](structmavsdk_1_1_telemetry_1_1_r_c_status.md).
std::ostream & | [operator<<](#namespacemavsdk_1aa2e1a513965c26ea6c7a23789eb3169a) (std::ostream & str, [Telemetry::StatusText](structmavsdk_1_1_telemetry_1_1_status_text.md) const & status_text) | Stream operator to print information about a [Telemetry::StatusText](structmavsdk_1_1_telemetry_1_1_status_text.md).

## Enumeration Type Documentation


### enum ConnectionResult {#namespacemavsdk_1a0bad93f6d037051ac3906a0bcc09f992}

```
#include: connection_result.h
```


Result type returned when adding a connection.

**Note**: [Mavsdk](classmavsdk_1_1_mavsdk.md) does not throw exceptions. Instead a result of this type will be returned when you add a connection: add_udp_connection().

Value | Description
--- | ---
<span id="namespacemavsdk_1a0bad93f6d037051ac3906a0bcc09f992ad0749aaba8b833466dfcbb0428e4f89c"></span> `SUCCESS` | Connection succeeded. 
<span id="namespacemavsdk_1a0bad93f6d037051ac3906a0bcc09f992a070a0fb40f6c308ab544b227660aadff"></span> `TIMEOUT` | Connection timed out. 
<span id="namespacemavsdk_1a0bad93f6d037051ac3906a0bcc09f992aac87548d79aa92c60dcfac06ae83e5ad"></span> `SOCKET_ERROR` | Socket error. 
<span id="namespacemavsdk_1a0bad93f6d037051ac3906a0bcc09f992af69a41125696a14c45a8182ce7ba83a7"></span> `BIND_ERROR` | Bind error. 
<span id="namespacemavsdk_1a0bad93f6d037051ac3906a0bcc09f992a20766ec998922f65e7ac718b7a9b7a22"></span> `SOCKET_CONNECTION_ERROR` | Socket connection error. 
<span id="namespacemavsdk_1a0bad93f6d037051ac3906a0bcc09f992ac77f1f09dab2c0c9980fca7cfae02518"></span> `CONNECTION_ERROR` | Connection error. 
<span id="namespacemavsdk_1a0bad93f6d037051ac3906a0bcc09f992a3e860a081575fc82cc7b6ed2ca602947"></span> `NOT_IMPLEMENTED` | Connection type not implemented. 
<span id="namespacemavsdk_1a0bad93f6d037051ac3906a0bcc09f992a222a5d8795464ca9a47b49daf1357538"></span> `SYSTEM_NOT_CONNECTED` | No system is connected. 
<span id="namespacemavsdk_1a0bad93f6d037051ac3906a0bcc09f992a5a426189f0eb9043da73058f959c2ba1"></span> `SYSTEM_BUSY` | System is busy. 
<span id="namespacemavsdk_1a0bad93f6d037051ac3906a0bcc09f992a6fa4dbf368cea972db8d9156799d5dbe"></span> `COMMAND_DENIED` | Command is denied. 
<span id="namespacemavsdk_1a0bad93f6d037051ac3906a0bcc09f992a588cf56f08269878b055227a8490de67"></span> `DESTINATION_IP_UNKNOWN` | Connection IP is unknown. 
<span id="namespacemavsdk_1a0bad93f6d037051ac3906a0bcc09f992a9532aa7fe8e205a02479a2e43d05f6b1"></span> `CONNECTIONS_EXHAUSTED` | Connections exhausted. 
<span id="namespacemavsdk_1a0bad93f6d037051ac3906a0bcc09f992a269972fd1df83e8f423abead920f8780"></span> `CONNECTION_URL_INVALID` | URL invalid. 
<span id="namespacemavsdk_1a0bad93f6d037051ac3906a0bcc09f992a70b509145d288ea71f707a45fa6538bb"></span> `BAUDRATE_UNKNOWN` | Baudrate unknown. 

### enum ComponentType {#namespacemavsdk_1a20fe7f7c8312779a187017111bf33d12}

```
#include: system.h
```


Component Types.


Value | Description
--- | ---
<span id="namespacemavsdk_1a20fe7f7c8312779a187017111bf33d12a7b0b07ec8293a25730d05980f5bf1946"></span> `UNKNOWN` |  
<span id="namespacemavsdk_1a20fe7f7c8312779a187017111bf33d12a092366b39e29ed2f2a5429b0bf82023f"></span> `AUTOPILOT` |  
<span id="namespacemavsdk_1a20fe7f7c8312779a187017111bf33d12a2950492ed394e5c5bdf9b0eed9f5737b"></span> `CAMERA` |  
<span id="namespacemavsdk_1a20fe7f7c8312779a187017111bf33d12a9683a40d8c6ef6e539a71a3c12f7aee3"></span> `GIMBAL` |  

## Function Documentation


### connection_result_str() {#namespacemavsdk_1a59e8a165c1edafab6ab0c04df2c83679}

```
#include: connection_result.h
```
```cpp
const char* mavsdk::connection_result_str(const ConnectionResult result)
```


Returns a human-readable English string for a ConnectionResult.


**Parameters**

* const [ConnectionResult](namespacemavsdk.md#namespacemavsdk_1a0bad93f6d037051ac3906a0bcc09f992) **result** - The enum value for which a human readable string is required.

**Returns**

&emsp;const char * - Human readable string for the ConnectionResult.

### operator==() {#namespacemavsdk_1a4b91fa858984dd10b4f745169a7c815a}

```
#include: plugins/camera/camera.h
```
```cpp
bool mavsdk::operator==(const Camera::VideoStreamSettings &lhs, const Camera::VideoStreamSettings &rhs)
```


Equal operator to compare two [Camera::VideoStreamSettings](structmavsdk_1_1_camera_1_1_video_stream_settings.md) objects.


**Parameters**

* const [Camera::VideoStreamSettings](structmavsdk_1_1_camera_1_1_video_stream_settings.md)& **lhs** - 
* const [Camera::VideoStreamSettings](structmavsdk_1_1_camera_1_1_video_stream_settings.md)& **rhs** - 

**Returns**

&emsp;bool - `true` if items are equal.

### operator<<() {#namespacemavsdk_1a53ab7b39303999b5a1b5895cad3d670c}

```
#include: plugins/camera/camera.h
```
```cpp
std::ostream& mavsdk::operator<<(std::ostream &str, Camera::VideoStreamSettings const &video_stream_settings)
```


Stream operator to print information about a [Camera::VideoStreamSettings](structmavsdk_1_1_camera_1_1_video_stream_settings.md).


**Parameters**

* std::ostream& **str** - 
* [Camera::VideoStreamSettings](structmavsdk_1_1_camera_1_1_video_stream_settings.md) const& **video_stream_settings** - 

**Returns**

&emsp;std::ostream & - A reference to the stream.

### operator==() {#namespacemavsdk_1ae99c2da0ad5c58644f33e42183c0d6de}

```
#include: plugins/camera/camera.h
```
```cpp
bool mavsdk::operator==(const Camera::VideoStreamInfo &lhs, const Camera::VideoStreamInfo &rhs)
```


Equal operator to compare two [Camera::VideoStreamInfo](structmavsdk_1_1_camera_1_1_video_stream_info.md) objects.


**Parameters**

* const [Camera::VideoStreamInfo](structmavsdk_1_1_camera_1_1_video_stream_info.md)& **lhs** - 
* const [Camera::VideoStreamInfo](structmavsdk_1_1_camera_1_1_video_stream_info.md)& **rhs** - 

**Returns**

&emsp;bool - `true` if items are equal.

### operator<<() {#namespacemavsdk_1a65e3a42fd4080dbf56b41327744c632f}

```
#include: plugins/camera/camera.h
```
```cpp
std::ostream& mavsdk::operator<<(std::ostream &str, Camera::VideoStreamInfo const &video_stream_info)
```


Stream operator to print information about a [Camera::VideoStreamInfo](structmavsdk_1_1_camera_1_1_video_stream_info.md).


**Parameters**

* std::ostream& **str** - 
* [Camera::VideoStreamInfo](structmavsdk_1_1_camera_1_1_video_stream_info.md) const& **video_stream_info** - 

**Returns**

&emsp;std::ostream & - A reference to the stream.

### operator<<() {#namespacemavsdk_1ab725cd17112ca709dbfcdaec51d2a00e}

```
#include: plugins/camera/camera.h
```
```cpp
std::ostream& mavsdk::operator<<(std::ostream &str, Camera::VideoStreamInfo::Status const &video_stream_info_status)
```


Stream operator to print information about a [Camera::VideoStreamInfo::Status](structmavsdk_1_1_camera_1_1_video_stream_info.md#structmavsdk_1_1_camera_1_1_video_stream_info_1a429e643fccbc559bc193dc8e2ae66ed7).


**Parameters**

* std::ostream& **str** - 
* [Camera::VideoStreamInfo::Status](structmavsdk_1_1_camera_1_1_video_stream_info.md#structmavsdk_1_1_camera_1_1_video_stream_info_1a429e643fccbc559bc193dc8e2ae66ed7) const& **video_stream_info_status** - 

**Returns**

&emsp;std::ostream & - A reference to the stream.

### operator==() {#namespacemavsdk_1a6b1958328b5898997e3d86b8239ffccc}

```
#include: plugins/camera/camera.h
```
```cpp
bool mavsdk::operator==(const Camera::CaptureInfo &lhs, const Camera::CaptureInfo &rhs)
```


Equal operator to compare two [Camera::CaptureInfo](structmavsdk_1_1_camera_1_1_capture_info.md) objects.


**Parameters**

* const [Camera::CaptureInfo](structmavsdk_1_1_camera_1_1_capture_info.md)& **lhs** - 
* const [Camera::CaptureInfo](structmavsdk_1_1_camera_1_1_capture_info.md)& **rhs** - 

**Returns**

&emsp;bool - `true` if items are equal.

### operator<<() {#namespacemavsdk_1ac09a7c2eb9ffff7432bd521380f74a26}

```
#include: plugins/camera/camera.h
```
```cpp
std::ostream& mavsdk::operator<<(std::ostream &str, Camera::CaptureInfo const &capture_info)
```


Stream operator to print information about a [Camera::CaptureInfo](structmavsdk_1_1_camera_1_1_capture_info.md).


**Parameters**

* std::ostream& **str** - 
* [Camera::CaptureInfo](structmavsdk_1_1_camera_1_1_capture_info.md) const& **capture_info** - 

**Returns**

&emsp;std::ostream & - A reference to the stream.

### operator==() {#namespacemavsdk_1a173eabf041f819202fde27bbed651f5b}

```
#include: plugins/camera/camera.h
```
```cpp
bool mavsdk::operator==(const Camera::CaptureInfo::Position &lhs, const Camera::CaptureInfo::Position &rhs)
```


Equal operator to compare two [Camera::CaptureInfo::Position](structmavsdk_1_1_camera_1_1_capture_info_1_1_position.md) objects.


**Parameters**

* const [Camera::CaptureInfo::Position](structmavsdk_1_1_camera_1_1_capture_info_1_1_position.md)& **lhs** - 
* const [Camera::CaptureInfo::Position](structmavsdk_1_1_camera_1_1_capture_info_1_1_position.md)& **rhs** - 

**Returns**

&emsp;bool - `true` if items are equal.

### operator<<() {#namespacemavsdk_1a4b54951b60e8f76bf0b5e636f6762853}

```
#include: plugins/camera/camera.h
```
```cpp
std::ostream& mavsdk::operator<<(std::ostream &str, Camera::CaptureInfo::Position const &position)
```


Stream operator to print information about a [Camera::CaptureInfo::Position](structmavsdk_1_1_camera_1_1_capture_info_1_1_position.md).


**Parameters**

* std::ostream& **str** - 
* [Camera::CaptureInfo::Position](structmavsdk_1_1_camera_1_1_capture_info_1_1_position.md) const& **position** - 

**Returns**

&emsp;std::ostream & - A reference to the stream.

### operator==() {#namespacemavsdk_1a028cbcdf7965efa24296995727b3ba53}

```
#include: plugins/camera/camera.h
```
```cpp
bool mavsdk::operator==(const Camera::CaptureInfo::Quaternion &lhs, const Camera::CaptureInfo::Quaternion &rhs)
```


Equal operator to compare two [Camera::CaptureInfo::Quaternion](structmavsdk_1_1_camera_1_1_capture_info_1_1_quaternion.md) objects.


**Parameters**

* const [Camera::CaptureInfo::Quaternion](structmavsdk_1_1_camera_1_1_capture_info_1_1_quaternion.md)& **lhs** - 
* const [Camera::CaptureInfo::Quaternion](structmavsdk_1_1_camera_1_1_capture_info_1_1_quaternion.md)& **rhs** - 

**Returns**

&emsp;bool - `true` if items are equal.

### operator<<() {#namespacemavsdk_1a65d6ae0f4fc11653e6670fc0c294d75c}

```
#include: plugins/camera/camera.h
```
```cpp
std::ostream& mavsdk::operator<<(std::ostream &str, Camera::CaptureInfo::Quaternion const &quaternion)
```


Stream operator to print information about a [Camera::CaptureInfo::Quaternion](structmavsdk_1_1_camera_1_1_capture_info_1_1_quaternion.md).


**Parameters**

* std::ostream& **str** - 
* [Camera::CaptureInfo::Quaternion](structmavsdk_1_1_camera_1_1_capture_info_1_1_quaternion.md) const& **quaternion** - 

**Returns**

&emsp;std::ostream & - A reference to the stream.

### operator==() {#namespacemavsdk_1ade64639544aa662ca2b24e197f06fb5c}

```
#include: plugins/camera/camera.h
```
```cpp
bool mavsdk::operator==(const Camera::CaptureInfo::EulerAngle &lhs, const Camera::CaptureInfo::EulerAngle &rhs)
```


Equal operator to compare two [Camera::CaptureInfo::EulerAngle](structmavsdk_1_1_camera_1_1_capture_info_1_1_euler_angle.md) objects.


**Parameters**

* const [Camera::CaptureInfo::EulerAngle](structmavsdk_1_1_camera_1_1_capture_info_1_1_euler_angle.md)& **lhs** - 
* const [Camera::CaptureInfo::EulerAngle](structmavsdk_1_1_camera_1_1_capture_info_1_1_euler_angle.md)& **rhs** - 

**Returns**

&emsp;bool - `true` if items are equal.

### operator<<() {#namespacemavsdk_1a7a7a978fe79c8f328c7d4952905da2cd}

```
#include: plugins/camera/camera.h
```
```cpp
std::ostream& mavsdk::operator<<(std::ostream &str, Camera::CaptureInfo::EulerAngle const &euler_angle)
```


Stream operator to print information about a [Camera::CaptureInfo::EulerAngle](structmavsdk_1_1_camera_1_1_capture_info_1_1_euler_angle.md).


**Parameters**

* std::ostream& **str** - 
* [Camera::CaptureInfo::EulerAngle](structmavsdk_1_1_camera_1_1_capture_info_1_1_euler_angle.md) const& **euler_angle** - 

**Returns**

&emsp;std::ostream & - A reference to the stream.

### operator==() {#namespacemavsdk_1aea27aec45756fe4063540f6ae50f768d}

```
#include: plugins/camera/camera.h
```
```cpp
bool mavsdk::operator==(const Camera::Status &lhs, const Camera::Status &rhs)
```


Equal operator to compare two [Camera::Status](structmavsdk_1_1_camera_1_1_status.md) objects.


**Parameters**

* const [Camera::Status](structmavsdk_1_1_camera_1_1_status.md)& **lhs** - 
* const [Camera::Status](structmavsdk_1_1_camera_1_1_status.md)& **rhs** - 

**Returns**

&emsp;bool - `true` if items are equal.

### operator<<() {#namespacemavsdk_1ac574bad245c49c3de6647d66f1bedbbe}

```
#include: plugins/camera/camera.h
```
```cpp
std::ostream& mavsdk::operator<<(std::ostream &str, Camera::Status const &status)
```


Stream operator to print information about a [Camera::Status](structmavsdk_1_1_camera_1_1_status.md).


**Parameters**

* std::ostream& **str** - 
* [Camera::Status](structmavsdk_1_1_camera_1_1_status.md) const& **status** - 

**Returns**

&emsp;std::ostream & - A reference to the stream.

### operator<<() {#namespacemavsdk_1a8c0335660bfac6111e208b2cc16434fa}

```
#include: plugins/camera/camera.h
```
```cpp
std::ostream& mavsdk::operator<<(std::ostream &str, Camera::Status::StorageStatus const &storage_status)
```


Stream operator to print information about a [Camera::Status::StorageStatus](structmavsdk_1_1_camera_1_1_status.md#structmavsdk_1_1_camera_1_1_status_1ae4e4a1e5622e75cce5813ffdf2ffcc52).


**Parameters**

* std::ostream& **str** - 
* [Camera::Status::StorageStatus](structmavsdk_1_1_camera_1_1_status.md#structmavsdk_1_1_camera_1_1_status_1ae4e4a1e5622e75cce5813ffdf2ffcc52) const& **storage_status** - 

**Returns**

&emsp;std::ostream & - A reference to the stream.

### operator==() {#namespacemavsdk_1a82f7289502d74b0821660aa7077ae59f}

```
#include: plugins/camera/camera.h
```
```cpp
bool mavsdk::operator==(const Camera::Setting &lhs, const Camera::Setting &rhs)
```


Equal operator to compare two [Camera::Setting](structmavsdk_1_1_camera_1_1_setting.md) objects.


**Parameters**

* const [Camera::Setting](structmavsdk_1_1_camera_1_1_setting.md)& **lhs** - 
* const [Camera::Setting](structmavsdk_1_1_camera_1_1_setting.md)& **rhs** - 

**Returns**

&emsp;bool - `true` if items are equal.

### operator<<() {#namespacemavsdk_1adbff21782b5c2d9435b345bc527be581}

```
#include: plugins/camera/camera.h
```
```cpp
std::ostream& mavsdk::operator<<(std::ostream &str, Camera::Setting const &setting)
```


Stream operator to print information about a [Camera::Setting](structmavsdk_1_1_camera_1_1_setting.md).


**Parameters**

* std::ostream& **str** - 
* [Camera::Setting](structmavsdk_1_1_camera_1_1_setting.md) const& **setting** - 

**Returns**

&emsp;std::ostream & - A reference to the stream.

### operator==() {#namespacemavsdk_1aba0b44fe6b7c2a7ca2fe705987f7cfc8}

```
#include: plugins/camera/camera.h
```
```cpp
bool mavsdk::operator==(const Camera::Option &lhs, const Camera::Option &rhs)
```


Equal operator to compare two [Camera::Option](structmavsdk_1_1_camera_1_1_option.md) objects.


**Parameters**

* const [Camera::Option](structmavsdk_1_1_camera_1_1_option.md)& **lhs** - 
* const [Camera::Option](structmavsdk_1_1_camera_1_1_option.md)& **rhs** - 

**Returns**

&emsp;bool - `true` if items are equal.

### operator<<() {#namespacemavsdk_1ab05ee57d67e64f502927b48488009b5e}

```
#include: plugins/camera/camera.h
```
```cpp
std::ostream& mavsdk::operator<<(std::ostream &str, Camera::Option const &option)
```


Stream operator to print information about a [Camera::Option](structmavsdk_1_1_camera_1_1_option.md).


**Parameters**

* std::ostream& **str** - 
* [Camera::Option](structmavsdk_1_1_camera_1_1_option.md) const& **option** - 

**Returns**

&emsp;std::ostream & - A reference to the stream.

### operator==() {#namespacemavsdk_1ac22e24d381007660cbcf5deb3ff4e81c}

```
#include: plugins/camera/camera.h
```
```cpp
bool mavsdk::operator==(const Camera::SettingOptions &lhs, const Camera::SettingOptions &rhs)
```


Equal operator to compare two [Camera::SettingOptions](structmavsdk_1_1_camera_1_1_setting_options.md) objects.


**Parameters**

* const [Camera::SettingOptions](structmavsdk_1_1_camera_1_1_setting_options.md)& **lhs** - 
* const [Camera::SettingOptions](structmavsdk_1_1_camera_1_1_setting_options.md)& **rhs** - 

**Returns**

&emsp;bool - `true` if items are equal.

### operator<<() {#namespacemavsdk_1a56a292413ed3441ae4ab74c998b61686}

```
#include: plugins/camera/camera.h
```
```cpp
std::ostream& mavsdk::operator<<(std::ostream &str, Camera::SettingOptions const &setting_options)
```


Stream operator to print information about a [Camera::Option](structmavsdk_1_1_camera_1_1_option.md).


**Parameters**

* std::ostream& **str** - 
* [Camera::SettingOptions](structmavsdk_1_1_camera_1_1_setting_options.md) const& **setting_options** - 

**Returns**

&emsp;std::ostream & - A reference to the stream.

### operator==() {#namespacemavsdk_1a7dd59dabb4ce1a28a4b28d033415e00d}

```
#include: plugins/mission/mission_item.h
```
```cpp
bool mavsdk::operator==(const MissionItem &lhs, const MissionItem &rhs)
```


Equal operator to compare two [MissionItem](classmavsdk_1_1_mission_item.md) objects.


**Parameters**

* const [MissionItem](classmavsdk_1_1_mission_item.md)& **lhs** - 
* const [MissionItem](classmavsdk_1_1_mission_item.md)& **rhs** - 

**Returns**

&emsp;bool - `true` if items are equal.

### operator<<() {#namespacemavsdk_1a285b7c8eee38fd978aea94f48d31b549}

```
#include: plugins/mission/mission_item.h
```
```cpp
std::ostream& mavsdk::operator<<(std::ostream &str, MissionItem const &mission_item)
```


Stream operator to print infos about a [MissionItem](classmavsdk_1_1_mission_item.md).


**Parameters**

* std::ostream& **str** - 
* [MissionItem](classmavsdk_1_1_mission_item.md) const& **mission_item** - 

**Returns**

&emsp;std::ostream & - A reference to the stream.

### operator<<() {#namespacemavsdk_1ae2ef3a70228f55484d7cdb99b6f1d951}

```
#include: plugins/mission/mission_item.h
```
```cpp
std::ostream& mavsdk::operator<<(std::ostream &str, MissionItem::CameraAction const &camera_action)
```


Stream operator to print infos about a [MissionItem::CameraAction](classmavsdk_1_1_mission_item.md#classmavsdk_1_1_mission_item_1a132fb8fb01a95f7da406d6691a699b33).


**Parameters**

* std::ostream& **str** - 
* [MissionItem::CameraAction](classmavsdk_1_1_mission_item.md#classmavsdk_1_1_mission_item_1a132fb8fb01a95f7da406d6691a699b33) const& **camera_action** - 

**Returns**

&emsp;std::ostream & - A reference to the stream.

### operator==() {#namespacemavsdk_1a8fffe4f649d09ed4e0bddb93aa760927}

```
#include: plugins/offboard/offboard.h
```
```cpp
bool mavsdk::operator==(const Offboard::Attitude &lhs, const Offboard::Attitude &rhs)
```


Equal operator to compare two [Offboard::Attitude](structmavsdk_1_1_offboard_1_1_attitude.md) objects.


**Parameters**

* const [Offboard::Attitude](structmavsdk_1_1_offboard_1_1_attitude.md)& **lhs** - 
* const [Offboard::Attitude](structmavsdk_1_1_offboard_1_1_attitude.md)& **rhs** - 

**Returns**

&emsp;bool - `true` if items are equal.

### operator==() {#namespacemavsdk_1aa855b987ed2db4e060173cc7e56e99ac}

```
#include: plugins/offboard/offboard.h
```
```cpp
bool mavsdk::operator==(const Offboard::AttitudeRate &lhs, const Offboard::AttitudeRate &rhs)
```


Equal operator to compare two [Offboard::AttitudeRate](structmavsdk_1_1_offboard_1_1_attitude_rate.md) objects.


**Parameters**

* const [Offboard::AttitudeRate](structmavsdk_1_1_offboard_1_1_attitude_rate.md)& **lhs** - 
* const [Offboard::AttitudeRate](structmavsdk_1_1_offboard_1_1_attitude_rate.md)& **rhs** - 

**Returns**

&emsp;bool - `true` if items are equal.

### operator<<() {#namespacemavsdk_1a3d762a768e0f21786e38305b9f7ef655}

```
#include: plugins/offboard/offboard.h
```
```cpp
std::ostream& mavsdk::operator<<(std::ostream &str, Offboard::Attitude const &attitude)
```


Stream operator to print information about a [Offboard::Attitude](structmavsdk_1_1_offboard_1_1_attitude.md).


**Parameters**

* std::ostream& **str** - 
* [Offboard::Attitude](structmavsdk_1_1_offboard_1_1_attitude.md) const& **attitude** - 

**Returns**

&emsp;std::ostream & - A reference to the stream.

### operator<<() {#namespacemavsdk_1af08833298b8e9d03a1fc1018573b4e23}

```
#include: plugins/offboard/offboard.h
```
```cpp
std::ostream& mavsdk::operator<<(std::ostream &str, Offboard::AttitudeRate const &attitude_rate)
```


Stream operator to print information about a [Offboard::AttitudeRate](structmavsdk_1_1_offboard_1_1_attitude_rate.md).


**Parameters**

* std::ostream& **str** - 
* [Offboard::AttitudeRate](structmavsdk_1_1_offboard_1_1_attitude_rate.md) const& **attitude_rate** - 

**Returns**

&emsp;std::ostream & - A reference to the stream.

### operator==() {#namespacemavsdk_1a2598ec5e427ecd3408b53636ac4cbafa}

```
#include: plugins/offboard/offboard.h
```
```cpp
bool mavsdk::operator==(const Offboard::PositionNEDYaw &lhs, const Offboard::PositionNEDYaw &rhs)
```


Equal operator to compare two [Offboard::PositionNEDYaw](structmavsdk_1_1_offboard_1_1_position_n_e_d_yaw.md) objects.


**Parameters**

* const [Offboard::PositionNEDYaw](structmavsdk_1_1_offboard_1_1_position_n_e_d_yaw.md)& **lhs** - 
* const [Offboard::PositionNEDYaw](structmavsdk_1_1_offboard_1_1_position_n_e_d_yaw.md)& **rhs** - 

**Returns**

&emsp;bool - `true` if items are equal.

### operator<<() {#namespacemavsdk_1af53d7336622d62bacc686d4523a0e73c}

```
#include: plugins/offboard/offboard.h
```
```cpp
std::ostream& mavsdk::operator<<(std::ostream &str, Offboard::PositionNEDYaw const &position_ned_yaw)
```


Stream operator to print information about a [Offboard::PositionNEDYaw](structmavsdk_1_1_offboard_1_1_position_n_e_d_yaw.md).


**Parameters**

* std::ostream& **str** - 
* [Offboard::PositionNEDYaw](structmavsdk_1_1_offboard_1_1_position_n_e_d_yaw.md) const& **position_ned_yaw** - 

**Returns**

&emsp;std::ostream & - A reference to the stream.

### operator==() {#namespacemavsdk_1ab9227f4d8cdcc151ef5402a3cdbf435f}

```
#include: plugins/offboard/offboard.h
```
```cpp
bool mavsdk::operator==(const Offboard::VelocityBodyYawspeed &lhs, const Offboard::VelocityBodyYawspeed &rhs)
```


Equal operator to compare two [Offboard::VelocityBodyYawspeed](structmavsdk_1_1_offboard_1_1_velocity_body_yawspeed.md) objects.


**Parameters**

* const [Offboard::VelocityBodyYawspeed](structmavsdk_1_1_offboard_1_1_velocity_body_yawspeed.md)& **lhs** - 
* const [Offboard::VelocityBodyYawspeed](structmavsdk_1_1_offboard_1_1_velocity_body_yawspeed.md)& **rhs** - 

**Returns**

&emsp;bool - `true` if items are equal.

### operator<<() {#namespacemavsdk_1abf2d76a08000245b4ea66aa0486c17f8}

```
#include: plugins/offboard/offboard.h
```
```cpp
std::ostream& mavsdk::operator<<(std::ostream &str, Offboard::VelocityBodyYawspeed const &velocity_body_yawspeed)
```


Stream operator to print information about a [Offboard::VelocityBodyYawspeed](structmavsdk_1_1_offboard_1_1_velocity_body_yawspeed.md).


**Parameters**

* std::ostream& **str** - 
* [Offboard::VelocityBodyYawspeed](structmavsdk_1_1_offboard_1_1_velocity_body_yawspeed.md) const& **velocity_body_yawspeed** - 

**Returns**

&emsp;std::ostream & - A reference to the stream.

### operator==() {#namespacemavsdk_1ab2170a8ed79eea8749c794dba578ec46}

```
#include: plugins/offboard/offboard.h
```
```cpp
bool mavsdk::operator==(const Offboard::VelocityNEDYaw &lhs, const Offboard::VelocityNEDYaw &rhs)
```


Equal operator to compare two [Offboard::VelocityNEDYaw](structmavsdk_1_1_offboard_1_1_velocity_n_e_d_yaw.md) objects.


**Parameters**

* const [Offboard::VelocityNEDYaw](structmavsdk_1_1_offboard_1_1_velocity_n_e_d_yaw.md)& **lhs** - 
* const [Offboard::VelocityNEDYaw](structmavsdk_1_1_offboard_1_1_velocity_n_e_d_yaw.md)& **rhs** - 

**Returns**

&emsp;bool - `true` if items are equal.

### operator<<() {#namespacemavsdk_1a437c3579b70f077f836ffe8fd04c0a6a}

```
#include: plugins/offboard/offboard.h
```
```cpp
std::ostream& mavsdk::operator<<(std::ostream &str, Offboard::VelocityNEDYaw const &velocity_ned_yaw)
```


Stream operator to print information about a [Offboard::VelocityNEDYaw](structmavsdk_1_1_offboard_1_1_velocity_n_e_d_yaw.md).


**Parameters**

* std::ostream& **str** - 
* [Offboard::VelocityNEDYaw](structmavsdk_1_1_offboard_1_1_velocity_n_e_d_yaw.md) const& **velocity_ned_yaw** - 

**Returns**

&emsp;std::ostream & - A reference to the stream.

### operator==() {#namespacemavsdk_1a2f38aaafc84b4b7f46fd33cbbf3b8cba}

```
#include: plugins/telemetry/telemetry.h
```
```cpp
bool mavsdk::operator==(const Telemetry::PositionVelocityNED &lhs, const Telemetry::PositionVelocityNED &rhs)
```


Equal operator to compare two [Telemetry::PositionVelocityNED](structmavsdk_1_1_telemetry_1_1_position_velocity_n_e_d.md) objects.


**Parameters**

* const [Telemetry::PositionVelocityNED](structmavsdk_1_1_telemetry_1_1_position_velocity_n_e_d.md)& **lhs** - 
* const [Telemetry::PositionVelocityNED](structmavsdk_1_1_telemetry_1_1_position_velocity_n_e_d.md)& **rhs** - 

**Returns**

&emsp;bool - `true` if items are equal.

### operator==() {#namespacemavsdk_1a191d2a0c2c6e28c1f49afb4bc4fe9b87}

```
#include: plugins/telemetry/telemetry.h
```
```cpp
bool mavsdk::operator==(const Telemetry::Position &lhs, const Telemetry::Position &rhs)
```


Equal operator to compare two [Telemetry::Position](structmavsdk_1_1_telemetry_1_1_position.md) objects.


**Parameters**

* const [Telemetry::Position](structmavsdk_1_1_telemetry_1_1_position.md)& **lhs** - 
* const [Telemetry::Position](structmavsdk_1_1_telemetry_1_1_position.md)& **rhs** - 

**Returns**

&emsp;bool - `true` if items are equal.

### operator<<() {#namespacemavsdk_1aadeb8f386d025e70f4a029fdac856a43}

```
#include: plugins/telemetry/telemetry.h
```
```cpp
std::ostream& mavsdk::operator<<(std::ostream &str, Telemetry::Position const &position)
```


Stream operator to print information about a [Telemetry::Position](structmavsdk_1_1_telemetry_1_1_position.md).


**Parameters**

* std::ostream& **str** - 
* [Telemetry::Position](structmavsdk_1_1_telemetry_1_1_position.md) const& **position** - 

**Returns**

&emsp;std::ostream & - A reference to the stream.

### operator<<() {#namespacemavsdk_1ada8ebbf818db06d7a7e30190e5118737}

```
#include: plugins/telemetry/telemetry.h
```
```cpp
std::ostream& mavsdk::operator<<(std::ostream &str, Telemetry::PositionNED const &position_ned)
```


Stream operator to print information about a [Telemetry::PositionNED](structmavsdk_1_1_telemetry_1_1_position_n_e_d.md).


**Parameters**

* std::ostream& **str** - 
* [Telemetry::PositionNED](structmavsdk_1_1_telemetry_1_1_position_n_e_d.md) const& **position_ned** - 

**Returns**

&emsp;std::ostream & - A reference to the stream.

### operator<<() {#namespacemavsdk_1acc9e7235b5fedb39afc23011bfb92ced}

```
#include: plugins/telemetry/telemetry.h
```
```cpp
std::ostream& mavsdk::operator<<(std::ostream &str, Telemetry::VelocityNED const &velocity_ned)
```


Stream operator to print information about a [Telemetry::VelocityNED](structmavsdk_1_1_telemetry_1_1_velocity_n_e_d.md).


**Parameters**

* std::ostream& **str** - 
* [Telemetry::VelocityNED](structmavsdk_1_1_telemetry_1_1_velocity_n_e_d.md) const& **velocity_ned** - 

**Returns**

&emsp;std::ostream & - A reference to the stream.

### operator<<() {#namespacemavsdk_1ab7c10218203267a603cf58e0f9df83ab}

```
#include: plugins/telemetry/telemetry.h
```
```cpp
std::ostream& mavsdk::operator<<(std::ostream &str, Telemetry::PositionVelocityNED const &position_velocity_ned)
```


Stream operator to print information about a [Telemetry::PositionVelocityNED](structmavsdk_1_1_telemetry_1_1_position_velocity_n_e_d.md).


**Parameters**

* std::ostream& **str** - 
* [Telemetry::PositionVelocityNED](structmavsdk_1_1_telemetry_1_1_position_velocity_n_e_d.md) const& **position_velocity_ned** - 

**Returns**

&emsp;std::ostream & - A reference to the stream.

### operator==() {#namespacemavsdk_1afa0a77d20c18fc8c406a195ccd8403ce}

```
#include: plugins/telemetry/telemetry.h
```
```cpp
bool mavsdk::operator==(const Telemetry::Health &lhs, const Telemetry::Health &rhs)
```


Equal operator to compare two [Telemetry::Health](structmavsdk_1_1_telemetry_1_1_health.md) objects.


**Parameters**

* const [Telemetry::Health](structmavsdk_1_1_telemetry_1_1_health.md)& **lhs** - 
* const [Telemetry::Health](structmavsdk_1_1_telemetry_1_1_health.md)& **rhs** - 

**Returns**

&emsp;bool - `true` if items are equal.

### operator<<() {#namespacemavsdk_1a1fd300074aa856860f3e34a188c60272}

```
#include: plugins/telemetry/telemetry.h
```
```cpp
std::ostream& mavsdk::operator<<(std::ostream &str, Telemetry::Health const &health)
```


Stream operator to print information about a [Telemetry::Health](structmavsdk_1_1_telemetry_1_1_health.md).


**Parameters**

* std::ostream& **str** - 
* [Telemetry::Health](structmavsdk_1_1_telemetry_1_1_health.md) const& **health** - 

**Returns**

&emsp;std::ostream & - A reference to the stream.

### operator==() {#namespacemavsdk_1afb8fd460143b0b2cdd94182756b8ee02}

```
#include: plugins/telemetry/telemetry.h
```
```cpp
bool mavsdk::operator==(const Telemetry::GPSInfo &lhs, const Telemetry::GPSInfo &rhs)
```


Equal operator to compare two [Telemetry::GPSInfo](structmavsdk_1_1_telemetry_1_1_g_p_s_info.md) objects.


**Parameters**

* const [Telemetry::GPSInfo](structmavsdk_1_1_telemetry_1_1_g_p_s_info.md)& **lhs** - 
* const [Telemetry::GPSInfo](structmavsdk_1_1_telemetry_1_1_g_p_s_info.md)& **rhs** - 

**Returns**

&emsp;bool - `true` if items are equal.

### operator<<() {#namespacemavsdk_1a27f1b3bce30accddfe5c874970853f29}

```
#include: plugins/telemetry/telemetry.h
```
```cpp
std::ostream& mavsdk::operator<<(std::ostream &str, Telemetry::GPSInfo const &gps_info)
```


Stream operator to print information about a [Telemetry::GPSInfo](structmavsdk_1_1_telemetry_1_1_g_p_s_info.md).


**Parameters**

* std::ostream& **str** - 
* [Telemetry::GPSInfo](structmavsdk_1_1_telemetry_1_1_g_p_s_info.md) const& **gps_info** - 

**Returns**

&emsp;std::ostream & - A reference to the stream.

### operator==() {#namespacemavsdk_1a80896a794103e69c5ca72aa47f4b9011}

```
#include: plugins/telemetry/telemetry.h
```
```cpp
bool mavsdk::operator==(const Telemetry::Battery &lhs, const Telemetry::Battery &rhs)
```


Equal operator to compare two [Telemetry::Battery](structmavsdk_1_1_telemetry_1_1_battery.md) objects.


**Parameters**

* const [Telemetry::Battery](structmavsdk_1_1_telemetry_1_1_battery.md)& **lhs** - 
* const [Telemetry::Battery](structmavsdk_1_1_telemetry_1_1_battery.md)& **rhs** - 

**Returns**

&emsp;bool - `true` if items are equal.

### operator<<() {#namespacemavsdk_1a3254ebf618e006568cfc724a2969a3a5}

```
#include: plugins/telemetry/telemetry.h
```
```cpp
std::ostream& mavsdk::operator<<(std::ostream &str, Telemetry::Battery const &battery)
```


Stream operator to print information about a [Telemetry::Battery](structmavsdk_1_1_telemetry_1_1_battery.md).


**Parameters**

* std::ostream& **str** - 
* [Telemetry::Battery](structmavsdk_1_1_telemetry_1_1_battery.md) const& **battery** - 

**Returns**

&emsp;std::ostream & - A reference to the stream.

### operator==() {#namespacemavsdk_1ada20caf18bf2781eb8f07117b247412d}

```
#include: plugins/telemetry/telemetry.h
```
```cpp
bool mavsdk::operator==(const Telemetry::Quaternion &lhs, const Telemetry::Quaternion &rhs)
```


Equal operator to compare two [Telemetry::Quaternion](structmavsdk_1_1_telemetry_1_1_quaternion.md) objects.


**Parameters**

* const [Telemetry::Quaternion](structmavsdk_1_1_telemetry_1_1_quaternion.md)& **lhs** - 
* const [Telemetry::Quaternion](structmavsdk_1_1_telemetry_1_1_quaternion.md)& **rhs** - 

**Returns**

&emsp;bool - `true` if items are equal.

### operator<<() {#namespacemavsdk_1a74a1a53d8a08d5518f0b78e050c7fb36}

```
#include: plugins/telemetry/telemetry.h
```
```cpp
std::ostream& mavsdk::operator<<(std::ostream &str, Telemetry::Quaternion const &quaternion)
```


Stream operator to print information about a [Telemetry::Quaternion](structmavsdk_1_1_telemetry_1_1_quaternion.md).


**Parameters**

* std::ostream& **str** - 
* [Telemetry::Quaternion](structmavsdk_1_1_telemetry_1_1_quaternion.md) const& **quaternion** - 

**Returns**

&emsp;std::ostream & - A reference to the stream.

### operator==() {#namespacemavsdk_1a1f9d8c8f29bb52e305784093433aedeb}

```
#include: plugins/telemetry/telemetry.h
```
```cpp
bool mavsdk::operator==(const Telemetry::EulerAngle &lhs, const Telemetry::EulerAngle &rhs)
```


Equal operator to compare two [Telemetry::EulerAngle](structmavsdk_1_1_telemetry_1_1_euler_angle.md) objects.


**Parameters**

* const [Telemetry::EulerAngle](structmavsdk_1_1_telemetry_1_1_euler_angle.md)& **lhs** - 
* const [Telemetry::EulerAngle](structmavsdk_1_1_telemetry_1_1_euler_angle.md)& **rhs** - 

**Returns**

&emsp;bool - `true` if items are equal.

### operator<<() {#namespacemavsdk_1ad12d5557f83f327450850dca95706f9d}

```
#include: plugins/telemetry/telemetry.h
```
```cpp
std::ostream& mavsdk::operator<<(std::ostream &str, Telemetry::EulerAngle const &euler_angle)
```


Stream operator to print information about a [Telemetry::EulerAngle](structmavsdk_1_1_telemetry_1_1_euler_angle.md).


**Parameters**

* std::ostream& **str** - 
* [Telemetry::EulerAngle](structmavsdk_1_1_telemetry_1_1_euler_angle.md) const& **euler_angle** - 

**Returns**

&emsp;std::ostream & - A reference to the stream.

### operator==() {#namespacemavsdk_1a79b26da66253b9ac9a12f672ed9fef51}

```
#include: plugins/telemetry/telemetry.h
```
```cpp
bool mavsdk::operator==(const Telemetry::GroundSpeedNED &lhs, const Telemetry::GroundSpeedNED &rhs)
```


Equal operator to compare two [Telemetry::GroundSpeedNED](structmavsdk_1_1_telemetry_1_1_ground_speed_n_e_d.md) objects.


**Parameters**

* const [Telemetry::GroundSpeedNED](structmavsdk_1_1_telemetry_1_1_ground_speed_n_e_d.md)& **lhs** - 
* const [Telemetry::GroundSpeedNED](structmavsdk_1_1_telemetry_1_1_ground_speed_n_e_d.md)& **rhs** - 

**Returns**

&emsp;bool - `true` if items are equal.

### operator<<() {#namespacemavsdk_1adbada9caa34e673e1f3b0e58d18a5f7c}

```
#include: plugins/telemetry/telemetry.h
```
```cpp
std::ostream& mavsdk::operator<<(std::ostream &str, Telemetry::GroundSpeedNED const &ground_speed)
```


Stream operator to print information about a [Telemetry::GroundSpeedNED](structmavsdk_1_1_telemetry_1_1_ground_speed_n_e_d.md).


**Parameters**

* std::ostream& **str** - 
* [Telemetry::GroundSpeedNED](structmavsdk_1_1_telemetry_1_1_ground_speed_n_e_d.md) const& **ground_speed** - 

**Returns**

&emsp;std::ostream & - A reference to the stream.

### operator==() {#namespacemavsdk_1aa0d7b6aae3953c3e589ce4b8d5aaa198}

```
#include: plugins/telemetry/telemetry.h
```
```cpp
bool mavsdk::operator==(const Telemetry::RCStatus &lhs, const Telemetry::RCStatus &rhs)
```


Equal operator to compare two [Telemetry::RCStatus](structmavsdk_1_1_telemetry_1_1_r_c_status.md) objects.


**Parameters**

* const [Telemetry::RCStatus](structmavsdk_1_1_telemetry_1_1_r_c_status.md)& **lhs** - 
* const [Telemetry::RCStatus](structmavsdk_1_1_telemetry_1_1_r_c_status.md)& **rhs** - 

**Returns**

&emsp;bool - `true` if items are equal.

### operator<<() {#namespacemavsdk_1a855a444d9281f175fb6d3dcbac6c6b20}

```
#include: plugins/telemetry/telemetry.h
```
```cpp
std::ostream& mavsdk::operator<<(std::ostream &str, Telemetry::RCStatus const &rc_status)
```


Stream operator to print information about a [Telemetry::RCStatus](structmavsdk_1_1_telemetry_1_1_r_c_status.md).


**Parameters**

* std::ostream& **str** - 
* [Telemetry::RCStatus](structmavsdk_1_1_telemetry_1_1_r_c_status.md) const& **rc_status** - 

**Returns**

&emsp;std::ostream & - A reference to the stream.

### operator<<() {#namespacemavsdk_1aa2e1a513965c26ea6c7a23789eb3169a}

```
#include: plugins/telemetry/telemetry.h
```
```cpp
std::ostream& mavsdk::operator<<(std::ostream &str, Telemetry::StatusText const &status_text)
```


Stream operator to print information about a [Telemetry::StatusText](structmavsdk_1_1_telemetry_1_1_status_text.md).


**Parameters**

* std::ostream& **str** - 
* [Telemetry::StatusText](structmavsdk_1_1_telemetry_1_1_status_text.md) const& **status_text** - 

**Returns**

&emsp;std::ostream & - A reference to the stream.