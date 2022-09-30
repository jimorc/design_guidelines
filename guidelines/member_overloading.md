# Member Overloading

Member overloading means creating two or more members of the same type that differ only in the number or type of
parameters but have the same name. For example, in the following, the write_line method is overloaded.

```
class console
{
    public:
        static void write_line();
        static void write_line(const std::string& value);
        static void write_line(bool value);
        ...
};
```

Because only methods, constructors, and properties can have parameters, only those members can be overloaded.

Overloading is one of the most important techniques for improving usability, prouctivity, and readability of reusable
libraries. Overloading of the number of parameters makes it possible to provide simpler versions of constructors
and methods. Overloading on the parameter type makes it possible to use the same member name for members performing
identical operations on a selected set of different types.

**✓ Do** use descriptive parameter names to indicate the default used by shorter overloads.

**❌ Avoid** arbitrarily varying parameter names in overloads. If a parameter in one overload represents the same
input as a parameter in another overload, the parameters should have the same name.

**❌ Avoid** being inconsistent in the ordering of parameters in overloaded members. Parameters with the same name
should appear in the same position in all overloads.

**✓ Do** make only the longest overload virtual (if extensibility is required). Shorter overloads should simply call
through to a longer overload.

**❌ Do not** have overloads with parameters at the same position and similar types yet with different semantics.

**✓ Do** allow std::optional, or preferably, nullptr to be passed for optional arguments.

**✓ Do** use member overloading rather than defining members with default arguments.

Default arguments are not permitted.

# See Also

* [Member Design Guidelines](member_design_guidelines.md)
* [Design Guidelines](design_guidelines.md)
