## Funq

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
- ;

**Links:**

- https://www.tutorialsteacher.com/csharp/csharp-func-delegate;
