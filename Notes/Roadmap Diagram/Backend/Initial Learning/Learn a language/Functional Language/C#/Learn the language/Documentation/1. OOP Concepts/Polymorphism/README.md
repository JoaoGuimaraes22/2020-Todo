## Polymorphism

**What is it:**

- The concept that objects of different types can be accessed through the same interface;
- Each type can provide its own, independent implementation of this interface;

**Example of Polymorphism in C#:**

- Here, the class Polymorph implements three different (polymorph) versions of the method Print;
- The type of input decides which of the implementations is executed.

```
using System;

class Polymorph
{
    public void Print(int i)
    {
    	Console.WriteLine($"Printing int: {i}");
    }

    public void Print(double d)
    {
    	Console.WriteLine($"Printing double: {d}");
    }

    public void Print(string s)
    {
    	Console.WriteLine($"Printing string: {s}");
    }
}

class RunPolymorph {
   static void Main(string[] args) {
      var p = new Polymorph();
      p.Print(42);
      p.Print(3.14159265359);
      p.Print("I'm Polymorph");
   }
}


```

**Links:**

- https://stackify.com/oop-concept-polymorphism/ ;
