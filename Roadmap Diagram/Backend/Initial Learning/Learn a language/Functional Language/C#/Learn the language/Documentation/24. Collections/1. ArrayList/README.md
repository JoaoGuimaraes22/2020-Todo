## ArrayList

**Overview:**

- Can contain elements of any data types;
- It is similar to an array, except that it grows automatically as you add items in it;
- You don't need to specify the size of ArrayList;
- Implements IEnumerable, ICollection and IList interfaces;

**Creating an ArrayList:**

- Example:
  - `ArrayList myArryList = new ArrayList();`;

**Properties of ArrayList:**

- Capacity:
  - Gets or sets the number of elements that the ArrayList can contain;
- Count:
  - Gets the number of elements actually contained in the ArrayList;
- IsFixedSize:
  - Gets a value indicating whether the ArrayList has a fixed size;
- IsReadOnly:
  - Gets a value indicating whether the ArrayList is read-only;
- Item:
  - Gets or sets the element at the specified index;

**Methods:**

- Add(object value) / AddRange(ICollection c):
  - Adds single elements at the end / Adds all the elements from the specified collection;
- Insert(int index, object value) / InsertRange(int index, ICollection c):
  - Insert single elements at the specified index / Insert all the elements of the specified collection starting from specified index;
- Remove(object obj) / RemoveRange(int index, int count):
  - Removes the specified element / Removes a range of elements;
- RemoveAt(int index):
  - Removes the element at the specified index;
- Sort():
  - Sorts entire elements;
- Reverse():
  - Reverses the order of the elements;
- Contains():
  - Checks whether specified element exists or not;
  - Returns true if exists otherwise false;
- Clear():
  - Removes all the elements;
- CopyTo():
  - Copies all the elements or range of elements to compitible Array;
- GetRange():
  - Returns specified number of elements from specified index;
- IndexOf(object i):
  - Search specified element and returns zero based index if found;
  - Returns -1 if element not found;
- ToArray():
  - Returns compitible array from an ArrayList;

**See more:**

- See more in -> https://docs.microsoft.com/en-us/dotnet/api/system.collections.arraylist?view=netframework-4.8 ;

**Points to Remember:**

- ArrayList can store items(elements) of any datatype;
- ArrayList resizes automatically as you add the elements;
- ArrayList values must be cast to appropriate data types before using it;
- ArrayList can contain multiple null and duplicate items;
- ArrayList can be accessed using foreach or for loop or indexer;
- Use Add(), AddRange(), Remove(), RemoveRange(), Insert(), InsertRange(), Sort(), Reverse() methods;

**Links:**

- https://www.tutorialspoint.com/csharp/csharp_arraylist.htm ;
- https://www.tutorialsteacher.com/csharp/csharp-arraylist ;
