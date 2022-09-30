# Static Class Design

A static class is defined as a class that contains only static members and possibly a private constructor.
C++ does not provide built-in support for static classes.

Static classes are a compromise between pure object-oriented design and simplicity. They are commonly used to 
provide shortcuts to other operations, or functionality for which a full object-oriented wrapper is unwarranted.
Static classes are used in other languages such as C# to hold extension methods, but as of C++20, C++ does not support
extension methods.

**✓ Do** use static classes sparingly.

Static classes should be used only as supporting classes for the object-oriented core of the library or framework.

**❌ Do not** treat a static class as a miscellaneous bucket.

**❌ Do not** declare static classes as abstract because the C++ language does not
have built-in support for static classes.

**❌ Do not** instantiate a static class.

A simple static class that contains only static accessor, method, and data members can be instantiated, although the instantiated object is zero bytes in size. Instantiating a static class makes the code longer, makes it harder to follow what is being done, and lengthens the compile time slightly. 

There are a number of ways of declaring a static class to prevent it from being instantiated.

**✓ Do** declare a constructor with no arguments as deleted in the static class. The compiler will generate an
error for any attempt to instantiate that static class.

```C++
class Foo
{
  public:
    Foo() = delete;
    static void f();
  private:
    static int _data;
};

int main()
{
  Foo foo;  // compiler error here
}
```


## See Also

* [Type Design Guidelines](type_design_guidelines.md)
* [Design Guidelines](design_guidelines.md)