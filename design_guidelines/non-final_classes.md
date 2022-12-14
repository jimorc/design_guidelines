# Non-final Classes

Final classes cannot be inherited from, and they prevent extensibility. In contrast, classes that can be inherited from
are called non-final classes.

**🤔 Consider** using non-final classes with no added virtual or protected members as a great way to provide inexpensive
yet much appreciated extensibility to a framework.

Developers often want to inherit from non-final classes so as to add convenience members such as custom constructors,
new methods, or method overloads.

Classes are non-final by default in C++, and this is also the recommended default for most classes in frameworks. The
extensibility afforded by non-final types is much appreciated by framework users and quite inexpensive to provide
because of relatively low test costs associated with non-final types.

## See Also

* [Design of Extensibility](design_for_extensibility.md)
* [Design Guidelines](design_guidelines.md)