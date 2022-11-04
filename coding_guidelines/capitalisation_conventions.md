# Capitalisation Conventions

The guidelines in this chapter lay out a simple method for using case, that, when applied consistently, makes
identifieers for types, members, and parameters easy to read.

## Capitalisation Rules for Identifiers

There are several naming conventions for identifiers:
* PascalCase: Capitialisation is used to separate the individual words in the identifier. The first letter is also capitalised. For example:
```
PropertyDescriptor
Tag
```
* camelCase: Similar to Pascal Case, but the first letter in the identifier is not capitalised. For example:
```
propertyDescriptor
tag
```
* snake_case: All letters in identifiers are lowercase. Individual words and numbers in the identifier are separated by 
an underscore "_". This is the standard naming convention used in C, and also in the C++ standard library. For
example:
```
property_descriptor
tag
```

You will see all of these capitalisation rules used in C++ code and in C++ library APIs. No single rule is better than
another; what is important is consistency within a framework or project.

**✓ Do** use PascalCase for identifiers throughout the project.

A special case is made for two-, three-, or four-letter acronyms in which both or all three letters are not separated.
For example:
```
IOStream
mySDR
GPIO
```

**✓ Do** start all private properties with "m_" to differentiate them from public
and protected identifiers.

```C++
class MyClass
{
    public:
        int Value() const { return m_value; }
    private:
        int m_value;
}
```

 ## Compound Words and Common Terms
Most compound words and terms are treated as single words.

**✓ Do** treat common compound words as a single word. Use a current dictionary if necessary to determine if a 
compound word is written in closed form.

Here are some examples:

| Use | Not |
| --- | --- |
| BitFlag | bitflag |
| Callback | CallBack |
| DoNot | Dont |
| Email | EMail |
| Endpoint | EndPoint |
| FileName | Filename |
| Gridline | GridLine |
| Hashtable | HashTable |
| Metadata | MetaData |
| Multipanel | MultiPanel |
| SignIn | Signin |
| UserName | Username |
| WhiteSpace | Whitespace |

## Case Sensitivity
C++ is case sensitive.

## See Also
* [Naming Guidelines](naming_guidelines.md)
* [Design Guidelines](../design_guidelines/design_guidelines.md)
