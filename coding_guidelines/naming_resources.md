# Naming Resources

Because localizable resources can be referenced via certain objects as if they were properties, the naming guidelines for
resources are similar to property naming guidelines.

**✓ Do** use snake_casing in resource keys.

**✓ Do** provide descriptive rather than short identifiers.

**❌ Do not** use language-specific keywords of C++ and related languages.

**✓ Do** use only alphanumeric characters and underscores in naming resources.

**✓ Do** use the following naming convention for exception message resources.

The resource identifier should be the exception type name plus a short identifier of the exception:

**argument_exception_illegal_characters**

**argument_exception_invalid_name**

**argument_exception_file_name_is_malformed**

## See Also
* [Naming Guidelines](naming_guidelines.md)
* [Design Guidelines](../design_guidelines/design_guidelines.md)