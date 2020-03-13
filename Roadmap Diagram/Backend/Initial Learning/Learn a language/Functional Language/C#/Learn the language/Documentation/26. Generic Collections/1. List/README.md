## List<T>

**Overview:**

- Stores the elements in FIFO style (First In First Out)The List<T> collection is the same as an ArrayList except that List<T> is a generic collection whereas ArrayList is a non-generic collection;

**Creating a List<T>:**

- `List<int> intList = new List<int>();`;

**Properties:**

- Items:
  - Gets or sets the element at the specified index;
- Count:
  - Returns the total number of elements;

**Methods:**

- Add(T) / AddRange(IEnumarable T):
  - Adds an element / collection at the end;
- BinarySearch(T):
  - Search the element and returns an index of the element;
- Clear():
  - Removes all the elements;
- Contains(T):
  - Checks whether the speciied element exists or not;
- Find(Predictate<T>):
  - Finds the first element based on the specified predicate function;
- Foreach(Action<T>):
  - Iterates through a List<T>;
- Insert(int index, T) / InsertRange(int index, IEnumerable<T>):
  - Inserts an element / elements at the specified index;
- Remove(T) / RemoveRange(Predictate<T>):
  - Removes the element / elements;
- RemoveAt(int index):
  - Removes the elemente at specified index;
- Sort():
  - Sorts all of the elements;
- TrimExcess():
  - Sets the capacity to the actual number of elements;
- TrueForAll(Predictate<T>):
  - Determines whether every element in theÂ List<T> matches the conditions defined by the specified predicate;

**See more:**

- See more at -> https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.list-1?view=netframework-4.8#constructors ;

**Points to remember:**

- List<T> stores elements of the specified type and it grows automatically;
- List<T> can store multiple null and duplicate elements;
- List<T> can be assigned to IList<T> or List<T> type of variable. It provides more helper method When assigned to List<T> variable;
- List<T> can be access using indexer, for loop or foreach statement;
- LINQ can be use to query List<T> collection;
- List<T> is ideal for storing and retrieving large number of elements;

**Links:**

- https://www.tutorialsteacher.com/csharp/csharp-list ;
