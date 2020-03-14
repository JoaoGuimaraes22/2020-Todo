# Generic Constraints

## Overview

- Generics allow you to define a class with placeholders for the type of its fields, methods, parameters, etc;
- C# includes Constraints to specify which type of placeholder type with the generic class is allowed;

## Syntax

- Constraints can be applied using the where keyword;
- Example:

```c#
class MyGenericClass<T> where T: class
{
    private T genericMemberVariable;

    public MyGenericClass(T value)
    {
        genericMemberVariable = value;
    }

    public T genericMethod(T genericParameter)
    {
        Console.WriteLine("Parameter type: {0}, value: {1}", typeof(T).ToString(),genericParameter);
        Console.WriteLine("Return type: {0}, value: {1}", typeof(T).ToString(), genericMemberVariable);

        return genericMemberVariable;
    }

    public T genericProperty { get; set; }
}
```

- So now, you cannot use int as a placeholder type. The following would give a compile time error;
- String or any class type is a valid type because it is a reference type.
- Example:

```c#
MyGenericClass<string> strGenericClass = new MyGenericClass<string>("Hello World");

MyGenericClass<Student> strGenericClass = new MyGenericClass<Student>(new Student());
```

## Multiple Constraints

- A generic class can have multiple constraints as shown below:

```c#
class MyGenericClass<T, U> where T: class where U:struct
{
    ...
}
```

## Constraint on Generic Methods

- You can apply constraints on the generic methods also;
- Thus, constraints can be applied on generic types;

## Points to remember

- Constraints specifies the kind of types allowed with the generics;
- Constraints can be applied using the where keyword;
- Six types of constraints can be applied: class, struct, new(), base class name, interface and derived type;
- Multiple constraints also can be applied;

## Links

- <https://www.tutorialsteacher.com/csharp/constraints-in-generic-csharp> ;
