# Inheritance

## What is it

- It's a mechanism where you can derive a class from another class for a hierarchy of classes that share a set of attributes and methods;
- You can use it to add custom logic to existing frameworks, or map your domain model to a database, for example;

## Why use inheritance

- Allows us to define a class in terms of another class, which makes it easier to create and maintain an application;
- Provides us an opportunity to reuse the code functionality and speeds up implementation time;

## How to do it

- When creating a class, instead of writing completely new data members and member functions, the programmer can designate that the new class should inherit the members of an existing class;
- This existing class is called the base class, and the new class is referred to as the derived class;

## Base and Derived Classes

- A class can be derived from more than one class or interface, which means that it can inherit data and functions from multiple base classes or interfaces;
- Syntax:

```c#
<acess-specifier> class <base_class> {
   ...
}

class <derived_class> : <base_class> {
   ...
}
```

- Example:

```c#
using System;

namespace InheritanceApplication {
   class Shape {
      public void setWidth(int w) {
         width = w;
      }
      public void setHeight(int h) {
         height = h;
      }
      protected int width;
      protected int height;
   }

   // Derived class
   class Rectangle: Shape {
      public int getArea() {
         return (width * height);
      }
   }
   class RectangleTester {
      static void Main(string[] args) {
         Rectangle Rect = new Rectangle();

         Rect.setWidth(5);
         Rect.setHeight(7);

         // Print the area of the object.
         Console.WriteLine("Total area: {0}",  Rect.getArea());
         Console.ReadKey();
      }
   }
}
```

- Returns:

```markdown
Total area: 35
```

## Initializing Base Class

- The derived class inherits the base class member variables and member methods;
- Therefore the super class object should be created before the subclass is created;
- You can give instructions for superclass initialization in the member initialization list;
- For example:

```c#
using System;

namespace RectangleApplication {
   class Rectangle {

      //member variables
      protected double length;
      protected double width;

      public Rectangle(double l, double w) {
         length = l;
         width = w;
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
   class Tabletop : Rectangle {
      private double cost;
      public Tabletop(double l, double w) : base(l, w) { }

      public double GetCost() {
         double cost;
         cost = GetArea() * 70;
         return cost;
      }
      public void Display() {
         base.Display();
         Console.WriteLine("Cost: {0}", GetCost());
      }
   }
   class ExecuteRectangle {
      static void Main(string[] args) {
         Tabletop t = new Tabletop(4.5, 7.5);
         t.Display();
         Console.ReadLine();
      }
   }
}
```

- Returns:

```markdown
Length: 4.5
Width: 7.5
Area: 33.75
Cost: 2362.5
```

## Multiple Inheritance

- C# does not support multiple inheritance;
- However, you can use interfaces to implement multiple inheritance;
- For example:

```c#
using System;

namespace InheritanceApplication {
   class Shape {
      public void setWidth(int w) {
         width = w;
      }
      public void setHeight(int h) {
         height = h;
      }
      protected int width;
      protected int height;
   }

   // Base class PaintCost
   public interface PaintCost {
      int getCost(int area);
   }

   // Derived class
   class Rectangle : Shape, PaintCost {
      public int getArea() {
         return (width * height);
      }
      public int getCost(int area) {
         return area * 70;
      }
   }
   class RectangleTester {
      static void Main(string[] args) {
         Rectangle Rect = new Rectangle();
         int area;

         Rect.setWidth(5);
         Rect.setHeight(7);
         area = Rect.getArea();

         // Print the area of the object.
         Console.WriteLine("Total area: {0}",  Rect.getArea());
         Console.WriteLine("Total paint cost: ${0}" , Rect.getCost(area));
         Console.ReadKey();
      }
   }
}
```

- Returns:

```markdown
Total area: 35
Total paint cost: \$2450
```

## Links

- <https://stackify.com/oop-concept-inheritance/> ;
- <https://www.tutorialspoint.com/csharp/csharp_inheritance.htm> ;
