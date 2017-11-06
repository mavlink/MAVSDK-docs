# C++ Coding Style

## Formatting and white space

### Formatting tool

All **.cpp** and **.h** files should be formatted according to the [astyle](http://astyle.sourceforge.net/) settings defined by [astylerc](https://github.com/dronecore/DroneCore/blob/master/astylerc).

To automatically fix the formatting, run this command:

```
make fix_style
```

The formatting standard is open for discussions. It can change if there are valid reasons (other than just personal taste).

### Explanations

- Line length should be kept below 100 characters. (Why? To make 3-way-merges with 3 columns possible on decent monitors. To discourage too many nested ifs. Why not 80? To allow for verbose naming and prevent abbreviations.)


## General Guidelines

This are some guidelines that were followed while DroneCore was written. They are not written in stone and can be changed whenever there is a good reason.

- C++11: It is encouraged to make use of C++11 features and the standard library. Examples:
  - [`std::function`](http://en.cppreference.com/w/cpp/utility/functional/function) and [lambda expressions](http://en.cppreference.com/w/cpp/language/lambda)
  - [`std::vector`](http://en.cppreference.com/w/cpp/container/vector), [`std::map`](http://www.cplusplus.com/reference/map/map/)
  - [`std::thread`](http://www.cplusplus.com/reference/thread/thread/), [`std::mutex`](http://en.cppreference.com/w/cpp/thread/mutex)

- `using namespace std` is discouraged ([read why](https://stackoverflow.com/questions/1452721/why-is-using-namespace-std-considered-bad-practice)). If needed specific declarations can be used in the source files such as `using std::this_thread::sleep_for` to prevent verbosity.
- The usage of namespacing wherever possible is encouraged (e.g. `enum class` is to be used over `enum`).
- The filenames should be `.h` for header files and `.cpp` for consistency.
- In general, variable and method names should error on the side of verbosity instead of being quick to type and read. Also, abbreviations are only to be used for small scopes and should not be exposed in public APIs.
- All variables that have a physical unit should have the unit in the variable name (e.g. `_m` for meters, `_m_s` for meters/second).
- Variable and method names should be `snake_case` and class/struct/enum names `CamelCase`. Private variables should start with an underscore as `_variable_name`.
- Try to exit functions early instead of nesting ifs ([read why](https://softwareengineering.stackexchange.com/questions/18454/should-i-return-from-a-function-early-or-use-an-if-statement)).
