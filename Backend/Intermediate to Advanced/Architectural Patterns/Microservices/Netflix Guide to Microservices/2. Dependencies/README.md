# Dependencies

- Intra-service requests;
- Client libraries;
- Data persistence;
- Infrastructure;

## Intra-service requests

- This the calls from microservice A to microservice B to fulfill some larger request;

### Possible Risks

- Network latency;
- Congestion;
- Failure;
- Logical failures;
- Scaling failures;
- Can lead to **cascading failures**;

### Solving these issues

- Netflix used Hystrix;
- Create structured ways to handle tiemouts and retries;
- Create fallback responses and data;
- Create isolated thread pools;

### How do you know if it works

- Through Fault Injection and testing;
- Netflix created Fault Injection Testing (FIT) to test it;

### Critical Microservices

- Identify your most critical / depended upon services;
- Created FIT recipes to see if all the services function when these go away;

## Client Libraries

- Common code, patterns and languages with semantic logic;

### Risk of using Client Libraries

- Heap consumption;
- Logical defects;
- Transitive dependencies;

## Persistence

### CAP Theorem

- Netfllix choose availability;

## Infrastructure

- Used AWS;
- Netflix made their platform available in more than one region;
- If one region failed, traffic would be redirected to another region;
