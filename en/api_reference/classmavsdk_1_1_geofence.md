# mavsdk::Geofence Class Reference
`#include: geofence.h`

----


The [Geofence](classmavsdk_1_1_geofence.md) class enables setting a geofence. 


## Data Structures


struct [Polygon](structmavsdk_1_1_geofence_1_1_polygon.md)

## Public Types


Type | Description
--- | ---
enum [Result](#classmavsdk_1_1_geofence_1ab64d6e3b9aeb9b6d5e45ae8a843a2642) | Possible results returned for geofence requests.
std::function< void([Result](classmavsdk_1_1_geofence.md#classmavsdk_1_1_geofence_1ab64d6e3b9aeb9b6d5e45ae8a843a2642))> [result_callback_t](#classmavsdk_1_1_geofence_1aa7f9af6387e4fa0ea780cff97703c9ac) | Callback type for async geofence calls.

## Public Member Functions


Type | Name | Description
---: | --- | ---
&nbsp; | [Geofence](#classmavsdk_1_1_geofence_1a115762872a12894270e758af250549f0) ([System](classmavsdk_1_1_system.md) & system) | Constructor. Creates the plugin for a specific [System](classmavsdk_1_1_system.md).
&nbsp; | [~Geofence](#classmavsdk_1_1_geofence_1a96569ad53b521b74cc9891163bda035c) () | Destructor (internal use only).
&nbsp; | [Geofence](#classmavsdk_1_1_geofence_1afe9ee72e7a271f4109bcfe3d16762e35) (const [Geofence](classmavsdk_1_1_geofence.md) &)=delete | Copy constructor (object is not copyable).
void | [send_geofence_async](#classmavsdk_1_1_geofence_1a4f500473b4d387c2bc4815a67e7956c2) (const std::vector< std::shared_ptr< [Polygon](structmavsdk_1_1_geofence_1_1_polygon.md) >> & polygons, [result_callback_t](classmavsdk_1_1_geofence.md#classmavsdk_1_1_geofence_1aa7f9af6387e4fa0ea780cff97703c9ac) callback) | Uploads a geofence to the system (asynchronous).
const [Geofence](classmavsdk_1_1_geofence.md) & | [operator=](#classmavsdk_1_1_geofence_1a2e8a69dddfa9b4937df117060fa2e0d7) (const [Geofence](classmavsdk_1_1_geofence.md) &)=delete | Equality operator (object is not copyable).

## Static Public Member Functions


Type | Name | Description
---: | --- | ---
const char * | [result_str](#classmavsdk_1_1_geofence_1af41ed911efc759a449ed8a783b12c9b9) ([Result](classmavsdk_1_1_geofence.md#classmavsdk_1_1_geofence_1ab64d6e3b9aeb9b6d5e45ae8a843a2642) result) | Gets a human-readable English string for an [Geofence::Result](classmavsdk_1_1_geofence.md#classmavsdk_1_1_geofence_1ab64d6e3b9aeb9b6d5e45ae8a843a2642).


## Constructor & Destructor Documentation


### Geofence() {#classmavsdk_1_1_geofence_1a115762872a12894270e758af250549f0}
```cpp
mavsdk::Geofence::Geofence(System &system)
```


Constructor. Creates the plugin for a specific [System](classmavsdk_1_1_system.md).

The plugin is typically created as shown below: 

```cpp
auto geofence = std::make_shared<Geofence>(system);
```

**Parameters**

* [System](classmavsdk_1_1_system.md)& **system** - The specific system associated with this plugin.

### ~Geofence() {#classmavsdk_1_1_geofence_1a96569ad53b521b74cc9891163bda035c}
```cpp
mavsdk::Geofence::~Geofence()
```


Destructor (internal use only).


### Geofence() {#classmavsdk_1_1_geofence_1afe9ee72e7a271f4109bcfe3d16762e35}
```cpp
mavsdk::Geofence::Geofence(const Geofence &)=delete
```


Copy constructor (object is not copyable).


**Parameters**

* const [Geofence](classmavsdk_1_1_geofence.md)&  - 

## Member Typdef Documentation


### typedef result_callback_t {#classmavsdk_1_1_geofence_1aa7f9af6387e4fa0ea780cff97703c9ac}

```cpp
typedef std::function<void(Result)> mavsdk::Geofence::result_callback_t
```


Callback type for async geofence calls.


## Member Enumeration Documentation


### enum Result {#classmavsdk_1_1_geofence_1ab64d6e3b9aeb9b6d5e45ae8a843a2642}


Possible results returned for geofence requests.


Value | Description
--- | ---
<span id="classmavsdk_1_1_geofence_1ab64d6e3b9aeb9b6d5e45ae8a843a2642ad0749aaba8b833466dfcbb0428e4f89c"></span> `SUCCESS` | Request succeeded. 
<span id="classmavsdk_1_1_geofence_1ab64d6e3b9aeb9b6d5e45ae8a843a2642abb1ca97ec761fc37101737ba0aa2e7c5"></span> `ERROR` | Error. 
<span id="classmavsdk_1_1_geofence_1ab64d6e3b9aeb9b6d5e45ae8a843a2642ac8056eddde297ec65316ee409ff3a31b"></span> `TOO_MANY_GEOFENCE_ITEMS` | Too many [Polygon](structmavsdk_1_1_geofence_1_1_polygon.md) objects in the geofence. 
<span id="classmavsdk_1_1_geofence_1ab64d6e3b9aeb9b6d5e45ae8a843a2642a802706a9238e2928077f97736854bad4"></span> `BUSY` | Vehicle busy. 
<span id="classmavsdk_1_1_geofence_1ab64d6e3b9aeb9b6d5e45ae8a843a2642a070a0fb40f6c308ab544b227660aadff"></span> `TIMEOUT` | Request timed out. 
<span id="classmavsdk_1_1_geofence_1ab64d6e3b9aeb9b6d5e45ae8a843a2642af295a0c3e37c94f078e1c5476479132d"></span> `INVALID_ARGUMENT` | Invalid argument. 
<span id="classmavsdk_1_1_geofence_1ab64d6e3b9aeb9b6d5e45ae8a843a2642a696b031073e74bf2cb98e5ef201d4aa3"></span> `UNKNOWN` | Request succeeded. 

## Member Function Documentation


### send_geofence_async() {#classmavsdk_1_1_geofence_1a4f500473b4d387c2bc4815a67e7956c2}
```cpp
void mavsdk::Geofence::send_geofence_async(const std::vector< std::shared_ptr< Polygon >> &polygons, result_callback_t callback)
```


Uploads a geofence to the system (asynchronous).

The polygons are uploaded to a drone. Once uploaded the geofence will remain on the drone even if a connection is lost.

**Parameters**

* const std::vector< std::shared_ptr< [Polygon](structmavsdk_1_1_geofence_1_1_polygon.md) >>& **polygons** - Reference to vector of polygons.
* [result_callback_t](classmavsdk_1_1_geofence.md#classmavsdk_1_1_geofence_1aa7f9af6387e4fa0ea780cff97703c9ac) **callback** - Callback to receive result of this request.

### operator=() {#classmavsdk_1_1_geofence_1a2e8a69dddfa9b4937df117060fa2e0d7}
```cpp
const Geofence& mavsdk::Geofence::operator=(const Geofence &)=delete
```


Equality operator (object is not copyable).


**Parameters**

* const [Geofence](classmavsdk_1_1_geofence.md)&  - 

**Returns**

&emsp;const [Geofence](classmavsdk_1_1_geofence.md) & - 

### result_str() {#classmavsdk_1_1_geofence_1af41ed911efc759a449ed8a783b12c9b9}
```cpp
static const char* mavsdk::Geofence::result_str(Result result)
```


Gets a human-readable English string for an [Geofence::Result](classmavsdk_1_1_geofence.md#classmavsdk_1_1_geofence_1ab64d6e3b9aeb9b6d5e45ae8a843a2642).


**Parameters**

* [Result](classmavsdk_1_1_geofence.md#classmavsdk_1_1_geofence_1ab64d6e3b9aeb9b6d5e45ae8a843a2642) **result** - Enum for which string is required.

**Returns**

&emsp;const char * - Human readable string for the [Geofence::Result](classmavsdk_1_1_geofence.md#classmavsdk_1_1_geofence_1ab64d6e3b9aeb9b6d5e45ae8a843a2642).