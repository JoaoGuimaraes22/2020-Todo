## Ternary Operator

**Overview:**

- C# includes a special type of decision making operator '?:' called the ternary operator;

**Syntax:**

- `Boolean Expression ? First Statement : Second Statement`;
- First part (before ?) includes conditional expression that returns boolean value true or false;
- Second part (after ? and before :) contains a statement which will be returned if the conditional expression in the first part evalutes to true;
- The third part includes another statement which will be returned if the conditional expression returns false;

**Example:**

```
int x = 20, y = 10;

var result = x > y ? "x is greater than y" : "x is less than or equal to y";

Console.WriteLine(result);
```

- Returns:
  - `x is greater than y`;
- The ternary operator can return any data type;

**Links:**

- https://www.tutorialsteacher.com/csharp/csharp-ternary-operator ;
