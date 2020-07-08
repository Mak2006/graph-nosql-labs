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
9. **SSTable**
10. **Memtable** 
11. **Snitch**
12. **Seeds**, **Seed node**
13. **Data types** Set, Map 	
14. **Hashing**
15. **Consistency Level**
16. **Replication Level**
17. **Replication strategy**
18. **Sharding Shard**
19. **Keyspace**
20.  **Key cache**
21. **Ring** the sequence of nodes
22.  **Sharding**
23. **Gossip** - this is the protocol used by Nodes to talk to each other.
24. **Anti entropy**
25. **CAP theorem** Brewers theorem **Eventual consistency**
26. **Paxos algorithm**
27. **Hotspot**
28. **Acid**
29. **Base**
30. **Bloom Filter**
31. **C**
32. **C cluster**
33. **CQL**
34. **cqlsh**
35. **C* yaml**
36. **Token**
37. **Ring**
38. **Data center** **Rack**
39. **Primary Key**
40. **Clustering column**
41. **Commit Log**
42. **Compaction**
43. **Node repair**
44. **Nodetool**
45. **Quorum**
46. **Rolling restart**
47. **SEDA**
48. 

## Cassandra Algorithm
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTExMzYyODExMTAsLTg0NDEyNDI3MSwyMT
UxOTQzNjEsNTgyMTEzMTQyLC01NDc4OTE3NDUsMTk4Mjk1ODI5
Nyw4MjYwNDQxNDYsLTEyODI5NTk3NzQsLTQ5NjY3MzcwNSwtNT
Q3NzU0MDI4LC0xNTY5NDg0OTg1LC03MzA0NzczNzgsMTUzNTIx
Mjc0OSw2MTc4OTQ2OTYsLTE2NDMwNTk0NTFdfQ==
-->