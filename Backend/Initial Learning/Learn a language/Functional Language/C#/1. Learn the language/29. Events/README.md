# Events

## Overview

- Are user actions;
- Applications need to respond to events when they occur;
- Used for inter-process communication;

## Using delegates with events

- The events are declared and raised in a class and associated with the event handlers using delegates within the same class or some other class;
- The class containing the event is used to publish the event;
- This is called the publisher class;
- Some other class that accepts this event is called the subscriber class;
- This is the publisher-subscriber model;
- A publisher is an object that contains the definition of the event and the delegate;
- A subscriber is an object that accepts the event and provides an event handler;

## Declaring events

- First, you must declare a delegate type for the even as:
  - `public delegate string BoilerLogHandler(string str);`;
- Then, you can declare the event:
  - `event BoilerLogHandler BoilerEventLog;`;

## Example

```c#
using System;

namespace SampleApp {
   public delegate string MyDel(string str);

   class EventProgram {
      event MyDel MyEvent;

      public EventProgram() {
         this.MyEvent += new MyDel(this.WelcomeUser);
      }
      public string WelcomeUser(string username) {
         return "Welcome " + username;
      }
      static void Main(string[] args) {
         EventProgram obj1 = new EventProgram();
         string result = obj1.MyEvent("Tutorials Point");
         Console.WriteLine(result);
      }
   }
}
```

- Returns:

```markdown
Welcome Tutorials Point
```

## Event Arguments

- Events can pass data as an argument to their subscribed handler;
- Example:

```c#
public class PrintHelper
{
    public delegate void BeforePrint(string message);
    public event BeforePrint beforePrintEvent;


    public void PrintNumber(int num)
    {
        if (beforePrintEvent != null)
            beforePrintEvent.Invoke("PrintNumber");

        Console.WriteLine("Number: {0,-12:N0}", num);
    }

    public void PrintDecimal(int dec)
    {
        if (beforePrintEvent != null)
            beforePrintEvent("PrintDecimal");

        Console.WriteLine("Decimal: {0:G}", dec);
    }

    public void PrintMoney(int money)
    {
        if (beforePrintEvent != null)
            beforePrintEvent("PrintMoney");

        Console.WriteLine("Money: {0:C}", money);
    }

    public void PrintTemperature(int num)
    {
        if (beforePrintEvent != null)
            beforePrintEvent("PrintTemerature");

        Console.WriteLine("Temperature: {0,4:N1} F", num);
    }

    public void PrintHexadecimal(int dec)
    {
        if (beforePrintEvent != null)
            beforePrintEvent("PrintHexadecimal");

        Console.WriteLine("Hexadecimal: {0:X}", dec);
    }
}
```

## Points to remember

- Use event keyword with delegate type to declare an event;
- Check event is null or not before raising an event;
- Subscribe to events using "+=" operator. Unsubscribe it using "-=" operator;
- Function that handles the event is called event handler. Event handler must have same signature as declared by event delegate;
- Events can have arguments which will be passed to handler function;
- Events can also be declared static, virtual, sealed and abstract;
- An Interface can include event as a member;
- Events will not be raised if there is no subscriber;
- Event handlers are invoked synchronously if there are multiple subscribers;
- The .NET framework uses an EventHandler delegate and an EventArgs base class;

## Links

- <https://www.tutorialspoint.com/csharp/csharp_events.htm> ;
- <https://www.tutorialsteacher.com/csharp/csharp-event> ;
