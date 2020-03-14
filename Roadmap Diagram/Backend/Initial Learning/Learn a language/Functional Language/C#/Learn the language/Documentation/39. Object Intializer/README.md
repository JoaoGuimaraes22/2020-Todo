## Object Initializer

**Overview:**

- C# 3.0 (.NET 3.5) introduced Object Initializer Syntax, a new way to initialize an object of a class or collection. Object initializers allow you to assign values to the fields or properties at the time of creating an object without invoking a constructor;

**Syntax:**

```
public class Student
{
    public int StudentID { get; set; }
    public string StudentName { get; set; }
    public int Age { get; set; }
    public string Address { get; set; }
}

class Program
{
    static void Main(string[] args)
    {
        Student std = new Student() { StudentID = 1,
                                      StudentName = "Bill",
                                      Age = 20,
                                      Address = "New York"
                                    };
    }
}

```

**Collection Initializer Syntax:**

- Collection can be initialized the same way as class objects using collection initializer syntax:

```
IList<Student> studentList = new List<Student>() {
                    new Student() { StudentID = 1, StudentName = "John"} ,
                    new Student() { StudentID = 2, StudentName = "Steve"} ,
                    new Student() { StudentID = 3, StudentName = "Bill"} ,
                    new Student() { StudentID = 3, StudentName = "Bill"} ,
                    new Student() { StudentID = 4, StudentName = "Ram" } ,
                    new Student() { StudentID = 5, StudentName = "Ron" }
                };
```

**Advantages of Initializers:**

- Initializer syntax makes a code more readable, easy to add elements into the collection.;
- Useful in multi-threading;

**Links:**

- https://www.tutorialsteacher.com/csharp/csharp-object-initializer;
