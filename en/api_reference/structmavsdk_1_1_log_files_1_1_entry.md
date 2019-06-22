# mavsdk::LogFiles::Entry Struct Reference
`#include: log_files.h`

----


Log file type. 


Describes a log file entry that could be downloaded. 


## Data Fields


unsigned [id](#structmavsdk_1_1_log_files_1_1_entry_1a8a26ec40c20470b00d7601c42e8fee99) {} - ID of the logfile, to specify a file to be downloaded.

std::string [date](#structmavsdk_1_1_log_files_1_1_entry_1a5727aa32b382e3ce4be745a36efdd4bb) {} - Date of log file in UTC in ISO 8601 format "yyyy-mm-ddThh::mm::ssZ".

unsigned [size_bytes](#structmavsdk_1_1_log_files_1_1_entry_1a5c529bc3b0d90ddc9f50f7786570706d) {} -


## Field Documentation


### id {#structmavsdk_1_1_log_files_1_1_entry_1a8a26ec40c20470b00d7601c42e8fee99}

```cpp
unsigned mavsdk::LogFiles::Entry::id {}
```


ID of the logfile, to specify a file to be downloaded.


### date {#structmavsdk_1_1_log_files_1_1_entry_1a5727aa32b382e3ce4be745a36efdd4bb}

```cpp
std::string mavsdk::LogFiles::Entry::date {}
```


Date of log file in UTC in ISO 8601 format "yyyy-mm-ddThh::mm::ssZ".


### size_bytes {#structmavsdk_1_1_log_files_1_1_entry_1a5c529bc3b0d90ddc9f50f7786570706d}

```cpp
unsigned mavsdk::LogFiles::Entry::size_bytes {}
```


Size of file in bytes.