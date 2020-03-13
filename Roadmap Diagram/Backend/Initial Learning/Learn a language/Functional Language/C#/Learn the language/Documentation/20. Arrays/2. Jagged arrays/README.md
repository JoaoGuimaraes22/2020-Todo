## Jagged Arrays

**Overview:**

- A jagged array is an array of arrays;
- Example:
  - `int [][] scores;`;
- Declaring an array, does not create the array in memory;
- To create one, do:

```
int[][] scores = new int[5][];
for (int i = 0; i < scores.Length; i++) {
   scores[i] = new int[4];
}
```

- You can initialize a jagged array as:

```
int[][] scores = new int[2][]{new int[]{92,93,94},new int[]{85,66,87,88}};
```

- Here, scores is an array of two arrays of integers - scores[0] is an array of 3 integers and scores[1] is an array of 4 integers;

**Example:**

```
using System;

namespace ArrayApplication {
   class MyArray {
      static void Main(string[] args) {

         /* a jagged array of 5 array of integers*/
         int[][] a = new int[][]{new int[]{0,0},new int[]{1,2},
            new int[]{2,4},new int[]{ 3, 6 }, new int[]{ 4, 8 } };
         int i, j;

         /* output each array element's value */
         for (i = 0; i < 5; i++) {
            for (j = 0; j < 2; j++) {
               Console.WriteLine("a[{0}][{1}] = {2}", i, j, a[i][j]);
            }
         }
         Console.ReadKey();
      }
   }
}
```

- Returns:

```
a[0][0]: 0
a[0][1]: 0
a[1][0]: 1
a[1][1]: 2
a[2][0]: 2
a[2][1]: 4
a[3][0]: 3
a[3][1]: 6
a[4][0]: 4
a[4][1]: 8
```

**Links:**

- https://www.tutorialspoint.com/csharp/csharp_jagged_arrays.htm ;
