# Names of Classes, Structs and Interfaces

## General Type Naming
The naming guidelines in this section apply to general type naming.

**✓ Do** name classes and structs with nouns or noun phrases.

This distinguishes type names from methods, which are named with verb phrases.

**✓ Do** name interfaces with adjective phrases, or occasionally with nouns or noun phrases.

Nouns and noun phrases should be used rarely. They might indicate that the type should be an abstract class,
and not an interface.

**❌ Do not** give class names a prefix (e.g. "C", or "c").

**❌ Do not** add a postfix of "_base" to base classes.

**🤔 Consider** ending the name of derived classes with the name of the base class.

This is very readable and explains the relationship clearly. Some examples of this in code are: MainForm, which is a
type of form, and ToggleButton, which is a type of Button. However, it is important to use reasonable judgment in
applying this guideline; for example, the Button class is a kind of control event, although Control does not appear 
in its name.

**✓ Do** prefix interface names with the letter "I" to indicate that the type is an interface.
For example, IComponent (descriptive noun), ICustomAttributeProvider (noun phrase), and IPersistable
(adjective) are appropriate interace names. As with other types, avoid abbreviations.

**✓ Do** ensure that the names differ only by the "I" prefix on the interface name when you are defining
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

For example, a parameter constrained to ISession might be called *session_t*.

## Names of Common Types

**✓ Do** follow the guidelines described in the following table when naming types derived from or implementing
certain types.

| Base Type | Derived/Implementing Type Guideline |
| --- | --- |
| xtd::delegate | **✓ Do** add the suffix "EventHandler" to names of delegates that are used in events. |
| xtd::delegate | **✓ Do** add the suffix "Callback" to names of delegates other than those used as event handlers |
| xtd::delegate | **❌ Do not** add the suffix "Delegate" to a delegate |
| xtd::event_args | **✓ Do** add the suffix "EventArrgs". |
| xtd::event_handler | **✓ Do** add the suffix "EventHandler". |
| enum class | **❌ Do not** add the suffix "Enum" or "Flag". |
| xtd::exception | **✓ Do** add the suffix "Exception". |
| std::array | **✓ Do** add the suffix "Collection" for sequence containers. |
| std::vector | **✓ Do** add the suffix "Collection" for sequence containers. |
| std::deque | **✓ Do** add the suffix "Collection" for sequence containers. |
| std::forward_list | **✓ Do** add the suffix "Collection" for sequence containers. |
| std::list | **✓ Do** add the suffix "Collection" for sequence containers. |
| std::set | **✓ Do** add the suffix "Dictionary" for associative containers. |
| std::multiset | **✓ Do** add the suffix "Dictionary" for associative containers. |
| std::map | **✓ Do** add the suffix "Dictionary" for associative containers. |
| std::multimap | **✓ Do** add the suffix "Dictionary" for associative containers. |
| std::unordered_set | **✓ Do** add the suffix "Dictionary" for associative containers. |
| std::unordered_multiset | **✓ Do** add the suffix "Dictionary" for associative containers. |
| std::unordered_map | **✓ Do** add the suffix "Dictionary" for associative containers. |
| std::unordered_multimap | **✓ Do** add the suffix "Dictionary" for associative containers. |
| std::span | **✓ Do** add the suffix "Span". |
| std::istream | **✓ Do** add the suffix "Stream". |
| std::ostream | **✓ Do** add the suffix "Stream". |
| std::iostream | **✓ Do** add the suffix "Stream". |

## Naming Enumerations

Names of enumeration type (also called enums) in general should follow the standard type-naming rules
(camelCasing, etc.). However, there are additional guidelines that apply specifically to enums.

**✓ Do** use a singular type name for an enumeration unless its values are bit fields.

**✓ Do** use a plural name for an enumeration with bit fields as values, also called a flags enumeration.

**❌ Do not** use an "Enum" suffix in enum type names.

**❌ Do not** use "Flag" or "Flags" in enum type names.

**❌ Do not** use a prefix on enumeration value names (e.g. "rtf" for rich text enums).

## See Also
* [Naming Guidelines](naming_guidelines.md)
* [Design Guidelines](../design_guidelines/design_guidelines.md)