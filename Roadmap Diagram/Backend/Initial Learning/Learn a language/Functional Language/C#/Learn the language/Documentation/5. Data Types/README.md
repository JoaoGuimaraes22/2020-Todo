## Data Types

**Variables:**

- Variables in C# can be:
  - Value Types;
  - Reference types;
  - Pointer types;

**Value Types:**

- Value type variables can be assigned a value directly;
- Derived from the class System.ValueType;
- Directly contain data;
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
- **Object Type:**

  - Is the ultimate base class for all data types;
  - An alias for System.Object class;
  - Can be assigned values of any other types, value types, reference types, predefined or user-defined types;
  - When a value type is converted to object type, and when an object type is converted to a value type, it is called unboxing.
  - For example:

    ```
    object obj;
    obj = 100; // this is boxing
    ```

- **Dynamic Type:**

  - Can store any type of value;
  - Type checking for these types of variables takes place at run-time;
  - For example:

    ```
    dynamic d = 20;
    ```

  - Dynamic types are similar to object types except that type checking for object type variables takes place at compile time, whereas that for the dynamic type variables takes place at run time;

- **String Type:**

  - Allows you to assign any string values to a variable;
  - Is an alias for the System.String class;
  - For example:

  ```
  String str = "Tutorials Point";
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
**More:**

- See more in-depth about numbers in:
  - Numbers;
  - String;
  - DateTime;


**Links:**

- https://www.tutorialspoint.com/csharp/csharp_data_types.htm ;
- https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/value-types ;
- https://www.tutorialsteacher.com/csharp/csharp-data-types ;
