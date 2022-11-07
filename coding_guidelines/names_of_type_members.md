# Names of Type Members

Types are made of members: methods, properties, events, constructors, and fields. The following sections describe
guildelines for naming type members.

## Names of Methods

Because methods are the means of taking action, the design guidelines require that method names be verbs or verb phrases.
Following this guideline serves to distinguish method names from property and type names, which are noun or adjective
phrases.

**✓ Do** use verbs or verb phrases for method names.

**✓ Do** use PascalCase for method names.

```C++
class BigNumber
{
    public:
        int CompareTo(const BigNumber&) const noexcept;
        void Increment() { AddOne(); }
    private:
        void AddOne();
};
```

## Names of Properties

Properties are getters and setters for field values. Properties are a concept from C#, so they do not formally exist in C++, but are handy to think of because it is obvious that they access fields.

Unlike other methods, properties should be given noun phrase or adjective names. This is because a property refers
to data, and the name of the property reflects that.

**✓ Do** name properties using a noun, noun phrase, or adjective.

**❌ Do not** have properties that match the name of "Get" or "Set" methods.

**✓ Do** use PascalCase when naming properties.

```C++
class BigNumber
{
    public:
        inline long long Value() const noexcept { return m_value; }
        inline void Value(const long long& bigValue) noexcept { m_value = bigValue; }
    private:
        long long m_value;
};
```

Using "Get" and "Set" indicates that the property should really be a method.

**✓ Do** name collection properties with a plural phrase describing the items in the collection instead of using
a singular phrase followed by "Collection".

```C++
class widget
{
    public:
        inline ItemsCollection& Items() const noexcept { return m_items; }
    private:
        ItemsCollection m_items;
}
```
**✓ Do** name boolean properties with an affirmative phrase (CanSeek instead of CannotSeek). Optionally, you can
also prefix boolean properties with "Is", "Can", or "Has" but only where it adds value.

**🤔 Consider** giving a property the same name as its field.

```C++
class BigNumber
{
    public:
        inline long long Value() const noexcept { return m_value; }
        inline void Value(const long long& bigValue) noexcept { m_value = bigValue; }
    private:
        long long m_value;
};
```

## Names of Events

Events always refer to some action, either one that is happening, or one that has occurred. Therefore, as with
methods, events are named with verbs or verb phrases, and the verb tense is used to indicate the time when
the event is raised.

**✓ Do** name events with a verb or a verb phrase.

Examples include "Clicked", "Painting", "DroppedDown", and so forth.

**✓ Do** give events names with a concept of before or after, using present and past tenses.

For example, a close event that is raised before a window is closed would be called "Closing", and one that is
raised after the window is closed would be called "Closed".

**❌ Do not** use "Before" or "After" prefixes or postfixes to indicate pre- and post-events. Use present
and past tenses as just described.

**✓ Do** name event handlers (delegates used as types of events) with the "EventHandler" suffix, as shown
in the following example:

```C++
using ClickedEventHandler = delegate<void(object&, const EventArgs&)>;
```

**✓ Do** use two parameters named *sender* and *e* in event handlers.

The *sender* parameter represents the object that raised the event. The *sender* parameter is typically of type
*object*, even if it is possible to employ a more specific type.

**✓ Do** name event argument classes with the "EventArgs" suffix.

## Names of Fields

### Static Public and Protected Fields

**✓ Do** use camelCase in field names.

**✓ Do** name fields using a noun, noun phrase, or adjective.

**❌ Do not** use a prefix for global field names.

For example, do not use "g_" or "s_" to indicate static fields.

## Public and Protected Instances Fields

**❌ Do not** specify public or protected instance fields in classes, only in structures.

**🤔 Consider** declaring a class with private instance fields and public properties rather than specifying a structure.

## Private Instance Fields

**✓ Do** postfix all private instance fields with "m_".

```C++
class BigNumber
{
    public:
        long long& Value() const noexcept { return m_value; }
        void Value(const long long& bigValue) noexcept { m_value = bigValue; }
    private:
        long long m_value;
};
```

## See Also
* [Naming Guidelines](naming_guidelines.md)
* [Design Guidelines](../design_guidelines/design_guidelines.md)