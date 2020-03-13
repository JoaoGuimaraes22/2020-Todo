## Anonymous Type

**Overview:**

- Is a type that doesn't have any name;
- Allows you to create an object with the new keyword without defining its class
- The implicitly typed variable - `var` is used to hold the reference of anonymous types;
- Example:
```
var myAnonymousType = new { firstProperty = "First", 
    secondProperty = 2, 
    thirdProperty = true 
};
```

**Features:**

- An anonymous type is a temporary data type that is inferred based on the data that you include in an object initializer;
- Properties of anonymous types will be read-only properties so you cannot change their values;
- Anonymous types have intellisense support in Visual Studio;
- Internally, the compiler automatically generates the new type for anonymous types;

**Nested Anonymous Type:**

- An anonymous type can have another anonymous type as a property:
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
- Nested anonymous types also have intellisense support;

**Scope of Anonymous Type:**

- Usually, you cannot pass an anonymus type to another method; however, you can pass it to a method that accepts a parameter of dynamic type;
- For example:
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

**Anonymous Types with a LINQ Query:**

- Linq Select clause creates an anonymous type as a result of a query to include various properties which is not defined in any class;
- For example:
```
public class Student
{
    public int StudentID { get; set; }
    public string StudentName { get; set; }
    public int age { get; set; }
}

class Program
{
    static void Main(string[] args)
    {
        IList<Student> studentList = new List<Student>() { 
                        new Student() { StudentID = 1, StudentName = "John", age = 18 } ,
                        new Student() { StudentID = 2, StudentName = "Steve",  age = 21 } ,
                        new Student() { StudentID = 3, StudentName = "Bill",  age = 18 } ,
                        new Student() { StudentID = 4, StudentName = "Ram" , age = 20  } ,
                        new Student() { StudentID = 5, StudentName = "Ron" , age = 21 } 
                    };

        var studentNames = from s in studentList
                           select new { StudentID = s.StudentID, 
                                        StudentName = s.StudentName 
                                      };
    }
}
```

**Points to Remember:**

- Anonymous type can be defined using the new keyword and object initializer syntax;
- The implicitly typed variable - `var`, is used to hold an anonymous type;
- Anonymous type is a reference type and all the properties are read-only;
- The scope of an anonymous type is local to the method where it is defined;

**Links:**

- https://www.tutorialsteacher.com/csharp/csharp-anonymous-type ;