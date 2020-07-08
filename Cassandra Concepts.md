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
5. **Partition** - A section of the data. 
6. **Partitioner** - The one that decides which partition the data goes in. The default program is the **Murmur3Partitioner**, other is **RandomPartitioner**
7. **Token** 
8. **Token range** - 
9. **Snitch**
10. **Seeds**, **Seed node**
11. **Data types** Set, Map 	
12. **Hashing**
13. **Consistency Level**
14. **Replication Level**
15. **Sharding Shard**
16. **Keyspace**
17.  **Key cache**
18. **Memtable** 
19.  **SSTable**
20. **Gossip** - this is the protocol used by Nodes to talk to each other.
21. **Anti entropy**
22. **CAP theorem** Brewers theorem **Eventual consistency**
23. **Paxos algorithm**
24. **Hotspot**
25. **Acid**
26. **Base**
27. **Bloom Filter**
28. **C**
29. **C cluster**
30. **CQL**
31. **cqlsh**
32. **C* yaml**
33. **Token**
34. **Ring**
35. **Data center** **Rack**
36. **Primary Key**
37. **Clustering column**
38. **Commit Log**
39. **Compaction**
40. **Node repair**
41. **Nodetool**
42. **Quorum**
43. **Rolling restart**
44. **SEDA**
45. 

## Cassandra Algorithm
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTIwMzU3MDA0NSwxOTgyOTU4Mjk3LDgyNj
A0NDE0NiwtMTI4Mjk1OTc3NCwtNDk2NjczNzA1LC01NDc3NTQw
MjgsLTE1Njk0ODQ5ODUsLTczMDQ3NzM3OCwxNTM1MjEyNzQ5LD
YxNzg5NDY5NiwtMTY0MzA1OTQ1MV19
-->