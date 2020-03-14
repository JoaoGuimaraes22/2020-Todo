# Extension Method

## Overview

- Are additional methods;
- Allow you to inject additional methods without modifying, deriving or recompiling the original class, struct or interface;
- Can be added to your own custom class, .NET framework classes, or third party classes or interfaces;

## Extension Methdos

- An extension method is actually a special kind of static method defined in a static class;
- To define an extension method, first of all, define a static class;
- Now, define a static method as an extension method where the first parameter of the extension method specifies the type on which the extension method is applicable;
- Example:

```c#
namespace ExtensionMethods
{
    public static class IntExtensions
     {
        public static bool IsGreaterThan(this int i, int value)
        {
            return i > value;
        }
    }
}
```

- Now, you can include the ExtensionMethods namespace wherever you want to use this extension method:

```c#
using ExtensionMethods;

class Program
{
    static void Main(string[] args)
    {
        int i = 10;

        bool result = i.IsGreaterThan(100);

        Console.WriteLine(result);
    }
}
```

- Returns:

```markdown
false
```

## Points to Remember

- Extension methods are additional custom methods which were originally not included with the class;
- Extension methods can be added to custom, .NET Framework or third party classes, structs or interfaces;
- The first parameter of the extension method must be of the type for which the extension method is applicable, preceded by the this keyword;
- Extension methods can be used anywhere in the application by including the namespace of the extension method;

## Links

- <https://www.tutorialsteacher.com/csharp/csharp-extension-method;>
