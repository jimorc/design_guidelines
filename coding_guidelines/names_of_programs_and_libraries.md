# Names of Programs and Libraries

This chapter describes only program and library naming conventions and not any file extension names for these.

# Program Names

A program represents a stand-alone unit of execution, that is a unit that can be called directly from the command line
or started through a GUI desktop.

**✓ Do** choose program names that describe what the program does.

For example: SDRReceiver indicates that the program is a Software Defined Radio receiver.

# Library Names

A library is an executable file that can be shared among a number of programs. You can use a static link
library (.lib or .a) or a dynamic link library (.dll, .so, or .dylib). 

**✓ Do** choose names for your libraries that suggest large chunks of functionality, such as MyGUI.Drawing.

Library names do not have to correspond to namespace names, but it is reasonable to follow the namespace name
when naming a library. A good rule of thumb is to name the library based on the common prefix of the namespaces contained
within the library. For example, a library with two namespaces, MyCompany::MyTechnology::FirstFeature and
MyCompany::MyTechnology::SecondFeature could be called MyCompanyMyTechnology.lib.

**🤔 Consider** naming libraries according to the pattern:
```
<company><component>.lib
```
where the name contains two or more underscore-separated or upper-case character separated clauses. For example: JimorcJxtd.lib.

**❌ Do not** prefix the library name with "lib".

The linker (typically ld.exe, or just ld) generates a library by collecting into one file all of the compiled files that make up the library. On Unix-like systems, the linker prepends lib to the library name, so:

* A library generated for jxtd becomes libjxtd.lib and so forth.

* A library generated for libjxtd becomes liblibjxtd.lib and so forth.

CMake also is familiar with these naming conventions, so it automatically prepends library names with lib.

## See Also

* [Naming Guidelines](naming_guidelines.md)
* [Design Guidelines](../design_guidelines/design_guidelines.md)