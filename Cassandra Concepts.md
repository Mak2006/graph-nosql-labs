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
6. **Seeds**, **Seed node**
7. **Data types** Set, Map 	
8. **Hashing**
9. **Consistency Level**
10. **Replication Level**
11. **Sharding Shard**
12. **Keyspace**
13.  **Key cache**
14. **Memtable** 
15.  **SSTable**
16. **Gossip** - this is the protocol used by Nodes to talk to each other.
17. **Anti entropy**
18. **CAP theorem** Brewers theorem **Eventual consistency**
19. **Paxos algorithm**
20. **Hotspot**
21. **Acid**
22. **Base**
23. **Bloom Filter**
24. **C**
25. **C cluster**
26. **CQL**
27. **cqlsh**
28. **C* yaml**
29. **Token**
30. **Ring**
31. **Data center** **Rack**
32. **Primary Key**
33. **Clustering column**
34. **Commit Log**
35. **Compaction**
36. **Node repair**
37. **Nodetool**
38. **Quorum**
39. **Rolling restart**
40. **SEDA**
41. 

## Cassandra Algorithm
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTQ5NjY3MzcwNSwtNTQ3NzU0MDI4LC0xNT
Y5NDg0OTg1LC03MzA0NzczNzgsMTUzNTIxMjc0OSw2MTc4OTQ2
OTYsLTE2NDMwNTk0NTFdfQ==
-->