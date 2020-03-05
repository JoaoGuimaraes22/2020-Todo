## Encapsulation

- It's the bundling of data and methods that operate on that data in one unit;
- Often used to hide the values or state of a structured data object inside a class;
- Publicly accessible methods are generally provided in the class (so-called `getters` and `setters`), to access the values;

**Example of encapsulation in C#:**

- The class Counter, has the inner state counterValue which is hidden for the outside and can only be modified by the methods CountUp and CountDown;

```
using System;

public class Counter
{
	private int counterValue = 0;

	public void CountUp()
	{
		counterValue++;
	}

	public void CountDown()
	{
		counterValue--;
	}

	public int GetCounterValue()
	{
		return counterValue;
	}
}

class ExecuteEncapsulation {
	static void Main(string[] args) {
        var c = new Counter();
        Console.WriteLine(c.GetCounterValue()); //Expected 0
        c.CountUp(); // value wil be increased to: 1
        c.CountUp(); // value wil be increased to: 2
        Console.WriteLine(c.GetCounterValue()); //Expected 2
        c.CountDown(); // value wil be decreased to: 1
        Console.WriteLine(c.GetCounterValue()); //Expected 1
   }
}


```

**Links:**

- https://stackify.com/oop-concept-for-beginners-what-is-encapsulation/ ;
- https://en.wikipedia.org/wiki/Encapsulation_(computer_programming) ;
