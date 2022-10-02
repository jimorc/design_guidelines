# Exceptions and Performance

One common concern related to exceptions is that if exceptions are used for code that routinely fails, the performance
of the implementation will be unacceptable. This is a valid concern. When a member throws an exception, its
performance can be orders of magnitude slower. However, it is possible to use either the *Tester-Doer* Pattern or the
*Try-Parse* Pattern, described in the next two sections.

## Tester-Doer Pattern

Sometimes performance of an exception-throwing member can be improved by breaking the member into two. Let's look at
the *at* method of the std::vector<type_t> interface:

```C++
std::vector<int> numbers = ...
auto val = numbers.at(9);
```

The method *at* throws if the collection size is less than 10. This can be a performance problem in scenarios where the
method call is expected to fail often. One of the ways to mitigate the problem is to test whether the vector size is
greater or equal to 10 before trying to get a value:

```C++
std::vector<int> numbers = ...
...
if (numbers.size() >= 10)
{
    auto val = numbers.at(9);
}
```

The member used to test a condition, which in our case is the property *size*, is referred to as the tester. The member
used to perform a potentially throwinig operation, the *at* method in our example, is referred to as the doer.

**🤔 Consider** the Tester-Doer Pattern for members that might throw exceptions in common scenarios to avoid performance
problems related to exceptions.

## Try-Parse Pattern

For extremely performance-sensitive APIs, an even faster pattern than the *Tester-Doer* Pattern described in the
previous section should be used. The pattern calls for adjusting the member name to make a well-defined test case
a part of the member semantics. For example, consider a date_time class that defines a parse method that throws an
exception if parsing of a string fails. It also defines a corresponding try_parse method that attempts to parse,
but returns false if parsing is unsuccessful and returns the result of a successful parsing using a ref parameter.

```
struct date_time
{
    public:
        static date_time parse(const string& date_time)
        {
            ...
        }
        static bool try_parse(const string& date_time, date_time& result)
        {
            ...
        }
};
```

When using this pattern, it is important to define the try functionality in strict terms. If the member fails for any
reason other than the well-defined try, the member must still throw a corresponding exception.

**🤔 Consider** the *Try-Parse* Pattern for members that might throw exceptions in common scenarios to avoid
performance problems related to exceptions.

**✓ Do** use the prefix "try_" and boolean return type for methods implementing this pattern.

**Do** provide an exception-throwing member for each member using the *Try-Parse* Pattern.

## See Also

* [Design Guidelines for Exception](design_guidelines_for_exception.md)
* [Design Guidelines](design_guidelines.md)