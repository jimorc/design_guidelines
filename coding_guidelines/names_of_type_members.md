# Names of Type Members

Types are made of members: methods, properties, events, contstructors, and fields. The following sections describe
guildelines for naming type members.

## Names of Methods

Because methods are the means of taking action, the design guidelines require that method names be verbs or verb phrases.
Following this guideline serves to distinguish method names from property and type names, which are noun or adjective
phrases.

**✓ Do** give method names that are verbs or verb phrases.

```C++
class big_number
{
    public:
        int compare_to(const big_number&) const noexcept;
        void increment();
};
```

**✓ Do** postfix private methods with an underscore.

```C++
class big_number
{
    public:
        int compare_to(const big_number&) const noexcept;
        void increment() { add_one_(); }
    private:
        void add_one_();
};
```

## Names of Properties

Unlike other members, properties should be given noun phrase or adjective names. This is because a property refers
to data, and the name of the property reflects that. snake_casing is always used for property names.

**✓ Do** name properties using a noun, noun phrase, or adjective.

**❌ Do not** have properties that match the name of "get_" or "set_" methods.

```C++
class big_number
{
    public:
        long long value() const noexcept { return _value; }
        void value(const long long& big_value) noexcept { _value = big_value; }
    private:
        long long _value;
};
```

Using "get_" and "set_" indicates that the property should really be a method.

**✓ Do** name collection properties with a plural phrase describing the items in the collection instead of using
a singular phrase followed by "_collection".

```C++
class widget
{
    public:
        items_collection& items() { return _items; }
    private:
        items_collection _items;
}

**✓ Do** name boolean properties with an affirmative phrase (can_seek instead of cant_seek). Optionally, you can
also prefix boolean properties with "is_", "can_", or "has_" but only where it adds value.

**🤔 Consider** giving a property the same name as its type.

```C++
class big_number
{
    public:
        long long& value() const noexcept { return _value; }
        void value(const long long& big_value) noexcept { _value = big_value; }
    private:
        long long _value;
};
```

## Names of Events

Events always refer to some action, either one that is happening, or one that has occurred. Therefore, as with
methods, events are named with verbs or verb phrases, and the verb tense is used to indicate the time when
the event is raised.

**✓ Do** name events with a verb or a verb phrase.

Examples include "clicked", "painting", "dropped_down", and so forth.

**✓ Do** give event names with a concept of before or after, using present and past tenses.

For example, a close event that is raised before a window is closed would be called "closing", and one that is
raised after the window is closed would be called "closed".

**❌ Do not** use "before_" or "after_" prefixes or postfixes to indicate pre- and post-events. Use present
and past tenses as just described.

**✓ Do** name event handlers (delegates uses as types of events) with the "_event_handler" suffix, as shown
in the following example:

```C++
using clicked_event_handler = delegate<void(object&, consst event_args&)>;
```

**✓ Do** use two parameters named *sender* and *e* in event handlers.

The *sender* parameter represents the object that raised the event. The *sender* parameter is typically of type
*object*, even if it is possible to employ a more specific type.

**✓ Do** name event argument classes with the "event_args" suffix.

## Names of Fields

### Static Public and Protected Fields

**✓ Do** use snake_casing in field names.

**✓ Do** name fields using a noun, noun phrase, or adjective.

**❌ Do not** use a prefix for field names.

For example, do not use "g_" or "s_" to indicate static fields.

## Public and Protected Instances Fields

**❌ Do not** specify public or protected instance fields in classes, only in structures.

**🤔 Consider** declaring a class with private instance fields and public properties rather than specifying a structure.

## Private Instance Fields

**✓ Do** postfix all private instance fields with an underscore.

```C++
class big_number
{
    public:
        long long& value() const noexcept { return _value; }
        void value(const long long& big_value) noexcept { _value = big_value; }
    private:
        long long value_;
};
```

## See Also
* [Naming Guidelines](naming_guidelines.md)
* [Design Guidelines](../design_guidelines/design_guidelines.md)