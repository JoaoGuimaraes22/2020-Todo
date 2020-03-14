# For Loops

## Overview

- The `for` keyword indicates a loop;

## Syntax

```c#
for (variable initialization; condition; steps)
{
    //execute this code block as long as condition is satisfied
}
```

- Variable initialization:
  - Declare & initialize a variable here which will be used in conditional expression and steps part;
- Condition:
  - The condition is a boolean expression which will return either true or false;
- Steps:
  - The steps defines the incremental or decremental part;

## Example

```c#
for (int i = 0; i < 10; i++)
{
    Console.WriteLine("Value of i: {0}", i);
}
```

- Returns:

```markdown
Value of i: 0
Value of i: 1
Value of i: 2
Value of i: 3
Value of i: 4
Value of i: 5
Value of i: 6
Value of i: 7
Value of i: 8
Value of i: 9
```

## Features

- It is not necessary to put the initialization, condition and steps into brackets;
- You can initialize a variable before the 'for' loop, and the condition and steps can be defined inside the for loop;

## Infinite for Loop

- It will be an infinite loop if for loop does not contain initialization, condition or steps part;
- Example:

```c#
for (  ;  ; )
{
    Console.Write(1);
}
```

- Returns:
  - `1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1...`;

## break in for Loop

- You can exit from a for loop using `break`;
- Example:

```c#
for (int i = 0; i < 10; i++)
{
    if( i == 5 )
        break;

    Console.WriteLine("Value of i: {0}", i);
}
```

- Returns:

```markdown
Value of i: 0
Value of i: 1
Value of i: 2
Value of i: 3
Value of i: 4
```

## Nested for loop

- C# allows a for loop inside another for loop:
- Example:

```c#
for (int i = 0; i < 10; i++)
{
    for(int j =i; j< 10; j++)
        Console.WriteLine("Value of i: {0}, J: {1} ", i,j);
}
```

## Points to remeber

- The for loop executes the block of code repeatedly;
- The for loop has three steps: initialization, condition and increment/decrement;
- The for loop can use control variable of any numeric data type;
- Use break keyword to stop the execution and exit from for loop;
- Nested for loop is allowed in C#;

## Links

- <https://www.tutorialsteacher.com/csharp/csharp-for-loop;>
