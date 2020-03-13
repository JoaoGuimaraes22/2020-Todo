## The Array Class

**Overview:**

- Is the base class for all the arrays;
- Defined in the System namespace;

**Properties of the Array class:**

- IsFixedSize:
  - Returns a bollean indicating whether the Array has a fixed size;
- IsReadOnly:
  - Returns a bollean indicating whether the Array is read-only.
- Length:
  - Gets a 32-bit integer that represents the total number of elements in all the dimensions of the Array;
- LongLength:
  - Gets a 64-bit integer that represents the total number of elements in all the dimensions of the Array;
- Rank:
  - Gets the rank (number of dimensions) of the Array;

**Methods of the Array class:**

- Clear:
  - Sets a range of elements in the Array to zero, to false, or to null, depending on the element type;
- Copy(Array, Array, Int32):
  - Copies a range of elements from an Array starting at the first element and pastes them into another Array starting at the first element;
  - The length is specified as a 32-bit integer;
- CopyTo(Array, Int32):
  - Copies all the elements of the current one-dimensional Array to the specified one-dimensional Array starting at the specified destination Array index;
  - The index is specified as a 32-bit integer;
- GetLength:
  - Gets a 32-bit integer that represents the number of elements in the specified dimension of the Array;
- GetLongLength:
  - Gets a 64-bit integer that represents the number of elements in the specified dimension of the Array;
- GetLowerBound:
  - Gets the lower bound of the specified dimension in the Array;
- GetType:
  - Gets the Type of the current instance. (Inherited from Object.);
- GetUpperBound:
  - Gets the upper bound of the specified dimension in the Array;
- GetValue(Int32):
  - Gets the value at the specified position in the one-dimensional Array;
  - The index is specified as a 32-bit integer;
- IndexOf(Array, Object):
  - Searches for the specified object and returns the index of the first occurrence within the entire one-dimensional Array;
- Reverse(Array):
  - Reverses the sequence of the elements in the entire one-dimensional Array;
- SetValue(Object, Int32):
  - Sets a value to the element at the specified position in the one-dimensional Array. The index is specified as a 32-bit integer;
- Sort(Array):
  - Sorts the elements in an entire one-dimensional Array using the IComparable implementation of each element of the Array;
- ToString:
  - Returns a string that represents the current object. (Inherited from Object.);

**All:**

- For a complete list see -> https://docs.microsoft.com/en-us/dotnet/api/system.array?view=netframework-4.8 ;

**Links:**

- https://www.tutorialspoint.com/csharp/csharp_array_class.htm ;
- https://docs.microsoft.com/en-us/dotnet/api/system.array.isfixedsize?view=netframework-4.8 ;
