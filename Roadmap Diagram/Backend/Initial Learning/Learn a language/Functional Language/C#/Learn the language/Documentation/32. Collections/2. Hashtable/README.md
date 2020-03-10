## Hashtable

**Overview:**

- Similar to generic Dictionary collection;
- Stores key-value pairs;
- Optimizes lookups by computing the hash code of each key and stores it in a different bucket internally and then matches the hash code of the specified key at the time of accessing values;

**Creating a Hashtable:**

- Example:
  - `Hashtable ht = new Hashtable();`;

**Properties:**

- Count:
  - Gets the number of key/value pairs;
- IsReadOnly:
  - Gets boolean value indicating whether the Hashtable is read-only;
- Item:
  - Gets or sets the element at the specified key;
- Keys:
  - Gets an ICollection of keys;
- Values:
  - Gets an ICollection of values;

**Methods:**

- Add(object key, object value):
  - Adds an item with a key and value;
- Remove(object key):
  - Removes the item with the specified key;
- Clear():
  - Removes all the items;
- Contains(object key) / ContainsKey(object key):
  - Checks whether the hashtable contains a specific key;
- ContainsValue(object value):
  - Checks whether the hashtable contains a specific value;
- GetHash(object key):
  - Returns the hash code for the specified key;

**See more:**

- See more at -> https://docs.microsoft.com/en-us/dotnet/api/system.collections.hashtable?view=netframework-4.8 ;

**Links:**

- https://www.tutorialsteacher.com/csharp/csharp-hashtable ;
- https://www.tutorialspoint.com/csharp/csharp_hashtable.htm ;
