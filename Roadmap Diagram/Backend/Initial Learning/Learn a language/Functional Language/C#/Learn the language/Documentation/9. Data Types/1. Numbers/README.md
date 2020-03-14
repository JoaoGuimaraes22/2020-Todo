# Numbers

## Overview

- Can be divided into two types:
  - Integer type numbers are whole numbers without decimal points;
  - Floating-point type is numbers with one or more decimal points;

## Integer Types

- Positive or negative whole numbers without decimal points;
- Includes byte, short, int, and long;

### Byte

- Integer;
- Stores numbers from 0 to 255;
- The `sbyte` is the same as `byte`, but it can store negative numbers from -128 to 127;

### Short

- The `short` data type is a signed integer;
- Stores numbers from -32,768 to 32,767;
- The `ushort` data type is an unsigned integer;
- Can store only positive numbers from 0 to 65,535;

### Int

- The `int` data type is 32-bit signed integer;
- Stores numbers from -2,147,483,648 to 2,147,483,647;
- The `uint` is 32-bit unsigned integer;
- Stores positive numbers from 0 to 4,294,967,295;

### Long

- The `long` type is 64-bit signed integers;
- Can store numbers from -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807;
- The `ulong` type stores positive numbers from 0 to 18,446,744,073,709,551,615;

## Floating Pont Types

- Are positive or negative numbers with one or more decimal points;
- Includes float, double, and decimal;

### Float

- The float data type can store fractional numbers from 3.4eâˆ’038 to 3.4e+038;

### Double

- The double data type can store fractional numbers from 1.7eâˆ’308 to 1.7e+308;

### Decimal

- The decimal data type can store fractional numbers from Â±1.0 x 10-28 to Â±7.9228 x 1028;
- The decimal type has more precision and a smaller range than both float and double, and so it is appropriate for financial and monetary calculations;

## Scientific Notation

- Use e or E to indicate the power of 10 as exponent part of scientific notation with float, double or decimal;
- Example:

```c#
double d = 0.12e2;
Console.WriteLine(d);  // 12;

float f = 123.45e-2f;
Console.WriteLine(f);  // 1.2345

decimal m = 1.2e6m;
Console.WriteLine(m);// 1200000
```

## Links

- <https://www.tutorialsteacher.com/csharp/numbers> ;
