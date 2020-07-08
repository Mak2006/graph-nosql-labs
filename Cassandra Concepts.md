## Cassandra concepts

## History
Cassandra is a wide column distributed database, its originated from Facebook and later contributed to Apache open source.  It is distributed wide column database. 

## Salient points
1. **Problem statement** - How can we have  reliable distributed database holding big data, which may not be as consistent but available and partition tolerant. 
2. **Distributed database holding big data** - Big data is defined using the V's. For our purpose it is that data which is too large for a single server. The issue then is how can we make database divided into two or more parts each on its own server having different network, yet the database behaves as a single database. 

## Concepts  and Story
1. **Node** - A single Cassandra instance, this is on a machine. This machine may be on a separate  network and may contain other nodes. Two nodes can be geographically separated, altogether in a separate data center and be in separate networks. Nodes can see each other, that is each node is connected to other nodes, even though they may be separated.  
2. **Algorithm** - the key algorithm of cassandra is then 
	1. Distribute the data accross different nodes, each node has a part of the data. These data parts are called partitions. Partitions are based on some key using which we can divide the data. To maintain failover, the nodes also have additional responsibility of having other partitions a  
3. **Partition Key**
4. **Partition index**
5. **Partition**, Partition range, Partitioner
6. **Snitch**
7. **Seeds**, **Seed node**
8. **Data types** Set, Map 	
9. **Hashing**
10. **Consistency Level**
11. **Replication Level**
12. **Sharding Shard**
13. **Keyspace**
14.  **Key cache**
15. **Memtable** 
16.  **SSTable**
17. **Gossip** - this is the protocol used by Nodes to talk to each other.
18. **Anti entropy**
19. **CAP theorem** Brewers theorem **Eventual consistency**
20. **Paxos algorithm**
21. **Hotspot**
22. **Acid**
23. **Base**
24. **Bloom Filter**
25. **C**
26. **C cluster**
27. **CQL**
28. **cqlsh**
29. **C* yaml**
30. **Token**
31. **Ring**
32. **Data center** **Rack**
33. **Primary Key**
34. **Clustering column**
35. **Commit Log**
36. **Compaction**
37. **Node repair**
38. **Nodetool**
39. **Quorum**
40. **Rolling restart**
41. **SEDA**
42. 

## Cassandra Algorithm
<!--stackedit_data:
eyJoaXN0b3J5IjpbNTM4ODA1ODkzLC0xMjgyOTU5Nzc0LC00OT
Y2NzM3MDUsLTU0Nzc1NDAyOCwtMTU2OTQ4NDk4NSwtNzMwNDc3
Mzc4LDE1MzUyMTI3NDksNjE3ODk0Njk2LC0xNjQzMDU5NDUxXX
0=
-->