# dronecore::Camera::Status Struct Reference
`#include: camera.h`

----


Information about camera status. 


## Public Types


Type | Description
--- | ---
enum [StorageStatus](#structdronecore_1_1_camera_1_1_status_1afa86d9f3e4aee66d5696821eb9ffdae2) | 

## Data Fields


bool [video_on](#structdronecore_1_1_camera_1_1_status_1a228352c68d7f6abe6abc961040ecf5cf)  - true if video capture is currently running.

bool [photo_interval_on](#structdronecore_1_1_camera_1_1_status_1ab3e50e6d6963863c82ff6660e196b7bc)  - true if video timelapse is currently active.

enum [dronecore::Camera::Status::StorageStatus](structdronecore_1_1_camera_1_1_status.md#structdronecore_1_1_camera_1_1_status_1afa86d9f3e4aee66d5696821eb9ffdae2) [storage_status](#structdronecore_1_1_camera_1_1_status_1a43d2eeb9377626136cc545ee91adfdb2)  - Storage status.

float [used_storage_mib](#structdronecore_1_1_camera_1_1_status_1aefb571ba8dc7349269aebc620a73cff5)  - Used storage in MiB.

float [available_storage_mib](#structdronecore_1_1_camera_1_1_status_1ab3f17dcb321c73fe134878fcaa30618f)  - Available storage in MiB.

float [total_storage_mib](#structdronecore_1_1_camera_1_1_status_1aeb60a963b4fc6c57ff2a266259332317)  - Total storage in MiB.


## Member Enumeration Documentation


### enum StorageStatus {#structdronecore_1_1_camera_1_1_status_1afa86d9f3e4aee66d5696821eb9ffdae2}


Value | Description
--- | ---
<span id="structdronecore_1_1_camera_1_1_status_1afa86d9f3e4aee66d5696821eb9ffdae2ad07995fa8f4a3a019d134fcbfca4669a"></span> `NOT_AVAILABLE` | Storage status not available. 
<span id="structdronecore_1_1_camera_1_1_status_1afa86d9f3e4aee66d5696821eb9ffdae2a59a97044815b7b8b5362c52e4092cff0"></span> `UNFORMATTED` | Storage is not formatted (has no recognized file system). 
<span id="structdronecore_1_1_camera_1_1_status_1afa86d9f3e4aee66d5696821eb9ffdae2ae77643642b5ef53c28801d2e2eb469e7"></span> `FORMATTED` | Storage is formatted (has recognized a file system). 

## Field Documentation


### video_on {#structdronecore_1_1_camera_1_1_status_1a228352c68d7f6abe6abc961040ecf5cf}

```cpp
bool dronecore::Camera::Status::video_on
```


true if video capture is currently running.


### photo_interval_on {#structdronecore_1_1_camera_1_1_status_1ab3e50e6d6963863c82ff6660e196b7bc}

```cpp
bool dronecore::Camera::Status::photo_interval_on
```


true if video timelapse is currently active.


### storage_status {#structdronecore_1_1_camera_1_1_status_1a43d2eeb9377626136cc545ee91adfdb2}

```cpp
enum dronecore::Camera::Status::StorageStatus  dronecore::Camera::Status::storage_status
```


Storage status.


### used_storage_mib {#structdronecore_1_1_camera_1_1_status_1aefb571ba8dc7349269aebc620a73cff5}

```cpp
float dronecore::Camera::Status::used_storage_mib
```


Used storage in MiB.


### available_storage_mib {#structdronecore_1_1_camera_1_1_status_1ab3f17dcb321c73fe134878fcaa30618f}

```cpp
float dronecore::Camera::Status::available_storage_mib
```


Available storage in MiB.


### total_storage_mib {#structdronecore_1_1_camera_1_1_status_1aeb60a963b4fc6c57ff2a266259332317}

```cpp
float dronecore::Camera::Status::total_storage_mib
```


Total storage in MiB.

