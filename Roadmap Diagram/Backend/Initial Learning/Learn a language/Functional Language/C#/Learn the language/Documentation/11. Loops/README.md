## Loops

**Overview:**

- Used when you need to execute a block of code several number of times;
- In general, the statements are executed sequentially;

**Types of loop statements:**

- `while` loops;
- `for` loops;
- `do...while` loops;
- nested `loops`;

**While loops:**

- Executes a target statement as long as a given condition is true;
- Syntax:

```
while(condition) {
   statement(s);
}
```

- The loop iterates while the condition is true;
- When the condition becomes false, program control passes to the line immediately following the loop;

**For loops:**

- Is a repetition control structure that allows you to efficiently write a loop that needs to execute a specific number of times;
- Syntax:

```
for ( init; condition; increment ) {
   statement(s);
```

- The init step is executed first, and only once. This step allows you to declare and initialize any loop control variables. You are not required to put a statement here, as long as a semicolon appears;
- Next, the condition is evaluated. If it is true, the body of the loop is executed. If it is false, the body of the loop does not execute and flow of control jumps to the next statement just after the for loop;
- After the body of the for loop executes, the flow of control jumps back up to the increment statement. This statement allows you to update any loop control variables. This statement can be left blank, as long as a semicolon appears after the condition;
- The condition is now evaluated again. If it is true, the loop executes and the process repeats itself (body of loop, then increment step, and then again testing for a condition). After the condition becomes false, the for loop terminates;
- You can exit from a for loop by using the break keyword

**Do While loops:**

- Checks its condition at the end of the loop;
- Similar to a while loop, except that a do...while loop is guaranteed to execute at least one time;
- Syntax:

```
do {
   statement(s);
} while( condition );
```

- The conditional expression appears at the end of the loop, so the statement(s) in the loop execute once before the condition is tested;
- If the condition is true, the flow of control jumps back up to do, and the statement(s) in the loop execute again;
- This process repeats until the given condition becomes false;

**Loop Control Statements:**

- They change execution from its normal sequence;
- When execution leaves a scope, all automatic objects that were created in that scope are destroyed;
- They are:
  - **`break`** statement:
    - Terminates the loop or switch statement and transfers execution to the statement immediately following the loop or switch;
  - **`continue`** statement:
    - Causes the loop to skip the remainder of its body and immediately retest its condition prior to reiterating;

**Infinite Loops:**

- You can make infinte loops, if your condition is never false;
- Example:

```
while(true){
    // Something
}
```

**Links:**

- https://www.tutorialspoint.com/csharp/csharp_loops.htm ;
- https://www.tutorialspoint.com/csharp/csharp_while_loop.htm ;
- https://www.tutorialspoint.com/csharp/csharp_for_loop.htm ;
- https://www.tutorialspoint.com/csharp/csharp_do_while_loop.htm ;
