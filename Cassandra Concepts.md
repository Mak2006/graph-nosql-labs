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
3. **Partition Key** - In C*, a partition key is required to be defined. It is consists of at least on column. So when a row comes in, the **Partitoner**, uses a hash function on the value of the column and creates a **Token**. The all possible values of these token is the **token range**.  Each of the nodes now are designated to hold data for a subset of the total token range. The Partitioners pushes the data to that node designated for that token range.  Partition key is at least a single column. It can be multiple columns as well. So primary key =  
4. **Partition index** - An on-disk data structure for SSTables which lists partition keys, their file offset position for each keys' corresponding partition in the SSTable.
5. **Partition** - A section of the data.  Part of a table
6. **Partitioner** - The one that decides which partition the data goes in. The default program is the **Murmur3Partitioner**, other is **RandomPartitioner**
7. **Token** - One hash of a row, calculated by the partitioner
8. **Token range** - The range of possible tokens possible. This is subset of partition range.
9. **Clustering columns** - this defines the storage order within partitions
10.**Sparse tables** - Tables where some cells may not have data.
10.**Ordering columns** -  
11. **SSTable**
12. **Memtable** 
13. **Snitch**
14. **Seeds**, **Seed node**
15. **Data types** Set, Map 	
16. **Hashing**
17. **Consistency Level**
18. **Replication Level**
19. **Replication strategy**
20. **Sharding Shard**
21. **Keyspace**
22.  **Key cache**
23. **Ring** the sequence of nodes
24.  **Sharding**
25. **Gossip** - this is the protocol used by Nodes to talk to each other.
26. **Anti entropy**
27. **CAP theorem** Brewers theorem **Eventual consistency**
28. **Paxos algorithm**
29. **Hotspot**
30. **Acid**
31. **Base**
32. **Bloom Filter**
33. **C**
34. **C cluster**
35. **CQL**
36. **cqlsh**
37. **C* yaml**
38. **Token**
39. **Ring**
40. **Data center** **Rack**
41. **Primary Key**
42. **Clustering column**
43. **Commit Log**
44. **Compaction**
45. **Node repair**
46. **Nodetool**
47. **Quorum**
48. **Rolling restart**
49. **SEDA**
50. 

## Cassandra Algorithm
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTQxODUxMDAwNiwtMTEzNjI4MTExMCwtOD
Q0MTI0MjcxLDIxNTE5NDM2MSw1ODIxMTMxNDIsLTU0Nzg5MTc0
NSwxOTgyOTU4Mjk3LDgyNjA0NDE0NiwtMTI4Mjk1OTc3NCwtND
k2NjczNzA1LC01NDc3NTQwMjgsLTE1Njk0ODQ5ODUsLTczMDQ3
NzM3OCwxNTM1MjEyNzQ5LDYxNzg5NDY5NiwtMTY0MzA1OTQ1MV
19
-->