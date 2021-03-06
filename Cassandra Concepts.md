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
![Overall process](https://i.imgur.com/M5VFrQ1.png)

**Overall process is to design the tables to serve the queries that is required.** 

1. Normal RDBMS modellign of data does not work in entirety and requires tweaking
	2.  Identify the entities
2. Some heuristics are 
	1. Enumerate all use-cases and their interdependencies. 
		1. What are the user cases and what data is required for the use case.
		2. Does the use case require other prior uses cases?
	2. Use the use cases to identify all queries the app will perform
		1. Determine type of query select / insert / update
		2. For each access, identify the inputs and the outputs
		3. For queries, the inputs become keys and the outputs become data columns 
	3. Use the queries to drive the table definitions
		1. We are likely to have one table for each of the types of query we have. 
		2. 
3.  Note we are  using de normalization, so when we upsert we are upserting into multiple tables. to maintain the relations. For examples users and user_creds are two tabls. Both have userid as the partition key. When a user is created we create a user_cred row as well. 
4. 
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

**What are the dependencies?**
We focus on the secondary use cases first. SU4 is dependent on SU1 or SU2.
SU1 is most common use case. 

What is the data required for each use case. 
```markdown
|                     | Access required   | inputs required                                 | output required |   |
|---------------------|-------------------|-------------------------------------------------|-----------------|---|
| SU1 -LOGIN          | READ ONLY, SELECT | USERID PASSWORD                               | none         |   |
| SU2 - User creation | INSERT            | USERID, PASSWORD, FIRSTNM, LAST NAMEM, EMAIL | USER ID         |   |
|                     |                   |                                                 |                 |   |
```

**Table definition for UC's**

|                     | Primary key | Primary key                                     | clustering columns | Other cols |   |
|---------------------|-------------|-------------------------------------------------|--------------------|------------|---|
| SU1 -LOGIN          | userid      | USERNAME PASSWORD                               |                    |            |   |
| SU2 - User creation | email       | USER NAME, PASSWORD, FIRSTNM, LAST NAMEM, EMAIL |                    |            |   |
|                     |             |                                                 |                    |            |   |


**More**
[https://24b4dt1v60e526bo2p349l4c-wpengine.netdna-ssl.com/wp-content/uploads/2015/11/Cassandra-NoSQL-Data-Model-Design-v1.0.pdf](https://24b4dt1v60e526bo2p349l4c-wpengine.netdna-ssl.com/wp-content/uploads/2015/11/Cassandra-NoSQL-Data-Model-Design-v1.0.pdf)  
 
 
## C* rdbms differences
```markdown
|   | C*  | RDBMS   |More info   |   |
|---|---|---|---|---|
|Insert   |Upsert   |Insert   |   |   |
|TABLE FOR EACH QUERY   | YES   | NO SO FINE  | c* WE ARE OK with denormalized data  |   |
|   |   |   |   |   |
``` 
![diff](https://i.imgur.com/HhfFhzo.png)

The procedure to model in C*
![](https://i.imgur.com/skRJICz.png)

ACID TRADITIONAL![](https://i.imgur.com/RHm6iUi.png)

ACID C*
![](https://i.imgur.com/Nz2oOID.png)
**Tunable consistency** It means you can choose the level of consitency required. 

CAP in c*
![](https://i.imgur.com/x7E3GTh.png)
C* isa thus an AP database by defulat. 

Without Joins how does C* handle data. In C*, we create tables specific to the queries required, redundant data is there in the table. Tables are denormalized. As such when upsert is made it is written to multiple tables. The primary keys are different and the data is same, inserted into two tables.
![](https://i.imgur.com/3dytiQl.png) 

Referential integrity is ensured by application development or DSE apache spark.
## Cassandra data types
1. SET -  un ordered, list of strings.
2. COUNTER - a SEQUENCE ID. We cannot insert a row with counter, we can only update.  -   Counters cannot be part of a primary key
-   Incrementing or decrementing counters is not idempotent
-   Incrementing or decrementing a counter is not always guaranteed to work - under high traffic situations, it is possible for one of these operations to get dropped
3. ata too large for a single server. The issue is the
<!--stackedit_data:
eyJoaXN0b3J5IjpbMjA1MzEyMjgxMiwtMjY4MzgwMjA1LC0xMz
U1OTg1MTcxLDExNzg1MjkzNTAsLTE0ODc5NTU1NjgsOTYxNzg2
MDI1LC04NDM5MTczMzIsLTY2NjYzNDg1NiwtNjY5NDA5ODE5LD
E0MjkwMDU0OTMsLTE5MTI1MTk5MDgsMjk0ODM2MTUxLC0yMTE5
NjAxMDA4LDE0NTQ3ODY1OCwxODUyNTg0MjQwLC0xNDI3NjE1Nz
csNjg5NDM2NzAxLDU4NzM1MTA5MCwtMTk5NTA4ODczOSwtNjY1
NTk3NDYyXX0=
-->