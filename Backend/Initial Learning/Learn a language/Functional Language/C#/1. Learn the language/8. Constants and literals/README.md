# Constants and literals

## Constants

- Constants refer to fixed values that the program may not alter during its execution;
- These fixed values are also called literals;
- Can be of any of the basic data type;

## Integer literals

- Can be a decimal or a hexadecimal;
- A prefix specifies the base or radix: 0x or 0X for hexadecimal, and there is no prefix id for decimal;
- An integer literal can also have a suffix that is a combination of U and L, for unsigned and long, respectively;
- The suffix can be uppercase or lowercase and can be in any order;
- For example:

```markdown
212 /_ Legal _/
215u /_ Legal _/
0xFeeL /_ Legal _/
```

## Floating-point Literals

- A floating-point literal has an integer part, a decimal point, a fractional part, and an exponent part;
- You can represent floating point literals either in decimal form or exponential form;
- For example:

```markdown
3.14159 /_ Legal _/
314159E-5F /_ Legal _/
510E /_ Illegal: incomplete exponent _/
210f /_ Illegal: no decimal or exponent _/
.e55 /_ Illegal: missing integer or fraction _/
```

## Character Constants

- They are enclosed in single quotes;
- They can be a plain character (such as 'x'), an escape sequence (such as '\t'), or a universal character (such as '\u02C0');

## Escape sequence code

- Sometimes, you must 'escape' code to make it formated the way you want it to;
- See escape sequence code here -> <https://docs.microsoft.com/en-us/cpp/c-language/escape-sequences?view=vs-2019> ;

## String literals

- They are enclosed in double quotes "" or with @"";
- Contains characters that are similar to character literals: plain characters, escape sequences, and universal characters;
- For example:

```markdown
"hello, dear"
"hello, \
dear"
"hello, " "d" "ear"
@"hello dear"
```

## Defining constants

- Defined using the `const` keyword;
- The syntax is:
  - `const <data_type> <constant_name> = value;`

## Links

- <https://www.tutorialspoint.com/csharp/csharp_constants.htm> ;
