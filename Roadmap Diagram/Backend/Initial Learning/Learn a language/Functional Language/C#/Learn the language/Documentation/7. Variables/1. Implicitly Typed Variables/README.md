# Implicitly-Typed Variables

## Overview

- Var can only be defined in a method as a local variable;
- The compiler will infer its type based on the value to the right of the "=" operator;
- Example:

```c#
int i = 100;// explicitly typed
var j = 100; // implicitly typed
```

## Features

- Implicitly-typed variables must initialized at the time of declaration;
- Multiple declerations of `var` variables in a single statement is not allowed;
- `var` cannot be used for function parameters;
- `var` variables can be used for following different contexts:
  - Local variable in a function;
  - For loop;
  - Foreach loop;
  - Using statement;
  - As an anonymous type;
  - In a LINQ query expression;

## Points to Remember

- var can only be declared and initialized in a single statement;
- var cannot be used as a field type at the class level;
- var cannot be used in an expression like `var i += 10`;
- Multiple vars cannot be declared and initialized in a single statement;

## Links

- <https://www.tutorialsteacher.com/csharp/csharp-var-implicit-typed-local-variable> ;
