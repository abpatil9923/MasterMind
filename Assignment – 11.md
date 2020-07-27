### Assignment – 11

####  Subqueries.



###### 1)  Write a query that uses a subquery to obtain all orders for the customer named Cisneros. Assume you do not know his customer number (cnum).

```

mysql> select * from orders where cnum = ( select cnum from customers where cname = 'Cisneros');

+------+-------+------------+------+------+
| Onum | Amt   | Odate      | Cnum | Snum |
+------+-------+------------+------+------+
| 3001 | 18.69 | 1990-10-03 | 2008 | 1007 |
+------+-------+------------+------+------+

```



###### 2) Write a query that produces the names and ratings of all customers who have above-average orders.

```

mysql> SELECT cname, rating FROM customers WHERE cnum IN(SELECT cnum FROM orders WHERE amt > (SELECT avg(amt) FROM orders));
+---------+--------+
| cname   | rating |
+---------+--------+
| Clemens |    100 |
| Liu     |    200 |
+---------+--------+
```



###### 3)  Write a query that selects the total amount in orders for each salesperson for whom this total is  	  greater than the amount of the largest order in the table.

```

mysql> select sum(amt) from orders group by snum having sum(amt) > ( select max(amt) from orders );
+----------+
| sum(amt) |
+----------+
| 15382.07 |
+----------+  
```



######  

