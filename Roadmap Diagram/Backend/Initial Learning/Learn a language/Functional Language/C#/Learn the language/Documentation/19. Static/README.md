## Static

**Overview:**

- The `static` keyword can be applied on classes, variables, methods, properties, operators, events and constructors;
- Cannot be used with indexers, destructors or types other than classes;
- Makes an item non-instantiable;
- If the static modifier is applied to a variable, method or property of class then they can be accessed without creating an object of the class, just use className.propertyName, className.methodName;

**Example:**

```
public static class MyStaticClass
{
    public static int myStaticVariable = 0;

    public static void MyStaticMethod()
    {
        Console.WriteLine("This is a static method.");
    }

    public static int MyStaticProperty { get; set; }
}

class Program
{
    static void Main(string[] args)
    {
        
        Console.WriteLine(MyStaticClass.myStaticVariable);

        MyStaticClass.MyStaticMethod();

        MyStaticClass.MyStaticProperty = 100;

        Console.WriteLine(MyStaticClass.MyStaticProperty);
    }
}
```
- Returns:
```
0
This is a static method.
100
```

**Features:**

- You can have static members in non-static classes just like a normal class;
- All the static members can be access using className without creating an object of a class;

**Static constructor:**

- A static constructor in a non-static class runs only once when the class is instantiated for the first time;
- A static constructor in a static class runs only once when any of its static members accessed for the first time;
- Example:
```
public static class MyStaticClass
{
    static MyStaticClass()
    {
        Console.WriteLine("Inside static constructor.");
    }
    public static int myStaticVariable = 0;

    public static void myStaticMethod()
    {
        Console.WriteLine("This is static method.");
    }

    public static int MyStaticProperty { get; set; }

}

class Program
{

    static void Main(string[] args)
    {
        
        MyStaticClass.myStaticVariable = 100;

        MyStaticClass.MyStaticProperty = 200;

        MyStaticClass.myStaticVariable = 300;

        MyStaticClass.MyStaticProperty = 400;

    }
}
```
- Returns:
```
Inside static constructor.
```

**Memory Allocation for Static Items:**

- Static members are stored in a special area inside the heap called High Frequency Heap; 
- So the changes done by one instance will be reflected in all the other instances;

**Points to Remember:**

- Static classes cannot be instantiated using the new keyword;
- Static items can only access other static items. For example, a static class can only contain static members, e.g., variables, methods, etc. A static method can only contain static variables and can only access other static items;
- Static items share the resources between multiple users;
- Static cannot be used with indexers, destructors or types other than classes;
- A static constructor in a non-static class runs only once when the class is instantiated for the first time;
- A static constructor in a static class runs only once when any of its static members accessed for the first time;
- Static members are allocated in high frequency heap area of the memory; 

**Links:**

- https://www.tutorialsteacher.com/csharp/csharp-static;
