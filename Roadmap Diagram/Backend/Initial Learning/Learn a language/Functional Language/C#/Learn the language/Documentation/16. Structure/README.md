## Structure

**Overview:**

- A structure is a value data type;
- Helps you make a singe variable hold related data of various data types;
- Structures are used to represent a record;

**Defining a structure:**

- To define a structure, you must use the struct statement;
- The struct statement defines a new data type, with more than one member for your program;
- For example:

```
struct Books {
   public string title;
   public string author;
   public string subject;
   public int book_id;
};
```

- Example:

```
using System;

struct Books {
   public string title;
   public string author;
   public string subject;
   public int book_id;
};

public class testStructure {
   public static void Main(string[] args) {
      Books Book1;   /* Declare Book1 of type Book */
      Books Book2;   /* Declare Book2 of type Book */

      /* book 1 specification */
      Book1.title = "C Programming";
      Book1.author = "Nuha Ali";
      Book1.subject = "C Programming Tutorial";
      Book1.book_id = 6495407;

      /* book 2 specification */
      Book2.title = "Telecom Billing";
      Book2.author = "Zara Ali";
      Book2.subject =  "Telecom Billing Tutorial";
      Book2.book_id = 6495700;

      /* print Book1 info */
      Console.WriteLine( "Book 1 title : {0}", Book1.title);
      Console.WriteLine("Book 1 author : {0}", Book1.author);
      Console.WriteLine("Book 1 subject : {0}", Book1.subject);
      Console.WriteLine("Book 1 book_id :{0}", Book1.book_id);

      /* print Book2 info */
      Console.WriteLine("Book 2 title : {0}", Book2.title);
      Console.WriteLine("Book 2 author : {0}", Book2.author);
      Console.WriteLine("Book 2 subject : {0}", Book2.subject);
      Console.WriteLine("Book 2 book_id : {0}", Book2.book_id);

      Console.ReadKey();
   }
}
```

- Returns:

```
Book 1 title : C Programming
Book 1 author : Nuha Ali
Book 1 subject : C Programming Tutorial
Book 1 book_id : 6495407
Book 2 title : Telecom Billing
Book 2 author : Zara Ali
Book 2 subject : Telecom Billing Tutorial
Book 2 book_id : 6495700
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
- Structures cannot have default constructor;

**Links:**

- https://www.tutorialspoint.com/csharp/csharp_struct.htm ;
