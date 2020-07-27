### Assignment – 12

#####  Using the operators IN, ANY, and ALL.



######  1) Write a query that selects all customers whose ratings are equal to or greater than ANY of Serres’.

```
SELECT * FROM customers WHERE rating >=ANY ( SELECT rating FROM customers WHERE snum IN
( SELECT snum FROM salespeople WHERE sname='serres' ) );
```



######  2) Write a query using ANY or ALL that will find all salespeople who have no customers located in their city. 

```
1)
SELECT snum FROM salespeople WHERE (snum,city) NOT IN (SELECT snum,city FROM customers);

2)
SELECT snum FROM salespeople WHERE (snum,city) !=all (SELECT snum,city FROM customers);

```



###### 3) Write a query that selects all orders for amounts greater than any for the customers in London.

```
SELECT * FROM orders WHERE amt > ANY ( SELECT amt FROM orders WHERE cnum IN ( SELECT cnum
FROM customers WHERE city='london' ) );
```



######  4) Write the above query using MIN or MAX. 

```
mysql> SELECT min(amt) FROM orders WHERE cnum IN ( SELECT cnum FROM customers WHERE cnum IN ( select cnum from customers where city = 'london'));
+----------+
| min(amt) |
+----------+
|   767.19 |
+----------+


mysql> SELECT max(amt) FROM orders WHERE cnum IN ( SELECT cnum FROM customers WHERE cnum IN ( select cnum from customers where city = 'london'));
+----------+
| max(amt) |
+----------+
|  9891.88 |
+----------+
```

   