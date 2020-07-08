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
4. **Partition index** - An on-disk data structure for SSTables which lists partition keys, their file offset position for each keys' corresponding partition in the SSTable.
5. **Partition** - A section of the data. 
6. **Partitioner** - The one that decides which partition the data goes in. The default program is the **Murmur3Partitioner**, other is **RandomPartitioner**
7. **Token** - One hash of a row, calculated by the partitioner
8. **Token range** - The range of possible tokens possible. This is subset of partition range.
9. **SSTable**
10. **Memtable** 
11. **Snitch**
12. **Seeds**, **Seed node**
13. **Data types** Set, Map 	
14. **Hashing**
15. **Consistency Level**
16. **Replication Level**
17. **Sharding Shard**
18. **Keyspace**
19.  **Key cache**
20. 
21.  
22. **Gossip** - this is the protocol used by Nodes to talk to each other.
23. **Anti entropy**
24. **CAP theorem** Brewers theorem **Eventual consistency**
25. **Paxos algorithm**
26. **Hotspot**
27. **Acid**
28. **Base**
29. **Bloom Filter**
30. **C**
31. **C cluster**
32. **CQL**
33. **cqlsh**
34. **C* yaml**
35. **Token**
36. **Ring**
37. **Data center** **Rack**
38. **Primary Key**
39. **Clustering column**
40. **Commit Log**
41. **Compaction**
42. **Node repair**
43. **Nodetool**
44. **Quorum**
45. **Rolling restart**
46. **SEDA**
47. 

## Cassandra Algorithm
<!--stackedit_data:
eyJoaXN0b3J5IjpbMjE1MTk0MzYxLDU4MjExMzE0MiwtNTQ3OD
kxNzQ1LDE5ODI5NTgyOTcsODI2MDQ0MTQ2LC0xMjgyOTU5Nzc0
LC00OTY2NzM3MDUsLTU0Nzc1NDAyOCwtMTU2OTQ4NDk4NSwtNz
MwNDc3Mzc4LDE1MzUyMTI3NDksNjE3ODk0Njk2LC0xNjQzMDU5
NDUxXX0=
-->