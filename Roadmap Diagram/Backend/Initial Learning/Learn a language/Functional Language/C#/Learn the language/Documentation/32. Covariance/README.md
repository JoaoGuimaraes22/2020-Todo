## Covariance and Contravariance

**Overview:**

- Covariance and contravariance allow us to be flexible when dealing with class hierarchy;
- For example:

```
public class Small
{

}
public class Big: Small
{

}
public class Bigger : Big
{

}
```

- Here, small is a base class for big and big is a base class for bigger;
- A derived class will always have something more than a base class, so the base class is relatively smaller than the derived class
- An instance can accept big even if it demands small, but it cannot accept small if it demands big;

**Covariance:**

- Enables you to pass a derived type where a base type is expected;
- The base class and other derived classes are considered to be the same kind of class that adds extra functionalities to the base type;
- Allows you to use a derived class where a base class is expected;
- Can be applied on delegate, generic, array, interface, etc.;

**Covariance w/ delegate:**

- Covariance in delegates allows flexiblity in the return type of delegate methods, for example:

```
public delegate Small covarDel(Big mc);

class Program
{

    static Big Method1(Big bg)
    {
        Console.WriteLine("Method1");

        return new Big();
    }
    static Small Method2(Big bg)
    {
        Console.WriteLine("Method2");

        return new Small();
    }

    static void Main(string[] args)
    {
        covarDel del = Method1;

        Small sm1 = del(new Big());

        del= Method2;
        Small sm1 = del(new Big());
    }
}
```

- Returns:

```
Method1
Method2
```

- Here, covariance allows you to assign a method to the delegate that has a less derived return type;

**Contravariance:**

- Applied to parameters;
- Allows a method with the parameter of a base class to be assigned to a delegate that expects the parameter of a derived class;
- For example:

```
delegate Small covarDel(Big mc);

class Program
{
    static Big Method1(Big bg)
    {
        Console.WriteLine("Method1");
        return new Big();
    }
    static Small Method2(Big bg)
    {
        Console.WriteLine("Method2");
        return new Small();
    }

    static Small Method3(Small sml)
    {
        Console.WriteLine("Method3");

        return new Small();
    }
    static void Main(string[] args)
    {
        covarDel del = Method1;
        del += Method2;
        del += Method3;

        Small sm = del(new Big());
}
```

- Returns:

```
Method1
Method2
Method3
```

- As you can see, Method3 has a parameter of Small class whereas delegate expects a parameter of Big class. Still, you can use Method3 with the delegate;

- You can also use covariance and contravariance in the same method;

**Links:**

- https://www.tutorialsteacher.com/csharp/csharp-covariance-and-contravariance;
