# Variables

## Here you will learn

- Variables;
  - Implicitly-typed variables;

## Overview

- A name given to a storage area used to store values of various data types;
- They have a specific type, which determine their size and layout of the variable's memory the range of values that can be stored within that memory and the set of operations that can be applied to the variable;
- Basic variables examples:
  - Integral Types:
    - sbyte, byte, short, ushort, int, uint, long, ulong, and char;
  - Floating point types:
    - float and double;
  - Decimal types:
    - decimal;
  - Boolean types:
    - true or false;
  - Nullable types:
    - nullable data types;
- See all in -> <https://docs.microsoft.com/en-us/dotnet/csharp/tour-of-csharp/types-and-variables> ;

## Defining variables

- The syntax is:
  - `<data_type> <variable_list>`;

## Initializing variables

- Variables are initialized (assigned a value) with an equal sign followed by a constant expression;
- The syntax is:
  - `variable_name = value;`
- Variables can be initalized in their definition:
  - `<data_type> <variable_name> = value;`;
- You can also do multi-line declarations, for example:

```c#
int i, j, k, l = 0;

int amount, num;
```

## Accepting values from user

- The function `ReadLine()` from the `System` namespace accepts input from the user and stores it into a variable;
- For example:

```c#
int num;
num = Convert.ToInt32(Console.ReadLine());
```

## Lvalue and Rvalue expressions

- There are two kinds of expressions in C#:
  - lvalue:
    - An expression that is an lvalue may appear as either the left-hand or right-hand side of an assignment;
  - rvalue:
    - An expression that is an rvalue may appear on the right- but not left-hand side of an assignment;
- Variables are lvalues;
- Numeric literals are rvalues and hence they may not be assigned and can not appear on the left-hand side;

## Implicitly-Typed Local Variable - var

- Var can only be defined in a method as a local variable;
- The compiler will infer its type based on the value to the right of the "=" operator;
- Example:

```c#
int i = 100;// explicitly typed
var j = 100; // implicitly typed
```

- Implicitly-typed variables must be initialized;
- Multiple declerations of var variables in a single statement is not allowed;
- var cannot be used for function parameters;

## Points to remember

- The variable is a name given to a data value;
- A variable holds the value of specific data type e.g string, int, float etc;
- A variable can be declared and initialized in separate statements and also in the single statement;
- The value of a variable can be changed at any time throught out the program as long as it is accessible;
- Multiple variables can be defined seperated by comma (,) in a single or multiple line till semicolon(;);
- A value must be assigned to a variable before using it otherwise it will give compile time error;

## Links

- <https://www.tutorialspoint.com/csharp/csharp_variables.htm> ;
- <https://www.guru99.com/c-sharp-variables-operator.html> ;
- <https://www.tutorialsteacher.com/csharp/csharp-variable> ;
- <https://www.tutorialsteacher.com/csharp/csharp-var-implicit-typed-local-variable> ;
