# Abstract Class Design

**❌ Do not** define public constructors in abstract types.

Constructors should be public only if users will need to create instances of the type. Because you cannot create
instances of an abstract type, an abstract type with a public constructor is incorrectly designed and misleading
to the users.

**✓ Do** define a protected constructor in abstract classes.

A protected constructor allows the base class to do its own initalization when subtypes of the abstract class
are created.

**✓ Do** provide at least one concrete type that inherits from each abstract class.

Doing this helps to validate the design of the abstract class.

## See Also

* [Type Design Guidelines](type_design_guidelines.md)
* [Design Guidelines](design_guidelines.md)