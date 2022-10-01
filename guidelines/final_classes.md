# Final Classes

One of the features of object-oriented frameworks is that developers can extend and customize them in ways
unanticipated by the framework designers. This is both the power and danger of extensible design. When you design your
framework, it is therefore, very important to carefully design for extensibility when it is desired, and to limit
extensibility when it is dangerous.

A powerful mechanism that prevents extensibility is to mark the class with "final". You can seal the class, but you
cannot seal any of its individual members. Marking a class with "final" prevents users from inheriting from the class.

**❌ Do not** mark classes "final" without having a good reason for doing so.

Marking a class "final" because you cannot think of an extensibility scenario is not a good reason. Framework users
like to inherit from classes for various non-obvious reasons, like adding convenience members. See
[Non-final Classes](non-final_classes.md) for examples of non-obvious reasons users want to inherit from a type.

Good reasons for marking a class "final" include the following:

* The class is a static class. See [Static Class Design](static_class_design.md).
* The class stores security-sensitive secrets in inherited protected members.
* The class is an attribute that requires very fast runtime lookup. Attributes marked "final" have slightly higher
performance levels than non-final ones.

**❌ Do not** declare protected or virtual members on "final" types. By definition, "final" types cannot be inherited
from. This means that protected members on "final" types cannot be called, and virtual methods on "final" types
cannot be overridden.

## See Also

* [Design of Extensibility](design_for_extensibility.md)
* [Design Guidelines](design_guidelines.md)