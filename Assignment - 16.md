### Assignment - 16

##### \##Creating Tables and Indexes.



###### 1) Write a command that will enable a user to pull orders grouped by date out of the Orders table quickly.

```
 create index  i_index on orders(odate);
 
 select count(onum),odate from group by odate;
```



###### 2) If the Orders table has already been created, how can you force the onum field to be unique (		assume all current values are unique)?

```
Alter table orders add unique(onum);
```



###### 3) Create an index that would permit each salesperson to retrieve his or her orders grouped by date   	quickly.'

```
 create index  i_index on orders(odate);
 
 select * from orders group by snum;
```



###### 4) Let us suppose that each salesperson is to have only one customer of a given rating, and that this   is currently the case. Enter a command that enforces it.

```
Alter table customers add primary key (rating);
```



