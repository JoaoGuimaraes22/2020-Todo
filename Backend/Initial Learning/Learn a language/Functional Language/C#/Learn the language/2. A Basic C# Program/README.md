# A Basic C# Program

## What makes a C# program

- Namespace declaration;
- A class;
- Class methods;
- Class atributes;
- A Main method;
- Statements and Expressions;
- Comments;

## For example

```c#
using System;

namespace HelloWorldApplication {
   class HelloWorld {
      static void Main(string[] args) {
         /* my first program in C# */
         Console.WriteLine("Hello World");
         Console.ReadKey();
      }
   }
}
```

- When it compiles, it produces the result "Hello World";

### The various parts

- `using System`:
  - Used to include the `System` namespace in the program;
- The namespace declaration:
  - A namespace is a collection of classes;
- The class declaration, `HelloWorld`:
  - The class contains data and methods;
  - Methods define the behavior of the class;
  - The `HelloWorld` class has the method `Main`;
- The line `/* */` is put to add a comment:
  - Comments get ignored by the compiler;
- The `Main` method specifies its behavior with the statement `Console.WriteLine("Hello World");`;
  - `WriteLine` is a method of the `Console` class in the `System` namespace;

## Some Key Points

- C# is case sensitive;
- All statements and expressions must end with a semi-colon (;);
- The program execution starts at the `Main` method;

## Links

- <https://www.tutorialspoint.com/csharp/csharp_program_structure.htm>m> ;
