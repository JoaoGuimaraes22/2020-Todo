# Multi-dimensional arrays

## Overview

- Multi-dimensional arrays are also called rectangular arrays;
- Syntax for creating a 2 dimensional string array:
  - `string [,] names;`;
- Syntax for creating a 3 dimensional int array:
  - `int [ , , ] m;`;
- And so on and so on, you get the gist of it;

## Two-Dimensional Arrays

- A 2-dimensional array is a list of one-dimensional arrays;
- A 2-dimensional array can be thought of as a table, which has x number of rows and y number of columns;
- For example:
  ![2 Dimensional Array Image](https://github.com/JoaoGuimaraes22/2020-Todo/blob/master/Images/Backend/Initial%20Learning/Learn%20a%20language/Functional%20Language/C%23/1.20.1.two_dimensional_arrays-min.jpg)
- Here, every element in the array a is identified by an element name of the form a[ i , j ], where a is the name of the array, and i and j are the subscripts that uniquely identify each element in array a;

## Initializing two-dimensional arrays

- May be initialized by specifying bracketed values for each row;
- For example:

```c#
int [,] a = new int [3,4] {
   {0, 1, 2, 3} ,   /*  initializers for row indexed by 0 */
   {4, 5, 6, 7} ,   /*  initializers for row indexed by 1 */
   {8, 9, 10, 11}   /*  initializers for row indexed by 2 */
};
```

## Accessing two-dimensional arrays

- Accessed by using the subscripts, row and collumn index of the array;
- Syntax:
  - `int val = a[2,3];`;
- Example:

```c#
using System;

namespace ArrayApplication {
   class MyArray {
      static void Main(string[] args) {
         /* an array with 5 rows and 2 columns*/
         int[,] a = new int[5, 2] {{0,0}, {1,2}, {2,4}, {3,6}, {4,8} };
         int i, j;

         /* output each array element's value */
         for (i = 0; i < 5; i++) {

            for (j = 0; j < 2; j++) {
               Console.WriteLine("a[{0},{1}] = {2}", i, j, a[i,j]);
            }
         }
         Console.ReadKey();
      }
   }
}
```

- Returns:

```markdown
a[0,0]: 0
a[0,1]: 0
a[1,0]: 1
a[1,1]: 2
a[2,0]: 2
a[2,1]: 4
a[3,0]: 3
a[3,1]: 6
a[4,0]: 4
a[4,1]: 8
```

## Links

- <https://www.tutorialspoint.com/csharp/csharp_multi_dimensional_arrays.htm> ;
