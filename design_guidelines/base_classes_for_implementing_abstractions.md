# Base Classes for Implementing Abstractions

Strictly speaking, a class becomes a base class when another class is derived from it. For the purpose of this section,
however, a base class is a class designed mainly to provide a common abstraction or for other classes to reuse some
default implementation through inheritance. Base classes usually sit in the middle of inheritance hierarchies,
between an astraction at the root of a hierarchy and several custom implementations at the bottom.

They serve as implementation helpers for implementing abstractions.

Base classes are usually not suited to serve as abstractions by themselves, because they tend to contain too much
implementation.

As previously discussed, base classes can provide invaluable help for users who need to implement abstractions, but
at the same time they can be a significant liability. They add surface area and increase the depth of inheritance
hierarchies and so conceptually complicate the framework. Therefore, base classes should be used only if they
provide significant value to users of the framework. They should be avoided if they provide value only to the 
implementers of the framework, in which case delegation to an internal implementation instead of inheritance from
a base class should be strongly considered.

**🤔 Consider** placing base classes in a separate namespace from the mainline scenario types. By definition, base
classes are intended for advanced extensibility scenarios and therefore are not interesting to the majority of
users.

**❌ Avoid** naming base classes with a "_base" suffix if the class is intended for use in public APIs.

## See Also

* [Design of Extensibility](design_for_extensibility.md)
* [Design Guidelines](design_guidelines.md)