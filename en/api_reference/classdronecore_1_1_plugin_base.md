# dronecore::PluginBase Class Reference
`#include: plugin_base.h`

----


Base class for every plugin. 


## Public Member Functions


Type | Name | Description
---: | --- | ---
&nbsp; | [PluginBase](#classdronecore_1_1_plugin_base_1adb7f0389b1f3eee3edd428f8cfab0652) ()=default | Default Constructor.
&nbsp; | [~PluginBase](#classdronecore_1_1_plugin_base_1a99a11523b84feb2fc1664eed1d4995f3) ()=default | Default Destructor.
&nbsp; | [PluginBase](#classdronecore_1_1_plugin_base_1a9a163fe7dc7cc9b8c65a1ce0e86a6750) (const [PluginBase](classdronecore_1_1_plugin_base.md) &)=delete | Copy constructor (object is not copyable).
const [PluginBase](classdronecore_1_1_plugin_base.md) & | [operator=](#classdronecore_1_1_plugin_base_1a971a2166cd7528fedb4f18209b2ba699) (const [PluginBase](classdronecore_1_1_plugin_base.md) &)=delete | Assign operator (object is not copyable).


## Constructor & Destructor Documentation


### PluginBase() {#classdronecore_1_1_plugin_base_1adb7f0389b1f3eee3edd428f8cfab0652}
```cpp
dronecore::PluginBase::PluginBase()=default
```


Default Constructor.


### ~PluginBase() {#classdronecore_1_1_plugin_base_1a99a11523b84feb2fc1664eed1d4995f3}
```cpp
virtual dronecore::PluginBase::~PluginBase()=default
```


Default Destructor.


### PluginBase() {#classdronecore_1_1_plugin_base_1a9a163fe7dc7cc9b8c65a1ce0e86a6750}
```cpp
dronecore::PluginBase::PluginBase(const PluginBase &)=delete
```


Copy constructor (object is not copyable).


**Parameters**

* const [PluginBase](classdronecore_1_1_plugin_base.md)&  - 

## Member Function Documentation


### operator=() {#classdronecore_1_1_plugin_base_1a971a2166cd7528fedb4f18209b2ba699}
```cpp
const PluginBase& dronecore::PluginBase::operator=(const PluginBase &)=delete
```


Assign operator (object is not copyable).


**Parameters**

* const [PluginBase](classdronecore_1_1_plugin_base.md)&  - 

**Returns**

&emsp;const [PluginBase](classdronecore_1_1_plugin_base.md) & - 