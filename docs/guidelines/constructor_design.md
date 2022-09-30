# Constructor Design

Constructors run when an instance of a type is created.

Constructors that don't take any parameters are called default constructors.

Constructors are the most natural way to create instances of a type. Most developers will search and try to use a
constructor before they consider alternative ways of creating instances (such as factory methods).

**🤔 Consider** providing simple, ideally default, constructors.

A simple constructor has a very small number of parameters, and all parameters are primitives or enums. Such simple
constructors increase the usability of a library or framework.

**🤔 Consider** using a static factory method instead of a constructor if the semantics of the desired operation do
not map directly to the construction of a new instance, or if following the constructor design guidelines feels
unnatural.

**✓ Do** use constructor parameters as shortcuts for setting main properties.

**✓ Do** minimal work in the constructor.

Constructors should not do much work other than capture the constructor parameters. The cost of any other processing
should be delayed until required.

**✓ Do** throw exceptions from instance constructors, if appropriate.

**✓ Do** explicitly declare the public default constructor in classes if such a constructor is required.

If you do not explicitly declare any constructors on a class, the C++ compiler will automatically add a
public default constructor.

Adding a parameterized constructor to a class prevents the compiler from adding the default constructor. This
often causes accidental breaking changes.

**❌ Avoid** calling virtual members on an object inside its constructor. Calling a virtual member from inside a
constructor is not supported by C++.

**🤔 Consider** adding copy and move constructor declarations and set them to delete. If a copy or move constructor is
required, then set the constructor declarations to default, if applicable, or add a copy or move constructor that
provides the required functionality.

The C++ compiler automatically adds default copy and move constructors if they are not declared. If this is not what you
want, then specifically declare both constructors.

Only provide copy and move constructors if they are required. Otherwise mark them as deleted:

```
class foo
{
    public:
        foo();
        foo(const foo&) = delete;
        foo(foo&&) = delete;
}
```

If the copy or move constructor is required in your class, use the default copy or move constructor if it provides the 
required functionality. To specify this, declare the constructor as default. In the example below, the C++ compiler
will generate a default copy constructor: 

```
class foo
{
    public:
        foo();
        foo(const foo&) = default;
        foo(foo&&) = delete;
}
```

Only if the default copy or move constructor does not provide the required functionality should you define the required
constructor:
```
class foo
{
    public:
        foo();
        foo(const foo& right) { ... };
        foo(foo&&) = default;
}
```

If you require only one of the copy and move constructors, then set the other to delete.

# See Also

* [Member Design Guidelines](member_design_guidelines.md)
* [Design Guidelines](design_guidelines.md)