# Coding and Design Guidelines

Good coding and design guidelines ensure that:

* There is a consistent look to a project's code.
* The code is written using industry or company standard practices, such as using common design patterns.
* A framework's API is consistent.
* The API is properly documented using industry or company standard documentation methods and tools.

While, at first glance, code appears to be written to be compiled, linked, and executed on computers, it must also
be written for current and future developers and maintainers, including yourself. If you are writing one-off
code solely for your
own use and that code is never seen by another person, you can do anything you want. But for any application that
is used, maintained, and updated, then following good coding and design guidelines will make the job easier in the
long run.

Anecdote: I worked with a developer who once wrote an application with every variable named as something in one of his
hobbies. When he left, I was left holding the bag; I had to maintain the application. It was much harder than it
should have been.

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

Hopefully you understand the need to good guidelines.

## Guidelines

Here are the guidelines that I have started using in my C++ projects. 

* [Coding Guidelines](coding_guidelines/coding_guidelines.md)
* [Design Guidelines](design_guidelines/design_guidelines.md)

These guidelines began life as a set of documents published by Microsoft about their C# and .Net framework. They were modified by gammasoft71 for C++ and used for their 
[xtd GUI framework](https://github.com/gammasoft71/xtd). I further modified them for my use by removing some remaining
C# concepts and idioms, and by changing specifics for how I design and code. Most of the changes were in the coding
guidelines for such things as the placement of braces, spaces, and the naming of things.

There is some parallel between my guidelines and Bjarne Stroustrup and Herb Sutter's 
[C++ Core Guidelines](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md) although
my guidelines do not touch on everything in the core guidelines and also cover topics not included in the guidelines.
I suggest reviewing the core guidelines as well as my guidelines. The combination will provide a great starting point
for designing and building good C++ applications, libraries, and frameworks.

One final thing: if you are planning to contribute to one of my projects, then you must follow my guidelines. If you
contribute to other projects, you are expected to follow their coding and design guidelines. In many cases, one set
of guidelines is not better or worse than another set, just different. But having guidelines that are followed by
everyone contributing to a project makes life easier for everyone who ever work on that project.