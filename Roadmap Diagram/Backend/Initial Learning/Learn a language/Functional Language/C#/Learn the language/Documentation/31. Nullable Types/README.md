## Nullable Type

**Overview:**

- Nullable types that allow you to assign null to value type variables;

**Syntax:**

- You can declare nullable types using Nullable<t> where T is a type;
- Example:
  - `Nullable<int> i = null;`;

**Shorthand Syntax for Nullable Types:**

- You can use the '?' operator to shorthand the syntax e.g. int?, long? instead of using Nullable<T>;
- Example:

```
int? i = null;
double? D = null;
```

**?? Operator:**

- Use the '??' operator to assign a nullable type to a non-nullable type;
- Example:

```
int? i = null;

int j = i ?? 0;

Console.WriteLine(j);
```

- Returns:

```
0
```

**Assignment Rules:**

- A nullable type has the same assignment rules as a value type;
- It must be assigned a value before using it if nullable types are declared in a function as local variables;

**Nullable Helper Class:**

- Null is considered to be less than any value;
- Nullable static class is a helper class for Nullable types;
- It provides a compare method to compare nullable types;
- Example:

```
static void Main(string[] args)
{
    int? i = null;
    int j = 10;

    if (Nullable.Compare<int>(i, j) < 0)
        Console.WriteLine("i < j");
    else if (Nullable.Compare<int>(i, j) > 0)
        Console.WriteLine("i > j");
    else
        Console.WriteLine("i = j");
}
```

- Returns:

```
i < j
```

**Characteristics of Nullable Types:**

- Can only be used with value types;
- The Value property will throw an InvalidOperationException if value is null; otherwise it will return the value;
- The HasValue property returns true if the variable contains a value, or false if it is null;
- You can only use == and != operators with a nullable type. For other comparison use the Nullable static class;
- Nested nullable types are not allowed. Nullable<Nullable<int>> i; will give a compile time error;

**Points to Remember:**

- Nullable<T> type allows assignment of null to value types;
- ? operator is a shorthand syntax for Nullable types;
- Use value property to get the value of nullable type;
- Use HasValue property to check whether value is assigned to nullable type or not;
- Static Nullable class is a helper class to compare nullable types;

**Links:**

- https://www.tutorialsteacher.com/csharp/csharp-nullable-types ;
