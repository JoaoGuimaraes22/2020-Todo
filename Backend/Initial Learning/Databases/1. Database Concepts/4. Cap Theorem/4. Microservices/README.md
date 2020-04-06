# Microservices

## The CAP Theorem and Microservices

- Microservices are loosely coupled, independently deployable application components that incorporate their own stack—including their own database and database model—and communicate with each other over a network;
- As you can run microservices on both cloud servers and on-premises data centers, they have become highly popular for hybrid and multicloud applications;
- Understanding the CAP theorem can help you choose the best database when designing a microservices-based application running from multiple locations;

## Choosing the best

- For example, if the ability to quickly iterate the data model and scale horizontally is essential to your application, but you can tolerate eventual (as opposed to strict) consistency, an AP database like Cassandra or Apache CouchDB can meet your requirements and simplify your deployment;
- On the other hand, if your application depends heavily on data consistency—as in an eCommerce application or a payment service—you might opt for a relational database like PostgreSQL;

## Links

- <https://www.ibm.com/cloud/learn/cap-theorem> ;
