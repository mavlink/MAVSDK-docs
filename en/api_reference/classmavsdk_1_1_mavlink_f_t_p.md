# mavsdk::MavlinkFTP Class Reference
`#include: mavlink_ftp.h`

----


The [MavlinkFTP](classmavsdk_1_1_mavlink_f_t_p.md) class provides file uploading and downloading using MAVLink FTP. 


## Public Types


Type | Description
--- | ---
enum [Result](#classmavsdk_1_1_mavlink_f_t_p_1acb93717559ff4b14b9dff64071913c65) | Possible results returned for requests.
std::function< void([Result](classmavsdk_1_1_mavlink_f_t_p.md#classmavsdk_1_1_mavlink_f_t_p_1acb93717559ff4b14b9dff64071913c65))> [result_callback_t](#classmavsdk_1_1_mavlink_f_t_p_1a1af2e158ecd25829223790143615a83e) | Result callback type for async ftp calls.
std::function< void(uint32_t bytes_read, uint32_t total_bytes)> [progress_callback_t](#classmavsdk_1_1_mavlink_f_t_p_1ad6883e33e73602830e67b3b54e1aa77d) | Progress callback type for async ftp calls.
std::function< void([Result](classmavsdk_1_1_mavlink_f_t_p.md#classmavsdk_1_1_mavlink_f_t_p_1acb93717559ff4b14b9dff64071913c65), std::vector< std::string >)> [directory_items_and_result_callback_t](#classmavsdk_1_1_mavlink_f_t_p_1aadd35fb52523cdd4cac8a893b37c00a7) | Callback type for [list_directory_async()](classmavsdk_1_1_mavlink_f_t_p.md#classmavsdk_1_1_mavlink_f_t_p_1a8950aaf94644528f8732081a53b1c026) call to get directory items and result.
std::function< void([Result](classmavsdk_1_1_mavlink_f_t_p.md#classmavsdk_1_1_mavlink_f_t_p_1acb93717559ff4b14b9dff64071913c65), uint32_t)> [file_crc32_result_callback_t](#classmavsdk_1_1_mavlink_f_t_p_1ac087a6fb8d1f638e72773d9c3ed6f8ee) | Callback type for [calc_file_crc32_async()](classmavsdk_1_1_mavlink_f_t_p.md#classmavsdk_1_1_mavlink_f_t_p_1a8f45f5b8cec0d6c76c299ee1d21beae8) call to get file CRC32.

## Public Member Functions


Type | Name | Description
---: | --- | ---
&nbsp; | [MavlinkFTP](#classmavsdk_1_1_mavlink_f_t_p_1ad1eb0ed91bb6046af902a2b2cf8b0f4d) ([System](classmavsdk_1_1_system.md) & system) | Constructor. Creates the plugin for a specific [System](classmavsdk_1_1_system.md).
&nbsp; | [~MavlinkFTP](#classmavsdk_1_1_mavlink_f_t_p_1a708a51272ec3b713467ebbe1a8314530) () | Destructor (internal use only).
&nbsp; | [MavlinkFTP](#classmavsdk_1_1_mavlink_f_t_p_1aa8ef37b5cb5640ff1f97a2e6994376f9) (const [MavlinkFTP](classmavsdk_1_1_mavlink_f_t_p.md) &)=delete | Copy Constructor (object is not copyable).
std::string | [result_str](#classmavsdk_1_1_mavlink_f_t_p_1a07d16a7c8737aec430efc3ac4fd5873a) ([Result](classmavsdk_1_1_mavlink_f_t_p.md#classmavsdk_1_1_mavlink_f_t_p_1acb93717559ff4b14b9dff64071913c65) result) | Returns a human-readable English string for [MavlinkFTP::Result](classmavsdk_1_1_mavlink_f_t_p.md#classmavsdk_1_1_mavlink_f_t_p_1acb93717559ff4b14b9dff64071913c65).
void | [reset_async](#classmavsdk_1_1_mavlink_f_t_p_1a1ad863e3ff3e9e55542e948252b4ebc8) ([result_callback_t](classmavsdk_1_1_mavlink_f_t_p.md#classmavsdk_1_1_mavlink_f_t_p_1a1af2e158ecd25829223790143615a83e) callback) | Resets FTP server in case there are stale open sessions (asynchronous).
void | [download_async](#classmavsdk_1_1_mavlink_f_t_p_1a5fd076865c1df2e47e716c41f414f014) (const std::string & remote_file_path, const std::string & local_folder, [progress_callback_t](classmavsdk_1_1_mavlink_f_t_p.md#classmavsdk_1_1_mavlink_f_t_p_1ad6883e33e73602830e67b3b54e1aa77d) progress_callback, [result_callback_t](classmavsdk_1_1_mavlink_f_t_p.md#classmavsdk_1_1_mavlink_f_t_p_1a1af2e158ecd25829223790143615a83e) result_callback) | Downloads a file to local folder (asynchronous).
void | [upload_async](#classmavsdk_1_1_mavlink_f_t_p_1a309dca340ec91f6be90938c3abe0c95b) (const std::string & local_file_path, const std::string & remote_folder, [progress_callback_t](classmavsdk_1_1_mavlink_f_t_p.md#classmavsdk_1_1_mavlink_f_t_p_1ad6883e33e73602830e67b3b54e1aa77d) progress_callback, [result_callback_t](classmavsdk_1_1_mavlink_f_t_p.md#classmavsdk_1_1_mavlink_f_t_p_1a1af2e158ecd25829223790143615a83e) result_callback) | Uploads local file to remote folder (asynchronous).
void | [list_directory_async](#classmavsdk_1_1_mavlink_f_t_p_1a8950aaf94644528f8732081a53b1c026) (const std::string & path, [directory_items_and_result_callback_t](classmavsdk_1_1_mavlink_f_t_p.md#classmavsdk_1_1_mavlink_f_t_p_1aadd35fb52523cdd4cac8a893b37c00a7) callback) | Downloads a vector of directory items from the system (asynchronous).
void | [create_directory_async](#classmavsdk_1_1_mavlink_f_t_p_1a947e9396ba76852f701508bc06394c21) (const std::string & path, [result_callback_t](classmavsdk_1_1_mavlink_f_t_p.md#classmavsdk_1_1_mavlink_f_t_p_1a1af2e158ecd25829223790143615a83e) callback) | Creates directory (asynchronous).
void | [remove_directory_async](#classmavsdk_1_1_mavlink_f_t_p_1a0de90cdba985333375305101936404fc) (const std::string & path, [result_callback_t](classmavsdk_1_1_mavlink_f_t_p.md#classmavsdk_1_1_mavlink_f_t_p_1a1af2e158ecd25829223790143615a83e) callback) | Removes directory (asynchronous).
void | [remove_file_async](#classmavsdk_1_1_mavlink_f_t_p_1ac525a9160acdab5fdf85a361741e7305) (const std::string & path, [result_callback_t](classmavsdk_1_1_mavlink_f_t_p.md#classmavsdk_1_1_mavlink_f_t_p_1a1af2e158ecd25829223790143615a83e) callback) | Removes file (asynchronous).
void | [rename_async](#classmavsdk_1_1_mavlink_f_t_p_1a6f687e8722d9246dc705b1dbf538a844) (const std::string & from_path, const std::string & to_path, [result_callback_t](classmavsdk_1_1_mavlink_f_t_p.md#classmavsdk_1_1_mavlink_f_t_p_1a1af2e158ecd25829223790143615a83e) callback) | Renames fromPath to toPath (asynchronous).
void | [calc_file_crc32_async](#classmavsdk_1_1_mavlink_f_t_p_1a8f45f5b8cec0d6c76c299ee1d21beae8) (const std::string & path, [file_crc32_result_callback_t](classmavsdk_1_1_mavlink_f_t_p.md#classmavsdk_1_1_mavlink_f_t_p_1ac087a6fb8d1f638e72773d9c3ed6f8ee) callback) | Calculate CRC32 for file (asynchronous).
[MavlinkFTP::Result](classmavsdk_1_1_mavlink_f_t_p.md#classmavsdk_1_1_mavlink_f_t_p_1acb93717559ff4b14b9dff64071913c65) | [calc_local_file_crc32](#classmavsdk_1_1_mavlink_f_t_p_1a1c92338f09cb9011cfe640f87a313649) (const std::string & path, uint32_t & checksum) | Calculate CRC32 for local file.
void | [set_timeout](#classmavsdk_1_1_mavlink_f_t_p_1ae1eed534af3efc2bec7bd4fd45cf6ea0) (uint32_t timeout) | Set timeout for Mavlink FTP operation.
void | [set_retries](#classmavsdk_1_1_mavlink_f_t_p_1a53fc2f01aab159ac2c0454a2ca7e8a33) (uint32_t retries) | Set number of retries after timeout for Mavlink FTP operation.
void | [set_root_dir](#classmavsdk_1_1_mavlink_f_t_p_1aedeedce9d80d001db2f85d14b3f15427) (const std::string & root_dir) | Set root dir for Mavlink FTP server.
void | [set_target_component_id](#classmavsdk_1_1_mavlink_f_t_p_1a834ed33ff876a36fa9149bdf0b649290) (uint8_t component_id) | Set target component id. By default it is the autopilot.
uint8_t | [get_our_compid](#classmavsdk_1_1_mavlink_f_t_p_1a53dc9a4c243b6638faf6d074783f1f5d) () const | Get our own component ID.
const [MavlinkFTP](classmavsdk_1_1_mavlink_f_t_p.md) & | [operator=](#classmavsdk_1_1_mavlink_f_t_p_1ae39d40f73c47c18a7179225cda9a7a0b) (const [MavlinkFTP](classmavsdk_1_1_mavlink_f_t_p.md) &)=delete | Equality operator (object is not copyable).


## Constructor & Destructor Documentation


### MavlinkFTP() {#classmavsdk_1_1_mavlink_f_t_p_1ad1eb0ed91bb6046af902a2b2cf8b0f4d}
```cpp
mavsdk::MavlinkFTP::MavlinkFTP(System &system)
```


Constructor. Creates the plugin for a specific [System](classmavsdk_1_1_system.md).

The plugin is typically created as shown below: 

```cpp
auto mavlink_ftp = std::make_shared<MavlinkFTP>(system);
```

**Parameters**

* [System](classmavsdk_1_1_system.md)& **system** - The specific system associated with this plugin.

### ~MavlinkFTP() {#classmavsdk_1_1_mavlink_f_t_p_1a708a51272ec3b713467ebbe1a8314530}
```cpp
mavsdk::MavlinkFTP::~MavlinkFTP()
```


Destructor (internal use only).


### MavlinkFTP() {#classmavsdk_1_1_mavlink_f_t_p_1aa8ef37b5cb5640ff1f97a2e6994376f9}
```cpp
mavsdk::MavlinkFTP::MavlinkFTP(const MavlinkFTP &)=delete
```


Copy Constructor (object is not copyable).


**Parameters**

* const [MavlinkFTP](classmavsdk_1_1_mavlink_f_t_p.md)&  - 

## Member Typdef Documentation


### typedef result_callback_t {#classmavsdk_1_1_mavlink_f_t_p_1a1af2e158ecd25829223790143615a83e}

```cpp
typedef std::function<void(Result)> mavsdk::MavlinkFTP::result_callback_t
```


Result callback type for async ftp calls.


### typedef progress_callback_t {#classmavsdk_1_1_mavlink_f_t_p_1ad6883e33e73602830e67b3b54e1aa77d}

```cpp
typedef std::function<void(uint32_t bytes_read, uint32_t total_bytes)> mavsdk::MavlinkFTP::progress_callback_t
```


Progress callback type for async ftp calls.


### typedef directory_items_and_result_callback_t {#classmavsdk_1_1_mavlink_f_t_p_1aadd35fb52523cdd4cac8a893b37c00a7}

```cpp
typedef std::function<void(Result, std::vector<std::string>)> mavsdk::MavlinkFTP::directory_items_and_result_callback_t
```


Callback type for [list_directory_async()](classmavsdk_1_1_mavlink_f_t_p.md#classmavsdk_1_1_mavlink_f_t_p_1a8950aaf94644528f8732081a53b1c026) call to get directory items and result.


### typedef file_crc32_result_callback_t {#classmavsdk_1_1_mavlink_f_t_p_1ac087a6fb8d1f638e72773d9c3ed6f8ee}

```cpp
typedef std::function<void(Result, uint32_t)> mavsdk::MavlinkFTP::file_crc32_result_callback_t
```


Callback type for [calc_file_crc32_async()](classmavsdk_1_1_mavlink_f_t_p.md#classmavsdk_1_1_mavlink_f_t_p_1a8f45f5b8cec0d6c76c299ee1d21beae8) call to get file CRC32.


## Member Enumeration Documentation


### enum Result {#classmavsdk_1_1_mavlink_f_t_p_1acb93717559ff4b14b9dff64071913c65}


Possible results returned for requests.


Value | Description
--- | ---
<span id="classmavsdk_1_1_mavlink_f_t_p_1acb93717559ff4b14b9dff64071913c65ad0749aaba8b833466dfcbb0428e4f89c"></span> `SUCCESS` |  
<span id="classmavsdk_1_1_mavlink_f_t_p_1acb93717559ff4b14b9dff64071913c65a070a0fb40f6c308ab544b227660aadff"></span> `TIMEOUT` | Timeout. 
<span id="classmavsdk_1_1_mavlink_f_t_p_1acb93717559ff4b14b9dff64071913c65aca69f96c768067fbff6c911ca87bccc9"></span> `IN_PROGRESS` | Operation is already in progress. 
<span id="classmavsdk_1_1_mavlink_f_t_p_1acb93717559ff4b14b9dff64071913c65a51a3170802568adea957770681344e8b"></span> `FILE_IO_ERROR` | File IO operation error. 
<span id="classmavsdk_1_1_mavlink_f_t_p_1acb93717559ff4b14b9dff64071913c65a8f20045e0839c2e258547ee09fc961a0"></span> `FILE_EXISTS` | File exists already. 
<span id="classmavsdk_1_1_mavlink_f_t_p_1acb93717559ff4b14b9dff64071913c65a3299de72583a027be04a2353d9c7c21f"></span> `FILE_DOES_NOT_EXIST` | File does not exist. 
<span id="classmavsdk_1_1_mavlink_f_t_p_1acb93717559ff4b14b9dff64071913c65a950c40a1bbdb2f6c8df8d92fafd7ef36"></span> `FILE_PROTECTED` | File is write protected. 
<span id="classmavsdk_1_1_mavlink_f_t_p_1acb93717559ff4b14b9dff64071913c65afeb1a30cb74c35aaf4ea067736109e30"></span> `INVALID_PARAMETER` | Invalid parameter. 
<span id="classmavsdk_1_1_mavlink_f_t_p_1acb93717559ff4b14b9dff64071913c65a40aa75f8e8cfdf7b660c5620e953229f"></span> `UNSUPPORTED` | Unsupported command. 
<span id="classmavsdk_1_1_mavlink_f_t_p_1acb93717559ff4b14b9dff64071913c65a23f149f0f9ae9ed9e0119e7209178a5d"></span> `PROTOCOL_ERROR` | General protocol error. 

## Member Function Documentation


### result_str() {#classmavsdk_1_1_mavlink_f_t_p_1a07d16a7c8737aec430efc3ac4fd5873a}
```cpp
std::string mavsdk::MavlinkFTP::result_str(Result result)
```


Returns a human-readable English string for [MavlinkFTP::Result](classmavsdk_1_1_mavlink_f_t_p.md#classmavsdk_1_1_mavlink_f_t_p_1acb93717559ff4b14b9dff64071913c65).


**Parameters**

* [Result](classmavsdk_1_1_mavlink_f_t_p.md#classmavsdk_1_1_mavlink_f_t_p_1acb93717559ff4b14b9dff64071913c65) **result** - The enum value for which a human readable string is required.

**Returns**

&emsp;std::string - Human readable string for the [MavlinkFTP::Result](classmavsdk_1_1_mavlink_f_t_p.md#classmavsdk_1_1_mavlink_f_t_p_1acb93717559ff4b14b9dff64071913c65).

### reset_async() {#classmavsdk_1_1_mavlink_f_t_p_1a1ad863e3ff3e9e55542e948252b4ebc8}
```cpp
void mavsdk::MavlinkFTP::reset_async(result_callback_t callback)
```


Resets FTP server in case there are stale open sessions (asynchronous).


**Parameters**

* [result_callback_t](classmavsdk_1_1_mavlink_f_t_p.md#classmavsdk_1_1_mavlink_f_t_p_1a1af2e158ecd25829223790143615a83e) **callback** - Callback to receive result of this request.

### download_async() {#classmavsdk_1_1_mavlink_f_t_p_1a5fd076865c1df2e47e716c41f414f014}
```cpp
void mavsdk::MavlinkFTP::download_async(const std::string &remote_file_path, const std::string &local_folder, progress_callback_t progress_callback, result_callback_t result_callback)
```


Downloads a file to local folder (asynchronous).


**Parameters**

* const std::string& **remote_file_path** - Remote file to download
* const std::string& **local_folder** - Local folder where downloaded file will be stored
* [progress_callback_t](classmavsdk_1_1_mavlink_f_t_p.md#classmavsdk_1_1_mavlink_f_t_p_1ad6883e33e73602830e67b3b54e1aa77d) **progress_callback** - Callback to receive progress of this request.
* [result_callback_t](classmavsdk_1_1_mavlink_f_t_p.md#classmavsdk_1_1_mavlink_f_t_p_1a1af2e158ecd25829223790143615a83e) **result_callback** - Callback to receive result of this request.

### upload_async() {#classmavsdk_1_1_mavlink_f_t_p_1a309dca340ec91f6be90938c3abe0c95b}
```cpp
void mavsdk::MavlinkFTP::upload_async(const std::string &local_file_path, const std::string &remote_folder, progress_callback_t progress_callback, result_callback_t result_callback)
```


Uploads local file to remote folder (asynchronous).


**Parameters**

* const std::string& **local_file_path** - Local file to upload
* const std::string& **remote_folder** - Remote folder where uploaded file will be stored
* [progress_callback_t](classmavsdk_1_1_mavlink_f_t_p.md#classmavsdk_1_1_mavlink_f_t_p_1ad6883e33e73602830e67b3b54e1aa77d) **progress_callback** - Callback to receive progress of this request.
* [result_callback_t](classmavsdk_1_1_mavlink_f_t_p.md#classmavsdk_1_1_mavlink_f_t_p_1a1af2e158ecd25829223790143615a83e) **result_callback** - Callback to receive result of this request.

### list_directory_async() {#classmavsdk_1_1_mavlink_f_t_p_1a8950aaf94644528f8732081a53b1c026}
```cpp
void mavsdk::MavlinkFTP::list_directory_async(const std::string &path, directory_items_and_result_callback_t callback)
```


Downloads a vector of directory items from the system (asynchronous).


**Parameters**

* const std::string& **path** - Path of a directory to list
* [directory_items_and_result_callback_t](classmavsdk_1_1_mavlink_f_t_p.md#classmavsdk_1_1_mavlink_f_t_p_1aadd35fb52523cdd4cac8a893b37c00a7) **callback** - Callback to receive directory entries and result of this request.

### create_directory_async() {#classmavsdk_1_1_mavlink_f_t_p_1a947e9396ba76852f701508bc06394c21}
```cpp
void mavsdk::MavlinkFTP::create_directory_async(const std::string &path, result_callback_t callback)
```


Creates directory (asynchronous).


**Parameters**

* const std::string& **path** - Path of a directory to create
* [result_callback_t](classmavsdk_1_1_mavlink_f_t_p.md#classmavsdk_1_1_mavlink_f_t_p_1a1af2e158ecd25829223790143615a83e) **callback** - Callback to receive result of this request.

### remove_directory_async() {#classmavsdk_1_1_mavlink_f_t_p_1a0de90cdba985333375305101936404fc}
```cpp
void mavsdk::MavlinkFTP::remove_directory_async(const std::string &path, result_callback_t callback)
```


Removes directory (asynchronous).


**Parameters**

* const std::string& **path** - Path of a directory to remove
* [result_callback_t](classmavsdk_1_1_mavlink_f_t_p.md#classmavsdk_1_1_mavlink_f_t_p_1a1af2e158ecd25829223790143615a83e) **callback** - Callback to receive result of this request.

### remove_file_async() {#classmavsdk_1_1_mavlink_f_t_p_1ac525a9160acdab5fdf85a361741e7305}
```cpp
void mavsdk::MavlinkFTP::remove_file_async(const std::string &path, result_callback_t callback)
```


Removes file (asynchronous).


**Parameters**

* const std::string& **path** - Path of a file to remove
* [result_callback_t](classmavsdk_1_1_mavlink_f_t_p.md#classmavsdk_1_1_mavlink_f_t_p_1a1af2e158ecd25829223790143615a83e) **callback** - Callback to receive result of this request.

### rename_async() {#classmavsdk_1_1_mavlink_f_t_p_1a6f687e8722d9246dc705b1dbf538a844}
```cpp
void mavsdk::MavlinkFTP::rename_async(const std::string &from_path, const std::string &to_path, result_callback_t callback)
```


Renames fromPath to toPath (asynchronous).


**Parameters**

* const std::string& **from_path** - Path to rename
* const std::string& **to_path** - Destination path
* [result_callback_t](classmavsdk_1_1_mavlink_f_t_p.md#classmavsdk_1_1_mavlink_f_t_p_1a1af2e158ecd25829223790143615a83e) **callback** - Callback to receive result of this request.

### calc_file_crc32_async() {#classmavsdk_1_1_mavlink_f_t_p_1a8f45f5b8cec0d6c76c299ee1d21beae8}
```cpp
void mavsdk::MavlinkFTP::calc_file_crc32_async(const std::string &path, file_crc32_result_callback_t callback)
```


Calculate CRC32 for file (asynchronous).


**Parameters**

* const std::string& **path** - Path to file for which CRC32 is calculated.
* [file_crc32_result_callback_t](classmavsdk_1_1_mavlink_f_t_p.md#classmavsdk_1_1_mavlink_f_t_p_1ac087a6fb8d1f638e72773d9c3ed6f8ee) **callback** - Callback to receive result of this request.

### calc_local_file_crc32() {#classmavsdk_1_1_mavlink_f_t_p_1a1c92338f09cb9011cfe640f87a313649}
```cpp
MavlinkFTP::Result mavsdk::MavlinkFTP::calc_local_file_crc32(const std::string &path, uint32_t &checksum)
```


Calculate CRC32 for local file.


**Parameters**

* const std::string& **path** - Path to local file for which CRC32 is calculated.
* uint32_t& **checksum** - CRC32 of the file

**Returns**

&emsp;[MavlinkFTP::Result](classmavsdk_1_1_mavlink_f_t_p.md#classmavsdk_1_1_mavlink_f_t_p_1acb93717559ff4b14b9dff64071913c65) - Result of the operation

### set_timeout() {#classmavsdk_1_1_mavlink_f_t_p_1ae1eed534af3efc2bec7bd4fd45cf6ea0}
```cpp
void mavsdk::MavlinkFTP::set_timeout(uint32_t timeout)
```


Set timeout for Mavlink FTP operation.


**Parameters**

* uint32_t **timeout** - Timeout in milliseconds

### set_retries() {#classmavsdk_1_1_mavlink_f_t_p_1a53fc2f01aab159ac2c0454a2ca7e8a33}
```cpp
void mavsdk::MavlinkFTP::set_retries(uint32_t retries)
```


Set number of retries after timeout for Mavlink FTP operation.


**Parameters**

* uint32_t **retries** - Number of retries before ERR_TIMEOUT is issued

### set_root_dir() {#classmavsdk_1_1_mavlink_f_t_p_1aedeedce9d80d001db2f85d14b3f15427}
```cpp
void mavsdk::MavlinkFTP::set_root_dir(const std::string &root_dir)
```


Set root dir for Mavlink FTP server.


**Parameters**

* const std::string& **root_dir** - Root dir for

### set_target_component_id() {#classmavsdk_1_1_mavlink_f_t_p_1a834ed33ff876a36fa9149bdf0b649290}
```cpp
void mavsdk::MavlinkFTP::set_target_component_id(uint8_t component_id)
```


Set target component id. By default it is the autopilot.


**Parameters**

* uint8_t **component_id** - Target component id

### get_our_compid() {#classmavsdk_1_1_mavlink_f_t_p_1a53dc9a4c243b6638faf6d074783f1f5d}
```cpp
uint8_t mavsdk::MavlinkFTP::get_our_compid() const
```


Get our own component ID.


**Returns**

&emsp;uint8_t - our own component ID.

### operator=() {#classmavsdk_1_1_mavlink_f_t_p_1ae39d40f73c47c18a7179225cda9a7a0b}
```cpp
const MavlinkFTP& mavsdk::MavlinkFTP::operator=(const MavlinkFTP &)=delete
```


Equality operator (object is not copyable).


**Parameters**

* const [MavlinkFTP](classmavsdk_1_1_mavlink_f_t_p.md)&  - 

**Returns**

&emsp;const [MavlinkFTP](classmavsdk_1_1_mavlink_f_t_p.md) & - 