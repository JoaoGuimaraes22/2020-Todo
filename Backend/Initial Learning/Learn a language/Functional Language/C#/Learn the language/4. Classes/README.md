# Classes

## Here you will learn

1. Classes
   1. Partial Classes

## Overview

- When you define a class, you define a blueprint for a data type;
- Objects are instances of a class;
- Defines the kinds of data and the functionality their objects will have
- The methods and variables that constitute a class are called members of the class;

## Defining a class

- A class definition starts with the keyword class followed by the class name;
- The class body in enclosed in curly braces;
- Syntax:

```c#
<access specifier> class  class_name {
   // member variables
   <access specifier> <data type> variable1;
   <access specifier> <data type> variable2;
   ...
   <access specifier> <data type> variableN;
   // member methods
   <access specifier> <return type> method1(parameter_list) {
      // method body
   }
   <access specifier> <return type> method2(parameter_list) {
      // method body
   }
   ...
   <access specifier> <return type> methodN(parameter_list) {
      // method body
   }
}
```

### Access specifiers

- Specify the access rules for the members as well as the class itself;
- Example:

```c#
using System;

namespace BoxApplication {
   class Box {
      public double length;   // Length of a box
      public double breadth;  // Breadth of a box
      public double height;   // Height of a box
   }
   class Boxtester {
      static void Main(string[] args) {
         Box Box1 = new Box();   // Declare Box1 of type Box
         Box Box2 = new Box();   // Declare Box2 of type Box
         double volume = 0.0;    // Store the volume of a box here

         // box 1 specification
         Box1.height = 5.0;
         Box1.length = 6.0;
         Box1.breadth = 7.0;

         // box 2 specification
         Box2.height = 10.0;
         Box2.length = 12.0;
         Box2.breadth = 13.0;

         // volume of box 1
         volume = Box1.height * Box1.length * Box1.breadth;
         Console.WriteLine("Volume of Box1 : {0}",  volume);

         // volume of box 2
         volume = Box2.height * Box2.length * Box2.breadth;
         Console.WriteLine("Volume of Box2 : {0}", volume);
         Console.ReadKey();
      }
   }
}
```

- Returns:

```markdown
Volume of Box1 : 210
Volume of Box2 : 1560
```

## Member Functions and Encapsulation

- A member function of a class is a function that has its definition or its prototype within the class definition similar to any other variable;
- It operates on any object of the class of which it is a member, and has access to all the members of a class for that object;
- These variables can only be accessed using the public member functions;
- For example:

```c#
using System;

namespace BoxApplication {
   class Box {
      private double length;   // Length of a box
      private double breadth;  // Breadth of a box
      private double height;   // Height of a box

      public void setLength( double len ) {
         length = len;
      }
      public void setBreadth( double bre ) {
         breadth = bre;
      }
      public void setHeight( double hei ) {
         height = hei;
      }
      public double getVolume() {
         return length * breadth * height;
      }
   }
   class Boxtester {
      static void Main(string[] args) {
         Box Box1 = new Box();   // Declare Box1 of type Box
         Box Box2 = new Box();
         double volume;

         // Declare Box2 of type Box
         // box 1 specification
         Box1.setLength(6.0);
         Box1.setBreadth(7.0);
         Box1.setHeight(5.0);

         // box 2 specification
         Box2.setLength(12.0);
         Box2.setBreadth(13.0);
         Box2.setHeight(10.0);

         // volume of box 1
         volume = Box1.getVolume();
         Console.WriteLine("Volume of Box1 : {0}" ,volume);

         // volume of box 2
         volume = Box2.getVolume();
         Console.WriteLine("Volume of Box2 : {0}", volume);

         Console.ReadKey();
      }
   }
}
```

- Returns:

```markdown
Volume of Box1 : 210
Volume of Box2 : 1560
```

## Constructors

- It's a special member function of a class that is executed whenever we create new objects of that class;
- Are called when you create an instance of a class;
- It has exactly the same name as that of class and it does not have any return type;
- For example:

```c#
using System;

namespace LineApplication {
   class Line {
      private double length;   // Length of a line

      public Line() {
         Console.WriteLine("Object is being created");
      }
      public void setLength( double len ) {
         length = len;
      }
      public double getLength() {
         return length;
      }

      static void Main(string[] args) {
         Line line = new Line();

         // set line length
         line.setLength(6.0);
         Console.WriteLine("Length of line : {0}", line.getLength());
         Console.ReadKey();
      }
   }
}
```

- Returns:

```markdown
Object is being created
Length of line : 6
```

- You can have constructor with parameter, called **parameterized constructors**;
- Helps you to assign initial value to an object at the time of its creation;
- For example:

```c#
using System;

namespace LineApplication {
   class Line {
      private double length;   // Length of a line

      public Line(double len) {  //Parameterized constructor
         Console.WriteLine("Object is being created, length = {0}", len);
         length = len;
      }
      public void setLength( double len ) {
         length = len;
      }
      public double getLength() {
         return length;
      }
      static void Main(string[] args) {
         Line line = new Line(10.0);
         Console.WriteLine("Length of line : {0}", line.getLength());

         // set line length
         line.setLength(6.0);
         Console.WriteLine("Length of line : {0}", line.getLength());
         Console.ReadKey();
      }
   }
}
```

- Returns:

```markdown
Object is being created, length = 10
Length of line : 10
Length of line : 6
```

## Destructors

- It's a special member function of a class that is executed whenever an object of its class goes out of scope;
- Has exactly the same name as that of the class with a prefixed tilde (~) and it can neither return a value nor can it take any parameters;
- Useful for releasing memory resources before exiting the program;
- Cannot be inherited or overloaded;
- For example:

```c#
using System;

namespace LineApplication {
   class Line {
      private double length;   // Length of a line

      public Line() {   // constructor
         Console.WriteLine("Object is being created");
      }
      ~Line() {   //destructor
         Console.WriteLine("Object is being deleted");
      }
      public void setLength( double len ) {
         length = len;
      }
      public double getLength() {
         return length;
      }
      static void Main(string[] args) {
         Line line = new Line();

         // set line length
         line.setLength(6.0);
         Console.WriteLine("Length of line : {0}", line.getLength());
      }
   }
}
```

- Returns:

```markdown
Object is being created
Length of line : 6
Object is being deleted
```

## Static Members of a Class

- We can define class members as static using the `static` keyword;
- When we use it, it means no matter how many objects of the class are created, there is only one copy of the static member;
- Implies that only one instance of the member exists for a class;
- Are used for defining constants because their values can be retrieved by invoking the class without creating an instance of it;
- Can be initialized outside the member function or class definition;
- You can initialize static variables inside the class definition;
- For example:

```c#
using System;

namespace StaticVarApplication {
   class StaticVar {
      public static int num;

      public void count() {
         num++;
      }
      public int getNum() {
         return num;
      }
   }
   class StaticTester {
      static void Main(string[] args) {
         StaticVar s1 = new StaticVar();
         StaticVar s2 = new StaticVar();

         s1.count();
         s1.count();
         s1.count();

         s2.count();
         s2.count();
         s2.count();

         Console.WriteLine("Variable num for s1: {0}", s1.getNum());
         Console.WriteLine("Variable num for s2: {0}", s2.getNum());
         Console.ReadKey();
      }
   }
}
```

- Returns:

```markdown
Variable num for s1: 6
Variable num for s2: 6
```

### Member functions as static

- You can declare a member function as static;
- These can access only static variables;
- They exist even before the object is created;
- For example:

```c#
using System;

namespace StaticVarApplication {
   class StaticVar {
      public static int num;

      public void count() {
         num++;
      }
      public static int getNum() {
         return num;
      }
   }
   class StaticTester {
      static void Main(string[] args) {
         StaticVar s = new StaticVar();

         s.count();
         s.count();
         s.count();

         Console.WriteLine("Variable num: {0}", StaticVar.getNum());
         Console.ReadKey();
      }
   }
}
When the above code is compiled and executed, it produces the following result −

Variable num: 3
```

## Properties

- Defined using getters and setters;
- Property encapsulates a private field;
- It provides getters (get{}) to retrieve the value of the underlying field and setters (set{}) to set the value of the underlying field;
- For example:

```c#
private int _myPropertyVar;

public int MyProperty
{
    get { return _myPropertyVar; }
    set { _myPropertyVar = value; }
}
```

## Auto-implemented Property

- From C# 3.0 onwards, property declaration has been made easy if you don't want to apply some logic in get or set;
- You can now just do this:

```c#
public int MyAutoImplementedProperty { get; set; }
```

- And the backing field will be created automatically by the compiler;

## Partial Class and Methods

- C# provides the ability to have a single class implementation in multiple .cs files using the partial modifier keyword;
- For example, partial methods :

```c#
PartialClass1.cs:

public partial class MyPartialClass
{
    public MyPartialClass()
    {
    }

    public void Method1(int val)
    {
        Console.WriteLine(val);
    }
}

PartialClass2.cs:

public partial class MyPartialClass
{
    public void Method1(int val)
    {
        Console.WriteLine(val);
    }

    partial void PartialMethod(int val)
    {
        Console.WriteLine(val);
    }
}
```

- PartialClassFile1.cs contains the declaration of the partial method and PartialClassFile2.cs contains the implementation of the partial method;

## Links

- <https://www.tutorialspoint.com/csharp/csharp_classes.htm> ;
- <https://www.tutorialsteacher.com/csharp/csharp-class> ;
- <https://www.tutorialsteacher.com/csharp/csharp-partial-class> ;
