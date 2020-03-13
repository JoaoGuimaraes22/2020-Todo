## Delegates

**Overview:**

- A delegate is like a pointer to a function;
- Is a reference type variable that holds the reference to a method;
- Used for implementing events and the call-back methods;
- Derived from the System.Delegate class;

**Declaring Delegates:**

- Delegate declaration determines the methods that can be referenced by the delegate;
- For example:
  - `public delegate int MyDelegate (string s);`;
- Syntax:
  - `<access modifier> delegate <return type> <delegate_name>(<parameters>)`;

**Instantiating Delegates:**

- A delegate object must be created with the new keyword and be associated with a particular method;
- For example:

```
public delegate void printString(string s);
...
printString ps1 = new printString(WriteToScreen);
printString ps2 = new printString(WriteToFile);
```

- Example:

```
class Program
{
    // declare delegate
    public delegate void Print(int value);

    static void Main(string[] args)
    {
        // Print delegate points to PrintNumber
        Print printDel = PrintNumber;
        
        // or
        // Print printDel = new Print(PrintNumber);
            
        printDel(100000);
        printDel(200);

        // Print delegate points to PrintMoney
        printDel = PrintMoney;

        printDel(10000);
        printDel(200);
    }

    public static void PrintNumber(int num)
    {
        Console.WriteLine("Number: {0,-12:N0}",num);
    }

    public static void PrintMoney(int money)
    {
        Console.WriteLine("Money: {0:C}", money);
    }
}
```

- Returns:

```
Number: 10,000
Number: 200
Money: $ 10,000.00
Money: $ 200.00
```

**Multicasting of a Delegate:**

- Delegate objects can be composed using the "+" operator;
- A composed delegate calls the two delegates it was composed from;
- Using this property of delegates you can create an invocation list of methods that will be called when a delegate is invoked;
- For example:

```
using System;

delegate int NumberChanger(int n);
namespace DelegateAppl {
   class TestDelegate {
      static int num = 10;

      public static int AddNum(int p) {
         num += p;
         return num;
      }
      public static int MultNum(int q) {
         num *= q;
         return num;
      }
      public static int getNum() {
         return num;
      }
      static void Main(string[] args) {
         //create delegate instances
         NumberChanger nc;
         NumberChanger nc1 = new NumberChanger(AddNum);
         NumberChanger nc2 = new NumberChanger(MultNum);

         nc = nc1;
         nc += nc2;

         //calling multicast
         nc(5);
         Console.WriteLine("Value of Num: {0}", getNum());
         Console.ReadKey();
      }
   }
}
```

- Returns:

```
Value of Num: 75
```

**Using delegates:**

- Example:

```
using System;
using System.IO;

namespace DelegateAppl {

   class PrintString {
      static FileStream fs;
      static StreamWriter sw;

      // delegate declaration
      public delegate void printString(string s);

      // this method prints to the console
      public static void WriteToScreen(string str) {
         Console.WriteLine("The String is: {0}", str);
      }

      //this method prints to a file
      public static void WriteToFile(string s) {
         fs = new FileStream("c:\\message.txt",
         FileMode.Append, FileAccess.Write);
         sw = new StreamWriter(fs);
         sw.WriteLine(s);
         sw.Flush();
         sw.Close();
         fs.Close();
      }

      // this method takes the delegate as parameter and uses it to
      // call the methods as required
      public static void sendString(printString ps) {
         ps("Hello World");
      }

      static void Main(string[] args) {
         printString ps1 = new printString(WriteToScreen);
         printString ps2 = new printString(WriteToFile);
         sendString(ps1);
         sendString(ps2);
         Console.ReadKey();
      }
   }
}
```

- Returns:

```
The String is: Hello World
```

**Points to remember:**

- Delegate is a function pointer. It is reference type data type;
- Syntax: public delegate void <function name>(<parameters>);
- A method that is going to assign to delegate must have same signature as delegate;
- Delegates can be invoke like a normal function or Invoke() method;
- Multiple methods can be assigned to the delegate using "+" operator. It is called multicast delegate;


**Links:**

- https://www.tutorialspoint.com/csharp/csharp_delegates.htm ;
- https://www.tutorialsteacher.com/csharp/csharp-delegates ;
