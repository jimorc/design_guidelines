# General Naming Conventions

This section describes general naming conventions that relate to work choice, guidelines on using
abbreviations and acronyms, and recommendations on how to avoid using C++ names and keywords.

## Word Choice

**✓ Do** choose easily readable identifier names

| Yes | No |
| --- | --- |
| horizontal_alignment | alignment_horizontal |
| horizontal_layout_panel | horz_layout |
| frequency_digit | digit |

**✓ Do** favor readability over brevity

| Yes | No |
|--- | --- |
| can_scroll_horizontally | scrollable_x |
| frequency_digit | d_freq |

**❌ Do not** use hyphens or other non-alphanumeric characters except underscores. The C++ compiler will prevent you
from using most of these characters anyway.

**❌ Do not** use Hungarian notation or any variant of it. Do not preface pointer names with "p" or "ptr_".

**❌ Do not** use identifiers that conflict with C++ keywords. You may also want to avoid using keywords from other
widely used programming languages.

## Using Abbreviations and Acronyms

**❌ Do not** use abbreviations or contractions as part of identifier names.

| Yes | No |
| --- | --- |
| do_not | dont |
| horizontal_layout_panel | horz_lo_pnl |

## Avoid C++ Keywords

**✓ Do** use semantically interesting names rather than language-specific keywords for type names.

For example: to_length is a better name than to_int.

**✓ Do** use generic cstdint type names, rather than a C++ name, in the rare cases when an identifier has no
semantic meaning beyond its type.

For example, a method for converting to int64_t should be called to_int64, not to_long because int64_t is a
cstdint name for the C++ alias long long.

The following table presents several base data types using the cstdint type names as well as the corresponding type
names in C++.

| C++ | cstdint | Size in Bytes |
| --- | ------- | ------------- |
| char | int8_t | 1 |
| unsigned char | uint8_t | 1 |
| short | int16_t | 2 |
| unsigned short | unit16_t | 2 |
| int | int32_t | 4 |
| unsigned int | uint32_t | 4 |
| long | long | variable: 4 on 32-bit machines, 8 on 64-bit machines |
| unsigned long | unsigned long | variable: 4 on 32-bit machines, 8 on 64-bit machines |
| long long | int64_t | 8 |
| unsigned long long | uint64_t | 8 |
| float | float | 4 |
| double | double | 8 |
| long double | long double | 16 |
| bool | bool | 1 |
| wchar_t | wchar_t | 4 |
| char* | string | variable |

**✓ Do** use a common name, such as value or item, rather than repeating the type name, in the rare cases
when an identifier has no semantic meaning and the type of the parameter is not important.

## Naming New Versions of Existing APIs

**✓ Do** use a name similar to the old API when creating new versions of an existing API.

This helps to highlight the relationship between the APIs.

**✓ Do** add a suffix rather than a prefix to indicate a new version of an existing API.

This will assist discovery when browsing documentation, or using intellisense. The old version of the API will
be organised close to the new APIs, because browsers and intellisense show identifiers in alphabetical order.

**✓ Do** use a brand new, but meaningful identifier, rather than adding a prefix or suffix to an existing
identifier.

**✓ Do** use a numeric suffix to indicate a new version of an existing API, particularly if the name of
the existing API is the only name that makes sense (i.e. if it is an industry standard) and if adding any
meaningful suffix, or changing the name, is not an appropriate action.

**❌ Do not** use "ex" or a similar suffix for an identifier to distinguish it from an earlier version of the 
same API.

**✓ Do** use the "64" suffix when introducing versions of APIs that operate on a 64-bit integer (a long integer)
instead of a 32-bit integer. You only need to take this approach when the existing 32-bit API exists; don't do
it for brand new APIs with only a 64-bit version.

## See Also
* [Naming Guidelines](naming_guidelines.md)
* [Design Guidelines](design_guidelines.md)