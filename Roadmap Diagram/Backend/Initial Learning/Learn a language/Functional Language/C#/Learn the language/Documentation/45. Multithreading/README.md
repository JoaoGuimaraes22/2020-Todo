# Multithreading

## Overview

- A thread is defined as the execution path of a program;
- Each thread defines a unique flow of control;
- If your application involves complicated and time consuming operations, then it is often helpful to set different execution paths or threads, with each thread performing a particular job;
- Use of threads saves wastage of CPU cycle and increase efficiency of an application;

## Thread Life Cycle

- The life cycle of a thread starts when an object of the System.Threading.Thread class is created and ends when the thread is terminated or completes execution;

### The Unstarted State

- When the instance of the thread is created but the Start method is not called;

### The Ready State

- When the thread is ready to run and waiting CPU cycle;

### The Not Runnable State

- A thread is not executable, when:
  - Sleep method has been called;
  - Wait method has been called;
  - Blocked by I/O operations;

### The Dead State

- When the thread completes execution or is aborted;

## The Main Thread

- The first thread to be executed in a process is called the main thread;
- When a program starts execution, the main thread is automatically created;
- The threads created using the Thread class are called the child threads of the main thread;
- You can access a thread using the CurrentThread property of the Thread class;
- For example:

```c#
using System;
using System.Threading;

namespace MultithreadingApplication {
   class MainThreadProgram {
      static void Main(string[] args) {
         Thread th = Thread.CurrentThread;
         th.Name = "MainThread";

         Console.WriteLine("This is {0}", th.Name);
         Console.ReadKey();
      }
   }
}
```

- Returns:

```markdown
This is MainThread
```

## Methods and properties of System.Threading

- There are many;
- See all in -> <https://docs.microsoft.com/en-us/dotnet/api/system.threading?view=netframework-4.8> ;

## Creating Threads

- Threads are created by extending the Thread class;
- The extended Thread class then calls the Start() method to begin the child thread execution;
- Example:

```c#
using System;
using System.Threading;

namespace MultithreadingApplication {
   class ThreadCreationProgram {
      public static void CallToChildThread() {
         Console.WriteLine("Child thread starts");
      }
      static void Main(string[] args) {
         ThreadStart childref = new ThreadStart(CallToChildThread);
         Console.WriteLine("In Main: Creating the Child thread");
         Thread childThread = new Thread(childref);
         childThread.Start();
         Console.ReadKey();
      }
   }
}
```

- Returns:

```markdown
In Main: Creating the Child thread
Child thread starts
```

## Managing Threads

- The following example demonstrates the use of the sleep() method for making a thread pause for a specific period of time:

```c#
using System;
using System.Threading;

namespace MultithreadingApplication {
   class ThreadCreationProgram {
      public static void CallToChildThread() {
         Console.WriteLine("Child thread starts");

         // the thread is paused for 5000 milliseconds
         int sleepfor = 5000;

         Console.WriteLine("Child Thread Paused for {0} seconds", sleepfor / 1000);
         Thread.Sleep(sleepfor);
         Console.WriteLine("Child thread resumes");
      }

      static void Main(string[] args) {
         ThreadStart childref = new ThreadStart(CallToChildThread);
         Console.WriteLine("In Main: Creating the Child thread");

         Thread childThread = new Thread(childref);
         childThread.Start();
         Console.ReadKey();
      }
   }
}
```

- Returns:

```markdown
In Main: Creating the Child thread
Child thread starts
Child Thread Paused for 5 seconds
Child thread resumes
```

## Destroying Threads

- The Abort() method is used for destroying threads;
- The runtime aborts the thread by throwing a ThreadAbortException, which cannot be caught;
- Example:

```c#
using System;
using System.Threading;

namespace MultithreadingApplication {
   class ThreadCreationProgram {
      public static void CallToChildThread() {
         try {
            Console.WriteLine("Child thread starts");

            // do some work, like counting to 10
            for (int counter = 0; counter <= 10; counter++) {
               Thread.Sleep(500);
               Console.WriteLine(counter);
            }

            Console.WriteLine("Child Thread Completed");
         } catch (ThreadAbortException e) {
            Console.WriteLine("Thread Abort Exception");
         } finally {
            Console.WriteLine("Couldn't catch the Thread Exception");
         }
      }
      static void Main(string[] args) {
         ThreadStart childref = new ThreadStart(CallToChildThread);
         Console.WriteLine("In Main: Creating the Child thread");

         Thread childThread = new Thread(childref);
         childThread.Start();

         //stop the main thread for some time
         Thread.Sleep(2000);

         //now abort the child
         Console.WriteLine("In Main: Aborting the Child thread");

         childThread.Abort();
         Console.ReadKey();
      }
   }
}
```

- Returns:

```markdown
In Main: Creating the Child thread
Child thread starts
0
1
2
In Main: Aborting the Child thread
Thread Abort Exception
Couldn't catch the Thread Exception
```

## Links

- <https://www.tutorialspoint.com/csharp/csharp_multithreading.htm> ;
