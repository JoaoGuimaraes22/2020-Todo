## Decision Making

**Overview:**

- Decision making structures requires the programmer to specify one or more conditions to be evaluated or tested by the program;
- Then, you code a statement or statements to be executed if the condition is determined to be true;
- And optionally, other statements to be executed if the condition is determined to be false;

**Types of conditional statements:**

- `if` statement;
- `if...else` statement;
- nested `if` statements;
- `switch` statements;
- nested `switch` statements;

**If statement:**

- Consists of a boolean expression followed by one or more statements;
- Syntax:

```
if(boolean_expression) {
   /* statement(s) will execute if the boolean expression is true */
}

```

- If the boolean expression evaluates to true, then the block of code inside the if statement is executed. If boolean expression evaluates to false, then the first set of code after the end of the if statement(after the closing curly brace) is executed;
- Can be followed by an optional else statement, which executes when the boolean expression is false;
- Syntax:

```
if(boolean_expression) {
   /* statement(s) will execute if the boolean expression is true */
} else {
   /* statement(s) will execute if the boolean expression is false */
}
```

- If the boolean expression evaluates to true, then the if block of code is executed, otherwise else block of code is executed;
- You can use one if or else if statement inside another if or else if statement(s);
- Syntax:

```
if( boolean_expression 1) {
   /* Executes when the boolean expression 1 is true */
   if(boolean_expression 2) {
      /* Executes when the boolean expression 2 is true */
   }
}
```

**Switch statements:**

- Allows a variable to be tested for equality against a list of values;
- Each value is called a case, and the variable being switched on is checked for each switch case;
- Syntax:

```
switch(expression) {
   case constant-expression1  :
      statement(s);
      break;
   case constant-expression2  :
   case constant-expression3  :
      statement(s);
      break;

   /* you can have any number of case statements */
   default : /* Optional */
   statement(s);
}
```

- The expression used in a switch statement must have an integral or enumerated type, or be of a class type in which the class has a single conversion function to an integral or enumerated type;
- You can have any number of case statements within a switch;
- The constant-expression for a case must be the same data type as the variable in the switch, and it must be a constant or a literal;
- When the variable being switched on is equal to a case, the statements following that case will execute until a break statement is reached;
- When a break statement is reached, the switch terminates, and the flow of control jumps to the next line following the switch statement;
- A switch statement can have an optional default case, which must appear at the end of the switch. The default case can be used for performing a task when none of the cases is true;

**The ? operators:**

- Can be used to replace if...else statements;
- Syntax:

```
Exp1 ? Exp2 : Exp3;
```

- The value of a ? expression is determined as follows:
  - Exp1 is evaluated, if is true, then Exp2 is evaluated and becomes the value of the entire ? expression;
  - If Exp1 is false, then Exp3 is evaluated and its value becomes the value of the expression;

**Links:**

- https://www.tutorialspoint.com/csharp/csharp_decision_making.htm ;
- https://www.tutorialspoint.com/csharp/if_statement_in_csharp.htm ;
- https://www.tutorialspoint.com/csharp/switch_statement_in_csharp.htm ;