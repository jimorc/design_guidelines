# Design for Extensibility

One important aspect of designing a framework is making sure the extensibility of the framework has been carefully
considered. This requires that you understand the costs and benefits associated with various extensibility
mechanisms. This chapter helps you decide which of the extensibility mechanisms - subclassing, events, virtual members,
callbacks, and so on - can best meet the requirements of the framework.

There are many ways to allow extensibility in frameworks. They range from less powerful and less costly to very
powerful but expensive. For any given extensibility requirement, you should choose the least costly extensibility
mechanism that meets the requirements. Keep in mind that it's usually possible to add more extensibility later, but
you can never take it away without introducing breaking changes.

## In This Section

* [Non-final Classes](non-final_classes.md)
* [Protected Members](protected_members.md)
* [Events and Callbacks](events_and_callbacks.md)
* [Virtual Members](virtual_members.md)
* [Abstractions (Abstract Types and Interfaces)](abstractions_abstract_types_and_interfaces.md)
* [Base Classes for Implementing Abstractions](base_classes_for_implementing_abstractions.md)
* [Final Classes](final_classes.md)

## See Also

* [Design Guidelines](design_guidelines.md)