# Predicate Delegate

## Overview

- It represents a method that contains a set of criteria and checks whether the passed parameter meets those criteria or not;
- A predicate delegate methods must take one input parameter and return a boolean - true or false;

## Predicate

- Same as other delegate types, Predicate can also be used with any method, anonymous method or lambda expression;
- Example:

```c#
static bool IsUpperCase(string str)
{
    return str.Equals(str.ToUpper());
}

static void Main(string[] args)
{
    Predicate<string> isUpper = IsUpperCase;

    bool result = isUpper("hello world!!");

    Console.WriteLine(result);
}
```

- Returns:

```markdown
false
```

## Anonymous Methdods with Predicate

- An anonymous method can also be assigned to a Predicate delegate type as shown below:

```c#
static void Main(string[] args)
{
    Predicate<string> isUpper = delegate(string s) { return s.Equals(s.ToUpper());};
    bool result = isUpper("hello world!!");
}
```

## Lambda Expressions with Predicate

- A lambda expression can also be assigned to a Predicate delegate type as shown below:

```c#
static void Main(string[] args)
{
    Predicate<string> isUpper = s => s.Equals(s.ToUpper());
    bool result = isUpper("hello world!!");
}
```

## Points to Remember

- Predicate delegate takes one input parameter and boolean return type;
- Anonymous method and Lambda expression can be assigned to the predicate delegate;

## Links

- <https://www.tutorialsteacher.com/csharp/csharp-predicate;>
