## Structure

**Overview:**

- A structure is a value data type;
- Helps you make a singe variable hold related data of various data types;
- Useful to hold small data value;
- Structures are used to represent a record;

**Defining a structure:**

- To define a structure, you must use the struct statement with public or internal modifier;
- Default is internal;
- You can use private or protected modifier when declared inside a class;
- The struct statement defines a new data type, with more than one member for your program;
- For example:

```
struct Employee
{
    public int EmpId;
    public string FirstName;
    public string LastName;
}
```

**Constructors in Struct:**

- A struct cannot contain parameterless constructor;
- Good for initializing struct members;
- Example:

```
struct Employee
{
    public int EmpId;
    public string FirstName;
    public string LastName;

    public Employee(int empid, string fname, string lname)
    {
        EmpId = empid;
        FirstName = fname;
        LastName = lname;
    }
}

Employee emp = new Employee(10, "Bill", "Gates");

Console.Write(emp.EmpId); // prints 10
Console.Write(emp.FirstName); // prints Bill
Console.Write(emp.LastName); // prints Gates
```

**Features of Structures:**

- The C# structures have the following features:
  - Can have methods, fields, indexers, properties, operator methods, and events;
  - Can have defined constructors, but not destructors;
  - You cannot define a default constructor for a structure;
  - The default constructor is automatically defined and cannot be changed;
  - Structures cannot inherit other structures or classes;
  - Structures cannot be used as a base for other structures or classes;
  - A structure can implement one or more interfaces;
  - Structure members cannot be specified as abstract, virtual, or protected;
  - When you create a struct object using the New operator, it gets created and the appropriate constructor is called;
  - Structs can be instantiated without using the New operator;
  - If the New operator is not used, the fields remain unassigned and the object cannot be used until all the fields are initialized;

**Classes versus Structures:**

- Classes are reference types and structs are value types;
- Structures do not support inheritance;
- Structures cannot have default constructor or destructor. However, it can have parametrized constructors;
- Struct can be instasntiated without the new operator. However, you won't be able to use any of its methods, events or properties if you do so;
- However, you won't be able to use any of its methods, events or properties if you do so;

**Links:**

- https://www.tutorialspoint.com/csharp/csharp_struct.htm ;
- https://www.tutorialsteacher.com/csharp/csharp-struct ;
