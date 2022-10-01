# Exception Throwing

Exception-throwing guidelines described in this section require a good definition of the meaning of execution failure.
Execution failure occurs whenever a member cannot do what it was designed to do (what the member name implies). For
example, if the open_file method cannot return an opened file handle to the caller, it would be considered an
execution failure.

Most developers have become comfortable using exceptions for errors such as division by zero or null references. In
a framework, exceptions should be used for all error conditions, including execution errors.

**❌ Do not** return error codes.

Exceptions are the primary means of reporting errors in frameworks.

**✓ Do** report execution failures by throwing exceptions.

**❌ Do not** use exceptions for the normal flow of control, if possible.

Except for system failures and operations with potential race conditions, framework designers should assign APIs so
users can write code that does not throw exceptions. For example, you can provide a way to check preconditions before
calling a member so users can write code that does not throw exceptions.

**🤔 Consider** the performance implications of throwing exceptions. Throw rates above 100 per second are likely to
noticeably impact the performance of most applications.

**✓ Do** document all exceptions thrown by publicly callable members because of a violation of the member contract
(rather than a system failure) and treat them as part of your contract.

Exceptions that are part of the contract should not change from one version to the next (i.e. exception type should
not change, and new exceptions should not be added).

**❌ Do not** have public members that can either throw or not based on some option.

**❌ Do not** have public members that return exceptions or a reference parameter as the return value.

Returning exceptions from public APIs instead of throwing them defeats many of the benefits of exception-based
error reporting.

**🤔 Consider** using exception builder methods.

It is common to throw the same exception from different places. To avoid code bloat, use helper methods that create
exceptions and initialize their properties.

Also, members that throw exceptions do not get inlined. Moving the throw statement inside the builder might allow
the member to be inlined.

**❌ Do not** throw exceptions from exception filter blocks.

## See Also

* [Design Guidelines for Exception](design_guidelines_for_exception.md)
* [Design Guidelines](design_guidelines.md)