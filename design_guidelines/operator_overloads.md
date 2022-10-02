# Operator Overloads

The principle of encapsulation is one of the most important notions in object-oriented design. This principle states
that data stored inside an object should be accessible only to that type.

Operator overloads allow framework and library types to appear as if they were built-in language primitive types.

Although allowed and useful in some situations, operator overloads should be used cautiously. There are many cases
in which operator overloading can be abused, such as when designers and developers start to use operators for
operations that should be simple methods.

The following guidelines should help you to decide when and how to use operator overloading.

**❌ Avoid** defining operator overloads, except in types that should feel like primitive (built-in) types.

**🤔 Consider** defining operator overloads in a type that should feel like a primitive type.

For example, std::string has operator= and operator+= defined.

**✓ Do** define operator overloads in structs that represent numbers.

**❌ Do not** be cute when defining operator overloads.

Operator overloading is useful in cases in which it is immediately obvious what the result of the operation will be.
For example, it make sense to be able to subtract one date_time from another date_time to get a time_span.
However, it is not appropriate to use the logical union operator to union two database queries, or to use the shift
operator to write to a stream.

**❌ Do not** provide operator overloads unless at least one of the operands is of the type defining the overload.

**✓ Do** overload operators in a symmetric fashion.

For example, if you overload operator==, you should also overload operator!=. Similarly, if you overload operator<,
you should overload operator>, and so on.

**🤔 Consider** providing methods with friendly names that correspond to each overloaded operator.

## equals

Here is an example of overloading operator== and operator!=. A virtual method called *equals* is also provided.
```
#include <iostream>
class object
{
  public:
    object(int x) : _x(x) {}
    bool operator==(const object& o) const
    {
      if (this == &o) return true;
      return equals(o);
    }
    bool operator!=(const object& o) const
    {
      if (this == &o) return false;
      return !equals(o);
    }
    virtual bool equals(const object& o) const
    {
      return _x == o._x;
    }
  private:
    int _x;
};
class cl : public object
{
  public:
    cl(int x, int y) : object(x), _y(y) {}
    bool equals(const object& o) const override
    {
      const cl* cln = static_cast<const cl*>(&o);
      return cln != nullptr && object::equals(o) && _y == cln->_y;
    }
  private:
    int _y;
};

int main()
{
  object o1(3);
  object o2(5);
  cl cl1(1, 2);
  cl cl2(1, 3);

  std::cout << "o1 == o1: " << (o1 == o1) << '\n';
  std::cout << "o1 == o2: " << (o1 == o2) << '\n';
  std::cout << "o1 != o1: " << (o1 != o1) << '\n';
  std::cout << "o1 != o2: " << (o1 != o2) << '\n';

  std::cout << "cl1 == cl1: " << (cl1 == cl1) << '\n';
  std::cout << "cl1 == cl2: " << (cl1 == cl2) << '\n';
}
```

This code in the example above defines a base class called *object* which contains == and != operators. It also contains
a virtual method called *equals* that is called from within operator== and operator!=.

*cl* is a class that is derived from *object*. It overrides the object::equals method and does the following:
1. Attempts to convert the *object* argument to a *cl*. 
2. Returns true or false depending on the all of the following conditions:
   * The *object* argument passed in is in fact a *cl*.
   * The base objects are equal.
   * The fields added by the *cl* class are equal.

## C++ Operators
Most, but not all operators can be overloaded. See [Operators in C and C++](https://en.wikipedia.org/wiki/Operators_in_C_and_C%2B%2B) for a list of all operators, prototype examples, and whether they can be overloaded.

# See Also

* [Member Design Guidelines](member_design_guidelines.md)
* [Design Guidelines](design_guidelines.md)