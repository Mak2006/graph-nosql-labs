## Cassandra concepts

## History
Cassandra is a wide column distributed database, its originated from Facebook and later contributed to Apache open source.  It is distributed wide column database. 

## Salient points
1. **Problem statement** - How can we have  reliable distributed database holding big data, which may not be as consistent but available and partition tolerant. 
2. **Distributed database holding big data** - Big data is data too large for a single server. The issue how can we make database divided into two or more parts each on its own server having different network, yet the database behaves as a single database. 

## Concepts 
1. **Node** - A single Cassandra instance, this is on a machine. This machine may be on a separate  network and may contain other nodes. Two nodes can be geographically separated, altogether in a separate data center and be in separate networks. Nodes can see each other, that is each node is connected to other nodes, even though theymay be separeated.  
2. 
<!--stackedit_data:
eyJoaXN0b3J5IjpbMjkyNzMxOTQ4LDE1MzUyMTI3NDksNjE3OD
k0Njk2LC0xNjQzMDU5NDUxXX0=
-->