## Param arrays

- At times, while declaring a method, you are not sure of the number of arguments passed as a parameter;
- This is where param arrays come into play;
- For example:

```
using System;

namespace ArrayApplication {
   class ParamArray {
      public int AddElements(params int[] arr) {
         int sum = 0;

         foreach (int i in arr) {
            sum += i;
         }
         return sum;
      }
   }
   class TestClass {
      static void Main(string[] args) {
         ParamArray app = new ParamArray();
         int sum = app.AddElements(512, 720, 250, 567, 889);

         Console.WriteLine("The sum is: {0}", sum);
         Console.ReadKey();
      }
   }
}
```

- Returns:

```
The sum is: 2938
```

**Links:**

- https://www.tutorialspoint.com/csharp/csharp_param_arrays.htm
