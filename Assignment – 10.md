### Assignment – 10

#### Joining a Table to Itself.





###### 1) Write a query that produces all pairs of salespeople who are living in the same city. 	  	Exclude combinations of salespeople with themselves as well as duplicate rows with
	the order reversed.



```
mysql> select m.sname, n.sname,m.city  from salespeople m, salespeople n where m.city = n.city and m.sname > n.sname;
+-------+--------+--------+
| sname | sname  | city   |
+-------+--------+--------+
| Peel  | Motika | London |
+-------+--------+--------+
```



###### 2) Write a query that produces the names and cities of all customers with the same rating  	as Hoffman.

```
mysql> select  cname,city from customers where rating = (select rating from customers where cname = 'Hoffman');

+---------+--------+
| cname   | city   |
+---------+--------+
| Hoffman | London |
| Clemens | London |
| Pereira | Rome   |
+---------+--------+
```









