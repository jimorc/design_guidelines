# Coding Conventions Guidelines
## Folders and Files Organization
### Folders Hierarchy

**✓ Do** follow the project hierarchy
```
root
| +- build
| +- docs
| +- examples
| +- src
| | +- jxtd
| | | +- include
| | | +- src
```
* **root** folder is the project folder where the libjxtd project was extracted or cloned to.
* **root/build** folder contains the build result. This folder is automatically created by CMake.
* **root/docs** folder contains markdown documentation.
* **root/examples** folder contains examples showing how to use the classes defined in libjxtd.
* **root/src** folder contains source files for the libjxtd project.
* **root/src/jxtd** contains the source files for the jxtd library.
* **root/src/jxtd/include** folder contains header files for the classes in libjxtd.
* **root/src/jxtd/src** folder contains the source code for the classes in libjxtd.

### File Names
**✓ Do** name files with the same name as the class, struct, enum, delegate or event that the file contains.
For example, the file containing the class declaration for the class frequency_digit, shall be named 
*frequency_digit.h*.

### File Extensions

**✓ Do** use .h for header files.

**✓ Do** use .cpp for source files.

**✓ Do** use .md for markdown files.

## Editor

**✓Do** replace the tab character with 4 spaces in your editor or IDE properties.

**✓Do** use 4 spaces for indentation in header and source files.

```C++
class my_control : public xtd::form::control
{
    public:
        my_control();
        my_control(const my_control&) = delete;
};
```

## Order of Parts in a Class or Struct Declaration
### First Order is the Protection Type

**✓ Do** put public members first.

**✓ Do** put protected members second.

**✓ Do** put private members last.

### Order for each Protection Type

**✓ Do** place inner classes and structs first.

**✓ Do** place constructors, destructors, and copy operators second.

**✓ Do** place properties third.

**✓ Do** place events fourth.

**✓ Do** place methods fifth.

**✓ Do** place data members last.

**✓ Do** organize properties, events, methods and members in alphabetical order.

**🤔 Consider** adding a blank line or a comment at the start of each section.

```C++
class my_control : public xtd::form::control
{
    public:
        my_control() = default;
        my_control(const my_control&) = delete;
        virtual ~my_control() noexcept;
        my_control& operator=(const mycontrol&) = delete;
        // properties
        int value() const noexcept { return _value; };
        void value(int val) noexcept { _value = val; };
        // events
        ...
        // methods
    protected:
        // events
        ...
        // methods
        ...
    private:
        void _do_something_privately();

        int _value;
}
```

## #define

**❌ Do not** use #define for any reason.

**✓ Do** instead use *static constexp* or *static const* for constants.

// header file
```
class my_class
{
    public:
        static constexpr int max_size = 42;
        static const std::string version;
};
```
// source file
```
const std::string my_class::version("0.4.2");
```

**❌ Do not** define macros.

**✓ Do** use templated methods instead

```C++
class math
{
    public:
        // equivalent to #define min(value1, value2) (value1 <= value2 ? value1 : value2)
        template<typename T>
        static T min(T value1, T value2) { return value1 <= value1 ? value1 : value2; }
};
```
## Globals
**❌ Do not** use global methods.

**✓ Do** place all methods inside a class. If necessary, create a class to group static methods.

**❌ Do not** define global variables.

**✓ Do** place all variables inside a class. If necessary, global or static variables can be created
in source (.cpp) files, but they must not be visible in header (.h) files.

**✓ Do** use factory, builder or singleton patterns to create unique objects.

## Comments

**✓ Do** use single line comments **//**.

**❌ Do not** use block comments /* */ .

```C++
// this is a
// multiline comment
int universal_constant = 42;
```

## Documentation
Doxygen is used to generate documentation.

**✓ Do** write Doxygen documentation only in header (.h) files.

**✓ Do** start all documentation comments with a triple slash **///** .
```C++
/// @brief my_class does something
class my_class
{

};
```

**✓ Do** start all Doxygen commands with **@** .
```C++
/// @brief my_method does something
/// @param name A string that contains the name
/// @remarks The name must begin with an uppercase character.
/// @exception std::invalid_argument when name does not start with an uppercase character.
void my_method(const std::string& name);
```

**❌ Do not** write Doxygen comments for private properties, methods, events, or member variables.
You may, however, comment normally for these items in the header file as needed.

## Indentation
**✓ Do** indent block contents.

**✓ Do** indent class and struct protection types.

```C++
class my_class
{
    public:
        my_class();

        void a_method()
        {
            int x;
            int y;
            swap(x, y);
        }
};
```

**❌ Do not** indent open and close braces.

```C++
class my_class
{
    public:
        void a_method()
        {
            // do something
        }
};
```

**✓ Do** indent switch sections.
```C++
switch (x)
{
    case 1:
        // do 1
        break;
    case 2:
        // do 2
        break;
}
```

**❌ Do not** indent labels.
 
 ```C++
 class a_dumb_label
 {
    void method()
    {
    label:
        // do something
    }
 };
```
## New Lines
### New Lines for Braces

**✓ Do** place open braces on a new line for types.

```C++
class a_class
{

};
```
**✓ Do** place open braces on a new line for methods.

```C++
void method()
{
    //do something
}
```

**❌ Do not** place open and close brace on new line for empty constuctor declarations/definitions.

```C++
class my_class
{
    my_class() {}
    ...
}
```

**❌ Do not** place open and close brace on new line for simple methods/properties in struct and class
declarations/definitions.

```C++
class my_class
{
    public:
        int value() { return _value; }
        void value(int val) { _value = val; }
    private:
        int _value;
}
```

**❌ Do not** place open brace on new line for lambda expressions

```C++
void example()
{
    auto del [&] (int x, int y) { // do something };
}

void example2()
{
    auto del [&] (int x, int y) { do something1(x, y);
        do_something2(); };
}
```
**✓ Do** place open brace on a new line for control blocks.

```C++
void example()
{
    if (true)
    {
        // do something
    }
}
```

**❌ Do not** place open brace on a new line for object initializers.

```C++
std::vector<int> my_vector {
    42, 43, 46};
}
```

### New Line Options for Keywords

**✓ Do** place *else* on new line
```C++
if (true)
{
    ...
}
else
{
    ...
}
```

**✓ Do** place *catch* on new line
```C++
try
{
    ...
}
catch (...)
{

}
```

### New Line Options for Expressions

**❌ Do not** place member object initializers on a new line

```C++
void example()
{
    size sz { 10, 24 };
    std::vector<int> a_big_vector { 1, 17,6, 32, 5,
        10, 11, 22, 23, 24, 56, 1, 27, 4 };
}
```

## Spacing
### Space Setting for Method Declarations

**❌ Do not** insert space between method name and its opening parenthesis
```C++
void do_something()
{

}
```

**❌ Do not** insert space immediately after opening parenthesis or immediately before ending parenthesis in argument
lists
```C++**
void do_something(int x, int y)
{

}
```

**❌ Do not** insert space within empty argument list parentheses
```C++
void do_something()
{

}
```

### Set Spacing for Method Calls
**❌ Do not** insert space between method name and its opening parenthesis
```C++
void do_it()
{
    do_it2();
}
```

**❌ Do not** insert space immediately after opening parenthesis or immediately before ending parenthesis in argument
lists
```C++
void do_it()
{
    do_it3(x, y);
}
```

**❌ Do not** insert space within empty argument list parentheses
```C++
void do_it()
{
    do_it2();
}
```

### Set Other Spacing Options
**✓ Do** insert space after keywords in control flow statements
```C++
for (auto x : y)
{

}
```

**❌ Do not** insert space at beginning or end of parentheses in expressions
```C++
i = (5 + x) * y;
```

**❌ Do not** insert space after casts
```C++
auto test = (const b*)c;
auto zz = static_cast<int>(a_pointer);
```

**✓ Do** insert space in declaration statements
```C++
int x = 42;
```

### Set Spacing for Braces
**❌ Do not** insert space inside empty braces

```C++
class my_class
{
    public:
        my_class() {}
};
```

**✓ Do** insert space after opening brace and before closing brace for object initializers.

```C++
int m[] { 1, 3, 27 };
```

**✓ Do** insert space after opening brace and before closing brace for simple definitions in declarations.

```C++
class my_class
{
    public:
        int value() { return _value; }
        void value(int val) { _value = val; }
    private:
        int _value;
}

**✓ Do** insert space after opening brace and before closing brace of single line lambda expressions.

```C++
auto del [&] (int x, int y) { do_something1(x, y); }
```

### Set Spacing for Square Brackets
**❌ Do not** insert space before open square bracket

```C++
thing[3] = 42;
```

**❌ Do not** insert space within empty square brackets

```C++
int m[] { 1, 2, 5 };
```

**❌ Do not** insert space immediately after beginning square bracket or before ending square bracket

```C++
m[3] = 15;
```

### Set Spacing (Other)
**✓ Do** insert space before and after colon for base or interface in type declaration

```C++
class foo : public bar
{
    ...
};
```

**✓ Do** insert space after comma

```C++
int i = 42, j = 97;
```

**❌ Do not** insert space before or after dot

```C++
    foo.bar().items().sort();
```

**❌ Do not** insert space before or after struct or class dereference

```C++
foo->bar()->items()->sort();
```

**✓ Do** insert space after semicolon in *for* statement

```C++
for (int i = 0; i < 10; ++i)
{
    ...
}
```

**❌ Do not** insert space before semicolon in *for* statement
```C++
for (int i = 0; i < 10; ++i)
{
    ...
}
```

**✓ Do** insert spacing around operators
```C++
int a = (5 + b) * c;
```

## See Also
[Design Guidelines](design_guidelines.md)