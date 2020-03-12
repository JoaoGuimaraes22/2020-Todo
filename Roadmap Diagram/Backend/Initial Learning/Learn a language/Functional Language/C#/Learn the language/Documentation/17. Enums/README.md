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

**Links:**

- https://www.tutorialspoint.com/csharp/csharp_enums.htm ;
- https://www.guru99.com/c-sharp-enum.html ;
