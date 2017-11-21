# VTOL Support

DroneCore has basic support for VTOL vehicles. 

> **Note** Most design and test effort has gone into multicopter support. 
> [Get in touch](../README.md#getting-help) if you would like to help enhance the VTOL/Fixed-wing experience! 

## Supported Functionality

Much of the functionality in DroneCore is generic, and useful on all vehicle types. 
At time of writing the only *VTOL-specific* functionality is the ability to 
[transition to fixed wing mode (and back)](../guide/taking_off_landing.html#transition_vtol).

This allows users to:

- Take off and land in *multicopter* mode
- Fly in multicopter mode or transition and fly in fixed wing mode. 
- Fly missions in the currently mode when the mission is started.
- Use the camera/gimbal and other generic features.


## Remaining Work

Known omissions:
- Takeoff and landing is not supported in missions.
- VTOL takeoff in fixed wing mode is not supported.
- More research is required to confirm that no other VTOL APIs are required. 
- VTOL specific testing needs to be considered and implemented.


## Further Information

Additional information/examples are linked below:

* [Guide: Taking Off and Landing > Transition to fixed wing mode](../guide/taking_off_landing.html#transition_vtol).
* [Example: VTOL Transitions](../examples/transition_vtol_fixed_wing.md)
* Integration tests:
  * [transition_multicopter_fixedwing.cpp](https://github.com/dronecore/DroneCore/blob/{{ book.github_branch }}/integration_tests/transition_multicopter_fixedwing.cpp)

