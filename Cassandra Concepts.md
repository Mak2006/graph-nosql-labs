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
		1. For each use-case, determine the database access you will need to support the use-case
		2. For each access, identify the inputs and the outputs
		3. For queries, the inputs become keys and the outputs become data columns 
	3. Use the queries to drive the table definitions
3. 
### Data modelling example 
For killrvideo what are the use cases
1. Primary use cases 
	2. MU1 -  get all my videos
	3. MU2 - See the comments on my videos
	4. MU3 - get to see other videos - recommended for me
	5. MU4 - Search for a video and see the results 
	6. MU5 - have a list of friends
	7. MU6 - have favorites list etc. 
	8. 
2. Secondary use cases
	3. SU1 - Login
	4. SU4 - Account maintenance
	5. SU2 - User creation
	6. SU3 - Friend list  

What are the dependencies?
We focus on the secondary use cases first. SU4 is dependent on SU1 or SU2.
SU1 is most common use case. 

What is the data required for each use case. 
SU1 - LOGIN - USER NAME , PASSWORD , retrieve. 

 

## C* rdbms differences
```markdown
|   | C*  | RDBMS   |More info   |   |
|---|---|---|---|---|
|Insert   |Upsert   |Insert   |   |   |
|   |   |   |   |   |
|   |   |   |   |   |
``` 


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE5OTUwODg3MzksLTY2NTU5NzQ2Miw4MT
ExNjY0NzEsLTU3Nzg5NDE3NSwtMTEzNjI4MTExMCwtODQ0MTI0
MjcxLDIxNTE5NDM2MSw1ODIxMTMxNDIsLTU0Nzg5MTc0NSwxOT
gyOTU4Mjk3LDgyNjA0NDE0NiwtMTI4Mjk1OTc3NCwtNDk2Njcz
NzA1LC01NDc3NTQwMjgsLTE1Njk0ODQ5ODUsLTczMDQ3NzM3OC
wxNTM1MjEyNzQ5LDYxNzg5NDY5NiwtMTY0MzA1OTQ1MV19
-->