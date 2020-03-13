## Enums

**Overview:**

- An enumeration is a set of named integer constants;
- Enumerations are value data types;
- Enumeration contains its own values and cannot inherit or cannot pass inheritance;
- Used to define a constant set of values;

**Declaring `enum` Variables:**

- Syntax:

```
enum <enum_name> {
   enumeration list
};
```

- Where:
  - The enum_name specifies the enumeration type name;
  - The enumeration list is a comma-separated list of identifiers.
- For example:
  - `enum Days { Sun, Mon, tue, Wed, thu, Fri, Sat };`;

**Example:**

```
using System;

namespace EnumApplication {
   class EnumProgram {
      enum Days { Sun, Mon, tue, Wed, thu, Fri, Sat };

      static void Main(string[] args) {
         int WeekdayStart = (int)Days.Mon;
         int WeekdayEnd = (int)Days.Fri;

         Console.WriteLine("Monday: {0}", WeekdayStart);
         Console.WriteLine("Friday: {0}", WeekdayEnd);
         Console.ReadKey();
      }
   }
}
```

- Returns:

```
Monday: 1
Friday: 5
```

**Enum Methods:**

- Format:
  -     Converts the specified value of enum type to the specified string format;
- GetName / GetNames:
  - Returns the name / array of names of the constant / all constants of the specified value of specified enum;
- GetValues:
  - Returns an array of the values of all the constants of specified enum;
- object Parse(type, string):
  - Converts the string representation of the name or numeric value of one or more enumerated constants to an equivalent enumerated object;
- bool TryParse(string, out TEnum):
  - Converts the string representation of the name or numeric value of one or more enumerated constants to an equivalent enumerated object. The return value indicates whether the conversion succeeded;

**Points to Remember:**

- The enum is a set of named constants;
- The value of enum constants starts from 0. Enum can have value of any valid numeric type;
- String enum is not supported in C#;
- Use of enum makes code more readable and manageable;

**Links:**

- https://www.tutorialspoint.com/csharp/csharp_enums.htm ;
- https://www.guru99.com/c-sharp-enum.html ;
