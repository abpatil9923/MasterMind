### **Assignment – 20**

##### \##Changing Values through Views.



###### 1) Which of these views are updateable (will allow DML operations)?

1)

```
CREATE VIEW updateble_view1 AS SELECT DISTINCT cnum, snum, onum, odate FROM Orders;
```

 2)

```
CREATE VIEW updateble_view2 AS SELECT * FROM updateble_view1 WHERE odate=’03-OCT-1990’;
```



###### 2) Create a view of the Salespeople table called Commissions. This view will include only the snum and comm fields. Through this view, someone could enter
or change commissions, but only to values between .10 and .20.

```
CREATE VIEW commission AS SELECT snum, comm FROM salespeople WHERE comm BETWEEN 
.10 AND .20;
```



```

mysql> update commission set  comm = .15 where snum = 1001;

SELECT *
FROM commission;

```



###### 3) Some SQL implementations have a built-in constant representing the current date, sometimes called “CURDATE” or “SYSDATE”. The word CURDATE can therefore be used in a SQL statement, and be replaced by the current date when the value is accessed by commands such as Select or Insert. We will use a view of the Orders table called Entryorders to insert rows into the Orders table. Create the Orders table, so that CURDATE is automatically inserted for odate if no value is
given. Then create the Entryorders view so that no values can be given.



```
create table orders3( onum int(4),amt float(7,2),odate date , cnum int(4),snum int(4));
```

```
create view Entryorders AS select onum, amt, odate, cnum, snum from orders3;
```

```
insert into Entryorders values ('3002',8000,curdate(),1002,1003) ;
```

