## Generics

**Overview:**

- Allow you to write a class or method that can work with any data type;
- A generic class can be defined using angle brackets <>;
- For example:

```
using System;
using System.Collections.Generic;

namespace GenericApplication {
   public class MyGenericArray<T> {
      private T[] array;

      public MyGenericArray(int size) {
         array = new T[size + 1];
      }
      public T getItem(int index) {
         return array[index];
      }
      public void setItem(int index, T value) {
         array[index] = value;
      }
   }
   class Tester {
      static void Main(string[] args) {

         //declaring an int array
         MyGenericArray<int> intArray = new MyGenericArray<int>(5);

         //setting values
         for (int c = 0; c < 5; c++) {
            intArray.setItem(c, c*5);
         }

         //retrieving the values
         for (int c = 0; c < 5; c++) {
            Console.Write(intArray.getItem(c) + " ");
         }

         Console.WriteLine();

         //declaring a character array
         MyGenericArray<char> charArray = new MyGenericArray<char>(5);

         //setting values
         for (int c = 0; c < 5; c++) {
            charArray.setItem(c, (char)(c+97));
         }

         //retrieving the values
         for (int c = 0; c< 5; c++) {
            Console.Write(charArray.getItem(c) + " ");
         }
         Console.WriteLine();

         Console.ReadKey();
      }
   }
}
```

- Returns:

```
0 5 10 15 20
a b c d e
```

**Features of Generics:**

- It helps you to maximize code reuse, type safety, and performance;
- You can create generic collection classes (we'll see more about this later);
- You can create your own generic interfaces, classes, methods, events, and delegates;
- You may create generic classes constrained to enable access to methods on particular data types;
- You may get information on the types used in a generic data type at run-time by means of reflection;

**Generic Methods:**

- For example:

```
using System;
using System.Collections.Generic;

namespace GenericMethodAppl {
   class Program {
      static void Swap<T>(ref T lhs, ref T rhs) {
         T temp;
         temp = lhs;
         lhs = rhs;
         rhs = temp;
      }
      static void Main(string[] args) {
         int a, b;
         char c, d;
         a = 10;
         b = 20;
         c = 'I';
         d = 'V';

         //display values before swap:
         Console.WriteLine("Int values before calling swap:");
         Console.WriteLine("a = {0}, b = {1}", a, b);
         Console.WriteLine("Char values before calling swap:");
         Console.WriteLine("c = {0}, d = {1}", c, d);

         //call swap
         Swap<int>(ref a, ref b);
         Swap<char>(ref c, ref d);

         //display values after swap:
         Console.WriteLine("Int values after calling swap:");
         Console.WriteLine("a = {0}, b = {1}", a, b);
         Console.WriteLine("Char values after calling swap:");
         Console.WriteLine("c = {0}, d = {1}", c, d);

         Console.ReadKey();
      }
   }
}
When the above code is compiled and executed, it produces the following result −

Int values before calling swap:
a = 10, b = 20
Char values before calling swap:
c = I, d = V
Int values after calling swap:
a = 20, b = 10
Char values after calling swap:
c = V, d = I
```

- Returns:

```
Int values before calling swap:
a = 10, b = 20
Char values before calling swap:
c = I, d = V
Int values after calling swap:
a = 20, b = 10
Char values after calling swap:
c = V, d = I
```

**Generic Delegates:**

- For example:

```
delegate T NumberChanger<T>(T n);
```

- Example:

```
using System;
using System.Collections.Generic;

delegate T NumberChanger<T>(T n);
namespace GenericDelegateAppl {
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
         NumberChanger<int> nc1 = new NumberChanger<int>(AddNum);
         NumberChanger<int> nc2 = new NumberChanger<int>(MultNum);

         //calling the methods using the delegate objects
         nc1(25);
         Console.WriteLine("Value of Num: {0}", getNum());

         nc2(5);
         Console.WriteLine("Value of Num: {0}", getNum());
         Console.ReadKey();
      }
   }
}
```

- Returns:

```
Value of Num: 35
Value of Num: 175
```

**Links:**

- https://www.tutorialspoint.com/csharp/csharp_generics.htm ;
- https://www.tutorialsteacher.com/csharp/csharp-generics ;
