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
3. **Partition Key** - In C*, a partition key is required to be defined. It is consists of at least on column. So when a row comes in, the **Partitoner**, uses a hash function on the value of the column and creates a **Token**. The all possible values of these token is the **token range**.  Each of the nodes now are designated to hold data for a subset of the total token range. The Partitioners pushes the data to that node designated for that token range.  
4. **Partition index**
5. **Partition**, Partition range, 
6. **Partitioner** - The one that decides which partition the data goes in. The default pro
7. **Token**, **Token range**
8. **Snitch**
9. **Seeds**, **Seed node**
10. **Data types** Set, Map 	
11. **Hashing**
12. **Consistency Level**
13. **Replication Level**
14. **Sharding Shard**
15. **Keyspace**
16.  **Key cache**
17. **Memtable** 
18.  **SSTable**
19. **Gossip** - this is the protocol used by Nodes to talk to each other.
20. **Anti entropy**
21. **CAP theorem** Brewers theorem **Eventual consistency**
22. **Paxos algorithm**
23. **Hotspot**
24. **Acid**
25. **Base**
26. **Bloom Filter**
27. **C**
28. **C cluster**
29. **CQL**
30. **cqlsh**
31. **C* yaml**
32. **Token**
33. **Ring**
34. **Data center** **Rack**
35. **Primary Key**
36. **Clustering column**
37. **Commit Log**
38. **Compaction**
39. **Node repair**
40. **Nodetool**
41. **Quorum**
42. **Rolling restart**
43. **SEDA**
44. 

## Cassandra Algorithm
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE2NjI4ODg2MTUsODI2MDQ0MTQ2LC0xMj
gyOTU5Nzc0LC00OTY2NzM3MDUsLTU0Nzc1NDAyOCwtMTU2OTQ4
NDk4NSwtNzMwNDc3Mzc4LDE1MzUyMTI3NDksNjE3ODk0Njk2LC
0xNjQzMDU5NDUxXX0=
-->