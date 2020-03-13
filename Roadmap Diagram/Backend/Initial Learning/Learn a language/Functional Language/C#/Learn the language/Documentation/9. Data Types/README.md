## Data Types

**Here you will learn about:**

- Data Types;
  - Numbers;
  - String;
  - DateTime;
  - Anonymous Type;
  - Dynamic Type;

**Overview:**

- Variables in C# can be:
  - Value Types;
  - Reference types;
  - Pointer types;

**Value Types:**

- Value type variables can be assigned a value directly;
- Derived from the class System.ValueType;
- Directly contain data, in it's own memory space;
- Value types include simple types (e.g. int, float, bool, and char), enum types, struct types, and Nullable value types;
- When you declare, for example, an **int** type, the system allocates memory to store the value;
- You can get the syze of a variable with the `syzeof` method, for example like `syzeof(int)`;

**Reference Types:**

- They do not contain the actual data stored in a variable, but they contain a reference to the variables;
- They refer to a memory location;
- Reference types include class types, interface types, delegate types, and array types;
- Examples:
  - **object**;
  - **dynamic**;
  - **string**;

**Object Type:**

- Is the ultimate base class for all data types;
- An alias for System.Object class;
- Can be assigned values of any other types, value types, reference types, predefined or user-defined types;
- When a value type is converted to object type, and when an object type is converted to a value type, it is called unboxing.
- For example:

```
object obj;
obj = 100; // this is boxing
```

**Dynamic Type:**

- Can store any type of value;
- Avoids compile time type checking;
- Dynamic types are similar to object types except that type checking for object type variables takes place at compile time, whereas that for the dynamic type variables takes place at run time;
- Example:
  - `dynamic dynamicVariable = 1;`;

**Methods and Properties of Dynamic Type:**

- If you assign class object to the dynamic type then the compiler would not check for correct methods and properties name of a dynamic type that holds the custom class object;

**Dynamic Type as a Method Parameter:**

- A method can have dynamic type parameters so that it can accept any type of parameter at run time;

**Anonymous Type:**

- Is a type that doesn't have any name;
- The implicitly typed variable- var is used to hold the reference of anonymous types;
- Example:

```
var myAnonymousType = new { firstProperty = "First",
    secondProperty = 2,
    thirdProperty = true
};
```

- An anonymous type is a temporary data type that is inferred based on the data that you include in an object initializer;
- Properties of anonymous types will be read-only properties so you cannot change their values;

**Nested Anonymous Type:**

- An anonymous type can have another anonymous type as a property;
- For example:

```
var myAnonymousType = new
                        {
                            firstProperty = "First",
                            secondProperty = 2,
                            thirdProperty = true,
                            anotherAnonymousType = new { nestedProperty = "Nested"}
                        };
```

**Scope of Anonymous Type:**

- An anonymous type will always be local to the method where it is defined;
- You can only pass them a method that accepts a parameter of dynamic type;
- Example:

```
static void Main(string[] args)
{

    var myAnonymousType = new
                            {
                                firstProperty = "First Property",
                                secondProperty = 2,
                                thirdProperty = true
                            };

    DoSomethig(myAnonymousType);
}

static void DoSomethig(dynamic param)
{
    Console.WriteLine(param.firstProperty);
}
```

- Returns:

```
First Property
```

**Pointer Type:**

- Store the memory address of another type;
- For example:

  ```
  char* cptr;
  int* iptr;
  ```

**Default value:**

- Every data type has a default value;
- Numeric type is 0, boolean has false and char has '/0' as default value;
- Use default(typename) to assign a default value of the data type or C# 7.1 onward, use default literal, for example:

```
int i = default(int); // 0
float f = default(float);// 0
decimal d = default(decimal);// 0
bool b = default(bool);// false
char c = default(char);// '\0'

// C# 7.1 onwards
int i = default; // 0
float f = default;// 0
decimal d = default;// 0
bool b = default;// false
char c = default;// '\0'
```

**See More:**

- See more in-depth about:
  - Numbers;
  - String;
  - DateTime;
  - Anonymous Type;
  - Dynamic Type;

**Points to remember:**

- Value type stores the value in its memory space, whereas reference type stores the address of the value where it is stored.;
- Primitive data types and struct are of the 'Value' type;
- Class objects, string, array, delegates are reference types;
- Value type passes byval by default;
- Reference type passes byref by default;
- Value types and reference types stored in Stack and Heap in the memory depends on the scope of the variable;

**Links:**

- https://www.tutorialspoint.com/csharp/csharp_data_types.htm ;
- https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/value-types ;
- https://www.tutorialsteacher.com/csharp/csharp-data-types ;
- https://www.tutorialsteacher.com/csharp/csharp-anonymous-type ;
