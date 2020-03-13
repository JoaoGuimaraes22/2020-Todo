## Preprocessor Directives

**Overiview:**

- They give instructions to the compiler to preprocess the information before actual compilation starts;
- Begin with `#`;
- Preprocessor directives are not statements, so they do not end with a semicolon (;);
- Preprocessor directives are used to help in conditional compilation;

**List of preprocessor directives:**

- #define:
  - Defines a sequence of characters, called a symbol;
- #undef:
  - Allows you to undefine a symbol;
- #if, #else, #elif:
  - Allows testing a symbol or symbols to see if they evaluate to true;
- #endif:
  - Specifies the end of a conditional dirctive;
- #line:
  - Lets you modify the compiler's line number and (optionally) the file name output for errors and warnings
- #error:
  - Allows generating an error from a specific location in your code;
- #warning:
  - Allows generating a level one warning from a specific location of your code;
- #region:
  - Lets you specify a block of code that you can expand or collapse when using the outlining feature of the Visual Studio Code Editor;
- #endregion:
  - Marks the end of a #region block;
- See all in -> https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/preprocessor-directives/ ;

**The #define preprocessor:**

- Creates symbolic constants;
- Syntax:

```
#define symbol
```

- For example:

```
#define PI
using System;

namespace PreprocessorDAppl {
   class Program {
      static void Main(string[] args) {
         #if (PI)
            Console.WriteLine("PI is defined");
         #else
            Console.WriteLine("PI is not defined");
         #endif
         Console.ReadKey();
      }
   }
}
```

- Returns:

```
PI is defined
```

**Conditional Directives:**

- Use the #if directive to create a conditional directive;
- for testing a symbol or symbols to check if they evaluate to true;
- Syntax:
  - `#if symbol [operator symbol]...`;
- For example:

```
#define DEBUG
#define VC_V10
using System;

public class TestClass {
   public static void Main() {
      #if (DEBUG && !VC_V10)
         Console.WriteLine("DEBUG is defined");
      #elif (!DEBUG && VC_V10)
         Console.WriteLine("VC_V10 is defined");
      #elif (DEBUG && VC_V10)
         Console.WriteLine("DEBUG and VC_V10 are defined");
      #else
         Console.WriteLine("DEBUG and VC_V10 are not defined");
      #endif
      Console.ReadKey();
   }
}
```

- Returns:

```
DEBUG and VC_V10 are defined
```

**Links:**

- https://www.tutorialspoint.com/csharp/csharp_preprocessor_directives.htm ;
