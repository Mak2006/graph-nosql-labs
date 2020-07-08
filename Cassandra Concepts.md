## Cassandra concepts

## History
Cassandra is a wide column distributed database, its originated from Facebook and later contributed to Apache open source.  It is distributed wide column database. 

## Salient points
1. **Problem statement** - How can we have  reliable distributed database holding big data, which may not be as consistent but available and partition tolerant. 
2. **Distributed database holding big data** - Big data is defined using the V's. For our purpose it is that data which is too large for a single server. The issue then is how can we make database divided into two or more parts each on its own server having different network, yet the database behaves as a single database. 

## Concepts  and Story
1. **Node** - A single Cassandra instance, this is on a machine. This machine may be on a separate  network and may contain other nodes. Two nodes can be geographically separated, altogether in a separate data center and be in separate networks. Nodes can see each other, that is each node is connected to other nodes, even though they may be separated.  
2. **Algorithm** - the key algorithm of cassandra is then 
	1. Distribute the data accross different nodes, each node has a part of the data. These data parts are called partitions. Partitions are based on some key using which we can divide the data. To maintain failover, the nodes also have additional responsibility of having other partitions as well.  
3. **Partition Key** - A grouping of some
4. **Partition index**
5. **Partition**, Partition range, Partitioner
6. **Token**, **Token range**
7. **Snitch**
8. **Seeds**, **Seed node**
9. **Data types** Set, Map 	
10. **Hashing**
11. **Consistency Level**
12. **Replication Level**
13. **Sharding Shard**
14. **Keyspace**
15.  **Key cache**
16. **Memtable** 
17.  **SSTable**
18. **Gossip** - this is the protocol used by Nodes to talk to each other.
19. **Anti entropy**
20. **CAP theorem** Brewers theorem **Eventual consistency**
21. **Paxos algorithm**
22. **Hotspot**
23. **Acid**
24. **Base**
25. **Bloom Filter**
26. **C**
27. **C cluster**
28. **CQL**
29. **cqlsh**
30. **C* yaml**
31. **Token**
32. **Ring**
33. **Data center** **Rack**
34. **Primary Key**
35. **Clustering column**
36. **Commit Log**
37. **Compaction**
38. **Node repair**
39. **Nodetool**
40. **Quorum**
41. **Rolling restart**
42. **SEDA**
43. 

## Cassandra Algorithm
<!--stackedit_data:
eyJoaXN0b3J5IjpbODI2MDQ0MTQ2LC0xMjgyOTU5Nzc0LC00OT
Y2NzM3MDUsLTU0Nzc1NDAyOCwtMTU2OTQ4NDk4NSwtNzMwNDc3
Mzc4LDE1MzUyMTI3NDksNjE3ODk0Njk2LC0xNjQzMDU5NDUxXX
0=
-->