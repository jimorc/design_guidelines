# Field Design

The principle of encapsulation is one of the most important principles in object-oriented design. This principle states
that data stored inside an object should be accessible only to that object.

A useful way to interpret the principle is to say that a type should be designed so that changes to fields of that type
(name or type changes) can be made without breaking code other than for members of the type. This interpretation
immediately implies that all fields must be private.

**✓ Do** specify all instance fields as private.

You should provide properties for accessing fields instead of making them public or protected.

**❌ Do not** use public static fields for predefined object instances.

# See Also

* [Member Design Guidelines](member_design_guidelines.md)
* [Design Guidelines](design_guidelines.md)