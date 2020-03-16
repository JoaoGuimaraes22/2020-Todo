# Fibonacci Scale

## Overview

- In Agile software development, the Fibonacci scale consists of a sequence of numbers used for estimating the relative size of user stories in points;
- The Fibonacci sequence consists of numbers that are the summation of the two preceding numbers, starting with [0, 1];
- Agile uses the Fibonacci sequence to achieve better results by reducing complexity, effort, and doubt when determining the development time required for a task, which can range from a few minutes to several weeks;

## Procedure

- It is easier to determine the relative complexity of a task rather than figuring out how much time it requires;
- As such, a revised Fibonacci scale is used in terms of points to estimate the work, as opposed to the traditional measurement of time;
- There are different methods to calculate story points;
- Giving each member the opportunity to think individually reduces pressure and may result in a more accurate representation of the feature’s size;

### The Planning Poker Method

- The Product Owner sits down with the team to estimate the user stories;
- Each member estimates a number on the Fibonacci scale that he/she believes represents the size of the task;
- All members are ordered to disclose their number at once;
- Any differences in the numbers will be followed by a discussion until a consensus is reached;
- Each user story is added to a bucket which represents the corresponding point on the Fibonacci scale;
- The steps above are repeated for all user stories;
- The buckets are added to the backlog;

### The Two Pass Relative Sizing Method

- Also known as the Steve Bockman Method and the Team Estimation Game;
- The product manager sits down with the team to estimate a project's worth of user stories, which are provided to the team in a stack of 3x5 or 4x6 cards;
- The first team member reads the first card and places it on the table, passing the remaining stack to the next team member;
- The second team member reads the second card, may declare a belief that the story is larger or smaller than the card already on the table or may ask the team for help in so determining, and establishes which direction is smaller or larger by placing the card to the left or right of the first card; and passes the remaining stack to the next team member;
- The third team member has a choice: to move the position of the second card; or to read the third card, declare a belief that the story is larger than the first two, smaller than the first two; or belongs between the first two; and passes the remaining stack to the next team member;
- When all the cards are on the table - if the product manager truly provided a project's worth, then there are likely 60 or 100 or 130 cards and the team has had to "snake" them to fit them all - then the team begins with the smallest story and assigns it a "1", continuing to assign "1"s to subsequent stories until they see an obvious jump to "2"s, and then to "3"s, "5"s, "8"s, and so on. With the result that the "snake" of cards is now numbered from the smallest story, a "1", to the largest epic, a "100";

## Significance

- People estimate user stories with smaller points more accurately than user stories that have higher costs associated with them;
- As the numbers increase, the difference between two succeeding numbers increases exponentially and leads to less accurate estimates;
  - Using Fibonacci series is helpful in this scenario because the larger user stories (i.e. stories of size greater than 8) that tend to lead to inconsistent estimates between each team member can be grouped to the nearest estimated Fibonacci number of the corresponding bucket in the backlog;
  - In case of small user stories the bucket difference is small and hence the final cost of resource and time can be finalized more accurately;
- An advantage of Fibonacci sequence is that it allows developers to disaggregate a user story from one large bucket into two preceding buckets (since a bucket is formed by adding the size of two preceding buckets);
- This process helps to create optimal user stories;

## Links

- <https://en.wikipedia.org/wiki/Fibonacci_scale_(agile)> ;
