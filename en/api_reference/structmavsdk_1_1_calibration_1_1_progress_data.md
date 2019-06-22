# mavsdk::Calibration::ProgressData Struct Reference
`#include: calibration.h`

----


Progress data coming from calibration. 


Can be a progress percentage, or an instruction text. 


## Public Member Functions


Type | Name | Description
---: | --- | ---
&nbsp; | [ProgressData](#structmavsdk_1_1_calibration_1_1_progress_data_1a75f6fc10af74a78ec58fb60ee87194f4) (const bool _has_progress, const float _progress, const bool _has_status_text, const std::string & _status_text) |

## Data Fields


bool [has_progress](#structmavsdk_1_1_calibration_1_1_progress_data_1a1b34241aba778eb9e1e67ae9f3404249)  - Whether or not this struct contains progress information.

float [progress](#structmavsdk_1_1_calibration_1_1_progress_data_1a573b314b1440961d593881f931aeca32)  - The actual progress.

bool [has_status_text](#structmavsdk_1_1_calibration_1_1_progress_data_1ac6780fbc4f8e8eaea3a2ccf6290a2c78)  - Whether or not this struct contains an instruction text.

std::string [status_text](#structmavsdk_1_1_calibration_1_1_progress_data_1a8fae64b0166ed65158d045b07ed9b48d)  - The actual instruction text.


## Constructor & Destructor Documentation


### ProgressData() {#structmavsdk_1_1_calibration_1_1_progress_data_1a75f6fc10af74a78ec58fb60ee87194f4}
```cpp
mavsdk::Calibration::ProgressData::ProgressData(const bool _has_progress, const float _progress, const bool _has_status_text, const std::string &_status_text)
```


Constructor for [ProgressData](structmavsdk_1_1_calibration_1_1_progress_data.md).

**Parameters**

* const bool **_has_progress** - Whether or not this struct contains progress information.
* const float **_progress** - The actual progress.
* const bool **_has_status_text** - Whether or not this struct contains an instruction text.
* const std::string& **_status_text** - The actual instruction text.

## Field Documentation


### has_progress {#structmavsdk_1_1_calibration_1_1_progress_data_1a1b34241aba778eb9e1e67ae9f3404249}

```cpp
bool mavsdk::Calibration::ProgressData::has_progress
```


Whether or not this struct contains progress information.


### progress {#structmavsdk_1_1_calibration_1_1_progress_data_1a573b314b1440961d593881f931aeca32}

```cpp
float mavsdk::Calibration::ProgressData::progress
```


The actual progress.


### has_status_text {#structmavsdk_1_1_calibration_1_1_progress_data_1ac6780fbc4f8e8eaea3a2ccf6290a2c78}

```cpp
bool mavsdk::Calibration::ProgressData::has_status_text
```


Whether or not this struct contains an instruction text.


### status_text {#structmavsdk_1_1_calibration_1_1_progress_data_1a8fae64b0166ed65158d045b07ed9b48d}

```cpp
std::string mavsdk::Calibration::ProgressData::status_text
```


The actual instruction text.

