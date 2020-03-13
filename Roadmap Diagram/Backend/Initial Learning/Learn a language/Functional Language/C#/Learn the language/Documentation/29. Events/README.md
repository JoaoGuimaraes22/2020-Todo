## Events

**Overview:**

- Are user actions;
- Applications need to respond to events when they occur;
- Used for inter-process communication;

**Using delegates with events:**

- The events are declared and raised in a class and associated with the event handlers using delegates within the same class or some other class;
- The class containing the event is used to publish the event;
- This is called the publisher class;
- Some other class that accepts this event is called the subscriber class;
- This is the publisher-subscriber model;
- A publisher is an object that contains the definition of the event and the delegate;
- A subscriber is an object that accepts the event and provides an event handler;

**Declaring events:**

- First, you must declare a delegate type for the even as:
  - `public delegate string BoilerLogHandler(string str);`;
- Then, you can declare the event:
  - `event BoilerLogHandler BoilerEventLog;`;

**Example:**

```
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

```
Welcome Tutorials Point

```

**Links:**

- https://towardsdatascience.com/real-time-mobile-video-object-detection-using-tensorflow-a75fa0c5859d ;
