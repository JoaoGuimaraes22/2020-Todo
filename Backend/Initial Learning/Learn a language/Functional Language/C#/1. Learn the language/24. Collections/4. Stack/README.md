# Stack

## Overview

- Stores elements in LIFO style (Last In First Out);
- Allows null value and also duplicate values;
- Provides a Push() method to add a value and Pop() or Peek() methods to retrieve values;

## Creating a Stack

- Syntax:

```c#
Stack myStack = new Stack();
```

## Properties

- Count:
  - Returns the total count of elements in the Stack;

## Methods

- Push(object obj):
  - Inserts an item at the top of the stack;
- Peek():
  - Returns the top item from the stack;
- Pop():
  - Removes and returns items from the top of the stack;
- Contains():
  - Checks whether an item exists in the stack;
- Clear():
  - Clears all the items;

## See more

- See more at -> <https://docs.microsoft.com/en-us/dotnet/api/system.collections.stack?view=netframework-4.8> ;

## Points to Remember

- Stack stores the values in LIFO (Last in First out) style. The element which is added last will be the element to come out first;
- Use the Push() method to add elements into Stack;
- The Pop() method returns and removes elements from the top of the Stack. Calling the Pop() method on the empty Stack will throw an exception;
- The Peek() method always returns top most element in the Stack;

## Links

- <https://www.tutorialsteacher.com/csharp/csharp-stack> ;
- <https://www.tutorialspoint.com/csharp/csharp_stack.htm> ;
