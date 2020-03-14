# Partial Classes

## Overview

- The partial modifier can be applied to a class, method, interface or structure, and it provides the ability to have a single class implementation in multiple .cs files;
- For example, the following MyPartialClass splits into two files, PartialClassFile1.cs and PartialClassFile2.cs:

```c#
PartialClassFile1.cs

public partial class MyPartialClass
{
    public MyPartialClass()
    {
    }

    public void Method1(int val)
    {
        Console.WriteLine(val);
    }
}

```

```c#
PartialClassFile2.cs

public partial class MyPartialClass
{
    public void Method2(int val)
    {
        Console.WriteLine(val);
    }
}
```

- Then, the compiler combines these two partial classes into one class as shown below:

```c#
public class MyPartialClass
{
    public MyPartialClass()
    {
    }

    public void Method1(int val)
    {
        Console.WriteLine(val);
    }

    public void Method2(int val)
    {
        Console.WriteLine(val);
    }
}
```

## Partial Class Requirements

- Must be in the same assembly and namespace;
- Must have the same accessibility like public or private, etc;
- If any part is declared abstract, sealed or base type then the whole class is declared of the same type;
- Different parts can have different base types and so the final class will inherit all the base types;

## Advantages of the Partial Class

- Multiple developers can work simultaneously with a single class in separate files;
- When working with automatically generated source, code can be added to the class without having to recreate the source file;

## Partial Methods

- A partial class or struct may contain partial methods;
- If the partial method doesn't have an implementation in any part then the compiler will not generate that method in the final class;
- For example:

```c#
PartialClassFile1.cs:

public partial class MyPartialClass
{
    partial void PartialMethod(int val);

    public MyPartialClass()
    {

    }

    public void Method2(int val)
    {
        Console.WriteLine(val);
    }
}
```

```c#
PartialClassFile2.cs

public partial class MyPartialClass
{
    public void Method1(int val)
    {
        Console.WriteLine(val);
    }

    partial void PartialMethod(int val)
    {
        Console.WriteLine(val);
    }
}
```

- Here, PartialClassFile1.cs contains the declaration of the partial method and PartialClassFile2.cs contains the implementation of the partial method;

### Requirements for Partial Method

- Must begin with the partial modifier;
- Can have a ref but not an out parameter;
- Are implicitly private;
- Can be static methods;
- Can be generic;

## Points to Remeber

- Use the partial keyword to split interface, class, method or structure into multiple .cs files;
- The partial method must be declared before implementation;
- All the partial class, method , interface or structs must have the same access modifiers;

## Links

- <https://www.tutorialsteacher.com/csharp/csharp-partial-class> ;
