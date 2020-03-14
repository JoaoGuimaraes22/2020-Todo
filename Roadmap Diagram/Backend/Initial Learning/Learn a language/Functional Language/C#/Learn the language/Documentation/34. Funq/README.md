## Funq Delegate

**Overview:**

- C# 3.0 includes built-in generic delegate types Func and Action, so that you don't need to define custom delegates;

**Func:**

- It's a generic delegate included in the System namespace;
- Has zero or more input parameters and one out parameters;
- For example:

```
namespace System
{
    public delegate TResult Func<in T, out TResult>(T arg);
}
```

- For example, here is one where it takes two input parameters of int type and returns a value of int type:
  - `Func<int, int, int> sum;`;
- You can assign any method to the above func delegate that takes two int parameters and returns an int value;
- Can include 0 to 16 input parameters of different types;
- However, it must include one out parameter for result;

**Func with an Anonymous Method:**

- You can assign an anonymous method to the Func delegate by using the delegate keyword;
- Example:

```
Func<int> getRandomNumber = delegate()
                            {
                                Random rnd = new Random();
                                return rnd.Next(1, 100);
                            };
```

**Funq with Lambda Expression:**

- A Func delegate can also be used with a lambda expression;
- Example:

```
Func<int> getRandomNumber = () => new Random().Next(1, 100);

//Or

Func<int, int, int>  Sum  = (x, y) => x + y;
```

**Points to Remember:**

- Func is built-in delegate type;
- Func delegate type must return a value;
- Func delegate type must return a value;
- Func delegate does not allow ref and out parameters;
- Func delegate type can be used with an anonymous method or lambda expression;

**Links:**

- https://www.tutorialsteacher.com/csharp/csharp-func-delegate;
