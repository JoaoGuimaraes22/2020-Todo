## Regular Expressions

**Overview:**

- It's a pattern that could be matched against an input text;
- A pattern consists of one or more character literals, operators, or constructs;

**Constructs for defining regular expressions:**

- There are various categories of characters, operators, and constructs that lets you to define regular expressions, for example:
  - Character escapes;
  - Character classes;
  - Anchors;
  - Grouping constructs;
  - Quantifiers;
  - Backreference constructs;
  - Alternation constructs;
  - Substituitions;
  - Miscellaneous constructs;

**The Regex Class Methods:**

- IsMatch(string input, (optional) int startAt):
  - Indicates whether the regular expression specified in the Regex constructor finds a match in a specified input string and returns a boolean;
- IsMatch(string input, string pattern):
  - Indicates whether the specified regular expression finds a match in the specified input string;
- MatchCollection Matches(string input):
  - Searches the specified input string for all occurrences of a regular expression;
- Replace(string input, string replacement):
  - In a specified input string, replaces all strings that match a regular expression pattern with a specified replacement string;
- Split(string input):
  - Splits an input string into an array of substrings at the positions defined by a regular expression pattern specified in the Regex constructor
- See all at -> https://docs.microsoft.com/en-us/dotnet/api/system.text.regularexpressions.regex?view=netframework-4.8

**Links:**

- https://www.tutorialspoint.com/csharp/csharp_regular_expressions.htm ;
