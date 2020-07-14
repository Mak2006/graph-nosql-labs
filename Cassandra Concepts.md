## Cassandra concepts

## History
Cassandra is a wide column distributed database, its originated from Facebook and later contributed to Apache open source.  It is distributed wide column database. 

## Salient points
1. **Problem statement** - How can we have  reliable distributed database holding big data, which may not be as consistent but available and partition tolerant. 
2. **Distributed database holding big data** - Big data is defined using the V's. For our purpose it is that data which is too large for a single server. The issue then is how can we make database divided into two or more parts each on its own server having different network, yet the database behaves as a single database. 

## Concepts  and Story
 - **Node** - A single Cassandra instance, this is on a machine. This machine may be on a separate  network and may contain other nodes. Two nodes can be geographically separated, altogether in a separate data center and be in separate networks. Nodes can see each other, that is each node is connected to other nodes, even though they may be separated.  
 - **Algorithm** - the key algorithm of cassandra is then 
	1. Distribute the data accross different nodes, each node has a part of the data. These data parts are called partitions. Partitions are based on some key using which we can divide the data. To maintain failover, the nodes also have additional responsibility of having other partitions as well.  
 - **Partition Key** - In C*, a partition key is required to be defined. It is consists of at least on column. So when a row comes in, the **Partitoner**, uses a hash function on the value of the column and creates a **Token**. The all possible values of these token is the **token range**.  Each of the nodes now are designated to hold data for a subset of the total token range. The Partitioners pushes the data to that node designated for that token range.  Partition key is at least a single column. It can be multiple columns as well. Casssandra hashes the full partition key to retrieve a partition. This has implied consequences:

Retrieving a single partition is very fast. Retrieving multiple partitions will be slower Partition keys have no inherent order, so  you cannot perform "greater than" or "less than" types of operations    on partition keys

 - **Partition index** - An on-disk data structure for SSTables which lists partition keys, their file offset position for each keys' corresponding partition in the SSTable.
 - **Partition** - A section of the data.  Part of a table
 - **Partitioner** - The one that decides which partition the data goes in. The default program is the **Murmur3Partitioner**, other is **RandomPartitioner**
 - **Token** - One hash of a row, calculated by the partitioner
 - **Token range** - The range of possible tokens possible. This is subset of partition range.
 - **Clustering columns** - this defines the storage order within partitions. Since Cassandra orders the rows within a partition based on clustering columns, you can perform "greater than" or "less than" operations on clustering columns after you specify the partition key
10.**Sparse tables** - Tables where some cells may not have data.
10.**Ordering columns** -  
 - **SSTable**
 - **Memtable** 
 - **Snitch**
 - **Seeds**, **Seed node**
 - **Data types** Set, Map 	
 - **Hashing**
 - **Consistency Level**
 - **Replication Level**
 - **Replication strategy**
 - **Sharding Shard**
 - **Keyspace**
 -  **Key cache**
 - **Ring** the sequence of nodes
 -  **Sharding**
 - **Gossip** - this is the protocol used by Nodes to talk to each other.
 - **Anti entropy**
 - **CAP theorem** Brewers theorem **Eventual consistency**
 - **Paxos algorithm**
 - **Hotspot**
 - **Acid**
 - **Base**
 - **Bloom Filter**
 - **C**
 - **C cluster**
 - **CQL**
 - **cqlsh**
 - **C* yaml**
 - **Token**
 - **Ring**
 - **Data center** **Rack**
 - **Primary Key**
 - **Clustering column**
 - **Commit Log**
 - **Compaction**
 - **Node repair**
 - **Nodetool**
 - **Quorum**
 - **Rolling restart**
 - **SEDA**
 - **Upsert - C* Inserts** - Insert inserts teh data, if the data is there, it updates. What is not evident is it does not read the data prior to insert. This is an **Upsert**
 - 

## Cassandra Algorithms
### Read 
### Write

## Cassandra data modelling 
1. Normal RDBMS modellign of data does not work
2. some heuristics are 
	1. Enumerate all use-cases and their interdependencies. 
		1. What are the user cases and what data is required for the use case.
		2. Does the use case require other prior uses cases?
	2. Use the use cases to identify all queries the app will perform
	3. Use the queries to drive the table definitions
3. 
### Data modelling example 
For killrvideo what are the use cases
1. Primary use cases 
	2. MU1 -  get all my videos
	3. MU2 - See the comments on my videos
	4. MU3 - get to see other videos - recommended for me
	5. MU4 - Search for a video and see the results 
	6. 
2. Secondary use cases
	3. SU1 - Login and account maintenance
	4. SU2 - 

## C* rdbms differences
```markdown
|   | C*  | RDBMS   |More info   |   |
|---|---|---|---|---|
|Insert   |Upsert   |Insert   |   |   |
|   |   |   |   |   |
|   |   |   |   |   |
``` 


<!--stackedit_data:
eyJoaXN0b3J5IjpbMTAzMjg2NzYzNiwtNjY1NTk3NDYyLDgxMT
E2NjQ3MSwtNTc3ODk0MTc1LC0xMTM2MjgxMTEwLC04NDQxMjQy
NzEsMjE1MTk0MzYxLDU4MjExMzE0MiwtNTQ3ODkxNzQ1LDE5OD
I5NTgyOTcsODI2MDQ0MTQ2LC0xMjgyOTU5Nzc0LC00OTY2NzM3
MDUsLTU0Nzc1NDAyOCwtMTU2OTQ4NDk4NSwtNzMwNDc3Mzc4LD
E1MzUyMTI3NDksNjE3ODk0Njk2LC0xNjQzMDU5NDUxXX0=
-->