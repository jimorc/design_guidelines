# Design Guidelines
This document and its subdocuments provide guidelines that I follow in my C++ projects starting in 2022. The goal is to
help contributors ensure API consistency, ease of use, and ease of reading the source code by providing a unified
programming model for development. I recommend that you follow these design guidelines when modifying the code
in my repositories, and when submitting new functionality to them. Inconsistent application and framework
design adversely affects developer productivity and discourages adoption.

 From a recent discussion on Code Project:

 > You don't write code for yourself, or even for the compiler; you write it for the poor soul who has to maintain your code when you have moved on. Therefore:  
>
>* The code should, as far as possible be self-explanatory - meaningful variable /function / ... names, etc.
>>
> * Where the code is not self-explanatory, it must be commented sufficiently to explain what you have done.
>
> * Ideally, all functional blocks should appear once, and once only, in the module. This implies refactoring common code into functions, etc.
> * A design document is typically necessary in order to explain your decisions. This cannot be replaced by comments in the code!
>
> Anything and everything else (code formatting etc.) is a matter of personal taste. Many companies have guidelines that might clash with your preferred style, but this is not a hill to die upon.
>
> -- Daniel Pfeffer

The guidelines in this document attempt to satisfy most of the requirements outlined by Daniel. Where personal choice is
involved, I am the sole source for the guidelines and specifications. That is because I started the projects.

The guidelines are organized as simple recommendations prefixed with the terms **✓ Do**, **🤔 Consider**, **❌ Avoid**, 
and  **❌ Do not**. 
However, they must be followed for any additions or modifications to the projects that specify these guidelines.

## Guidelines
* [Type Design Guidelines](type_design_guidelines.md) 
* [Member Design Guidelines](member_design_guidelines.md)
* [Design for Extensibility](design_for_extensibility.md)
* [Design Guidelines for Exception](design_guidelines_for_exception.md)
* [Common Design Patterns](common_design_patterns.md)

## See Also

* [Coding Guidelines](../coding_guidelines/coding_guidelines.md)