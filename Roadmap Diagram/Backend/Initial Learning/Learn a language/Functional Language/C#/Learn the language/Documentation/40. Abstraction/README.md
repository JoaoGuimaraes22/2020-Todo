# Abstraction

## What is it

- Allows you to handle complexity by hidding unnecessary details from the user;
- Enables more complex logic on top of provided abstraction to have no need of undestanding the complexity behind it;

## Example of abstraction in CSharp

- The class manual can't be instantiated since it has the modifier abstract;
- Only the class Dog and Human can be instantiated;
- All functionality data which is generic for mammals are hidden in the Mamal class;
- The abstract method MakeASound needs to be implemented in all classes which inherits from Mammal;

```c#
using System;

public abstract class Mammal
{
 private int numberOfLegs = 0;
 private string specie = string.Empty;

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

 public abstract void MakeASound();
}

public class Dog : Mammal
{
 public Dog() : base("Dogs", 4)
 {
 }

 public override void MakeASound()
 {
  Console.WriteLine("Wuf");
 }
}

public class Human : Mammal
{
 public Human() : base("Humans", 2)
 {
 }

 public override void MakeASound()
 {
  Console.WriteLine("Hello World");
 }
}

class ExecuteAbstraction{
 static void Main(string[] args) {
        var d = new Dog();
        Console.WriteLine($"{d.Specie} has {d.NumberOfLegs} legs");
        Console.Write("The dog say: ");
        d.MakeASound();

        var h = new Human();
        Console.WriteLine($"{h.Specie} has {h.NumberOfLegs} legs");
        Console.Write("The human say: ");
        h.MakeASound();
   }
}
```

## Links

- <https://stackify.com/oop-concept-abstraction/> ;
