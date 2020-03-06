## Strings

**Overview:**

- You can use strings as array of characters;
- However, more common practice is to use the string keyword to declare a string variable;
- The string keyword is an alias for the System.String class;

**Creating a String object:**

- You can create string object using one of the following methods:
  - Assigning a string literal to a String variable;
  - Using a String class constructor;
  - Using the string concatenation operator (+);
  - Retrieving a property or calling a method that returns a string;
  - Calling a formatting method to convert a value or an object to its string representation;
- For example:

```
using System;

namespace StringApplication {

   class Program {

      static void Main(string[] args) {
         //from string literal and string concatenation
         string fname, lname;
         fname = "Rowan";
         lname = "Atkinson";

         char []letters= { 'H', 'e', 'l', 'l','o' };
         string [] sarray={ "Hello", "From", "Tutorials", "Point" };

         string fullname = fname + lname;
         Console.WriteLine("Full Name: {0}", fullname);

         //by using string constructor { 'H', 'e', 'l', 'l','o' };
         string greetings = new string(letters);
         Console.WriteLine("Greetings: {0}", greetings);

         //methods returning string { "Hello", "From", "Tutorials", "Point" };
         string message = String.Join(" ", sarray);
         Console.WriteLine("Message: {0}", message);

         //formatting method to convert a value
         DateTime waiting = new DateTime(2012, 10, 10, 17, 58, 1);
         string chat = String.Format("Message sent at {0:t} on {0:D}", waiting);
         Console.WriteLine("Message: {0}", chat);
      }
   }
}
```

- Returns:

```
Full Name: RowanAtkinson
Greetings: Hello
Message: Hello From Tutorials Point
Message: Message sent at 5:58 PM on Wednesday, October 10, 2012
```

**Properties of the String Class:**

- Chars:
  - Gets the Char object at a specified position in the current String object;
- Length:
  - Gets the number of characters in the current String object;

**Methods of the String Class:**

- Compare(string strA, string strB):
  - Compares two specified string objects and returns an integer that indicates their relative position in the sort order;
- Compare(string strA, string strB, bool ignoreCase ):
  - Compares two specified string objects and returns an integer that indicates their relative position in the sort order;
  - However, it ignores case if the Boolean parameter is true;
- Concat(string str0, string str1, string str2, ...):
  - Concatenates string objects.;
- Contains(string value):
  - Returns a bollean indicating whether the specified String object occurs within this string;
- Copy(string str):
  - Creates a new String object with the same value as the specified string;
- CopyTo(int sourceIndex, char[] destination, int destinationIndex, int count):
  - Copies a specified number of characters from a specified position of the String object to a specified position in an array of Unicode characters;
- EndsWith(string value):
  - Determines whether the end of the string object matches the specified string and returns a boolean;
- Equals(string value, string b):
  - Determines whether the current String object and the specified String object have the same value and returns a boolean;
- Format(string format, Object argo0):
  - Replaces one or more format items in a specified string with the string representation of a specified object;
- IndexOf((char value or string value or char[] value), (optional) int startIndex):
  - Returns the zero-based index of the first occurrence of the specified value in the current string;
  - Optionally, starting search at the specified character position;
- Insert(int startIndex, string value):
  - Returns a new string in which a specified string is inserted at a specified index position in the current string object;
- IsNullOrEmpty(string value):
  - Indicates whether the specified string is null or an Empty string and returns a boolean;
- Join(string separator, params string[] value):
  - Concatenates all the elements of a string array, using the specified separator between each element;
- LastIndexOf((char value or string value)):
  - Returns the zero-based index position of the last occurrence of the specified Unicode character or string within the current string object;
- Remove(int startIndex, (optional) int count):
  - Removes the specified number of characters in the current string beginning at a specified position and returns the string;
- Replace((char oldChar or string oldString) , (char newChar or string newString)):
  - Replaces all occurrences of a specified Unicode character or string in the current string object with the specified Unicode character or string and returns the new string;
- Split(char[] seperator, int count):
  - Returns a string array that contains the substrings in the current string object, delimited by elements of a specified Unicode character array;
- StartsWith(string value):
  - Determines whether the beginning of this string instance matches the specified string and returns a boolean;
- ToCharArray():
  - Returns a Unicode character array with all the characters in the current string object;
- ToCharArray(int startIndex, int length):
  - Returns a Unicode character array with all the characters in the current string object, starting from the specified index and up to the specified length;
- ToLower():
  - Returns a copy of this string converted to lowercase;
- ToUpper():
  - Returns a copy of this string converted to uppercase;
- Trim():
  - Removes all leading and trailing white-space characters from the current String object;

**See all:**

- See all in -> https://docs.microsoft.com/en-us/dotnet/api/system.string?view=netframework-4.8 ;

**Links:**

- https://www.tutorialspoint.com/csharp/csharp_strings.htm ;
