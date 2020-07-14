## CQL commands

### Meta commands
// Describe the schema of the keyspace and tables 
// format DESCRIBE RES_TYPE NAME
`DESCRIBE keyspace killrvideo;`
`Describe table killrvideo.video_recommendations;`



### Create commands
**Create keyspace**
```
CREATE  KEYSPACE [IF NOT EXISTS] keyspace_name 
   WITH REPLICATION = { 
      'class' : 'SimpleStrategy', 'replication_factor' : N } 
     | 'class' : 'NetworkTopologyStrategy', 
       'dc1_name' : N [, ...] 
   }
   [AND DURABLE_WRITES =  true|false] ;
```

**Create syntax**
```
//Basic syntax
CREATE TABLE killrvideo.users (
//  colName datatype,
    userid uuid,
    firstname text, 
    email text,
    created_date timestamp,
    tags set<text>,       # a set element example
    PRIMARY KEY (userid)
) {optional WITH statement};
 
```
A full blown create statement

```
CREATE TABLE keyspName.tablName (
//  colName datatype,
    videoid uuid,
    views counter,
    PRIMARY KEY (videoid)
) WITH 
// Bunch of parameters for Cassandra 

read_repair_chance = 0.0
    AND dclocal_read_repair_chance = 0.0
    AND gc_grace_seconds = 864000
    AND bloom_filter_fp_chance = 0.01
    AND caching = { 'keys' : 'ALL', 'rows_per_partition' : 'NONE' }
    AND comment = ''
    AND compaction = { 'class' : 'org.apache.cassandra.db.compaction.SizeTieredCompactionStrategy', 'max_threshold' : 32, 'min_threshold' : 4 }
    AND compression = { 'enabled' : 'false' }
    AND default_time_to_live = 0
    AND speculative_retry = 'NONE'
    AND min_index_interval = 128
    AND max_index_interval = 2048
    AND crc_check_chance = 1.0
    AND cdc = false
    AND memtable_flush_period_in_ms = 0
    AND nodesync = { 'enabled' : 'true', 'incremental' : 'true' };

```

Another example 

```

CREATE TABLE killrvideo.video_recommendations (
    userid uuid,
    added_date timestamp,
    videoid uuid,
    authorid uuid,
    name text,
    preview_image_location text,
    rating float,
    PRIMARY KEY (userid, added_date, videoid)
) WITH CLUSTERING ORDER BY (added_date DESC, videoid ASC)

```
**Partition key** is userid 
**Clustering colums** are added data and videoid and 
**Ordering colums -** added_date DESC, videoid ASC  - ordering columns

### Insert commands
```
INSERT INTO killrvideo.users (userid, firstname, lastname, email, created_date)+
  VALUES(uuid(), 'Jeff', 'Carpenter', 'jc@datastax.com', toTimestamp(now()));
```

if you want to insert with a specific key **(insert will now update)**

`INSERT INTO killrvideo.users (userid, firstname, lastname, email, created_date)
  VALUES(11111111-1111-1111-1111-111111111111, 'Jeff', 'Carpenter', 'jc@datastax.com', toTimestamp(now()));`
  
// Inserting a set. tags is a set
INSERT INTO killrvideo.videos (videoid, tags)
  VALUES(12121212-1212-1212-1212-121212121212 , {'Favorite', 'Fast-paced', 'Funny'});

### Select statements
`SELECT * FROM killrvideo.video_recommendations;` // Note - select is not a good practice and select must have the partition key in the where, else C* has to do a FTS.

`SELECT * FROM killrvideo.video_recommendations where userid = 11111111-1111-1111-1111-111111111111;`

[a sample](https://i.imgur.com/3eCVr1Q.png)
<!--stackedit_data:
eyJoaXN0b3J5IjpbNzg1OTgzMzU3LC0zODAyNDUwNDcsLTY4Nz
k2MDM5NSwyMDEwMDcwODczLC0yMTMzMjYwNzEyLDEyOTU2NDA3
MTIsLTIwMzY3NDUwNDEsLTM0MDgzMzcxOSw0OTgzOTMxMTIsLT
cwNzE4ODQwMCwyMDY4MjY2Mzg1LC02NTQ4MjA0OTksMTUwMzc5
NDU4NiwzOTM3MTIwMDBdfQ==
-->