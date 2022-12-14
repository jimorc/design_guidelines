# Property Design

Although properties are technically similar to methods, they are quite different in terms of their usage scenarios.

**✓ Do** create get-only (const) properties if the caller should not be able to change the value of the property.

Keep in mind that if the type of the property is a mutable reference type, the property value can be changed
even if the property is get-only.

**❌ Do not** provide set-only properties, or properties with the setter having broader accessibility than
the getter.

For example, do not use properties with a public setter and a protected getter.

If the property setter cannot be provided, implement the functionality as a method instead. Consider starting the
method name with set_ and follow with what you would have named the property. For example, a domain class might have
a method called set_cache_path instead of having a set-only property called cache_path.

**✓ Do** provide sensible default values for all properties, ensuring that the defaults do not result in a security
hole or terribly inefficient code.

**✓ Do** allow properties to be set in any order even if this results in a temporary invalid state of the object.
It is common for two or more properties to be interrelated to a point where some values of one property might be
invalid given the values of other properties on the same object. In such cases, exceptions resulting from the
invalid state should be postponed until the interrelated properties are actually used together by the object.

**✓ Do** preserve the previous value if a property setter throws an exception.

**❌ Avoid** throwing exceptions from property getters.

Property getters should be simple operations and should not have any preconditions. If a getter can throw an
exception, it should probably be redesigned to be a method. Notice that this rule does not apply to indexers,
where we do expect exceptions as a result of validating the arguments.

# See Also

* [Member Design Guidelines](member_design_guidelines.md)
* [Design Guidelines](design_guidelines.md)