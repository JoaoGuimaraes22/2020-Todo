# The features and purpose of Transactions

## Definition

- A database transaction, by definition, must be atomic (it must either complete in its entirety or have no effect whatsoever), consistent (it must conform to existing constraints in the database), isolated (it must not affect other transactions) and durable (it must get written to persistent storage);
- Database practitioners often refer to these properties of database transactions using the acronym [ACID](https://github.com/JoaoGuimaraes22/2020-Todo/tree/master/Backend/Initial%20Learning/Databases/1.%20Database%20Concepts/3.%20ACID/1.%20Introduction);

## The purpose of Transactions

- Databases and other data stores which treat the integrity of data as paramount often include the ability to handle transactions to maintain the integrity of data;
- A single transaction consists of one or more independent units of work, each reading and/or writing information to a database or other data store;
- When this happens it is often important to ensure that all such processing leaves the database or data store in a consistent state;
- Examples from double-entry accounting systems often illustrate the concept of transactions;
- In double-entry accounting every debit requires the recording of an associated credit;
- If one writes a check for \$100 to buy groceries, a transactional double-entry accounting system must record the following two entries to cover the single transaction:
  - Debit \$100 to Groceries Expense Account;
  - Credit \$100 to Checking Account;
- A transactional system would make both entries pass or both entries would fail;
- By treating the recording of multiple entries as an atomic transactional unit of work the system maintains the integrity of the data recorded;
- In other words, nobody ends up with a situation in which a debit is recorded but no associated credit is recorded, or vice versa;

## Links

- <https://en.wikipedia.org/wiki/Database_transaction> ;
