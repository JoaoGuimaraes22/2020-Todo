# 3NF

## 3NF (Third Normal Form)

- For a table to be in the third normal form:
  - It should be in the Second Normal form;
  - it should not have Transitive Dependency;
- As such, for a table to be in 3NF, it needs to be in 2NF and Every non-prime attribute of it must be non-transitively dependent on every key of the table;

## What is Transitive Dependency

- Transitive dependency occurs when a non-prime attribute depends on other non-prime attributes rather than depending upon the prime attributes or primary key;
- For example, to follow 3NF, a subject_name key should not be associated with a non-primary atribute, and should instead be associated with a primary key, such as a subject_id;

## How to remove Transitive Dependency

- Make separate tables with unique primary keys and include the collumns that previously referenced the non-prime keys, and make them then reference the new table's primary key;

## Links

- <https://www.studytonight.com/dbms/third-normal-form.php> ;
- <https://en.wikipedia.org/wiki/Third_normal_form> ;
