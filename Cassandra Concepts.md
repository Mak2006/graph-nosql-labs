## Cassandra concepts

## History
Cassandra is a wide column distributed database, its originated from Facebook and later contributed to Apache open source.  It is distributed wide column database. 

## Salient points
1. **Problem statement** - How can we have  reliable distributed database holding big data, which may not be as consistent but available and partition tolerant. 
2. **Distributed database holding big data** - Big data is data too large for a single server. The issue how can we make database divided into two or more parts each on its own server having different network, yet the database behaves as a single database. 

## Concepts 
1. **Node** - A single Cassandra instance, this is on a machine. This machine may be on a separate  network and may contain other nodes. Two nodes can be geographically separated, altogether in a separate data center and be in separate networks. Nodes can see each other, that is each node is connected to other nodes, even though they may be separated.  
2. **Seeds**
3. **Gossip** - this is the protocol used by Nodes to talk to each other.
4. **Anti entropy**
5. **CAP theorem** Brewers theorem
6. **Paxos algorithm**
7. **Acid**
8. **Base**
9. **Bloom Filter**
10. **C**
11. **C cluster**
12. **CQL**
13. **C* yaml**
14. 

 
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTExMjMyNzI3MzEsMTUzNTIxMjc0OSw2MT
c4OTQ2OTYsLTE2NDMwNTk0NTFdfQ==
-->