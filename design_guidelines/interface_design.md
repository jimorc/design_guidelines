# Interface Design

Although most APIs are best modeled using classes and structs, there are cases in which interfaces are more
appropriate or are the only option.

C++ does support multiple inheritance (i.e. C++ classes can inherit from more than one base class), but for more
simplicity, and to avoid diamond structure, it is preferable to implement one or more interfaces in addition to 
inheriting from a base class. Therefore, interfaces are often used to achieve the effect of multiple inheritance.

The other situation in which defining an interface is appropriate is in creating a common interface that can
be supported by several types, including some value types. For more information on the uses and advantages of interfaces
in C++, see [C++ Interface Classes - An Introduction](https://accu.org/journals/overload/12/62/radford_233/).

Interfaces in C++ are defined by using pure virtual classes.

**✓ Do** define an interface if you need some common API to be supported by a set of types.

For example, you may have a set of shape objects, such as lines, circles, and rectangles, that each have a different 
drawing method. Drawing is not core functionality for  shape objects, so you may want to define a drawing interface that each of lines, circles, and rectangles inherit and implement.

**🤔 Consider** defining an interface if you need to support its functionality on types that already inherit from some
other type.

For the example stated above, line, circle, and rectangle classes all inherit from the shape class. Rather than also
inheriting from a drawing class, inherit from a drawing interface instead.

**❌ Avoid** using marker interfaces (interfaces with no members).

The correct way to mark mark a class as having a specific characteristic (marker) is to use a custom attribute, but
C++, as of C++20 does not support user-defined attributes. Therefore, use a marker interface, but only if there is
no other way to accomplish the same thing.

**✓ Do** provide at least one type that is an implementation of an interface.

Doing this helps to validate the design of the interface.

**✓ Do** provide at least one API that consumes each interface you define (a method taking the interface as a parameter,
or a property typed as the interface).

Doing this helps to validate the interface design.

**❌ Do not** add members to an interface that has previously shipped.

Doing so would break implementations of the interface. You should create a new interface in order to avoid versioning
problems.

Except for the situations described in these guidelines, you should, in general, choose classes rather than interfaces
in designing reusable libraries.

# See Also

* [Type Design Guidelines](type_design_guidelines.md)
* [Design Guidelines](design_guidelines.md)