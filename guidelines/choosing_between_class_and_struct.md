# Choosing Between Class and Struct

One of the basic design decisions every framework and library designer faces is whether to design a type as a class or as
a struct.

The only difference between a class and a struct in C++ is that structs have default public members and bases, and
classes have default private members and basess. Both classes and structs can have a mixture of public and
private members, can use inheritance, and can have member functions.

**🤔 Consider** defining a struct instead of a class if instances of the type are small and commonly short-lived or
are commonly embedded in other objects.

**❌ Avoid** defining a struct unless the type has all of the following characteristics:

* It logically represents a single value, similar to primitive types (int, double, etc.).
* It is immutable.

In all other cases, you should define your types as classes.

## See Also

* [Type Design Guidelines](type_design_guidelines.md)
* [Design Guidelines](design_guidelines.md)