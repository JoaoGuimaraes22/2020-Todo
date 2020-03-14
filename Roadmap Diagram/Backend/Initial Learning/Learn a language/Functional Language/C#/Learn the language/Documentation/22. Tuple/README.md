# Tuple

## Overview

- It's a data structure that contains a sequence of elements of different data types;
- Used when you want to have a data structure to hold an object with properties, but you don't want to create a separate type for it;

## Syntax

```c#
Tuple<T1, T2, T3, T4, T5, T6, T7, TRest>
```

- Example:

```c#
Tuple<int, string, string> person =
                        new Tuple <int, string, string>(1, "Steve", "Jobs");
```

## Tuple.Create()

- C# includes a static helper class Tuple which returns an instance of the `Tuple<T>` without specifying the type of each element, as shown below:

```c#
var person = Tuple.Create(1, "Steve", "Jobs");
```

## Maximum Elements

- A tuple can only include maximum eight elements;

## Accessing Tuple Elements

- The elements of a tuple can be accessed with `Item<elementNumber>` properties;
- The last element (the 8th element) will be returned using the Rest property;
- Example:

```c#
var person = Tuple.Create(1, "Steve", "Jobs");
person.Item1; // returns 1
person.Item2; // returns "Steve"
person.Item3; // returns "Jobs"


var numbers = Tuple.Create("One", 2, 3, "Four", 5, "Six", 7, 8);
numbers.Item1; // returns "One"
numbers.Item2; // returns 2
numbers.Item3; // returns 3
numbers.Item4; // returns "Four"
numbers.Item5; // returns 5
numbers.Item6; // returns "Six"
numbers.Item7; // returns 7
numbers.Rest; // returns (8)
numbers.Rest.Item1; // returns 8
```

## Nested Tuples

- If you want to include more than eight elements in a tuple, you can do that by nesting another tuple object as the eighth element;
- To access the nested tuple's element, use the `Rest.Item1.Item<elelementNumber>` property;
- Example:

```c#
var numbers = Tuple.Create(1, 2, 3, 4, 5, 6, 7, Tuple.Create(8, 9, 10, 11, 12, 13));
numbers.Item1; // returns 1
numbers.Item7; // returns 7
numbers.Rest.Item1; //returns (8, 9, 10, 11, 12, 13)
numbers.Rest.Item1.Item1; //returns 8
numbers.Rest.Item1.Item2; //returns 9
```

## Tuple as a Method Parameter

- Example:

```c#
static void Main(string[] args)
{
    var person = Tuple.Create(1, "Steve", "Jobs");
    DisplayTuple(person);
}

static void DisplayTuple(Tuple<int,string,string> person)
{
    Console.WriteLine($"Id = { person.Item1}");
    Console.WriteLine($"First Name = { person.Item2}");
    Console.WriteLine($"Last Name = { person.Item3}");
}
```

## Tuple as a Return Type

- Example:

```c#
static void Main(string[] args)
{
    var person = GetPerson();
}

static Tuple<int, string, string> GetPerson()
{
    return Tuple.Create(1, "Bill", "Gates");
}
```

## Usage of Tuple

- When you want to return multiple values from a method without using ref or out parameters;
- When you want to pass multiple values to a method through a single parameter;
- When you want to hold a database record or some values temporarily without creating a separate class;

## Tuple Limitiations

- Tuple is a reference type and not a value type. It allocates on heap and could result in CPU intensive operations;
- Tuple is limited to include 8 elements. You need to use nested tuples if you need to store more elements. However, this may result in ambiguity;
- Tuple elements can be accessed using properties with a name pattern `Item<elementNumber>` which does not make sense;

- C# 7 includes ValueTuple to overcome the limitations of Tuple and also makes it even easier to work with Tuple. Learn about it in next;

## Links

- <https://www.tutorialsteacher.com/csharp/csharp-tuple;>
