## Type conversion

**Types of conversions:**

- Implicit conversions;
- Explicit conversions (casts);
- User-defined conversions;
- Conversions with helper classes;

**Implicit conversions:**

- Performed in a type-safe manner;
- Can be made when the value to be stored can fit into the variable without being truncated or rounded off;
- For example, there are conversions from smaller to larger integral types and conversions from derived classes to base classes;
- Examples:

```
int num = 2147483647;
long bigNum = num;
```

- List of implicit conversions -> https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/numeric-conversions#implicit-numeric-conversions ;

**Explicit Conversions (casts):**

- If a conversion cannot be made without a risk of losing information, the compiler requires that you perform an explicit conversion;
- To perform a cast, specify the type that you are casting to in parentheses in front of the value or variable to be converted;
- Example:

```
class Test
{
    static void Main()
    {
        double x = 1234.7;
        int a;
        // Cast double to int.
        a = (int)x;
        System.Console.WriteLine(a);
    }
}
// Output: 1234
```

- List of explictit conversions -> https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/numeric-conversions#explicit-numeric-conversions ;

**Type conversion methods:**

- ToBoolean;
- To(S)Byte;
- ToChar;
- ToDateTime;
- ToDecimal;
- ToDouble;
- ToInt(16, 32, 64);
- ToSingle;
- ToString;
- ToType;
- ToUInt(16, 32, 64);

**Links:**

- https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/types/casting-and-type-conversions ;
- https://www.tutorialspoint.com/csharp/csharp_type_conversion.htm ;
- https://www.tutorialsteacher.com/csharp/csharp-data-types ;