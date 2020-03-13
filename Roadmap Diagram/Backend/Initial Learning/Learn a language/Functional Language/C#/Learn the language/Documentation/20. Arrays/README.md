## Arrays

**Here you will learn about:**

- Arrays:
  - Multi-dimensional arrays;
  - Jagged Arrays;
  - Passing arrays to functions;
  - Param arrays;
  - The Array class;

**Overview:**

- Stores a fixed-size sequential collection of elements of the same type;
- Used to store a collection of data, but it is often more useful to think of an array as a collection of variables of the same type stored at contiguous memory locations;
- All arrays consist of contiguous memory locations;
- The lowest address corresponds to the first element and the highest address to the last element (all elements are indexed);

**Declaring arrays:**

- Syntax:
  - `datatype[] arrayName;`;
  - Where:
    - `datatype` is used to specify the type of elements in the array;
    - `[]` specifies the rank of the array, which specifies its size;
    - `arrayName` specifies the name of the array;
  - Example:
    - `double[] balance;`

**Initializing an array:**

- Array is a reference type, so you need to use the `new` keyword to create an instance of an array;
- For example:
  - `double[] balance = new double[10]`;

**Assigning values to an array:**

- You can assign values to individual array elements, by using the index number;
- Syntax:
  - `double[] balance = new double[10]`;
  - `balance[0] = 4500.0`;
- You can assign values to the array at the time of the declaration;
- Syntax:
  - `double[] balance = {2340.0, 2123.0, 3421.0}`;
- You can also create an initialize the array:
- Syntax:
  - `int[] marks = new int[4] {99, 98, 85, 53}`;
- You may also ommit the size of the array;
- Syntax:
  - `int[] marks = new int[] {99, 98, 85, 77}`;
- You can copy an array variable into another target array variable;
- Here, both the target and source point to the same memory location;
- Syntax:
  - `int [] marks = new int[] { 99, 98, 92, 97, 95};`;
  - `int[] score = marks;`;

**Accesing Array Elements:**

- An element is accessed through it's index;
- This is done by placing the index of the element within square brackets after the name of the array;
- Syntax:
  - `double salary = balance[9]`;
- For example:

```
using System;

namespace ArrayApplication {
   class MyArray {
      static void Main(string[] args) {
         int []  n = new int[10]; /* n is an array of 10 integers */
         int i,j;

         /* initialize elements of array n */
         for ( i = 0; i < 10; i++ ) {
            n[ i ] = i + 100;
         }

         /* output each array element's value */
         for (j = 0; j < 10; j++ ) {
            Console.WriteLine("Element[{0}] = {1}", j, n[j]);
         }
         Console.ReadKey();
      }
   }
}
```

- Returns:

```
Element[0] = 100
Element[1] = 101
Element[2] = 102
Element[3] = 103
Element[4] = 104
Element[5] = 105
Element[6] = 106
Element[7] = 107
Element[8] = 108
Element[9] = 109
```

**Using the `foreach` loop:**

- You can also use a `foreach` statement to iterate through an array;
- For example:

```
using System;

namespace ArrayApplication {
   class MyArray {
      static void Main(string[] args) {
         int []  n = new int[10]; /* n is an array of 10 integers */

         /* initialize elements of array n */
         for ( int i = 0; i < 10; i++ ) {
            n[i] = i + 100;
         }

         /* output each array element's value */
         foreach (int j in n ) {
            int i = j-100;
            Console.WriteLine("Element[{0}] = {1}", i, j);
         }
         Console.ReadKey();
      }
   }
}
```

- Returns:

```
Element[0] = 100
Element[1] = 101
Element[2] = 102
Element[3] = 103
Element[4] = 104
Element[5] = 105
Element[6] = 106
Element[7] = 107
Element[8] = 108
Element[9] = 109
```

**Array Concepts:**

- There are following few important concepts related to array which should be clear to a C# programmers:
  - Multi-dimensional arrays;
  - Jagged arrays;
  - Passing arrays to functions;
  - Param arrays;
  - The Array class;

**Links:**

- https://www.tutorialspoint.com/csharp/csharp_arrays.htm
