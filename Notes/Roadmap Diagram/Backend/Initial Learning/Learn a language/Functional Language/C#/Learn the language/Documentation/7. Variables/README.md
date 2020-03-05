## Variables

**What is a variable:**

- A name given to a storage area that our programs can manipulate;
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
- See all in -> https://docs.microsoft.com/en-us/dotnet/csharp/tour-of-csharp/types-and-variables ;

**Defining variables:**

- The syntax is:
  - `<data_type> <variable_list>`;

**Initializing variables:**

- Variables are initialized (assigned a value) with an equal sign followed by a constant expression;
- The syntax is:
  - `variable_name = value;`
- Variables can be initalized in their definition:
  - `<data_type> <variable_name> = value;`;

**Accepting values from user:**

- The function `ReadLine()` from the `System` namespace accepts input from the user and stores it into a variable;
- For example:

```
int num;
num = Convert.ToInt32(Console.ReadLine());
```

**Lvalue and Rvalue expressions:**

- There are two kinds of expressions in C#:
  - lvalue:
    - An expression that is an lvalue may appear as either the left-hand or right-hand side of an assignment;
  - rvalue:
    - An expression that is an rvalue may appear on the right- but not left-hand side of an assignment;
- Variables are lvalues;
- Numeric literals are rvalues and hence they may not be assigned and can not appear on the left-hand side;

**Links:**

- https://www.tutorialspoint.com/csharp/csharp_variables.htm ;
