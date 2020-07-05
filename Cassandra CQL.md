## CQL commands

### Meta commands
`Describe keyspace keyspaceName`


### Create commands

```
//Basic syntax
CREATE TABLE killrvideo.users (
//  colName datatype,
    userid uuid,
    firstname text, 
    lastname text, 
    email text,
    created_date timestamp,
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


> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTUwMzc5NDU4NiwzOTM3MTIwMDBdfQ==
-->