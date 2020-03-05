## Inheritance

**What is it:**

- It's a mechanism where you can derive a class from another class for a hierarchy of classes that share a set of attributes and methods;
- You can use it to add custom logic to existing frameworks, or map your domain model to a database, for example;

**Example of inheritance in C#:**

- Here, the species dog and human is in the functionality of the mammal, and modifies the two parameters legs and specie;

```
using System;

public class Mammal
{
	private int numberOfLegs = 0;
	private string specie = string.Empty;

    public Mammal(){
		specie = "Unknown";
	}

	public Mammal(string specie, int numberOfLegs)
	{
		this.numberOfLegs = numberOfLegs;
		this.specie = specie;
	}

	public int NumberOfLegs
	{
		get
		{
			return numberOfLegs;
		}
	}

	public string Specie
	{
		get
		{
			return specie;
		}
	}
}

public class Dog : Mammal
{
	public Dog() : base("Dogs", 4)
	{
	}
}

public class Human : Mammal
{
	public Human() : base("Humans", 2)
	{
	}
}

class ExecuteInheritance {
	static void Main(string[] args) {
        var m = new Mammal();
		Console.WriteLine($"{m.Specie} has {m.NumberOfLegs} legs");

        var d = new Dog();
        Console.WriteLine($"{d.Specie} has {d.NumberOfLegs} legs");

        var h = new Human();
        Console.WriteLine($"{h.Specie} has {h.NumberOfLegs} legs");
   }
}

```

**Links:**

- https://stackify.com/oop-concept-inheritance/ ;
