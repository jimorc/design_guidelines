# Naming Parameters

Beyond the obvious reason of readability, it is important to follow the guidelines for parameter names because parameters
are displayed in documentation and when IDEs provide intellisense and class browsing functionality.

**✓ Do** use snake_casing in parameter names.

**✓ Do** use descriptive parameter names.

**✓ Do** use a parameter name based on the  parameter's meaning rather than the parameter's type.

## Naming Operator Overload Parameter

**✓ Do** use left and right for binary operator overload parameter names if there is no meaning to the parameters.

**✓ Do** use value for the unary operator overload parameter name if there is no meaning to the parameter.

**✓ Do** use meaningful names for operator overload parameters if doing so adds significant value.

**❌ Do not** use abbreviations or numeric indices for operator overload parameter names.

## See Also
* [Naming Guidelines](naming_guidelines.md)
* [Design Guidelines](design_guidelines.md)