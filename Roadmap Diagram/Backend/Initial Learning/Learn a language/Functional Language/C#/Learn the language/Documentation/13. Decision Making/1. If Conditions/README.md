## If Conditions

**Overview:**

- Contains boolean expression inside brackets followed by a single or multi line code block;
- At runtime, if a boolean expression is evalutes to true then the code block will be executed;

**Example:**

```
int i = 10, j = 20;

if (i > j)
{
    Console.WriteLine("i is greater than j");
}

if (i < j)
{
    Console.WriteLine("i is less than j");
}

if (i == j)
{
    Console.WriteLine("i is equal to j");
}
```

**if-else statements:**

- The else statement must follow if or else if statement;
- else statement can appear only one time in a if-else statement chain;
- Example:

```
int i = 10, j = 20;

if (i > j)
{
    Console.WriteLine("i is greater than j");
}
else
{
    Console.WriteLine("i is either equal to or less than j");
}
```

**else if statement:**

- The 'if' statement can also follow an 'else' statement, if you want to check for another condition in the else part;
- Example:

```
static void Main(string[] args)
{
    int i = 10, j = 20;

    if (i > j)
    {
        Console.WriteLine("i is greater than j");
    }
    else if (i < j)
    {
        Console.WriteLine("i is less than j");
    }
    else
    {
        Console.WriteLine("i is equal to j");
    }
}
```

**Nested if statements:**

- Example:

```
int i = 10;

if (i > 0)
{
    if (i <= 100)
    {
        Console.WriteLine("i is positive number less than 100");
    }
    else
    {
        Console.WriteLine("i is positive number greater than 100");
    }
}
```

**Points to Remember:**

- if-else statement controls the flow of program based on the evaluation of the boolean expression;
- It should start from the if statement followed by else or else-if statements;
- Only one else statement is allowed in the if-else chain;
- Multiple else-if statements are allowed in a single if-else chain;
- Nested if-else statement is allowed;

**Links:**

- https://www.tutorialsteacher.com/csharp/csharp-if-else;
