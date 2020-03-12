## Anonymous Methods

**Overview:**

- Anonymous methods provide a technique to pass a code block as a delegate parameter;
- Are defined using the delegate keyword;
- They must be assigned to a delegate;
- Can access outer variables or functions;
- Can be passed to a method that accepts the delegate as a parameter;
- Can be used as event handlers;

**Writing an Anonymous method:**

- For example:
```
delegate void NumberChanger(int n);
...
NumberChanger nc = delegate(int x) {
   Console.WriteLine("Anonymous Method: {0}", x);
};
```

**Links:**

- https://www.tutorialspoint.com/csharp/csharp_anonymous_methods.htm ;
- https://www.tutorialsteacher.com/csharp/csharp-anonymous-method ;