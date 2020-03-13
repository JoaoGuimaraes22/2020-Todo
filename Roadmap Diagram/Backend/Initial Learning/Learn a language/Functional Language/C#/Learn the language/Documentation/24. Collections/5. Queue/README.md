## Queue

**Overview:**

- Stores the elements in FIFO style (First In First Out);
- Contains the elements in the order they were added;
- Allows multiple null and duplicate values;
- Use the Enqueue() method to add values and the Dequeue() method to retrieve the values from the Queue;

**Creating a Queue:**

- `Queue queue = new Queue();`;

**Properties:**

- Count:
  - Returns the total count of elements in the Queue;

**Methods:**

- Enqueue(object obj):
  - Adds an item;
- Dequeue():
  - Removes and returns an item from the beginning of the queue;
- Peek()
  - Returns the first item;
- Contains(object obj):
  - Checks whether an item is in the queue or not;
- Clear():
  - Removes all the items;
- TrimToSize():
  - Sets the capacity of the queue to the actual number of items in the queue;

**See more:**

- See more at -> https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.queue-1?view=netframework-4.8 ;

**Points to Remember:**

- The Queue stores the values in FIFO (First in First out) style. The element which is added first will come out First;
- Use the Enqueue() method to add elements into Queue;
- The Dequeue() method returns and removes elements from the beginning of the Queue. Calling the Dequeue() method on an empty queue will throw an exception;
- The Peek() method always returns top most element;

**Links:**

- https://www.tutorialspoint.com/csharp/csharp_queue.htm ;
- https://www.tutorialsteacher.com/csharp/csharp-queue ;
