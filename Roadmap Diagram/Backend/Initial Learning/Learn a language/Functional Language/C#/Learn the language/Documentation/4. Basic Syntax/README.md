## Basic Syntax

**Overview:**

- A program consists of various objects that interact with each other by means of actions;
- The actions that an object may take are called methods;

**Example Program:**

```
using System;

namespace RectangleApplication {
   class Rectangle {

      // member variables
      double length;
      double width;

      public void Acceptdetails() {
         length = 4.5;
         width = 3.5;
      }
      public double GetArea() {
         return length * width;
      }
      public void Display() {
         Console.WriteLine("Length: {0}", length);
         Console.WriteLine("Width: {0}", width);
         Console.WriteLine("Area: {0}", GetArea());
      }
   }
   class ExecuteRectangle {
      static void Main(string[] args) {
         Rectangle r = new Rectangle();
         r.Acceptdetails();
         r.Display();
         Console.ReadLine();
      }
   }
}
```

**The `using` Keyword:**

- Used for including the namespaces in the program;

**The `class` Keyword:**

- Used for declaring a class;

**Comments in C#:**

- Used for explaining code;
- Compilers ignore the comment entries;
- Multiline comments in C# programs start with /_ and terminates with the characters _/;
- Single-line comments are indicated by the '//' symbol;

**Member variables:**

- Are attributes or data members of a class, used for storing data;

**Member functions:**

- Are set of statements that perform a specific task;
- The member functions of a class are declared within the class;

**Instantiating a Class:**

- In the preceding program, the class ExecuteRectangle contains the Main() method and instantiates the Rectangle class;

**Identifiers:**

- Used to identify a class, variable, function, or any other user-defined item;

**Links:**

- https://www.tutorialspoint.com/csharp/csharp_basic_syntax.htm ;