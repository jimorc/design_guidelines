# Parameter Design

This section provides broad guidelines on parameter design, including sections for checking arguments. In addition,
you should refer to guidelines  described in [Naming Parameters](../coding_guidelines/naming_parameters.md).

**✓ Do** use the least derived parameter type that provides the functionality required by the member.

For example, suppose you are coding a library of GUI widgets. You have classes called *button* and *label*, both of which have *control* as its parent class. Now suppose you want to design a method that changes the size of every control.
Such a method should take *control* as its parameter, not *button* or *label*.

**❌ Do not** use reserved parameters.

If more input to a member is needed in some future version, a new overload can be added.

**❌ Do not** have publicly exposed methods that take pointers, arrays of pointers, or multidimensional arrays as
parameters.

Pointers and multidimensional arrays are relatively difficult to use properly. In almost all cases, APIs can be
redesigned to avoid using these types as parameters.

**✓ Do** be consistent in naming parameters when overriding members or implementing interface members.

This better communicates the relationship between the methods.

## Choosing Between enum and boolean Parameters

**✓ Do** use enums if a member would otherwise have two or more boolean parameters.

**❌ Do not** use booleans unless you are absolutely sure there will never be a need for two or more boolean values.

Enums give you some room for the future addition of values, but you should be aware of all of the implications
of adding values to enums, which are described in [Enum Design](enum_design.md).

**🤔 Consider** using booleans in constructor parameters that are truly two-state values and are simply used to
initialize boolean properties.

## Validating Arguments

**✓ Do** validate arguments passed to public, protected, or explicitly implemented members. Throw std::invalid_argument or xtd::argument_exception, as appropriate, or one of their subclasses, if the validation fails.

Note that the actual validation does not necessarily have to happen in the public or protected member itself. It
could happen at a lower level in some private routine. The main point is that the entire surface area that is exposed
to the end users checks the arguments.

**✓ Do** throw std::argument_exception or xtd::argument_null_exception, as appropriate, if a nullptr argument is
passed and the member does not support nullptr arguments.

Note the guideline above about not having publicly exposed methods that take pointers.

**✓ Do** validate enum parameters. Do not assume enum arguments will be in the range defined by the enum. The C++
language allows casting any integer value into an enum value even if the value is not defined in the enum.

**✓ Do** be aware that mutable arguments might have changed after they were validated.

If the member is security sensitive, you are encouraged to make a copy and then validate and process the argument.

## Parameter Passing

From the perspecive of a framework designer, there are three main types of parameters: value parameters, const ref
parameters, and ref parameters. 

When an argument is passed through by value, the member receives a copy of the actual argument passed in. C++ defaults
to passing parameters by value.

When an argument is passed through a ref parameter or a const ref parameter, the member receives a reference to the
actual argument passed in. A reference to the argument is put on the stack. Ref parameters can be used to allow the
member to modify arguments passed by the caller.

# See Also

* [Member Design Guidelines](member_design_guidelines.md)
* [Design Guidelines](design_guidelines.md)