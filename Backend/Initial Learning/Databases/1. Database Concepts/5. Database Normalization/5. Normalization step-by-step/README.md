# Normalization step-by-step

## Example of a step-by-step normalization

- The process for normalization is progressive, and a higher level of database normalization cannot be achieved unless the previous levels have been satisfied;
- However, it's worth noting that normal forms beyond 4NF are mainly of academic interest, as the problems they exist to solve rarely appear in practice;
- Note that the data in the following example were intentionally designed to contradict most of the normal forms;
- In real life, it's quite possible to be able to skip some of the normalization steps because the table doesn't contain anything contradicting the given normal form;
- It also commonly occurs that fixing a violation of one normal form also fixes a violation of a higher normal form in the process;
- Also one table has been chosen for normalization at each step, meaning that at the end of this example process, there might still be some tables not satisfying the highest normal form;

## Intial Data

- Let a database table with the following structure:

| Title                                            | Author       | Author Nationality | Format    | Price | Subject               | Pages | Thickness | Publisher | Publisher Country | Publication Type | Genre ID | Genre Name |
| ------------------------------------------------ | ------------ | ------------------ | --------- | ----- | --------------------- | ----- | --------- | --------- | ----------------- | ---------------- | -------- | ---------- |
| Beginning MySQL Database Design and Optimization | Chad Russell | American           | Hardcover | 49.99 | MySQL,Database,Design | 520   | Thick     | Apress    | USA               | E-book           | 1        | Tutorial   |

## Links

- <https://en.wikipedia.org/wiki/Database_normalization> ;
