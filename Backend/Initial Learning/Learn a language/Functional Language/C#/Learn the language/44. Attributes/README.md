# Attributes

## Overview

- It's a declarative tag that is used to convey information to runtime about the behaviors of various elements;
- Used for adding metadata, such as compiler instruction and other information such as comments, description, methods and classes to a program;
- There are two types of attributes:
  - The pre-defined attributes;
  - The custom built attributes;

## Specifying an attribute

- Syntax:

```c#
[attribute(positional_parameters, name_parameter = value, ...)]
element
```

- Name of the attribute and its values are specified within the square brackets, before the element to which the attribute is applied;
- Positional parameters specify the essential information and the name parameters specify the optional information;

## Predefined attributes

- There are three pre-defined attributes:
  - AttributeUsage;
  - Conditional;
  - Obsolete;

## AttributeUsage

- Describes how a custom attribute class can be used;
- Specifies the types of items to which the attribute can be applied;
- Syntax:

```c#
[AttributeUsage (
   validon,
   AllowMultiple = allowmultiple,
   Inherited = inherited
)]
```

### Parameters

- The parameter validon specifies the language elements on which the attribute can be placed. It is a combination of the value of an enumerator AttributeTargets. The default value is AttributeTargets.All;
- he parameter allowmultiple (optional) provides value for the AllowMultiple property of this attribute, a Boolean value. If this is true, the attribute is multiuse. The default is false (single-use);
- The parameter inherited (optional) provides value for the Inherited property of this attribute, a Boolean value. If it is true, the attribute is inherited by derived classes. The default value is false (not inherited);
- For example:

```c#
[AttributeUsage(
   AttributeTargets.Class |
   AttributeTargets.Constructor |
   AttributeTargets.Field |
   AttributeTargets.Method |
   AttributeTargets.Property,
   AllowMultiple = true)]
```

## Conditional

- Marks a conditional method whose execution depends on a specified preprocessing identifier;
- Causes conditional compilation of method calls, depending on the specified value such as Debug or Trace;
- Syntax:

```c#
[Conditional(
   conditionalSymbol
)]
```

- For example:

```c#
[Conditional("DEBUG")]
```

- Example:

```c#
#define DEBUG
using System;
using System.Diagnostics;

public class Myclass {
   [Conditional("DEBUG")]

   public static void Message(string msg) {
      Console.WriteLine(msg);
   }
}
class Test {
   static void function1() {
      Myclass.Message("In Function 1.");
      function2();
   }
   static void function2() {
      Myclass.Message("In Function 2.");
   }
   public static void Main() {
      Myclass.Message("In Main function.");
      function1();
      Console.ReadKey();
   }
}
```

- Returns:

```markdown
In Main function
In Function 1
In Function 2
```

## Obsolete

- Marks a program entity that should not be used;
- Enables you to inform the compiler to discard a particular target element;
- Syntax:

```c#
[Obsolete (
   message
)]

[Obsolete (
   message,
   iserror
)]
```

### Where

- The parameter message, is a string describing the reason why the item is obsolete and what to use instead;
- The parameter iserror, is a Boolean value. If its value is true, the compiler should treat the use of the item as an error. Default value is false (compiler generates a warning);

- For example:

```c#
using System;

public class MyClass {
   [Obsolete("Don't use OldMethod, use NewMethod instead", true)]

   static void OldMethod() {
      Console.WriteLine("It is the old method");
   }
   static void NewMethod() {
      Console.WriteLine("It is the new method");
   }
   public static void Main() {
      OldMethod();
   }
}
```

- Returns:

```markdown
Don't use OldMethod, use NewMethod instead
```

## Creating custom attributes

- Creating and using custom attributes involve four steps:
  - Declaring a custom attribute;
  - Constructing the custom attribute;
  - Apply the custom attribute on a target program element,
  - Accessing Attributes Through Reflection;

## Declaring a Custom Attribute

- A custom attribute is derived from the System.Attribute class:
- For example:

```c#
//a custom attribute BugFix to be assigned to a class and its members
[AttributeUsage(
   AttributeTargets.Class |
   AttributeTargets.Constructor |
   AttributeTargets.Field |
   AttributeTargets.Method |
   AttributeTargets.Property,
   AllowMultiple = true)]

public class DeBugInfo : System.Attribute
```

- Here, we created a new custom attribute, `DeBugInfo`;

## Constructing the Custom Attribute

- This custom example will have the following properties:

  - The code number for the bug;
  - Name of the developer who identified the bug;
  - Date of last review of the code;
  - A string message for storing the developer's remarks;

- Example:

```c#
//a custom attribute BugFix to be assigned to a class and its members
[AttributeUsage(
   AttributeTargets.Class |
   AttributeTargets.Constructor |
   AttributeTargets.Field |
   AttributeTargets.Method |
   AttributeTargets.Property,
   AllowMultiple = true)]

public class DeBugInfo : System.Attribute {
   private int bugNo;
   private string developer;
   private string lastReview;
   public string message;

   public DeBugInfo(int bg, string dev, string d) {
      this.bugNo = bg;
      this.developer = dev;
      this.lastReview = d;
   }
   public int BugNo {
      get {
         return bugNo;
      }
   }
   public string Developer {
      get {
         return developer;
      }
   }
   public string LastReview {
      get {
         return lastReview;
      }
   }
   public string Message {
      get {
         return message;
      }
      set {
         message = value;
      }
   }
}
```

## Applying a custom attribute

- Example:

```c#
[DeBugInfo(45, "Zara Ali", "12/8/2012", Message = "Return type mismatch")]
[DeBugInfo(49, "Nuha Ali", "10/10/2012", Message = "Unused variable")]
class Rectangle {
   //member variables
   protected double length;
   protected double width;
   public Rectangle(double l, double w) {
      length = l;
      width = w;
   }
   [DeBugInfo(55, "Zara Ali", "19/10/2012", Message = "Return type mismatch")]

   public double GetArea() {
      return length * width;
   }
   [DeBugInfo(56, "Zara Ali", "19/10/2012")]

   public void Display() {
      Console.WriteLine("Length: {0}", length);
      Console.WriteLine("Width: {0}", width);
      Console.WriteLine("Area: {0}", GetArea());
   }
}
```

## Links

- <https://www.tutorialspoint.com/csharp/csharp_attributes.htm> ;
