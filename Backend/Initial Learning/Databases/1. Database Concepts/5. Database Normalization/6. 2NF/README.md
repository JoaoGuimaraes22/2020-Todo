# 2NF

## 2NF (Second Normal Form)

- For a table to be in the Second Normal Form, it must satisfy two conditions:
  - The table should be in the First Normal Form;
  - There should be no Partial Dependency;
- As such, it needs to be in first normal form and it cant't have any non-prime attribute that is functionally dependent on any proper subset of any candidate key of the relation;
- A non-prime attribute of a relation is an attribute that is not a part of any candidate key of the relation;

## What is Dependency

- A **Primary Key** for a table is the column or a group of columns(composite key) which can uniquely identify each record in the table;
- Collumns that depend of other primary collumns are **dependent** of those primary collumns;
- For example, most columns on a table are associated with an id;
- This is **dependency**, and we also call it **functional dependency**;

## What is Partial Dependency

- A **Candidate Key** is a group of 2 or more collumns used to uniquely identifie a row in a table;
- Where there are **candidate keys**, there is partial dependecies;
- For example, if a user_id and store_id collums are together a candidate key, it means that the rest of the collums in the table are partially dependent of user_id or of store_id;
- As such, **partial dependency** occurs where an attribute in a table depends on only a part of the primary key and not on the whole key;

## Removing partial dependency

- To remove Partial dependency, one should divide the table, remove the attribute which is causing partial dependency, and move it to some other table where it fits in well;

## Links

- <https://www.studytonight.com/dbms/second-normal-form.php> ;
- <https://en.wikipedia.org/wiki/Second_normal_form> ;
