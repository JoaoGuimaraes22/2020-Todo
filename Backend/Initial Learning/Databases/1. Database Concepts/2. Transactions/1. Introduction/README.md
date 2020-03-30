# Introduction

## Overview

- A database transaction symbolizes a unit of work performed within a database management system (or similar system) against a database, and treated in a coherent and reliable way independent of other transactions;
- Represent any change in database;

## Transactions in a database environment

- Need to provide reliable units of work that allow correct recovery from failures and keep a database consistent even in cases of system failure, when execution stops (completely or partially) and many operations upon a database remain uncompleted, with unclear status;
- Need to provide isolation between programs accessing a database concurrently, because if this isolation is not provided, the programs' outcomes are possibly erroneous;

## In a DBMS

- In a DBMS, a transaction is a single unit of logic or work, sometimes made up of multiple operations;
- Any logical calculation done in a consistent mode in a database is known as a transaction;

## Links

- <https://en.wikipedia.org/wiki/Database_transaction> ;
