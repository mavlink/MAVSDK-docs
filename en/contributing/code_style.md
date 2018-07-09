# C++ Coding Style

This topic contains the SDK C++ formatting and coding guidelines.

> **Note** These guidelines are not written in stone! 
  [Start a discussion](../README.md#getting-help) if you have suggestions for improvement (the project will consider anything other than "matters of personal taste"). 

## Formatting and White Space

All **.cpp** and **.h** files should be formatted according to the [astyle](http://astyle.sourceforge.net/) settings defined by [astylerc](https://github.com/Dronecode/DronecodeSDK/blob/{{ book.github_branch }}/astylerc).

To automatically fix the formatting, run the command:

```
make fix_style
```

Explanations:

- Line length should be kept below 100 characters.
  - Enables 3-way-merges with 3 columns possible on decent monitors. 
  - Discourages too many nested ifs. 
  - Large enough o allow for verbose naming and prevent abbreviations.


## General Guidelines

The following general guidelines should be used for all code:

- C++11 is encouraged to allow developers to use C++11 features and the standard library. 
  Examples:
  - [`std::function`](http://en.cppreference.com/w/cpp/utility/functional/function) and [lambda expressions](http://en.cppreference.com/w/cpp/language/lambda)
  - [`std::vector`](http://en.cppreference.com/w/cpp/container/vector), [`std::map`](http://www.cplusplus.com/reference/map/map/)
  - [`std::thread`](http://www.cplusplus.com/reference/thread/thread/), [`std::mutex`](http://en.cppreference.com/w/cpp/thread/mutex)

- `using namespace std` is discouraged ([read why](https://stackoverflow.com/questions/1452721/why-is-using-namespace-std-considered-bad-practice)). 
  If needed specific declarations can be used in the source files such as `using std::this_thread::sleep_for` to reduce verbosity.
- The usage of namespacing wherever possible is encouraged (e.g. `enum class` is to be used over `enum`).
- Filename extensions should be `.h` for header files and `.cpp` for source files (for consistency).
- Variable and method names should err on the side of verbosity instead of being quick to type and read. Abbreviations are only to be used for small scopes and should not be exposed in public APIs.
- All variables that have a physical unit should have the unit in the variable name (e.g. `_m` for meters, `_m_s` for meters/second).
- Variable and method names should be `snake_case` and class/struct/enum names `CamelCase`. Private variables should start with an underscore, e.g.: `_variable_name`.
- Try to exit functions early instead of nesting ifs ([read why](https://softwareengineering.stackexchange.com/questions/18454/should-i-return-from-a-function-early-or-use-an-if-statement)).
- We don't use exceptions but use error codes. There are pros and cons for exceptions but given that the public API should be as simple as possible, it makes sense to refrain from exceptions altogether.
