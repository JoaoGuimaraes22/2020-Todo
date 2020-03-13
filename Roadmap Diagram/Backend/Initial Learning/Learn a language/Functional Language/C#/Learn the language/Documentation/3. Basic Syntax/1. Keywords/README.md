## Keywords

**Overview:**

- C# contains reserved words, that have special meaning for the compiler, and these cannot be used as names identifiers for variables;

**Modifier Keywords:**

- Modifiers allow or prevent certain parts of programs from being modified by other parts;
- abstract;
- async;
- const;
- event;
- extern;
- new;
- override;
- partial;
- readonly;
- sealed;
- static;
- unsafe;
- virtual;
- volatile;

**Access Modifier Keywords:**

- Define the accessibility of the class and its members:
  - public:
    - Allows any part of the program in the same assembly or another assembly to access the type and its members;
  - private:
    - Restricts other parts of the program from accessing the type and its members. Only code in the same class or struct can access it;
  - internal:
    - Allows other program code in the same assembly to access the type or its members. This is default access modifiers if no modifier is specified;
  - protected:
    - Allows codes in the same class or a class that derives from that class to access the type or its members;

**Statement Keywords:**

- Related to program flow:
  - if;
  - else;
  - switch;
  - case;
  - do;
  - for;
  - foreach;
  - in;
  - while;
  - break;
  - continue;
  - default;
  - goto;
  - return;
  - yield;
  - throw;
  - try;
  - catch;
  - finnaly;
  - checked;
  - unchecked;
  - fixed;
  - lock;

**Method Parameter Keywords:**

- These keywords are applied on the parameters of a method:
  - params;
  - ref;
  - out;

**Namespace Keywords:**

- These keywords are applied with namespace and related operators:
  - using;
  - . operator;
  - :: operator;
  - extern alias,

**Operator Keywords:**

- These keywords are applied with namespace and related operators:
  - as;
  - await;
  - is;
  - new;
  - sizeof;
  - typeof;
  - stackalloc;
  - checked;
  - unchecked;

**Access Keywords:**

- Access keywords are used to access the containing class or the base class of an object or class:
  - base;
  - this;

**Literal Keywords:**

- Literal keywords apply to the current instance or value of an object:
  - null;
  - false;
  - true;
  - value;
  - void;

**Type Keywords:**

- Type keywords are used for data types:
  - bool;
  - byte;
  - char;
  - class;
  - decimal;
  - double;
  - enum;
  - float;
  - int;
  - long;
  - sbyte;
  - short;
  - string;
  - struct;
  - uint;
  - ulong;
  - ushort;

**Contextual Keywords:**

- Contextual keywords are considered as keywords, only if used in certain contexts;
- They are not reserved and so can be used as names or identifiers:
  - add;
  - var;
  - dynamic;
  - global;
  - set;
  - value;

**Query Keywords:**

- Query keywords are contextual keywords used in LINQ queries:
  - from;
  - where;
  - select;
  - group;
  - into;
  - orderby;
  - join;
  - let;
  - in;
  - on;
  - equals;
  - by;
  - ascending;
  - descending;

**Points to remember:**

- Keywords are reserved words that cannot be used as name or identifier;
- Prefix '@' with keywords if you want to use it as identifier;
- C# includes various categories of keywords e.g. modifier keywords, access modifiers keywords, statement keywords, method param keywords etc;
- Contextual keywords can be used as identifier;

**Links:**

- https://www.tutorialsteacher.com/csharp/csharp-keywords ;
