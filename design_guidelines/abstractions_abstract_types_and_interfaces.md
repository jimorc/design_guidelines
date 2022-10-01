# Abstractions (Abstract Types and Interfaces)

An abstraction is a type that describes a contract but does not provide a full implementation of the contract.
Abstractions are usually implemented as abstract classes or as interfaces, and they come with a well-defined set
of reference documentation describing the required semantics of the types implementing the contract.

You can extend frameworks by implementing a concrete type that supports the contract of an abstraction and using
this concrete type with framework APIs consuming (operating on) the abstraction.

A meaningful and useful abstraction that is able to withstand the test of time is very difficult to design. The main
difficulty is getting the right set of members, no more and no fewer. If an abstraction has too many members, it
becomes difficult or even impossible to implement. If it has too few members for the promised functionality, it
becomes useless in many interesting scenarios.

Too many abstractions in a framework also negatively affects usability of the framework. It is often quite difficult
to understand an abstraction without understanding how it fits into the larger picture of the concrete implementations
and the APIs operating on the abstraction. Also, names of abstractions and their members are necessarily abstract,
which often makes them cryptic and unapproachable without first understanding the broader context of their usage.


However, abstractions provide extremely powerful extensibility that the other extensibility mechanisms cannot often
match. They are at the core of many architectural patterns, such as plug-ins, Inversion of Control (IoC), pipelines,
and so on. They are also extremely important for testability of frameworks. Good abstractions make it possible
to stub out heavy dependencies for the purpose of unit testing. In summary, abstractions are responsible for the
sought-after richness of modern object-oriented frameworks.

**❌ Do not** provide abstractions unless they are tested by developing several concrete implementations and APIs
consuming the abstractions.

**✓ Do** choose carefully between an abstract class and an interface when designing an abstraction.

**🤔 Consider** providing reference tests for concrete implementation of abstractions. Such tests should allow
users to test whether their implementions correctly implement the contract.

## See Also

* [Design of Extensibility](design_for_extensibility.md)
* [Design Guidelines](design_guidelines.md)