## Exception Handling

**Overview:**

- An exception is a problem that arises during the execution of a program;
- Exception handling is built upon four keywords: try, catch, finally, and throw:
  - try:
    - Identifies a block of code for which particular exceptions is activated;
    - It is followed by one or more catch blocks;
  - catch:
    - Catches an exception with an exception handler at the place in a program where you want to handle the problem;
    - Indicates the catching of an exception;
- finnaly:
  - Used to execute a given set of statements, whether an exception is thrown or not thrown;
  - For example, if you open a file, it must be closed whether an exception is raised or not;
- throw:
  - Throws an exception when a problem shows up;

**Syntax:**

```
try {
   // statements causing exception
} catch( ExceptionName e1 ) {
   // error handling code
} catch( ExceptionName e2 ) {
   // error handling code
} catch( ExceptionName eN ) {
   // error handling code
} finally {
   // statements to be executed
}
```

- You can list down multiple catch statements to catch different type of exceptions in case your try block raises more than one exception in different situations;

**Exception Classes:**

- Exception are mainly derived from the System.Exception class;
- Exception classes:
  - System.IO.Exception:
    - Handles I/O errors;
  - System.IndexOutOfRangeException:
    - Handles errors generated when a method refers to an array index out of range;
  - System.ArrayTypeMismatchException:
    - Handles errors generated when type is mismatched with the array type;
  - System.NullReferenceException:
    - Handles errors generated from referencing a null object;
  - System.DivideByZeroException:
    - Handles errors generated from dividing a dividend with zero;
  - System.InvalidCastException:
    - Handles errors generated during typecasting;
  - System.OutOfMemoryException:
    - Handles errors generated from insufficient free memory;
  - System.StackOverflowException:
    - Handles errors generated from stack overflow;

**Handling exceptions:**

- Using a structured solution to the exception handling in the form of try and catch blocks;
- For example:

```
using System;

namespace ErrorHandlingApplication {
   class DivNumbers {
      int result;

      DivNumbers() {
         result = 0;
      }
      public void division(int num1, int num2) {
         try {
            result = num1 / num2;
         } catch (DivideByZeroException e) {
            Console.WriteLine("Exception caught: {0}", e);
         } finally {
            Console.WriteLine("Result: {0}", result);
         }
      }
      static void Main(string[] args) {
         DivNumbers d = new DivNumbers();
         d.division(25, 0);
         Console.ReadKey();
      }
   }
}
```

- Returns:

```
Exception caught: System.DivideByZeroException: Attempted to divide by zero.
at ...
Result: 0
```

**Creating user-defined exceptions:**

**Links:**

- https://www.tutorialspoint.com/csharp/csharp_exception_handling.htm ;
