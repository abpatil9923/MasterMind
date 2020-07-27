### Assignment – 9

#### Querying Multiple Tables at Once.





###### 1) Write a query that lists each order number followed by the name of the customer who made the order.



```

mysql> SELECT onum,cname FROM orders o,customers c WHERE c.cnum=o.cnum ;
+------+----------+
| onum | cname    |
+------+----------+
| 3009 | Giovanni |
| 3007 | Grass    |
| 3008 | Clemens  |
| 3010 | Grass    |
| 3011 | Clemens  |
| 3012 | atul     |
| 3001 | Cisneros |
| 3002 | Hoffman  |
| 3003 | Pereira  |
| 3004 | Liu      |
+------+----------+

```



###### 2) Write a query that gives the names of both the salesperson and the customer for each order along with the order number.



```
SELECT sname,cname,onum FROM orders o,customers c,salespeople s WHERE o.snum = c.snum
AND o.snum = s.snum;
```



###### 3) Write a query that produces all customers serviced by salespeople with a commission above 12%.    	Output the customer’s name, the salesperson’s name,and the salesperson’s rate of commission.



```
mysql> select cname,sname,comm*100 " rate of commission " from customers c , salespeople s  WHERE   c.snum=s.snum  and s.comm > .12;

+----------+--------+---------------------+
| cname    | sname  | rate of commission  |
+----------+--------+---------------------+
| Liu      | Serres |               13.00 |
| Grass    | Serres |               13.00 |
| Cisneros | Rifkin |               15.00 |
+----------+--------+---------------------+
```



###### 4) Write a query that calculates the amount of the salesperson’s commission on each order by a customer with a rating above 100.



```
1)
select  amt, comm from  salespeople s,customers c, order o  where   o.snum = c.snum
AND o.snum = s.snum and rating  > 100;

2)
SELECT amt,comm FROM salespeople JOIN customers using(snum) JOIN orders using(snum) WHERE rating>100;


```









