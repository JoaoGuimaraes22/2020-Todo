## Methods

**Overview:**

- Is a group of statements that together perform a task;
- Every program has at least one class with a method named Main;
- To use a method, you need to:  
  - Define method;
  - Call the method;

**Defining Methods in C#:**

- The syntax is:

```
<Access Specifier> <Return Type> <Method Name>(Parameter List) {
   Method Body
}
```

- The elements of a method are:
  - Access specifier:
    - Determines the visibility of a variable or a method from another class;
  - Return value:
    - May or may not return a value;
    - The return type is the data type of the value the method returns;
    - If the method is not returning any values, then the return type is void;
  - Method name:
    - Is a unique identifier;
  - Paremeter List:
    - Enclosed between parentheses, the parameters are used to pass and receive data from a method;
    - The parameter list refers to the type, order, and number of the parameters of a method;
    - Parameters are optional;
  - Method body:
    - Contains the set of instructions needed to complete the required activity;
- Example:

```
class NumberManipulator {

   public int FindMax(int num1, int num2) {
      /* local variable declaration */
      int result;

      if (num1 > num2)
         result = num1;
      else
         result = num2;

      return result;
   }
   ...
}
```

**Calling Methods:**

- Example:

```
using System;

namespace CalculatorApplication {
   class NumberManipulator {
      public int FindMax(int num1, int num2) {
         /* local variable declaration */
         int result;

         if (num1 > num2)
            result = num1;
         else
            result = num2;
         return result;
      }

      static void Main(string[] args) {
         /* local variable definition */
         int a = 100;
         int b = 200;
         int ret;
         NumberManipulator n = new NumberManipulator();

         //calling the FindMax method
         ret = n.FindMax(a, b);
         Console.WriteLine("Max value is : {0}", ret );
         Console.ReadLine();
      }
   }
}
```

- Returns:

```
Max value is : 200
```

- You can also call a method from an instance of a class;

**Passing paramethers to a method:**

- There are three ways paramethers can be passed to a method:
  - Value parameters:
    - Copies the actual value of an argument into the formal parameter of the function;
    - In this case, changes made to the parameter inside the function have no effect on the argument;
  - Reference parameters:
    - Copies the reference to the memory location of an argument into the formal parameter;
    - This means that changes made to the parameter affect the argument;
  - Output parameters:
    - Helps in returning more than one value;

**Links:**

- https://www.tutorialspoint.com/csharp/csharp_methods.htm ;
- https://docs.microsoft.com/en-us/dotnet/csharp/methods ;
