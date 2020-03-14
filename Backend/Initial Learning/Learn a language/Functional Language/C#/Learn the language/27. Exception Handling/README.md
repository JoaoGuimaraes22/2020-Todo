# Exception Handling

## Overview

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

## Syntax

```c#
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

## Exception Classes

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

## Handling exceptions

- Using a structured solution to the exception handling in the form of try and catch blocks;
- For example:

```c#
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

```markdown
Exception caught: System.DivideByZeroException: Attempted to divide by zero.
at ...
Result: 0
```

## Creating user-defined exceptions

- User-defined exception classes are derived from the Exception class;
- For example:

```c#
using System;

namespace UserDefinedException {
   class TestTemperature {
      static void Main(string[] args) {
         Temperature temp = new Temperature();
         try {
            temp.showTemp();
         } catch(TempIsZeroException e) {
            Console.WriteLine("TempIsZeroException: {0}", e.Message);
         }
         Console.ReadKey();
      }
   }
}
public class TempIsZeroException: Exception {
   public TempIsZeroException(string message): base(message) {
   }
}
public class Temperature {
   int temperature = 0;

   public void showTemp() {

      if(temperature == 0) {
         throw (new TempIsZeroException("Zero Temperature found"));
      } else {
         Console.WriteLine("Temperature: {0}", temperature);
      }
   }
}
```

- Returns:

```markdown
TempIsZeroException: Zero Temperature found
```

## Throwing Objects

- You can throw an object if it is either directly or indirectly derived from the System.Exception class;
- For example:

```c#
Catch(Exception e) {
   ...
   Throw e
}
```

## Points to Remember

- Exception is a base class for any type of exception class in C#;
- Exception types: SystemException and ApplicationException;
- SystemException class is used for CLR related runtime errors;
- Exception class includes important properties e.g Message, StackTrack, InnerException, data etc. to associate important information with every exception;
- Use the try, catch and finally blocks to handle exceptions in C#;
- The try block must be followed by a catch or finally block or both;
- A multiple catch block is allowed with different exception filters. General catch{..} block must come last;
- `catch{..}` and `catch(Exception ex){ }` both cannot be used;
- The finally block must come after the try or catch block;
- The finally block will always execute irrespective of whether an exception occured or not;
- The finally block is appropriate place for disposing objects;
- The finally block cannot have a return or break because it isn't allow to leave the control;
- Nested try-catch blocks are allowed in C#;
- An Exception will be catched in the inner catch block if appropriate filter found, otherwise will be catched by outer catch block;

## Links

- <https://www.tutorialspoint.com/csharp/csharp_exception_handling.htm> ;
- <https://www.tutorialsteacher.com/csharp/csharp-exception> ;
- <https://www.tutorialsteacher.com/csharp/csharp-exception-handling> ;
