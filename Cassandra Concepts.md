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
9.  **Key cache**
10. **Memtable** 
11.  **SSTable**
12. **Gossip** - this is the protocol used by Nodes to talk to each other.
13. **Anti entropy**
14. **CAP theorem** Brewers theorem **Eventual consistency**
15. **Paxos algorithm**
16. **Hotspot**
17. **Acid**
18. **Base**
19. **Bloom Filter**
20. **C**
21. **C cluster**
22. **CQL**
23. **cqlsh**
24. **C* yaml**
25. **Token**
26. **Ring**
27. **Primary Key**
28. **Clustering column**
29. **Commit Log**
30. **Compaction**
31. 

## Cassandra Algorithm
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE1Njk0ODQ5ODUsLTczMDQ3NzM3OCwxNT
M1MjEyNzQ5LDYxNzg5NDY5NiwtMTY0MzA1OTQ1MV19
-->