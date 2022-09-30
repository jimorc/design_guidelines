# Events and Callbacks

Callbacks are extensibility points that allow a framework to call back into user code through a delegate. These
delegates are usually passed to the framework through a parameter of a method.

Events are a special case of callbacks that supports convenient and consistent syntax for supplying the delegate
(an event handler). In addition, many IDEs provide statement completion and designers provide help in using
event-based APIs. (See [Event Design](event_design.md).)

**🤔 Consider** using callbacks to allow users to provide custom code to be executed by the framework.

**🤔 Consider** using events to allow users to customize the behavior of a framework without the need for
understanding object-oriented design.

**✓ Do** prefer events over plain callbacks, because they are more familiar to a broader range of developers and are
integrated with statement completion in many IDEs.

**✓ Do** use *delegate* instead of *std::function* when defining APIs with callbacks.

*delegate* uses fewer resources than *std::function*.

**✓ Do** understand that by calling a delegate, you are executing arbitrary code and that could have security,
correctness, and compatibility repercussions.

## See Also

* [Design of Extensibility](design_for_extensibility.md)
* [Design Guidelines](design_guidelines.md)