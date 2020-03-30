# Atomicity

## Overview

- An atomic transaction is an indivisible and irreducible series of database operations such that either all occurs, or nothing occurs;
- A guarantee of atomicity prevents updates to the database occurring only partially, which can cause greater problems than rejecting the whole series outright;
- As a consequence, the transaction cannot be observed to be in progress by another database client;
- At one moment in time, it has not yet happened, and at the next it has already occurred in whole (or nothing happened if the transaction was cancelled in progress);

## Example

- An example of an atomic transaction is a monetary transfer from bank account A to account B;
- It consists of two operations, withdrawing the money from account A and saving it to account B;
- Performing these operations in an atomic transaction ensures that the database remains in a consistent state, that is, money is neither lost nor created if either of those two operations fail;

## Orthogonality

- Atomicity does not behave completely orthogonally with regard to the other ACID properties of the transactions;
- For example, isolation relies on atomicity to roll back changes in the event of isolation failures such as deadlock;
- Finally, atomicity itself relies on durability to ensure the atomicity of transactions even in the face of external failures;
- As a result of this, failure to detect errors and roll back the enclosing transaction may cause failures of isolation and consistency;

## Implementation

- Systems implement Atomicity by providing some mechanism to indicate which transactions have started and which finished, or by keeping a copy of the data before any changes occurred;
- Several filesystems have developed methods for avoiding the need to keep multiple copies of data, using journaling;
- Databases usually implement this using some form of logging to track changes;
- The system synchronizes the logs as necessary after changes have successfully taken place;
- Afterwards, crash recovery ignores incomplete entries;
- Although implementations vary depending on factors such as concurrency issues, the principle of atomicity remain;
- Ultimately, any application-level implementation relies on operating-system functionality;
- At the file-system level, POSIX-compliant systems provide system calls such as `open(2)` and `flock(2)` that allow applications to atomically open or lock a file;
- At the process level, POSIX Threads provide adequate synchronization primitives;
- The hardware level requires atomic operations such as Test-and-set, Fetch-and-add, Compare-and-swap, or Load-Link/Store-Conditional, together with memory barriers;
- Portable operating systems cannot simply block interrupts to implement synchronization, since hardware that lacks concurrent execution such as hyper-threading or multi-processing is now rare;

## Links

- <https://en.wikipedia.org/wiki/Atomicity_(database_systems)> ;
