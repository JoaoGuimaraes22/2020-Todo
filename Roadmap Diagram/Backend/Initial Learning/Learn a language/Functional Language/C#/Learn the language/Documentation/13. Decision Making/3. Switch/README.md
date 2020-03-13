## Switch

**Overview:**

- Executes the code block depending upon the resulted value of an expression;

**Syntax:**

- Switch statement contains an expression into brackets;
- Includes multiple case labels, where each case represents a particular literal value;
- Seperated by a break keyword which stops the execution of a particular case;
- Can include a default case to execute if no case value satisfies the expression

```
switch(expression)
{
    case <value1>
        // code block
        break;
    case <value2>
        // code block
        break;
    case <valueN>
        // code block
        break;
    default
        // code block
        break;
}
```

**Example:**

- Example:

```
string statementType = "switch";

switch (statementType)
{
    case "if.else":
        Console.WriteLine("if...else statement");
        break;
    case "ternary":
        Console.WriteLine("Ternary operator");
        break;
    case "switch":
        Console.WriteLine("switch statement");
        break;
}
```

- Returns:

```
switch statement
```

**Goto in switch:**

- You can use goto to jump over a different case:

```
string statementType = "switch";

switch (statementType)
{
    case "DecisionMaking":
        Console.Write(" is a decision making statement.");
        break;
    case "if.else":
        Console.Write("if-else");
        break;
    case "ternary":
        Console.Write("Ternary operator");
        break;
    case "switch":
        Console.Write("switch statement");
        goto case "DecisionMaking";
}
```

- Returns:

```
switch statement is a decision making statement.
```

- Allows nesting;

**Points to remember:**

- The switch statement tests the variable against a set of constants.;
- The switch statement contains multiple case labels;
- The switch case must include 'break' keyword to stop the execution of switch case;
- The default case executes when no case satisfies the expression;
- A nested switch statement is allowed;

**Links:**

- https://www.tutorialsteacher.com/csharp/csharp-switch ;
