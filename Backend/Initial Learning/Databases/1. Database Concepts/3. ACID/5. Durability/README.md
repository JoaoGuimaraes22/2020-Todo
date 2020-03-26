# Durability

## Overview

- It's the ACID property which guarantees that transactions that have committed will survive permanently;
- For example, if a flight booking reports that a seat has successfully been booked, then the seat will remain booked even if the system crashes;
- Durability can be achieved by flushing the transaction's log records to non-volatile storage before acknowledging commitment;
- In distributed transactions, all participating servers must coordinate before commit can be acknowledged;
- This is usually done by a two-phase commit protocol;
- Many DBMSs implement durability by writing transactions into a transaction log that can be reprocessed to recreate the system state right before any later failure;
- A transaction is deemed committed only after it is entered in the log;

## Links

- <https://en.wikipedia.org/wiki/Durability_(database_systems)> ;
