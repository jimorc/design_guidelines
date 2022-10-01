# Common Design Patterns

Design patterns are solutions to software design problems you find again and again in real-world application
development. Patterns are about reusable designs and interactions of objects.

The 23 Gang of Four (GoF) patterns are generally considered the foundation for all other patterns. They are
categorized in three groups: Creational, Structural. and Behavioral. See below for a complete list of patterns.

To give you a head start, the C++ source code for each pattern is provided in structural form. Structural code uses
type names as define in the pattern definition and UML diagrams.

## Notes

The Common Design Patterns are adapted to modern C++ and follow the std standard.

## The Patterns

Rather than repeat the work of others, I will simply provide an external link for each pattern. In most cases, the links
are to the bogotobogo website. There are links to other sites when the Source Code Examples site does not have a 
descrition of the pattern.

In every case, I have tried to find a description that includes both a UML diagram and sample source code for the
pattern.

## Creational Patterns

* [Abstract Factory](https://mail.bogotobogo.com/DesignPatterns/abstractfactorymethod.php) - 
Creates an instance of several families of classes.
* [Builder](https://medium.com/nerd-for-tech/builder-design-pattern-fluent-interface-c-70cae9490a91) -
Separates object construction from its representation
* [Factory Method](https://mail.bogotobogo.com/DesignPatterns/factorymethod.php) -
Creates an instance of several derived classes
* [Prototype](https://mail.bogotobogo.com/DesignPatterns/prototype.php) -
A fully initialized  instance to be copied or cloned
* [Singleton](https://iq.opengenus.org/singleton-design-pattern-in-cpp/) -
A class of which only a single instance can exist

## Structural Patterns

* [Adapter](https://www.bogotobogo.com/DesignPatterns/adapter.php) -
Match interfaces of different classes
* [Bridge](https://mail.bogotobogo.com/DesignPatterns/bridge.php) -
Separates an object's interface from its implementation
* [Composite](https://www.sourcecodeexamples.net/2020/09/c-composite-pattern-example.html) -
A tree structure of simple and composite objects
* [Decorator](https://mail.bogotobogo.com/DesignPatterns/decorator.php) -
Add responsibilities to objects dynamically
* [ Façade](https://mail.bogotobogo.com/DesignPatterns/facade.php) -
A single class that represents an entire subsystem
* [Flyweight](https://www.geeksforgeeks.org/flyweight-design-pattern/) -
A fine-grained instance used for efficient sharing
* [Proxy](https://mail.bogotobogo.com/DesignPatterns/proxy.php) -
An object representing another object

## Behavioral Patterns

* [Chain of Responsibility](https://www.bestprog.net/en/2021/09/25/patterns-the-chain-of-responsibility-pattern-implementation-in-c/) -
A way of passing a request between a chain of objects
* [Command](https://medium.com/geekculture/understanding-the-chain-of-responsibility-pattern-d729ef84621c) -
Encapsulate a commend request as an object
* [Interpreter](https://www.fatalerrors.org/a/c-design-pattern-interpreter-pattern.html) -
A way to include language elements in a program
* [Iterator](https://www.bestprog.net/en/2021/05/20/patterns-iterator-cursor-pattern-general-information/) -
Sequentially access the elements of a collection
* [Mediator](https://www.sourcecodeexamples.net/2020/09/c-mediator-pattern-example.html) -
Defines simplified communication between classes
* [Memento](https://www.sourcecodeexamples.net/2020/09/c-memento-pattern-example.html) - 
Capture and restore an object's state
* [Observer](https://iq.opengenus.org/observer-pattern-cpp/) - 
A way of notifying change to a number of classes
* [State](https://www.sourcecodeexamples.net/2020/09/c-state-pattern-example.html) -
Alter an object's behavior when its state changes
* [Strategy](https://www.bogotobogo.com/DesignPatterns/strategy.php) -
Encapsulates an algorithm inside a class
* [Template Method](https://mail.bogotobogo.com/DesignPatterns/template.php) -
Defer the exact steps of an algorithm to a subclass
* [Visitor](https://elegant-cpp.com/visitor-pattern-in-c-part-0/) -
Defines a new operation to a class without change

## See Also

* [Design Guidelines](design_guidelines.md)