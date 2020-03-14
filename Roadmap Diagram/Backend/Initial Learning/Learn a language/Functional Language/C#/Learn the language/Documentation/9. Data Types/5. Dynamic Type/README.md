# Dynamic Type

## Overview

- Avoids compile time type checking;
- Resolves type at run time;

## Syntax

```c#
dynamic dynamicVariable = 1;
```

- Compiles into objects in most cases;

## Features

- A dynamic type changes its type at runtime based on the value of the expression to the right of the "=" operator;

## Methods and Properties

- If you assign a class object to the dynamic type then the compiler won't check for correct methods and properties name of a dynamic type that holds the custom class object;

## Dynamic Type as a Method Parameter

- A method can have dynamic type parameters so that it can accept any type of parameter at run time;
- Example:

```c#
class Program
{
    static void PrintValue(dynamic val)
    {
        Console.WriteLine(val);
    }

    static void Main(string[] args)
    {

        PrintValue("Hello World!!");
        PrintValue(100);
        PrintValue(100.50);
        PrintValue(true);
        PrintValue(DateTime.Now);
    }
}
```

- Returns:

```markdown
Hello World!!
100
100.50
True
01-01-2014 10:10:50
```

## Points to Remember

- The dynamic types are resolved at runtime instead of compile time;
- The compiler skips the type checking for dynamic type;
- The dynamic types don't have Intellisense support in Visual Studio;
- A method can have parameters of the dynamic type;
- An exception is thrown at runtime if a method or property is not compatible;

## Links

- <https://www.tutorialsteacher.com/csharp/csharp-dynamic-type> ;
