# dronecode_sdk::Calibration::ProgressData Struct Reference
`#include: calibration.h`

----


Progress data coming from calibration. 


Can be a progress percentage, or an instruction text. 


## Public Member Functions


Type | Name | Description
---: | --- | ---
&nbsp; | [ProgressData](#structdronecode__sdk_1_1_calibration_1_1_progress_data_1a3442075ccca10f563e67d83a094ffd2b) (const bool _has_progress, const float _progress, const bool _has_status_text, const std::string & _status_text) |

## Data Fields


bool [has_progress](#structdronecode__sdk_1_1_calibration_1_1_progress_data_1a5d4a0ca26f2d8cbf5940c40e154d56da)  - Whether or not this struct contains progress information.

float [progress](#structdronecode__sdk_1_1_calibration_1_1_progress_data_1a2ad4ed301a084c8ff64e5d2f9469efb6)  - The actual progress.

bool [has_status_text](#structdronecode__sdk_1_1_calibration_1_1_progress_data_1a81f2ce5e1848c77c36f46e112315bfb4)  - Whether or not this struct contains an instruction text.

std::string [status_text](#structdronecode__sdk_1_1_calibration_1_1_progress_data_1a8a487282af108fa5b494b4b260915c66)  - The actual instruction text.


## Constructor & Destructor Documentation


### ProgressData() {#structdronecode__sdk_1_1_calibration_1_1_progress_data_1a3442075ccca10f563e67d83a094ffd2b}
```cpp
dronecode_sdk::Calibration::ProgressData::ProgressData(const bool _has_progress, const float _progress, const bool _has_status_text, const std::string &_status_text)
```


Constructor for [ProgressData](structdronecode__sdk_1_1_calibration_1_1_progress_data.md).

**Parameters**

* const bool **_has_progress** - Whether or not this struct contains progress information.
* const float **_progress** - The actual progress.
* const bool **_has_status_text** - Whether or not this struct contains an instruction text.
* const std::string& **_status_text** - The actual instruction text.

## Field Documentation


### has_progress {#structdronecode__sdk_1_1_calibration_1_1_progress_data_1a5d4a0ca26f2d8cbf5940c40e154d56da}

```cpp
bool dronecode_sdk::Calibration::ProgressData::has_progress
```


Whether or not this struct contains progress information.


### progress {#structdronecode__sdk_1_1_calibration_1_1_progress_data_1a2ad4ed301a084c8ff64e5d2f9469efb6}

```cpp
float dronecode_sdk::Calibration::ProgressData::progress
```


The actual progress.


### has_status_text {#structdronecode__sdk_1_1_calibration_1_1_progress_data_1a81f2ce5e1848c77c36f46e112315bfb4}

```cpp
bool dronecode_sdk::Calibration::ProgressData::has_status_text
```


Whether or not this struct contains an instruction text.


### status_text {#structdronecode__sdk_1_1_calibration_1_1_progress_data_1a8a487282af108fa5b494b4b260915c66}

```cpp
std::string dronecode_sdk::Calibration::ProgressData::status_text
```


The actual instruction text.

