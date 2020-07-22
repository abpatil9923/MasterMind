### Assignment –7

##### Summarizing Data with Aggregate Functions.



######  1) Write a query that counts all orders for October 3.

```
mysql> select count(*) from orders;
+----------+
| count(*) |
+----------+
|       11 |
+----------+
```



######  2) Write a query that counts the number of different non-NULL city values in the Customers table.



```
mysql> select count(*) from customers where city is NOT NULL;

+-------------+
| count(city) |
+-------------+
|           7 |
+-------------+
```



######  3) Write a query that selects each customer’s smallest order.



```
mysql> SELECT min(amt) "smallest order",cnum FROM orders GROUP BY cnum;

+----------------+------+
| smallest order | cnum |
+----------------+------+
|          18.69 | 2008 |
|         767.19 | 2001 |
|        1900.10 | 2007 |
|        5160.45 | 2003 |
|        1713.23 | 2002 |
|          75.75 | 2004 |
|        4723.00 | 2006 |
|           NULL | 2009 |
+----------------+------+
```



######  4) Write a query that selects the first customer, in alphabetical order, whose name begins with G.

```
mysql> select * from customers where cname like "G%" order by cname;

+------+----------+--------+--------+------+
| Cnum | Cname    | City   | Rating | Snum |
+------+----------+--------+--------+------+
| 2002 | Giovanni | Rome   |    200 | 1003 |
| 2004 | Grass    | Berlin |    300 | 1002 |
+------+----------+--------+--------+------+
```





######  5) Write a query that selects the highest rating in each city.

```
mysql> select max(rating) from customers group by rating;

+-------------+
| max(rating) |
+-------------+
|         400 |
+-------------+
```





######  6) Write a query that counts the number of salespeople registering orders for each day.(If a salesperson has more than one order on a given day, he or she should be counted only once.).

```
mysql> SELECT count(odate),odate FROM orders group by odate;
+--------------+------------+
| count(odate) | odate      |
+--------------+------------+
|            5 | 1990-10-03 |
|            2 | 1990-10-04 |
|            1 | 1990-10-05 |
|            2 | 1990-10-06 |
|            1 | 1990-10-07 |
+--------------+------------+
```





