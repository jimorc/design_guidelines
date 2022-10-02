# Event Design

Events are the most commonly used form of callbacks (constructs that allow the framework to call into user code).
Other callback mechanisms include members taking delegates, virtual methods, and interface-based plug-ins. Data
from usability studes indicate that the majority of developers are more comfortable using events than they are
using other callback mechanisms.

It is important to note that there are two groups of events: events raised before a state of the system changes,
called pre-events, and events raised after a state changes, called post-events. An example of a pre-event would be
window::closing, which is raised before a window is closed. An example of a post_event would be window::closed,
which is raised after the window is closed.

**✓ Do** use the term "raise" for events rather than "fire" or "trigger".

The following guidelines apply specifically to libjxtd:

* **✓ Do** use xtd::generic_event_handler<event_args_t> instead of manually creating new delegates to be used as
event handlers.

* **🤔 Consider** using a sublass of xtd::event_args as the event argument, unless you are absolutely sure the
event will never need to carry any data to the event handling method, in which case you can use xtd::event_args
directly.

  If you ship an API using xtd::event_args directly, you will never be able to add any data to be carried with
the event without breaking compatibility. If you use a subclass, even if initially completely empty, you will be able
to add properties to the subclass when needed.

* **✓ Do** use a public virtual method to raise each event. This is applicable to non-static events on classes, or
static events.

  The purpose of the method is to provide a way for a derived class to handle the event using an override. Overriding
is a more flexible, faster, and more natural way to handle base class events in derived classes. By convention, the
name of the method should start with "on_" and be followed by the name of the event.

  The derived class can choose not to call the base implementation of the method in its override. Be prepared for this
by not including any processing in the method that is required for the base class to work correctly.

* **✓ Do** take one parameter to the method that raises an event.

  The parameter should be named *e* and should be typed as the event argument class. You can pass xtd::event_args::empty
  if you don't want to pass any data to the event handling method.

# See Also

* [Member Design Guidelines](member_design_guidelines.md)
* [Design Guidelines](design_guidelines.md)