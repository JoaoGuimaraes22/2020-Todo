# Normalization step-by-step

## Example of a step-by-step normalization

- The process for normalization is progressive, and a higher level of database normalization cannot be achieved unless the previous levels have been satisfied;
- Normal forms beyond 4NF are mainly of academic interest, as the problems they exist to solve rarely appear in practice;
- The data in the following example were intentionally designed to contradict most of the normal forms;
- In real life, it's quite possible to be able to skip some of the normalization steps because the table doesn't contain anything contradicting the given normal form;
- It also commonly occurs that fixing a violation of one normal form also fixes a violation of a higher normal form in the process;
- Also one table has been chosen for normalization at each step, meaning that at the end of this example process, there might still be some tables not satisfying the highest normal form;

## Intial Data

- Let a database table with the following structure:

| Title                                            | Author       | Author Nationality | Format    | Price | Subject               | Pages | Thickness | Publisher | Publisher Country | Publication Type | Genre ID | Genre Name |
| ------------------------------------------------ | ------------ | ------------------ | --------- | ----- | --------------------- | ----- | --------- | --------- | ----------------- | ---------------- | -------- | ---------- |
| Beginning MySQL Database Design and Optimization | Chad Russell | American           | Hardcover | 49.99 | MySQL,Database,Design | 520   | Thick     | Apress    | USA               | E-book           | 1        | Tutorial   |

## Satisfying 1NF

- To satisfy 1NF, the values in each column of a table must be atomic;
- In the initial table, Subject contains a set of subject values, meaning it does not comply;
- One way to achieve the 1NF would be to separate the duplicities into multiple columns using repeating groups 'subject':

| Title                                            | Author       | Author Nationality | Format    | Price | Subject 1 | Subject 2 | Subject 3 | Pages | Thickness | Publisher | Publisher Country | Publication Type | Genre ID | Genre Name |
| ------------------------------------------------ | ------------ | ------------------ | --------- | ----- | --------- | --------- | --------- | ----- | --------- | --------- | ----------------- | ---------------- | -------- | ---------- |
| Beginning MySQL Database Design and Optimization | Chad Russell | American           | Hardcover | 49.99 | MySQL     | Database  | Design    | 520   | Thick     | Apress    | USA               | E-book           | 1        | Tutorial   |

- Although now the table formally complies to the 1NF (is atomic), the problem with this solution is obvious - if a book has more than three subjects, it cannot be added to the database without altering its structure;
- To solve the problem, it's necessary to identify entities represented in the table and separate them into their own respective tables;

- Book Table:

| Title                                            | Author       | Author Nationality | Format    | Price | Subject ID | Pages | Thickness | Publisher ID | Publication Type | Genre ID | Genre Name |
| ------------------------------------------------ | ------------ | ------------------ | --------- | ----- | ---------- | ----- | --------- | ------------ | ---------------- | -------- | ---------- |
| Beginning MySQL Database Design and Optimization | Chad Russell | American           | Hardcover | 49.99 | 1          | 520   | Thick     | 1            | E-book           | 1        | Tutorial   |

- Subject Table:

| Subject ID | Subject Name |
| ---------- | ------------ |
| 1          | MySQL        |
| 2          | Database     |
| 3          | Design       |

- Publisher Table:

| Publisher ID | Name   | Country |
| ------------ | ------ | ------- |
| 1            | Apress | USA     |

- Simply separating the initial data into multiple tables would break the connection between the data;
- That means the relationships between the newly introduced tables need to be determined;
- A book can fit many subjects, as well as a subject may correspond to many books;
- That means also a many-to-many relationship needs to be defined, achieved by creating a link table:

- Title - Subject Table.

| Title                                            | Subject ID |
| ------------------------------------------------ | ---------- |
| Beginning MySQL Database Design and Optimization | 1          |
| Beginning MySQL Database Design and Optimization | 2          |
| Beginning MySQL Database Design and Optimization | 3          |

- Instead of one table in unnormalized form, there are now 4 tables conforming to the **1NF**;

## Satisfying 2F

-

## Links

- <https://en.wikipedia.org/wiki/Database_normalization> ;
