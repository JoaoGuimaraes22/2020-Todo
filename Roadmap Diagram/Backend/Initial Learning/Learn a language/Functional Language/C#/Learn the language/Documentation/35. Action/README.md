# Action Delegate

## Overview

- Action is a delegate type;
- An Action type delegate is the same as Func delegate except that the Action delegate doesn't return a value;

## Action

- Example:

```c#
static void ConsolePrint(int i)
{
    Console.WriteLine(i);
}

static void Main(string[] args)
{
    Action<int> printActionDel = ConsolePrint;
    printActionDel(10);
}
```

## Initializing an Action delegate

- You can initialize an Action delegate using the new keyword or by directly assigning a method:

```c#
Action<int> printActionDel = ConsolePrint;

//Or

Action<int> printActionDel = new Action<int>(ConsolePrint);
```

## Features

- An Action delegate can take up to 16 input parameters of different types;
- An Anonymous method can also be assigned to an Action delegate, for example:

```c#
static void Main(string[] args)
{
    Action<int> printActionDel = delegate(int i)
                                {
                                    Console.WriteLine(i);
                                };

    printActionDel(10);
}
```

- Returns:

```markdown
10
```

- A Lambda expression also can be used with an Action delegate:

```c#
static void Main(string[] args)
{

    Action<int> printActionDel = i => Console.WriteLine(i);

    printActionDel(10);
}
```

## Advantages of Action and Func Delegates

- Easy and quick to define delegates;
- Makes code short;
- Compatible type throughout the application;

## Points to remember

- Action delegate is same as func delegate except that it does not return anything. Return type must be void;
- Action delegate can have 0 to 16 input parameters;
- Action delegate can be used with anonymous methods or lambda expressions;

## Links

- <https://www.tutorialsteacher.com/csharp/csharp-action-delegate;>
