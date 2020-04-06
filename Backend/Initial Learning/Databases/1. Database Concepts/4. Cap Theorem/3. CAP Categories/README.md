# CAP Theorem Categories

## System Types

- The CAP theorem categorizes systems into three categories:
  ![CAP Categories Image](https://github.com/JoaoGuimaraes22/2020-Todo/blob/master/Images/Backend/Initial%20Learning/Databases/1.%20Database%20Concepts/4.3.cap_diagram-min.jpeg)

### CP (Consistent and Partition Tolerant)

- CP is referring to a category of systems where availability is sacrificed only in the case of a network partition;

### CA (Consistent and Available)

- CA systems are consistent and available systems in the absence of any network partition;
- Often a single node's DB servers are categorized as CA systems;
- Single node DB servers do not need to deal with partition tolerance and are thus considered CA systems;
- The only hole in this theory is that single node DB systems are not a network of shared data systems and thus do not fall under the preview of CAP;

### AP (Available and Partition Tolerant)

- These are systems that are available and partition tolerant but cannot guarantee consistency;

## Partition tolerance is a must

- In a distributed system, partitions can’t be avoided;
- So, while we can discuss a CA distributed database in theory, for all practical purposes, a CA distributed database can’t exist;
- However, this doesn’t mean you can’t have a CA database for your distributed application if you need one; - Many relational databases, such as PostgreSQL, deliver consistency and availability and can be deployed to multiple nodes using replication;

## Choosing your system

- A network partition forces designers to either choose perfect consistency or perfect availability;
- Picking consistency means not being able to answer a client's query as the system cannot guarantee to return the most recent write, which sacrifices availability;
- Network partition forces nonfailing nodes to reject clients' requests as these nodes cannot guarantee consistent data;
- At the opposite end of the spectrum, being available means being able to respond to a client's request but the system cannot guarantee consistency, as such, the most recent value written;
- Available systems provide the best possible answer under the given circumstance.

## Links

- <https://dzone.com/articles/understanding-the-cap-theorem> ;
- <https://www.ibm.com/cloud/learn/cap-theorem> ;
