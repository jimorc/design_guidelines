# Struct Design

The general purpose value type in C++ is the struct. This section provides guidelines for general struct design.

**❌ Do not** provide a default constructor for a struct.

Following this guideline allows arrays of structs to be created without having to run the constructor on each
item in the array.

**✓ Do** ensure that a state where all instance data is set to zero, false, or null (as appropriate) is valid.

This prevents accidental creation of invalid instances when an array of structs is created.

**🤔 Consider** defining a class rather than a struct if you find you must define copy and move constructors and operator= methods.

The use of copy and move constructors and operator= methods generally indicates that object contains functionality
rather than just data values. A class is therefore more suitable.

# See Also

* [Type Design Guidelines](type_design_guidelines.md)
* [Design Guidelines](design_guidelines.md)