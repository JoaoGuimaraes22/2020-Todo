## SortedList

**Overview:**

- Stores key-value pairs in the ascending order of key by default;
- A sorted list is a combination of an array and a hash table;
- Contains a list of items that can be accessed using a key or an index;

**Creating a SortedList:**

- Example:
  - `SortedList sortedList1 = new SortedList();`;

**Properties:**

- Capacity:
  - Gets or sets the number of elements that the SortedList can contain;
- Count:
  - Gets the number of elements actually contained in the SortedList;
- IsFixedSize:
  - Gets a value indicating whether the SortedList has a fixed size;
- IsReadOnly:
  - Gets a value indicating whether the SortedList is read-only;
- Item:
  - Gets or sets the element at the specified key;
- Keys:
  - Gets list of keys;
- Values:
  - Gets list of values;

**Methods:**

- Add(object key, object value)):
  - Add key-value pairs;
- Remove(object key):
  - Removes element with specified key;
- RemoveAt(int index):
  - Removes the element at the specified index;
- Contains(object key):
  - Checks whether specified key exists or not;
  - Returns true if exists otherwise false;
- Clear():
  - Removes all the elements;
- GetByIndex(int index):
  - Returns the value by index stored in internal array;
- GetKey(int index):
  - Returns the key stored at specified index in internal array;
- IndexOfKey(object key):
  - Returns an index of specified key stored in internal array;
- IndexOfValue(object value):
  - Returns an index of specified value stored in internal array;

**See more:**

- See more in -> https://docs.microsoft.com/en-us/dotnet/api/system.collections.sortedlist?view=netframework-4.8 ;

**Links:**

- https://www.tutorialsteacher.com/csharp/csharp-sortedlist ;
- https://www.tutorialspoint.com/csharp/csharp_sortedlist.htm ;
