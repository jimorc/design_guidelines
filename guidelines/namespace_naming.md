# Namespace Naming

As with other naming guidelines, the goal when naming namespaces is to create sufficient clarity for the programmer
using the library or framework to immediately know what the content of the namespace is likely to be. The following
template specifies the general rule for naming namespaces:
```
<company>::(<product>|<technology>)[::<feature][::>subnamespace]>]
```
Here are some examples:

**fabrikam::math**

**bitware::security**

**✓ Do** prefix namespace names with a company name of *jimo* to prevent namespaces from different companies from having
the same name.

**✓ Do** use a stable, version-independent product name at the second level of the namespace name. For this project, use
*jxtd*.

## Namespace and Type Name Conflicts

**❌ Do not** use the same name for a namespace name and a type in that namespace.

For example, do not use jimo as a namespace name and then also provide a class named jimo in the same namespace.
Several compilers require such types to be fuly qualified.

**❌ Do not** introduce generic type names such as element, node, log, and message.

There is a high probability that doing so will lead to type name conflicts in common scenarios. You should
qualify the generic type names (form_element, xml_node, event_log, soap_message).

## See Also
* [Naming Guidelines](naming_guidelines.md)
* [Design Guidelines](design_guidelines.md)