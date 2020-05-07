# Scale

- Stateless Services;
- Stateful Services;
- Hybrid Services;

## Stateless Services

- Not a cache or database;
- Frequently accessed metadata;
- No instance affinity;
- Loss of a node is non-event

### Auto scaling

- Allows for compute efficiency;
- Nodes get replaced easily;
- Eases traffic spike impacts;
- Better for protection against performance bugs;

### Testing using chaos

- Test your scaling ability by applying chaos (high load, etc);
- Netflix uses Chaos Monkey;

## Stateful Services

- Include databases and caches;
- Custom apps which hold a lot of data;
- Loss of a node us is a notable event;

### Dedicated Shards - An Antipattern

- Redundancy is fundamental;
- Netflix used EVCache, a sharded wrapper around Memcached, with multiple copies written out to multiple loads;
- Read are local by default, but the application can fallback out of its availability zone if needed;

## Hybrid Services

- For Netflix, it's easy to take EV Cache for granted;
- It can take, for example, 30 million requests/sec, 2 trillion requests/day globally;
- Scales in a linear way;
- But, the problem is, if it went down, all services would as well;

### Solutions for solving Hybrid services problems

- Workload partitioning;
- Request-level caching;
- Secure token fallback;
- Test with chaos;
