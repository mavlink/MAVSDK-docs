# mavsdk::Tune Class Reference
`#include: tune.h`

----


The [Tune](classmavsdk_1_1_tune.md) class allows to send a tune to be played by the autopilot. 


## Public Types


Type | Description
--- | ---
enum [Result](#classmavsdk_1_1_tune_1aed2b008974298098cedd69b7e95e909d) | Possible results returned for tune requests.
enum [SongElement](#classmavsdk_1_1_tune_1a97d85b5d578c74edc82a4337fc7bed57) | Enum representing a song element.
std::function< void([Result](classmavsdk_1_1_tune.md#classmavsdk_1_1_tune_1aed2b008974298098cedd69b7e95e909d))> [result_callback_t](#classmavsdk_1_1_tune_1ac303631c82b5a6b41ad1122b9a84652c) | Callback type for async tune calls.

## Public Member Functions


Type | Name | Description
---: | --- | ---
&nbsp; | [Tune](#classmavsdk_1_1_tune_1a1f60ea360006940e2bbae055733cc40a) ([System](classmavsdk_1_1_system.md) & system) | Constructor. Creates the plugin for a specific [System](classmavsdk_1_1_system.md).
&nbsp; | [~Tune](#classmavsdk_1_1_tune_1a3b6b1ce61b620ad8e4d82227257151c7) () | Destructor (internal use only).
&nbsp; | [Tune](#classmavsdk_1_1_tune_1acea13c8927ff72394235c282289bcebc) (const [Tune](classmavsdk_1_1_tune.md) &)=delete | Copy constructor (object is not copyable).
void | [play_tune_async](#classmavsdk_1_1_tune_1a363ab79e7d4a9798494a47add5d6587a) (const std::vector< [SongElement](classmavsdk_1_1_tune.md#classmavsdk_1_1_tune_1a97d85b5d578c74edc82a4337fc7bed57) > & tune, const int tempo, [result_callback_t](classmavsdk_1_1_tune.md#classmavsdk_1_1_tune_1ac303631c82b5a6b41ad1122b9a84652c) callback) | Send a tune to be played by the system (asynchronous).
const [Tune](classmavsdk_1_1_tune.md) & | [operator=](#classmavsdk_1_1_tune_1ae4a076da0417c6858df6fb59fa5110b5) (const [Tune](classmavsdk_1_1_tune.md) &)=delete | Equality operator (object is not copyable).

## Static Public Member Functions


Type | Name | Description
---: | --- | ---
const char * | [result_str](#classmavsdk_1_1_tune_1a2311af1d0523317c61e11ac9f3146530) ([Result](classmavsdk_1_1_tune.md#classmavsdk_1_1_tune_1aed2b008974298098cedd69b7e95e909d) result) | Gets a human-readable English string for an [Tune::Result](classmavsdk_1_1_tune.md#classmavsdk_1_1_tune_1aed2b008974298098cedd69b7e95e909d).


## Constructor & Destructor Documentation


### Tune() {#classmavsdk_1_1_tune_1a1f60ea360006940e2bbae055733cc40a}
```cpp
mavsdk::Tune::Tune(System &system)
```


Constructor. Creates the plugin for a specific [System](classmavsdk_1_1_system.md).

The plugin is typically created as shown below: 

```cpp
auto tune = std::make_shared<Tune>(system);
```

**Parameters**

* [System](classmavsdk_1_1_system.md)& **system** - The specific system associated with this plugin.

### ~Tune() {#classmavsdk_1_1_tune_1a3b6b1ce61b620ad8e4d82227257151c7}
```cpp
mavsdk::Tune::~Tune()
```


Destructor (internal use only).


### Tune() {#classmavsdk_1_1_tune_1acea13c8927ff72394235c282289bcebc}
```cpp
mavsdk::Tune::Tune(const Tune &)=delete
```


Copy constructor (object is not copyable).


**Parameters**

* const [Tune](classmavsdk_1_1_tune.md)&  - 

## Member Typdef Documentation


### typedef result_callback_t {#classmavsdk_1_1_tune_1ac303631c82b5a6b41ad1122b9a84652c}

```cpp
typedef std::function<void(Result)> mavsdk::Tune::result_callback_t
```


Callback type for async tune calls.


## Member Enumeration Documentation


### enum Result {#classmavsdk_1_1_tune_1aed2b008974298098cedd69b7e95e909d}


Possible results returned for tune requests.


Value | Description
--- | ---
<span id="classmavsdk_1_1_tune_1aed2b008974298098cedd69b7e95e909dad0749aaba8b833466dfcbb0428e4f89c"></span> `SUCCESS` | Request succeeded. 
<span id="classmavsdk_1_1_tune_1aed2b008974298098cedd69b7e95e909daab302bdc9b9c65a30e5ffab1d78a4cc5"></span> `INVALID_TEMPO` | Invalid tempo (range: 32 - 255). 
<span id="classmavsdk_1_1_tune_1aed2b008974298098cedd69b7e95e909dacb0c24d6a4374d0aa7120eb98f04cc1a"></span> `TUNE_TOO_LONG` | Invalid tune: encoded string must be at most 230 chars. 
<span id="classmavsdk_1_1_tune_1aed2b008974298098cedd69b7e95e909dabb1ca97ec761fc37101737ba0aa2e7c5"></span> `ERROR` | Failed to send the request. 

### enum SongElement {#classmavsdk_1_1_tune_1a97d85b5d578c74edc82a4337fc7bed57}


Enum representing a song element.


Value | Description
--- | ---
<span id="classmavsdk_1_1_tune_1a97d85b5d578c74edc82a4337fc7bed57a2cb914dda503b0a3ef418693d230e476"></span> `STYLE_LEGATO` |  
<span id="classmavsdk_1_1_tune_1a97d85b5d578c74edc82a4337fc7bed57a98910b70530a309348f81011b2ac0c29"></span> `STYLE_NORMAL` |  
<span id="classmavsdk_1_1_tune_1a97d85b5d578c74edc82a4337fc7bed57a5f25b20dda27ce7ea726aed6e723ac0c"></span> `STYLE_STACCATO` |  
<span id="classmavsdk_1_1_tune_1a97d85b5d578c74edc82a4337fc7bed57a2f744521bfc64d76bc84de9c40ccaf56"></span> `DURATION_1` |  
<span id="classmavsdk_1_1_tune_1a97d85b5d578c74edc82a4337fc7bed57a0e888bea30ba6acf56732c2a44df0707"></span> `DURATION_2` |  
<span id="classmavsdk_1_1_tune_1a97d85b5d578c74edc82a4337fc7bed57a72491c453f7754fe35f804055131fc13"></span> `DURATION_4` |  
<span id="classmavsdk_1_1_tune_1a97d85b5d578c74edc82a4337fc7bed57aef11beae3b4eced4b997080d2e536519"></span> `DURATION_8` |  
<span id="classmavsdk_1_1_tune_1a97d85b5d578c74edc82a4337fc7bed57a4bea2628921fed97aa8ab7beba5802a4"></span> `DURATION_16` |  
<span id="classmavsdk_1_1_tune_1a97d85b5d578c74edc82a4337fc7bed57abb64e1cc6dec13967cf3c80ecffc66cd"></span> `DURATION_32` |  
<span id="classmavsdk_1_1_tune_1a97d85b5d578c74edc82a4337fc7bed57a0f936fc84409a28c31e7d7a95b82b762"></span> `NOTE_A` |  
<span id="classmavsdk_1_1_tune_1a97d85b5d578c74edc82a4337fc7bed57a721547250e6910fe1d3fa20013c3f3d7"></span> `NOTE_B` |  
<span id="classmavsdk_1_1_tune_1a97d85b5d578c74edc82a4337fc7bed57a4fafae5694cb0bb336558af1efbe2e61"></span> `NOTE_C` |  
<span id="classmavsdk_1_1_tune_1a97d85b5d578c74edc82a4337fc7bed57aef7c5257e0aaf706d25f0d8a252baac9"></span> `NOTE_D` |  
<span id="classmavsdk_1_1_tune_1a97d85b5d578c74edc82a4337fc7bed57a378811d5f5f213c70aa9f37f49e0bb73"></span> `NOTE_E` |  
<span id="classmavsdk_1_1_tune_1a97d85b5d578c74edc82a4337fc7bed57a33c3987b8f2ece540f822378d6d55a2e"></span> `NOTE_F` |  
<span id="classmavsdk_1_1_tune_1a97d85b5d578c74edc82a4337fc7bed57a0b54635a4ea230669d8d493714ff78ec"></span> `NOTE_G` |  
<span id="classmavsdk_1_1_tune_1a97d85b5d578c74edc82a4337fc7bed57a89a1afc44be0c4e756b37a6f6e0093cf"></span> `NOTE_PAUSE` |  
<span id="classmavsdk_1_1_tune_1a97d85b5d578c74edc82a4337fc7bed57a880065c5d3f742979771c76a1d09e614"></span> `SHARP` |  
<span id="classmavsdk_1_1_tune_1a97d85b5d578c74edc82a4337fc7bed57af88a77e3d68d251c3dc4008c327b5a0c"></span> `FLAT` |  
<span id="classmavsdk_1_1_tune_1a97d85b5d578c74edc82a4337fc7bed57a1de4c79a5c0dc841f7effbd0d8569eda"></span> `OCTAVE_UP` |  
<span id="classmavsdk_1_1_tune_1a97d85b5d578c74edc82a4337fc7bed57ac06019b19d8ad5dfa9974082ff3b06d2"></span> `OCTAVE_DOWN` |  

## Member Function Documentation


### play_tune_async() {#classmavsdk_1_1_tune_1a363ab79e7d4a9798494a47add5d6587a}
```cpp
void mavsdk::Tune::play_tune_async(const std::vector< SongElement > &tune, const int tempo, result_callback_t callback)
```


Send a tune to be played by the system (asynchronous).


**Parameters**

* const std::vector< [SongElement](classmavsdk_1_1_tune.md#classmavsdk_1_1_tune_1a97d85b5d578c74edc82a4337fc7bed57) >& **tune** - Reference to a vector of song elements.
* const int **tempo** - Tempo in quarter notes per minute (32 - 255).
* [result_callback_t](classmavsdk_1_1_tune.md#classmavsdk_1_1_tune_1ac303631c82b5a6b41ad1122b9a84652c) **callback** - Callback to receive result of this request.

### operator=() {#classmavsdk_1_1_tune_1ae4a076da0417c6858df6fb59fa5110b5}
```cpp
const Tune& mavsdk::Tune::operator=(const Tune &)=delete
```


Equality operator (object is not copyable).


**Parameters**

* const [Tune](classmavsdk_1_1_tune.md)&  - 

**Returns**

&emsp;const [Tune](classmavsdk_1_1_tune.md) & - 

### result_str() {#classmavsdk_1_1_tune_1a2311af1d0523317c61e11ac9f3146530}
```cpp
static const char* mavsdk::Tune::result_str(Result result)
```


Gets a human-readable English string for an [Tune::Result](classmavsdk_1_1_tune.md#classmavsdk_1_1_tune_1aed2b008974298098cedd69b7e95e909d).


**Parameters**

* [Result](classmavsdk_1_1_tune.md#classmavsdk_1_1_tune_1aed2b008974298098cedd69b7e95e909d) **result** - Enum for which string is required.

**Returns**

&emsp;const char * - Human readable string for the [Tune::Result](classmavsdk_1_1_tune.md#classmavsdk_1_1_tune_1aed2b008974298098cedd69b7e95e909d).