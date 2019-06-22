# mavsdk::Camera::Status Struct Reference
`#include: camera.h`

----


[Information](structmavsdk_1_1_camera_1_1_information.md) about camera status. 


## Public Types


Type | Description
--- | ---
enum [StorageStatus](#structmavsdk_1_1_camera_1_1_status_1ae4e4a1e5622e75cce5813ffdf2ffcc52) | Storage status type.

## Data Fields


bool [video_on](#structmavsdk_1_1_camera_1_1_status_1a08db484755b36139b96d7a53620480c3)  - true if video capture is currently running.

bool [photo_interval_on](#structmavsdk_1_1_camera_1_1_status_1aa04f9bf95629beb73edc605ff6d0a244)  - true if video timelapse is currently active.

enum [mavsdk::Camera::Status::StorageStatus](structmavsdk_1_1_camera_1_1_status.md#structmavsdk_1_1_camera_1_1_status_1ae4e4a1e5622e75cce5813ffdf2ffcc52) [storage_status](#structmavsdk_1_1_camera_1_1_status_1a83e5aac0fd3f73184704fe2955ce5ef8)  - Storage status.

float [used_storage_mib](#structmavsdk_1_1_camera_1_1_status_1a235ad5628e6aac6f9e9614c29b3a86d9)  - Used storage in MiB.

float [available_storage_mib](#structmavsdk_1_1_camera_1_1_status_1a41a3988f991a338a46d90df698358dd1)  - Available storage in MiB.

float [total_storage_mib](#structmavsdk_1_1_camera_1_1_status_1a9ddfe7a46bc22616553bec58c6b6ecc1)  - Total storage in MiB.

float [recording_time_s](#structmavsdk_1_1_camera_1_1_status_1a0c721ba431bb2708bc87f96c043a1a5d)  - Elapsed time since starting a video recording in seconds.

std::string [media_folder_name](#structmavsdk_1_1_camera_1_1_status_1a37ed53027e526dececc6b06c2db1cddc)  - Current folder name where media is saved.


## Member Enumeration Documentation


### enum StorageStatus {#structmavsdk_1_1_camera_1_1_status_1ae4e4a1e5622e75cce5813ffdf2ffcc52}


Storage status type.


Value | Description
--- | ---
<span id="structmavsdk_1_1_camera_1_1_status_1ae4e4a1e5622e75cce5813ffdf2ffcc52ad07995fa8f4a3a019d134fcbfca4669a"></span> `NOT_AVAILABLE` | Storage status not available. 
<span id="structmavsdk_1_1_camera_1_1_status_1ae4e4a1e5622e75cce5813ffdf2ffcc52a59a97044815b7b8b5362c52e4092cff0"></span> `UNFORMATTED` | Storage is not formatted (has no recognized file system). 
<span id="structmavsdk_1_1_camera_1_1_status_1ae4e4a1e5622e75cce5813ffdf2ffcc52ae77643642b5ef53c28801d2e2eb469e7"></span> `FORMATTED` | Storage is formatted (has recognized a file system). 

## Field Documentation


### video_on {#structmavsdk_1_1_camera_1_1_status_1a08db484755b36139b96d7a53620480c3}

```cpp
bool mavsdk::Camera::Status::video_on
```


true if video capture is currently running.


### photo_interval_on {#structmavsdk_1_1_camera_1_1_status_1aa04f9bf95629beb73edc605ff6d0a244}

```cpp
bool mavsdk::Camera::Status::photo_interval_on
```


true if video timelapse is currently active.


### storage_status {#structmavsdk_1_1_camera_1_1_status_1a83e5aac0fd3f73184704fe2955ce5ef8}

```cpp
enum mavsdk::Camera::Status::StorageStatus  mavsdk::Camera::Status::storage_status
```


Storage status.


### used_storage_mib {#structmavsdk_1_1_camera_1_1_status_1a235ad5628e6aac6f9e9614c29b3a86d9}

```cpp
float mavsdk::Camera::Status::used_storage_mib
```


Used storage in MiB.


### available_storage_mib {#structmavsdk_1_1_camera_1_1_status_1a41a3988f991a338a46d90df698358dd1}

```cpp
float mavsdk::Camera::Status::available_storage_mib
```


Available storage in MiB.


### total_storage_mib {#structmavsdk_1_1_camera_1_1_status_1a9ddfe7a46bc22616553bec58c6b6ecc1}

```cpp
float mavsdk::Camera::Status::total_storage_mib
```


Total storage in MiB.


### recording_time_s {#structmavsdk_1_1_camera_1_1_status_1a0c721ba431bb2708bc87f96c043a1a5d}

```cpp
float mavsdk::Camera::Status::recording_time_s
```


Elapsed time since starting a video recording in seconds.


### media_folder_name {#structmavsdk_1_1_camera_1_1_status_1a37ed53027e526dececc6b06c2db1cddc}

```cpp
std::string mavsdk::Camera::Status::media_folder_name
```


Current folder name where media is saved.

