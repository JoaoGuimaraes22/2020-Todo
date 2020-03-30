# Isolation

## Overview

- Determines how transaction integrity is visible to other users and systems;
- A lower isolation level increases the ability of many users to access the same data at the same time, but increases the number of concurrency effects users might encounter;
- A higher isolation level reduces the types of concurrency effects that users may encounter, but requires more system resources and increases the chances that one transaction will block another;

## Definition

- Isolation is typically defined at database level as a property that defines how/when the changes made by one operation become visible to others;
- On older systems, it may be implemented systemically, for example through the use of temporary tables, in two-tier systems, a Transaction Processing manager is required to maintain isolation;
- In n-tier systems, a combination of stored procedures and transaction management is required to commit the booking and send confirmation to the customer;

## Concurrency control

- Concurrency control comprises the underlying mechanisms in a DBMS which handle isolation and guarantee related correctness;
- Heavily used by the database and storage engines both to guarantee the correct execution of concurrent transactions, and the correctness of other DBMS processes;
- The transaction-related mechanisms typically constrain the database data access operations' timing to certain orders characterized as the serializability and recoverability;
- Constraining database access operation execution typically means reduced performance, and thus concurrency control mechanisms are typically designed to provide the best performance possible under the constraints;
- Two-phase locking is the most common transaction concurrency control method in DBMSs, used to provide both serializability and recoverability for correctness;
- In order to access a database object a transaction first needs to acquire a lock for this object;
- Depending on the access operation type and on the lock type, acquiring the lock may be blocked and postponed, if another transaction is holding a lock for that object;

## Read Phenomena

- The ANSI/ISO standard SQL 92 refers to three different read phenomena when Transaction 1 reads data that Transaction 2 might have changed;

### Dirty Reads

- A dirty read (aka uncommitted dependency) occurs when a transaction is allowed to read data from a row that has been modified by another running transaction and not yet committed;

### Non-repeatable reads

- A non-repeatable read occurs, when during the course of a transaction, a row is retrieved twice and the values within the row differ between reads;

### Phantom reads

- A phantom read occurs when, in the course of a transaction, new rows are added or removed by another transaction to the records being read;

## Isolation Levels

- The isolation property is the one most often relaxed in ACID;
- When attempting to maintain the highest level of isolation, a DBMS usually acquires locks on data which may result in a loss of concurrency or implements multiversion concurrency control, which requires adding logic for the application to function correctly;
- There are many transaction isolation levels, which control the degree of locking that occurs when selecting data;
- For many database applications, the majority of database transactions can be constructed to avoid requiring high isolation levels (e.g. SERIALIZABLE level), thus reducing the locking overhead for the system;
- The programmer must carefully analyze database access code to ensure that any relaxation of isolation does not cause software bugs that are difficult to find, also, if higher isolation levels are used, the possibility of deadlock is increased, which also requires careful analysis and programming techniques to avoid;
- Since each isolation level is stronger than those below, in that no higher isolation level allows an action forbidden by a lower one, the standard permits a DBMS to run a transaction at an isolation level stronger than that requested;
- The isolation levels defined by the ANSI/ISO SQL standard are listed as follows:

### Serializable

- This is the highest isolation level;
- Serializability requires read and write locks (acquired on selected data) to be released at the end of the transaction. Also range-locks must be acquired when a SELECT query uses a ranged WHERE clause, especially to avoid the phantom reads phenomenon;

### Repeatable reads

- In this isolation level, a lock-based concurrency control DBMS implementation keeps read and write locks (acquired on selected data) until the end of the transaction;
- However, range-locks are not managed, so phantom reads can occur;

### Read commited

- Read committed is an isolation level that guarantees that any data read is committed at the moment it is read;
- It simply restricts the reader from seeing any intermediate, uncommitted, 'dirty' read;
- It makes no promise whatsoever that if the transaction re-issues the read, it will find the same data;
- Data is free to change after it is read;

### Read uncommited

- This is the lowest isolation level;
- In this level, dirty reads are allowed, so one transaction may see not-yet-committed changes made by other transactions;

## Default isolation level

- The default isolation level of different DBMS's varies quite widely;

## Isolation levels, read phenomena, and locks

![Roadmap Image](https://github.com/JoaoGuimaraes22/2020-Todo/blob/master/Images/Others/Development_Roadmap_2020-min.png)

## Links

- <https://en.wikipedia.org/wiki/Isolation_(database_systems)> ;
