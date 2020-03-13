## ValueTuple

**Overview:**

- Value type representation of the Tuple;
- From the System.ValueTuple package;

**ValueTuple Initialization:**

- Created and initialized using parentheses () and specifying the values between them;
- Example:

```
var person = (1, "Bill", "Gates");

//equivalent Tuple
//var person = Tuple.Create(1, "Bill", "Gates");
```

- Can also be initialized by specifying the type of each element, as shown below:

```
ValueTuple<int, string, string> person = (1, "Bill", "Gates");
person.Item1;  // returns 1
person.Item2;   // returns "Bill"
person.Item3;   // returns "Gates"
```

- The following is a short way of declaring types for each member:

```
(int, string, string) person = (1, "Bill", "Gates");
person.Item1;  // returns 1
person.Item2;   // returns "Bill"
person.Item3;   // returns "Gates"
```

**Features:**

- Tuple requires at least two values;
- Unlike Tuple, a ValueTuple can include more than eight values;
- Example:
  - `var numbers = (1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14);`;

**Named Members :**

- We can assign names to ValueTuple properties instead of having the default property names Item1, Item2 and so on;
- For example:

```
(int Id, string FirstName, string LastName) person = (1, "Bill", "Gates");
person.Id;   // returns 1
person.FirstName;  // returns "Bill"
person.LastName; // returns "Gates"
```

**ValueTuple as a Return Type:**

- The following method returns a ValueTuple:

```
static void Main(string[] args)
{
    DisplayTuple(1, "Bill", "Gates");
}

static void DisplayTuple((int, string, string) person)
{
    Console.WriteLine($"Id = { person.Item1}");
    Console.WriteLine($"First Name = { person.Item2}");
    Console.WriteLine($"Last Name = { person.Item3}");
}
```

**Deconstruction:**

- Individual members of a ValueTuple can be retrieved by deconstructing it;
- A deconstructing declaration syntax splits a ValueTuple into its parts and assigns those parts individually to fresh variables;
- For example:

```
static void Main(string[] args)
{
    // change property names
    (int PersonId, string FName, string LName) = GetPerson();
}
static (int, string, string) GetPerson()
{
    return (Id:1, FirstName: "Bill", LastName: "Gates");
}
```

- We can use var instead:

```
static void Main(string[] args)
{
    // use var as datatype
    (var PersonId, var FName, var LName) person = GetPerson();
}
static (int, string, string) GetPerson()
{
    return (Id:1, FirstName: "Bill", LastName: "Gates");
}
```

- ValueTuple also allows "discards" in deconstruction for the members you are not going to use:

```
// use discard _ for the unused member LName
(var id, var FName, _) = GetPerson();
```

**Links:**

- https://www.tutorialsteacher.com/csharp/valuetuple;
