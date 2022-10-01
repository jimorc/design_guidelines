# Using Standard Exception Types

This section describes the standard exceptions that should be provided or used by a framework and the details of their
usage. This is by no means exhaustive. Please refer to the C++ std::exception documentation, or framework
documentation for usage of other exception types.

This document makes reference to standard exception types and exception types from the xtd framework. If extending a
different framework, make the appropriate substitutions for that framework. If creating a new framework, consider
defining equivalent exception classes.

## Exception and system_exception

**❌ Do not** throw std::exception, std::system_error, or xtd::system_exception.

**❌ Do not** not catch std::exception, std::system_error, or xtd::system_exception in framework code unless you intend to rethrow.

**❌ Avoid** catching std::exception, std::system_error, or xtd::system_exception, except in top-level exception handlers.

## Application Exceptions

**❌ Do not** throw or derive from xtd::application_exception.

## Invalid Operation Exception

**✓ Do** throw an xtd::invalid_operation_exception if the object is in an inappropriate state.

## Argument Exception, Argument Null Exception, and Argument Out of Range Exception

**✓ Do** throw std::invalid_argument, xtd::argument_exception, or one of its subtypes if bad arguments are passed to a
member. Prefer the most derived exception type, if applicable.

**✓ Do** include the parameter name for std::invalid_argument, or set the param_name property for xtd::argument_exception
when throwing one of its subclasses.

This property represent the name of the parameter that caused the exception to be thrown. Note that the property can be
set for xtd::argument_exception using one of the construction overloads.

**✓ Do** use *value* for the name of the implicit value parameter of property setters.

Stack Overflow Exceptions

There is no std::stack_overflow or equivalent exception; the system normally reports stack overflow as a segmentation fault, at least on MacOS.

**❌ Do not** explicitly attempt to throw an exception for a stack overflow condition. The exception should be
explicitly thrown only by the operating system.

**❌ Do not** attempt to catch a stack overflow exception.

It is almost impossible to write code that remains consistent in the presence of arbitrary stack overflows.

## Out of Memory Exception

Out of Memory exceptions may be thrown as std::bad_alloc or xtd::out_of_memory_exception.

**❌ Do not** throw std::bad_alloc or xtd::out_of_memory_exception. These exceptions are thrown by the operating
system or by the xtd infrastructure.

**❌ Do not** catch std::bad_alloc or xtd::out_of_memory_exception.

It is almost impossible to write code that remains consisten in the presence of arbitrary out of memory exceptions.

## Com, SEH, and execution_engine_exception

**❌ Do not** explicitly throw these exceptions. These exceptions are thrown either by the underlying system
infrastructure or the xtd infrastructure.

## See Also

* [Design Guidelines for Exception](design_guidelines_for_exception.md)
* [Design Guidelines](design_guidelines.md)