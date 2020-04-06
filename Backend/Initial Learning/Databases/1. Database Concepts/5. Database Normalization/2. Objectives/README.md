# Objectives

## The Objectives of Normalization

- A basic objective of the first normal form defined by Codd in 1970 was to permit data to be queried and manipulated using a "universal data sub-language" grounded in first-order logic, like SQL;
- Forms were defined to ensure normalization of databases;
- When an attempt is made to modify (update, insert into, or delete from) a relation, the following undesirable side-effects may arise in relations that have not been sufficiently normalized:

### Update Anomaly

- The same information can be expressed on multiple rows; therefore updates to the relation may result in logical inconsistencies;
- For example, each record in an "Employees' Skills" relation might contain an Employee ID, Employee Address, and Skill; thus a change of address for a particular employee may need to be applied to multiple records (one for each skill);

### Insertion Anomaly

- There are circumstances in which certain facts cannot be recorded at all;
- For example, each record in a "Faculty and Their Courses" relation might contain a Faculty ID, Faculty Name, Faculty Hire Date, and Course Code;
- Therefore, we can record the details of any faculty member who teaches at least one course, but we cannot record a newly hired faculty member who has not yet been assigned to teach any courses, except by setting the Course Code to null;

### Deletion Anomaly

- Under certain circumstances, deletion of data representing certain facts necessitates deletion of data representing completely different facts;
- The "Faculty and Their Courses" relation described in the previous example suffers from this type of anomaly, for if a faculty member temporarily ceases to be assigned to any courses, we must delete the last of the records on which that faculty member appears, effectively also deleting the faculty member, unless we set the Course Code to null;

### Minimize redesign when extending the database structure

- A fully normalized database allows its structure to be extended to accommodate new types of data without changing existing structure too much;
- As a result, applications interacting with the database are minimally affected;
- Normalized relations, and the relationship between one normalized relation and another, mirror real-world concepts and their interrelationships;

## Links

- <https://en.wikipedia.org/wiki/Database_normalization> ;
