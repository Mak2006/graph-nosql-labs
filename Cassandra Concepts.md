## Cassandra concepts

## History
Cassandra is a wide column distributed database, its originated from Facebook and later contributed to Apache open source.  It is distributed wide column database. 

## Salient points
1. **Problem statement** - How can we have  reliable distributed database holding big data, which may not be as consistent but available and partition tolerant. 
2. **Distributed database holding big data** - Big data is data too large for a single server. The issue how can we make database divided into two or more parts each on its own server having different network, yet the database behaves as a single database. 

## Concepts 
1. **Node** - A single Cassandra instance, this is on a machine. This machine may be on a separate  network and may contain other nodes. Two nodes can be geographically separated, altogether in a separate data center and be in separate networks. Nodes can see each other, that is each node is connected to other nodes, even though they may be separated.  
2. **Partition Key**
3. **Partition index**
4. **Partition**, Partition range, Partitioner
5. **Snitch**
6. **Seeds**
7. **Hashing**
8. **Consistency Level**
9. **Replication Level**
10. **Keyspace**
11.  **Key cache**
12. **Memtable** 
13.  **SSTable**
14. **Gossip** - this is the protocol used by Nodes to talk to each other.
15. **Anti entropy**
16. **CAP theorem** Brewers theorem **Eventual consistency**
17. **Paxos algorithm**
18. **Hotspot**
19. **Acid**
20. **Base**
21. **Bloom Filter**
22. **C**
23. **C cluster**
24. **CQL**
25. **cqlsh**
26. **C* yaml**
27. **Token**
28. **Ring**
29. **Data center** **Rack**
30. **Primary Key**
31. **Clustering column**
32. **Commit Log**
33. **Compaction**
34. **Node repair**
35. **Nodetool**
36. **Quorum**

## Cassandra Algorithm
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTU0Nzc1NDAyOCwtMTU2OTQ4NDk4NSwtNz
MwNDc3Mzc4LDE1MzUyMTI3NDksNjE3ODk0Njk2LC0xNjQzMDU5
NDUxXX0=
-->