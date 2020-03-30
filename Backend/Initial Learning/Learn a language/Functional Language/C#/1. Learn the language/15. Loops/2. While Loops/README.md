# While Loops

## Overview

- Executes a block of code repeatedly;

## Syntax

```c#
While(boolean expression)
{
    //execute code as long as condition returns true

}
```

- Includes a boolean expression as a condition which will return true or false;
- It executes the code block, as long as the specified conditional expression returns true;
- Example:

```c#
int i = 0;

while (i < 10)
{
    Console.WriteLine("Value of i: {0}", i);

    i++;
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

## Using break in a while Loop

- Use the break keyword to exit from a while loop;
- Example:

```c#
int i = 0;

while (true)
{
    Console.WriteLine("Value of i: {0}", i);

    i++;

    if (i > 10)
        break;
}
```

**Nested while loop:**

- Can be done;
- Example:

```c#
int i = 0;

while (i < 2)
{
    Console.WriteLine("Value of i: {0}", i);
    int j = 1;

    i++;

    while (j < 2)
    {
        Console.WriteLine("Value of j: {0}", j);
        j++;
    }
}
```

## Points to Remember

- The while loop executes the block of code repeatedly;
- The while loop includes condition expression. Increment/decrement step should be inside the loop;
- Use break keyword to stop the execution and exit from while loop;
- An nested while loop is allowed;

## Links

- <https://www.tutorialsteacher.com/csharp/csharp-while-loop;>
