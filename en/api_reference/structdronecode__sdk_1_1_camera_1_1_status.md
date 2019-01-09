# dronecode_sdk::Camera::Status Struct Reference
`#include: camera.h`

----


[Information](structdronecode__sdk_1_1_camera_1_1_information.md) about camera status. 


## Public Types


Type | Description
--- | ---
enum [StorageStatus](#structdronecode__sdk_1_1_camera_1_1_status_1ad5fe84902ac4bba14fa77825f1828879) | Storage status type.

## Data Fields


bool [video_on](#structdronecode__sdk_1_1_camera_1_1_status_1a803125f5fb20940298bfc4cfc2e35c3e)  - true if video capture is currently running.

bool [photo_interval_on](#structdronecode__sdk_1_1_camera_1_1_status_1add02c38ada8a4a138664957dc6fb2948)  - true if video timelapse is currently active.

enum [dronecode_sdk::Camera::Status::StorageStatus](structdronecode__sdk_1_1_camera_1_1_status.md#structdronecode__sdk_1_1_camera_1_1_status_1ad5fe84902ac4bba14fa77825f1828879) [storage_status](#structdronecode__sdk_1_1_camera_1_1_status_1a120758090afcd8b057ec521333c580ff)  - Storage status.

float [used_storage_mib](#structdronecode__sdk_1_1_camera_1_1_status_1ab6389346d012780ff97ee37136924f50)  - Used storage in MiB.

float [available_storage_mib](#structdronecode__sdk_1_1_camera_1_1_status_1af4e8ca1fbec381f4759a66d535f83ca5)  - Available storage in MiB.

float [total_storage_mib](#structdronecode__sdk_1_1_camera_1_1_status_1a41ee93b8baf849c185193b2599b13583)  - Total storage in MiB.

float [recording_time_s](#structdronecode__sdk_1_1_camera_1_1_status_1ace3e9b3d3c6001b62be78b998c4d8dea)  - Elapsed time since starting a video recording in seconds.

std::string [media_folder_name](#structdronecode__sdk_1_1_camera_1_1_status_1a548eb272c14f6493e349ddd18328dce1)  - Current folder name where media is saved.


## Member Enumeration Documentation


### enum StorageStatus {#structdronecode__sdk_1_1_camera_1_1_status_1ad5fe84902ac4bba14fa77825f1828879}


Storage status type.


Value | Description
--- | ---
<span id="structdronecode__sdk_1_1_camera_1_1_status_1ad5fe84902ac4bba14fa77825f1828879ad07995fa8f4a3a019d134fcbfca4669a"></span> `NOT_AVAILABLE` | Storage status not available. 
<span id="structdronecode__sdk_1_1_camera_1_1_status_1ad5fe84902ac4bba14fa77825f1828879a59a97044815b7b8b5362c52e4092cff0"></span> `UNFORMATTED` | Storage is not formatted (has no recognized file system). 
<span id="structdronecode__sdk_1_1_camera_1_1_status_1ad5fe84902ac4bba14fa77825f1828879ae77643642b5ef53c28801d2e2eb469e7"></span> `FORMATTED` | Storage is formatted (has recognized a file system). 

## Field Documentation


### video_on {#structdronecode__sdk_1_1_camera_1_1_status_1a803125f5fb20940298bfc4cfc2e35c3e}

```cpp
bool dronecode_sdk::Camera::Status::video_on
```


true if video capture is currently running.


### photo_interval_on {#structdronecode__sdk_1_1_camera_1_1_status_1add02c38ada8a4a138664957dc6fb2948}

```cpp
bool dronecode_sdk::Camera::Status::photo_interval_on
```


true if video timelapse is currently active.


### storage_status {#structdronecode__sdk_1_1_camera_1_1_status_1a120758090afcd8b057ec521333c580ff}

```cpp
enum dronecode_sdk::Camera::Status::StorageStatus  dronecode_sdk::Camera::Status::storage_status
```


Storage status.


### used_storage_mib {#structdronecode__sdk_1_1_camera_1_1_status_1ab6389346d012780ff97ee37136924f50}

```cpp
float dronecode_sdk::Camera::Status::used_storage_mib
```


Used storage in MiB.


### available_storage_mib {#structdronecode__sdk_1_1_camera_1_1_status_1af4e8ca1fbec381f4759a66d535f83ca5}

```cpp
float dronecode_sdk::Camera::Status::available_storage_mib
```


Available storage in MiB.


### total_storage_mib {#structdronecode__sdk_1_1_camera_1_1_status_1a41ee93b8baf849c185193b2599b13583}

```cpp
float dronecode_sdk::Camera::Status::total_storage_mib
```


Total storage in MiB.


### recording_time_s {#structdronecode__sdk_1_1_camera_1_1_status_1ace3e9b3d3c6001b62be78b998c4d8dea}

```cpp
float dronecode_sdk::Camera::Status::recording_time_s
```


Elapsed time since starting a video recording in seconds.


### media_folder_name {#structdronecode__sdk_1_1_camera_1_1_status_1a548eb272c14f6493e349ddd18328dce1}

```cpp
std::string dronecode_sdk::Camera::Status::media_folder_name
```


Current folder name where media is saved.

