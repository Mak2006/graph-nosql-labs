## Cassandra concepts

## History
Cassandra is a wide column distributed database, its originated from Facebook and later contributed to Apache open source.  It is distributed wide column database. 

## Salient points
1. **Problem statement** - How can we have  reliable distributed database holding big data, which may not be as consistent but available and partition tolerant. 
2. **Distributed database holding big data** - Big data is data too large for a single server. The issue how can we make database divided into two or more parts each on its own server having different network, yet the database behaves as a single database. 

## Concepts 
1. **Node** - A single Cassandra instance, this is on a machine. This machine may be on a separate  network and may contain other nodes. Two nodes can be geographically separated, altogether in a separate data center and be in separate networks. Nodes can see each other, that is each node is connected to other nodes, even though they may be separated.  
2. **Partition Key**
3. **Snitch**
4. **Seeds**
5. **Hashing**
6. **Consistency Level**
7. **Replication Level**
8. **Keyspace**
9.  **Key space**
10. **Gossip** - this is the protocol used by Nodes to talk to each other.
11. **Anti entropy**
12. **CAP theorem** Brewers theorem **Eventual consistency**
13. **Paxos algorithm**
14. **Hotspot**
15. **Acid**
16. **Base**
17. **Bloom Filter**
18. **C**
19. **C cluster**
20. **CQL**
21. **cqlsh**
22. **C* yaml**
23. **Token**
24. **Ring**
25. **Primary Key**
26. **Clustering column**
27. **Commit Log**
28. **Compaction**
29. 

## Cassandra Algorithm
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTg5NjUzNDQ3LC03MzA0NzczNzgsMTUzNT
IxMjc0OSw2MTc4OTQ2OTYsLTE2NDMwNTk0NTFdfQ==
-->