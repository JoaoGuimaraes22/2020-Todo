## Dictionary<TKey, TValue>

**Overview:**

- It's a collection of Keys and Values;

**Creating a Dictionary<TKey, TValue>:**

- `Dictionary<int, string> dict = new Dictionary<int, string>();`;

**Properties:**

- Count:
  - Returns the total number of elements;
- IsReadOnly:
  - Returns a boolean indicating whether the Dictionary<TKey,TValue> is read-only;
- Item:
  - Gets or sets the element with the specified key;
- Keys:
  - Returns collection of keys;
- Values:
  - Returns collection of values;

**Methods:**

- Add(TKey, TValue):
  - Adds the specified key and value;
- Remove(TKey):
  - Removes the value with the specified key;
- ContainsKey(TKey):
  - Checks whether the specified key exists;
- ContainsValue(TValue):
  - Checks whether the specified value exists;
- Clear():
  - Removes all the elements;
- TryGetValue(TKey, TValue):
  - Tries to get the value associated with the specified key, if can't returns false;

**See more:**

- See more at -> https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.dictionary-2?view=netframework-4.8 ;

**Points to Remember:**

- A Dictionary stores Key-Value pairs where the key must be unique;
- Before adding a KeyValuePair into a dictionary, check that the key does not exist using the ContainsKey() method;
- Use the TryGetValue() method to get the value of a key to avoid possible runtime exceptions;
- Use a foreach or for loop to iterate a dictionary;
- Use dictionary indexer to access individual item;
- Use custom class that derives IEqualityComparer to compare object of custom class with Contains() method;

**Links:**

- https://www.tutorialsteacher.com/csharp/csharp-dictionary ;
