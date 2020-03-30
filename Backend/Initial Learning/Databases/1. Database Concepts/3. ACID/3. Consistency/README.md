# Consistency

## Overview

- Consistency refers to the requirement that any given database transaction must change affected data only in allowed ways;
- Any data written to the database must be valid according to all defined rules, including constraints, cascades, triggers, and any combination;
- This does not guarantee correctness of the transaction in all ways the application programmer might have wanted but merely that any programming errors cannot result in the violation of any defined database constraints;

## As an ACID guarantee

- Consistency is one of the four guarantees that define ACID transactions; however, significant ambiguity exists about the nature of this guarantee;

### Guarantees

- The guarantee that any transactions started in the future necessarily see the effects of other transactions committed in the past;
- The guarantee that database constraints are not violated, particularly once a transaction commits;
- The guarantee that operations in transactions are performed accurately, correctly, and with validity, with respect to application semantics;

- As these various definitions are not mutually exclusive, it is possible to design a system that guarantees "consistency" in every sense of the word, as most relational database management systems in common use today arguably do;

## As a CAP trade-off

- The CAP theorem is based on three trade-offs:
  - One is "atomic consistency" (shortened to "consistency" for the acronym), about which the authors note:
    - "Discussing atomic consistency is somewhat different than talking about an ACID database, as database consistency refers to transactions, while atomic consistency refers only to a property of a single request/response operation sequence. And it has a different meaning than the Atomic in ACID, as it subsumes the database notions of both Atomic and Consistent.";

## Links

- <https://en.wikipedia.org/wiki/Consistency_(database_systems)> ;
