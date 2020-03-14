# Interfaces

## Overview

- Is defined as a syntactical contract that all the classes inheriting the interface should follow;
- The interface defines the 'what' part of the syntactical contract and the deriving classes define the 'how' part of the syntactical contract;
- Interfaces can contain methods, properties, indexers, and events as members;
- You can't use access modifiers for interfaces;
- Can only contain declarations;

## Declaring Interfaces

- Interfaces are declared using the interface keyword;
- For example:

```c#
public interface ITransactions {
   // interface members
   void showTransaction();
   double getAmount();
}
```

## Example

```c#
class Cello : IPen
{
    public string Color { get; set; }

    private bool isOpen = false;

    public bool Close()
    {
        isOpen = false;
        Console.WriteLine("Cello closed for writing!");

        return isOpen;
    }

    public bool Open()
    {
        isOpen = true;
        Console.WriteLine("Cello open for writing!");

        return isOpen;
    }

    public void Write(string text)
    {
        //write text if open
        if(isOpen)
            Console.WriteLine("Cello: " + text);
    }
}
```

## Explicit Interface Implementation

- Explicit implementation is useful when class is implementing multiple interface thereby it is more readable and eliminates the confusion;
- Example:

```c#
class Cello : IPen
{
    string IPen.Color { get; set; }

    private bool isOpen = false;

    bool IPen.Close()
    {
        isOpen = false;
        Console.WriteLine("Cello closed for writing!");

        return isOpen;
    }

    bool IPen.Open()
    {
        isOpen = true;
        Console.WriteLine("Cello open for writing!");

        return isOpen;
    }

    void IPen.Write(string text)
    {
        //write text if open
        if(isOpen)
            Console.WriteLine("Cello: " + text);
    }
}
```

## Implement Multiple Interfaces

- A class or struct can implement multiple interfaces and must define all the members of all interfaces;
- For example:

```c#
interface IBrandedPen
{
    string GetBrandName();
}

class Parker : IPen, IBrandedPen
{
    //Implement all members of IPen and IBrandedPen
}
```

- Now, the Parker class can be instantiated and assigned to either IPen or IBrandedPen interface, as shown below:

```c#
IPen pen1 = new Parker();
pen1.Open();// valid
pen1.GetBrandName(); //Compile-time error. Cannot call IBrandedPen method on the object of type IPen

IBrandedPen pen2 = new Parker();
pen2.GetBrandName();// valid
pen2.Open();//Compile-time error. Cannot call IPen method on the object of type IBrandedPen
```

- An interface can also inherit one or more interfaces;

## Points to Remember

- An interface only contains declarations of method, properties, indexers, and events;
- An interface can be implement implicitly or explicitly by a class or struct;
- A class or struct which implements an interface, must use 'public' access modifier;
- An interface cannot include private, protected, or internal members. All the members are public by default;
- Do not include 'public' in an interface as all the members are public by default. C# will give compile-time error if used 'public;
- Implement interface explicitly using InterfaceName. with all the members;
- An interface can inherit one or more interfaces;

## Links

- <https://www.tutorialspoint.com/csharp/csharp_interfaces.htm> ;
- <https://www.tutorialsteacher.com/csharp/csharp-interface> ;
