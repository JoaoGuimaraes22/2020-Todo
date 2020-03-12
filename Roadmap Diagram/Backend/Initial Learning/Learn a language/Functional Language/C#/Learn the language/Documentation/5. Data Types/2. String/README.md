## String

**Overview:**

- A string is a series of characters that is used to represent text;
- C# provides the String data type to store string literals:
    - `string ch = "S";`;
- A string is a collection or an array of characters;
- A string can be created using a char array or accessed like a char array;

**Special Characters:**

- A text in the real world can include any character;
- C# includes escaping character \ (backslash) before special characters to include in a string;
- Example:
```
string text = "This is a \"string\" in C#.";
string str = "xyzdef\\rabc";
string path = "\\\\mypc\\ shared\\project";
``` 
- Use @ and \ to declare a multi-line string:
```
string str = @"this is a \
multi line \
string";
```

**String Concatenation:**

- Multiple strings can be concatenated with + operator;
- Example:
```
string name = "Mr." + "James " + "Bond" + ", Code: 007";
 
string firstName = "James";
string lastName = "Bond";
string code = "007";
 
string agent = "Mr." + firstName + " " + lastName + ", Code: " + code;
```
- A String is immutable;
- It means it is read-only and cannot be changed once created in the memory;
- So, it is recommended to use StringBuilder instead of string if you concatenate more than five strings;

**String Interpolation:**

- It's a better way of concatenating strings;
- C# 6 includes a special character $ to identify an interpolated string;
- Example:
```
string firstName = "James";
string lastName = "Bond";
string code = "007";
 
string fullName = $"Mr. {firstName} {lastName}, Code: {code}";
```

**Links:**

- https://www.tutorialsteacher.com/csharp/csharp-string ;