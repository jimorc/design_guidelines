# Names of Classes, Structs and Interfaces

## General Type Naming
The naming guidelines in this section apply to general type naming.

**✓ Do** name classes and structs with nouns or noun phrases, using snake_case.

This distinguishes type names from methods, which are named with verb phrases.

**✓ Do** name interfaces with adjective phrases, or occasionally with nouns or noun phrases.

Nouns and noun phrases should be used rarely. They might indicate that the type should be an abstract class,
and not an interface.

**❌ Do not** give class names a prefix (e.g. "C", or "c").

**❌ Do not** add a postfix of "_base" to base classes.

**🤔 Consider** ending the name of derived classes with the name of the base class.

This is very readable and explains the relationship clearly. Some examples of this in code are: main_form, which is a
type of form, and toggle_button, which is a type of button. However, it is important to use reasonable judgment in
applying this guideline; for example, the button class is a kind of control event, although control does not appear 
in its name.

**✓ Do** prefix interface names with the letter "i" to indicate that the type is an interface.
For example, icomponent (descriptive noun), icustom_attribute_provider (noun phrase), and ipersistable
(adjective) are appropriate interace names. As with other types, avoid abbreviations.

**✓ Do** ensure that the names differ only by the "i" prefix on the interface name when you are defining
a class-interface pair with the class as a standard implementation of the interface.

## Names of Generic Type Parameters

Generics (templated items) have one or more identifiers called type parameters.

**✓ Do** name generic type parameters with descriptive names unless a single letter name is completely
self-explanatory and a descriptive name would not add value.

**🤔 Consider** using *type_t* as the type parameter name for types with a generic type parameter.

```C++
template<typename type_t>
class predicate : public delegate<bool(type_t)>
{
    ...
};
```

```C++
template<typename type_t = object>
struct nullable : public type_t
{
    ...
};
```

**✓ Do** postfix descriptive type parameter names with *_t*.

```C++
template<typename session_t>
```

**🤔 Consider** indicating constraints placed on a type parameter in the name of the parameter.

For example, a parameter constrained to isession might be called *session_t*.

## Names of Common Types

**✓ Do** follow the guidelines described in the following table when naming types derived from or implementing
certain xtd_widgets types.

| Base Type | Derived/Implementing Type Guideline |
| --- | --- |
| xtd_widgets::delegate | **✓ Do** add the suffix "_event_handler" to names of delegates that are used in events. |
| xtd_widgets::delegate | **✓ Do** add the suffix "_callback" to names of delegates other than those used as event handlers |
| xtd_widgets::delegate | **❌ Do not** add the suffix "_delegate" to a delegate |
| xtd_widgets::event_args | **✓ Do** add the suffix "_event_args". |
| xtd_widgets::event_handler | **✓ Do** add the suffix "_event_handler". |
| enum class | **❌ Do not** add the suffix "_enum" or "_flag". |
| xtd_widgets::exception | **✓ Do** add the suffix "_exception". |
| std::array | **✓ Do** add the suffix "_collection" for sequence containers. |
| std::vector | **✓ Do** add the suffix "_collection" for sequence containers. |
| std::deque | **✓ Do** add the suffix "_collection" for sequence containers. |
| std::forward_list | **✓ Do** add the suffix "_collection" for sequence containers. |
| std::list | **✓ Do** add the suffix "_collection" for sequence containers. |
| std::set | **✓ Do** add the suffix "_dictionary" for associative containers. |
| std::multiset | **✓ Do** add the suffix "_dictionary" for associative containers. |
| std::map | **✓ Do** add the suffix "_dictionary" for associative containers. |
| std::multimap | **✓ Do** add the suffix "_dictionary" for associative containers. |
| std::unordered_set | **✓ Do** add the suffix "_dictionary" for associative containers. |
| std::unordered_multiset | **✓ Do** add the suffix "_dictionary" for associative containers. |
| std::unordered_map | **✓ Do** add the suffix "_dictionary" for associative containers. |
| std::unordered_multimap | **✓ Do** add the suffix "_dictionary" for associative containers. |
| std::span | **✓ Do** add the suffix "_span". |
| std::istream | **✓ Do** add the suffix "_stream". |
| std::ostream | **✓ Do** add the suffix "_stream". |
| std::iostream | **✓ Do** add the suffix "_stream". |

## Naming Enumerations

Names of enumeration type(also called enums) in general should follow the standard type-naming rules
(snake_casing, etc.). However, there are additional guidelines that apply specifically to enums.

**✓ Do** use a singular type name for an enumeration unless its values are bit fields.

**✓ Do** use a plural name for an enumeration with bit fields as values, also called a flags enumeration.

**❌ Do not** use an "_enum" suffix in enum type names.

**❌ Do not** use "_flag" or "_flags" in enum type names.

**❌ Do not** use a prefix on enumeration value names (e.g. "rtf" for rich text enums).

## See Also
* [Naming Guidelines](naming_guidelines.md)
* [Design Guidelines](../design_guidelines/design_guidelines.md)