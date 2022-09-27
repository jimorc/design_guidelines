# Type Design Guidelines

From the C++ perspective, there are only two categories of types: native types and class types- but for the purpose of
a discussion about framework and library design, we divide types into more logical groups, each with specific
design rules.

Classes are the general case. They make up the bulk of types in the majority of frameworks and
libraries. Classes owe their popularity to the rich set of object-oriented features they support and to their
general applicability. Base classes and abstract classes are special logical groups related to extensibility.

Interfaces are types that can be implemented by both classes and structures. 

Structs should be reserved for small, simple types, similar to language primitives.

Enums are a special case of value types used to define short sets of values, such as the days of the week, console
colors, and so on.

Static classes are types intended to be containers for static members. They are commonly used to provide shortcuts
to other operations.

Delegates, exceptions, attributes, arrays, and collections are special cases intended for specific uses, and
guidelines for their design and usage are discussed elsewhere in these guidelines.

**✓ Do** ensure that each type is a well-defined set of related members, not just a random collection of
unrelated functionality.

## In This Section

* [Choosing Between Class and Struct](choosing_between_class_and_struct.md)
* [Abstract Class Design](abstract_class_design.md)
* [Static Class Design](static_class_design.md)
* [Interface Design](interface_design.md)

## See Also

* [Design Guidelines](design_guidelines.md)