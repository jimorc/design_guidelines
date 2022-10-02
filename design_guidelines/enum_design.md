# Enum Design

Enums are a special kind of value. Enums can be declared as standard enums (like C enums) and enums classes.
Regardless of whether standard enums or enums classes are used, there are two kinds of enums: simple enums and flag 
enums. 

Simple enums represent small closed sets of choices. A common example of a simple enum is a set of colors.

Flag enums are designed to support bitwise operations on the enum values. A common example of a flags enum is
a list of options.

In the rest of this document, assume enum to mean enum class.

**✓ Do** always use enum classes rather than standard enums.

Enum classes provide strong typing. If you must interface with a language, such as C, which does not support enum
classes, then you may define a simple enum. But a better choice would be to cast the enum class value to a simple
enum or integer value in that case.


**✓ Do** use an enum class to strongly type parameters, properties, and return values that represent sets of values.

**✓ Do** favor using enum class values instead of static constants.

**❌ Do not** use an enum class for open sets (such as the operating system version, names of your friends, etc.).

**❌ Do not** provide reserved enum values that are intended for future use.

You can always simply add values to an existing enum class at a later stage. 
See [Adding Values to Enums](#adding-values-to_enums) for more details on adding values to enums. 
Reserved values just polute the set of real values and tend to lead to user errors.

**❌ Avoid** publicly exposing enums that have only one value.

A common practice to ensure future extensibility of C APIs is to add reserved parameters to method signatures. Such
reserved parameters can be expressed as enums with a single default value. Do not do this in C++; use 
method overloading instead.

**❌ Do not** include sentinel values in enums.

Although they are sometimes helpful to framework developers, sentinel values are confusing to users of the framework.
They are used to track the state of the enum rather than being one of the values from the set represented by
the enum class.

**✓ Do** provide a value of zero on simple enums.

Consider calling the value something like "none". If such a value is not appropriate for this particular enum class,
the most common default value for the enum should be assigned the underlying value of zero.

**🤔 Consider** using int32_t (the default in C++) as the underlying type of an enum unless any of the following is
true:

* The enum is a flags enum and you have more than 32 flags, or expect to have more in the future.

* The underlying type needs to be different than int32 for easier interoperability with other APIs that expect
differently sized enum values.

* A smaller underlying type would result in substantial savings in space. If you expect the enum to be used mainly
as an argument for flow of control, the size makes little difference. The size savings might be significant if:
  * You expect the enum to be used as a field in a very frequently instantiated struct or class.
  * You expect users to create large arrays or collections of the enum instances.
  * You expect a large number of instances of the enum to be serialized. For in-memory usage, be aware that objects
  are by default aligned on 4 or 8 byte boundaries, so you effectively need multiple enums or other small
  structures in an instance to pack a smaller enum with in order to make a difference, because the total instance
  size is always going to be rounded up to 4 or 8 bytes.

  In other words, the savings are almost always so insignificant as to not be worth the effort.

**✓ Do** name flag enums with plural nouns or noun phrases and simple enums with singular nouns and noun phrases.

## Designing Flag Enums

**✓ Do** use powers of two for the flag enum values so they can be freely combined using the bitwise OR operation.

**🤔 Consider** providing special enum values for commonly used combinations of flags.

Bitwise operations are an advanced concept and should not be required for simple tasks. read_write is an example
of such as special value.

**❌ Avoid** creating flag enums where certain combinations of values are invalid.

**❌ Avoid** using flag enum values of zero unless the value represents "all flags are cleared" and is named
appropriately, as prescribed in the next guideline.

**✓ Do** name the zero value of flag enums "none". For a flag enum, the value must always mean "all flags are cleared".

## Adding Values to Enums

It is very common to discover that you need to add values to an enum after you have already shipped it. There is a
potential application compatibility problem when the newly added value is returned from an existing API, because
poorly written applications may not handle the new value correctly.

**🤔 Consider** adding values to enums, despite a small compatibility risk.

If you have real data about application incompatibilities caused by additions to an enum, consider adding a new API
that returns the new and old values, and deprecate the old API, which should continue returning just the old values.
This will ensure that your existing applications remain compatible.

## See Also

* [Type Design Guidelines](type_design_guidelines.md)
* [Design Guidelines](design_guidelines.md)
