# Passing arrays to functions

**Overview:**

- You can pass an array to a function as an argument;
- For example:

```c#
using System;

namespace ArrayApplication {
   class MyArray {
      double getAverage(int[] arr, int size) {
         int i;
         double avg;
         int sum = 0;

         for (i = 0; i < size; ++i) {
            sum += arr[i];
         }
         avg = (double)sum / size;
         return avg;
      }
      static void Main(string[] args) {
         MyArray app = new MyArray();

         /* an int array with 5 elements */
         int [] balance = new int[]{1000, 2, 3, 17, 50};
         double avg;

         /* pass pointer to the array as an argument */
         avg = app.getAverage(balance, 5 ) ;

         /* output the returned value */
         Console.WriteLine( "Average value is: {0} ", avg );
         Console.ReadKey();
      }
   }
}
```

- Returns:

```markdown
Average value is: 214.4
```

## Links

- <https://www.tutorialspoint.com/csharp/csharp_passing_arrays_to_functions.htm> ;
