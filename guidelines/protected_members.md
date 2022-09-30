# Protected Members

Protected members by themselves do not provide any extensibility, but they can make extensibility through subclassing
more powerful. They can be used to expose advanced customization options without unnecessarily complicating the main
public interface.

Framework designers need to be careful with protected members because the name "protected" can give a false sense of
security. Anyone is able to subclass a non-final class and access protected members,and so all the same defensive
coding practices used for public members apply to protected members.

**🤔 Consider** using protected members for advanced customization.

**✓ Do** treat protected members in non-final classes as public for the purpose of security, documentation, and
compatibility analysis.

Anyone can inherit from a class and access protected members.

## See Also

* [Design of Extensibility](design_for_extensibility.md)
* [Design Guidelines](design_guidelines.md)