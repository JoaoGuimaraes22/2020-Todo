## StringBuilder

**Overview:**

- A String is immutable, meaning String cannot be changed once created;
- To solve this problem, StringBuilder is a dynamic object that allows you to expand the number of characters in the string;

**StringBuilder Initialization:**

- Syntax:
```
StringBuilder sb = new StringBuilder();
            
//or

StringBuilder sb = new StringBuilder("Hello World!!");
```
- You can give an initial capacity of characters by passing an int value in the constructor;

**Important Methods of StringBuilder:**

- StringBuilder.Append(valueToAppend):
  - Appends the passed values to the end of the current StringBuilder object;
- StringBuilder.AppendFormat():
  - Replaces a format specifier passed in a string with formatted text;
- StringBuilder.Insert(index, valueToAppend):
  - Inserts a string at the specified index of the current StringBuilder object;
- StringBuilder.Remove(int startIndex, int length):
  - Removes the specified number of characters from the given starting position of the current StringBuilder object;
- StringBuilder.Replace(oldValue, newValue):
  - Replaces characters with new characters;

**ToString():**

- Use the `.ToString()` method to get a string of a StringBuilder;

**Points to Remember:**

- StringBuilder is mutable;
- StringBuilder performs faster than string when appending multiple string values;
- Initialize StringBuilder as class e.g. `StringBuilder sb = new StringBuilder()`;
- Use StringBuilder when you need to append more than three or four strings;
- Use Append() method to add or append strings with StringBuilder.;
- Use ToString() method to get the string from StringBuilder;

**Links:**

- https://www.tutorialsteacher.com/csharp/csharp-stringbuilder ;