# Explanation

## A distributed system

- A distributed system is a network that stores data on more than one node (physical or virtual machines) at the same time;
- All cloud applications are distributed systems;

## The "CAP" in the CAP Theorem

- Let's take a detailed look at the three distributed system characteristics to which the CAP theorem refers:

### Concistency

- Consistency means that all clients see the same data at the same time, no matter which node they connect to;
- For this to happen, whenever data is written to one node, it must be instantly forwarded or replicated to all the other nodes in the system before the write is deemed successful;

### Availability

- Availability means that that any client making a request for data gets a response, even if one or more nodes are down;
- As such, all working nodes in the distributed system return a valid response for any request, without exception;

### Partition tolerance

- A partition is a communications break within a distributed system - a lost or temporarily delayed connection between two nodes;
- Partition tolerance means that the cluster must continue to work despite any number of communication breakdowns between nodes in the system;

## Links

- <https://mwhittaker.github.io/blog/an_illustrated_proof_of_the_cap_theorem/> ;
- <https://www.ibm.com/cloud/learn/cap-theorem> ;
