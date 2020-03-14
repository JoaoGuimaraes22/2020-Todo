# Encapsulation

## Overview

- It's the bundling of data and methods that operate on that data in one unit;
- Often used to hide the values or state of a structured data object inside a class;
- Publicly accessible methods are generally provided in the class (so-called `getters` and `setters`), to access the values;
- Abstraction and encapsulation are related features in object oriented programming;
- Abstraction allows making relevant information visible and encapsulation enables a programmer to implement the desired level of abstraction;

## Encapsulation access specifiers

- An access specifier defines the scope and visibility of a class member;
- C# has the following specifiers:
  - Public;
  - Private;
  - Protected;
  - Internal;
  - Protected internal;

## Public access specifier

- Allows a class to expose its member variables and member functions to other functions and objects;
- Any public member can be accessed from outside the class;
- Example:

```c#
using System;

namespace RectangleApplication {
   class Rectangle {
      //member variables
      public double length;
      public double width;

      public double GetArea() {
         return length * width;
      }
      public void Display() {
         Console.WriteLine("Length: {0}", length);
         Console.WriteLine("Width: {0}", width);
         Console.WriteLine("Area: {0}", GetArea());
      }
   }//end class Rectangle

   class ExecuteRectangle {
      static void Main(string[] args) {
         Rectangle r = new Rectangle();
         r.length = 4.5;
         r.width = 3.5;
         r.Display();
         Console.ReadLine();
      }
   }
}
```

- Returns:

```markdown
Length: 4.5
Width: 3.5
Area: 15.75
```

- Here the member variables length and width are declared public, so they can be accessed from the function Main() using an instance of the Rectangle class, named r;
- The member function Display() and GetArea() can also access these variables directly without using any instance of the class;
- The member functions Display() is also declared public, so it can also be accessed from Main() using an instance of the Rectangle class, named r;

## Private Access Specifier

- Allows a class to hide its member variables and member functions from other functions and objects;
- Only functions of the same class can access its private members;
- An instance of a class cannot access its private members;
- Example:

```c#
using System;

namespace RectangleApplication {
   class Rectangle {
      //member variables
      private double length;
      private double width;

      public void Acceptdetails() {
         Console.WriteLine("Enter Length: ");
         length = Convert.ToDouble(Console.ReadLine());
         Console.WriteLine("Enter Width: ");
         width = Convert.ToDouble(Console.ReadLine());
      }
      public double GetArea() {
         return length * width;
      }
      public void Display() {
         Console.WriteLine("Length: {0}", length);
         Console.WriteLine("Width: {0}", width);
         Console.WriteLine("Area: {0}", GetArea());
      }
   }//end class Rectangle

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

- Returns:

```markdown
Enter Length:
4.4
Enter Width:
3.3
Length: 4.4
Width: 3.3
Area: 14.52
```

- Here, the member variables length and width are declared private, so they cannot be accessed from the function Main();
- The member functions AcceptDetails() and Display() can access these variables;
- ince the member functions AcceptDetails() and Display() are declared public, they can be accessed from Main() using an instance of the Rectangle class, named r;

## Protected Access Specifier

- Allows a child class to access the member variables and member functions of its base class;
- Helps in implementing inheritance;

## Internal Access Specifier

- Allows a class to expose its member variables and member functions to other functions and objects in the current assembly;
- Any member with internal access specifier can be accessed from any class or method defined within the application in which the member is defined;
- Example:

```c#
using System;

namespace RectangleApplication {
   class Rectangle {
      //member variables
      internal double length;
      internal double width;

      double GetArea() {
         return length * width;
      }
      public void Display() {
         Console.WriteLine("Length: {0}", length);
         Console.WriteLine("Width: {0}", width);
         Console.WriteLine("Area: {0}", GetArea());
      }
   }//end class Rectangle

   class ExecuteRectangle {
      static void Main(string[] args) {
         Rectangle r = new Rectangle();
         r.length = 4.5;
         r.width = 3.5;
         r.Display();
         Console.ReadLine();
      }
   }
}
```

- Returns:

```markdown
Length: 4.5
Width: 3.5
Area: 15.75
```

- Here, notice that the member function GetArea() is not declared with any access specifier;
- It defaults to **private**;

## Protected Internal Access Specifier

- Allows a class to hide its member variables and member functions from other class objects and functions, except a child class within the same application;
- Used while implementing inheritance;

## Example of encapsulation in CSharp

- The class Counter, has the inner state counterValue which is hidden for the outside and can only be modified by the methods CountUp and CountDown;

```c#
using System;

public class Counter
{
 private int counterValue = 0;

 public void CountUp()
 {
  counterValue++;
 }

 public void CountDown()
 {
  counterValue--;
 }

 public int GetCounterValue()
 {
  return counterValue;
 }
}

class ExecuteEncapsulation {
 static void Main(string[] args) {
        var c = new Counter();
        Console.WriteLine(c.GetCounterValue()); //Expected 0
        c.CountUp(); // value wil be increased to: 1
        c.CountUp(); // value wil be increased to: 2
        Console.WriteLine(c.GetCounterValue()); //Expected 2
        c.CountDown(); // value wil be decreased to: 1
        Console.WriteLine(c.GetCounterValue()); //Expected 1
   }
}
```

## Links

- <https://stackify.com/oop-concept-for-beginners-what-is-encapsulation/> ;
- <https://en.wikipedia.org/wiki/Encapsulation_(computer_programming)> ;
- <https://www.tutorialspoint.com/csharp/csharp_encapsulation.htm> ;
