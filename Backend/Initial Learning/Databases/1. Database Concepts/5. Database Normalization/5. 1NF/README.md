# 1NF

## 1NF (First Normal Form)

- The 1st Normal form expects you to design your table in such a way that it can easily be extended and it is easier for you to retrieve data from it whenever required;
- It enforces the following criteria:
  - Eliminate repeating groups in individual tables;
  - Create a separate table for each set of related data;
  - Identify each set of related data with a primary key;
- The first normal form expects you to follow a few simple rules while designing your database, and they are:

### Rule 1: Single Valued Attributes

- Each column of your table should be single valued;
- Atomicity is key for 1NF, as such, each collum should remain atomic, indivisble;

### Rule 2: Attribute Domain should not change

- In each column the values stored must be of the same kind or type;

### Rule 3: Unique name for Attributes/Columns

- This rule expects that each column in a table should have a unique name, to avoid confusion at the time of performing operation on the stored data;
- If one or more columns have same name, then the DBMS system will be left confused;

### Rule 4: Order doesn't matters

- This rule says that the order in which you store the data in your table doesn't matter;

## Links

- <https://www.studytonight.com/dbms/first-normal-form.php> ;
- <https://en.wikipedia.org/wiki/First_normal_form> ;
