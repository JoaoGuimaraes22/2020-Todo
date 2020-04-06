# Introduction

## Overview

- The CAP theorem, also named Brewer's theorem, states that it is impossible for a distributed sytem to simultaneously provide more than two out of the following three guarantees:
  - Consistency:
    - Every read receives the most recent write or an error;
  - Availability:
    - Every request receives a (non-error) response, without the guarantee that it contains the most recent write;
  - Partition Tolerance:
    - The system continues to operate despite an arbitrary number of messages being dropped (or delayed) by the network between nodes;
- When a network partition failure happens should we decide to:
  - Cancel the operation and thus decrease the availability but ensure consistency;
  - Proceed with the operation and thus provide availability but risk inconsistency;
- The CAP theorem implies that in the existence of a network partition, one has to choose between consistency and availability;
- Note that the Consistency defined in the CAP Theorem is different than the one in ACID transactions (see ACID notes for more);

## Links

- <https://en.wikipedia.org/wiki/CAP_theorem> ;
