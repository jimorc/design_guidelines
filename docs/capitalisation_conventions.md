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
property_desctiptor
tag
```

You will see all of these capitalisation rules used in C++ code and in C++ library APIs. No single rule is better than
another; what is important is consistency within a library or project.

**✓ Do** use snake_case for identifiers throughout the libjxtd project.

A special case is made for tw- or three-letter acronyms in which both or all three letters are not separated.
For example:
```
io_stream
my_sdr
```

**✓ Do** start all private properties, events, methods, and members with "_" to differentiate them from public
and protected identifiers.

```C++
class myclass
{
    public:
        int value() const { return _value; }
    private:
        int _value;
}
```

 ## Compound Words and Common Terms
Most compound words and terms are treaed as single words.

**✓ Do** treat common compound words as a single word. Use a current dictionary if necessary to determine if a 
compound word is written in closed form

Here are some examples:

| Use | Not |
| --- | --- |
| bit_flag | bitflag |
| callback | call_back |
| do_not | dont |
| email | e_mail |
| endpoint | end_point |
| file_name | filename |
| gridline | grid_line |
| hashtable | hash_table |
| metadata | meta_data |
| multipanel | multi_panel |
| namespace | name_space |
| placeholder | place_holder |
| sign_in | signin |
| user_name | username |
| white_space | whitespace |

## Case Sensitivity
C++ is case sensitive.

## See Also
* [Naming Guidelines](naming_guidelines.md)
* [Design Guidelines](design_guidelines.md)
