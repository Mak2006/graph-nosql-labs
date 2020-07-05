### CQL commands

##Create command

```
CREATE TABLE keyspName.tablName (
  userid uuid,
  added_date timestamp,
  videoid uuid,
  name text,
  preview_image_location text,
  PRIMARY KEY ((userid), added_date, videoid)
  ... // Nasty boilerplate code omitted here
);
```


> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTEwNTg4NDI1NiwzOTM3MTIwMDBdfQ==
-->