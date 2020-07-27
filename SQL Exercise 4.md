#### SQL Exercise 4 

###### 1) Display the minimum Status in the Supplier table. 

```
mysql> select min(status) from supplier;
+-------------+
| min(status) |
+-------------+
| 10          |
+-------------+
```



###### 2) Display the maximum Weight in the Parts table. 

```
mysql> select max(weight) from parts

+-------------+
| max(weight) |
+-------------+
| 42          |
+-------------+
```



###### 3) Display the average Weight of the Parts. 

```

mysql> select avg(weight) from parts;

+-------------+
| avg(weight) |
+-------------+
|          33 |
+-------------+
```



###### 4)  Display the total Quantity sold for part ‘P1’. 

```

```



###### 5) Display the total Quantity sold for each part. 



```

```



###### 6) Display the average Quantity sold for each part. 

```

```



###### 7) Display the maximum Quantity sold for each part, provided the maximum Quantity is greater than 800. 

```

```



###### 8) Display the Status and the count of Suppliers with that Status. 

```

mysql> select count(s_id) " count of suppliers ",status from supplier group by s_id;

+---------------------+--------+
| count of suppliers  | status |
+---------------------+--------+
|                   1 | 20     |
|                   2 | 30     |
|                   1 | 10     |
+---------------------+--------+
```



###### 9) Display the count of Projects going on in different cities.

```
 mysql> select city, count(j_id) " projects " from projects group by city;
+---------+-----------+
| city    | projects  |
+---------+-----------+
| pune    |         1 |
| Abad    |         1 |
| nashik  |         1 |
| Pachora |         1 |
+---------+-----------+
```



###### 10) What is the difference between COUNT(Status) and COUNT(*) ? 



- count ( status ) will return the count  of status rows except null
- count ( * ) will return the count of row along with all column



```
mysql> select count(*) from supplier;
+----------+
| count(*) |
+----------+
|        4 |
+----------+
1 row in set (0.00 sec)

mysql> select count(status) from supplier;
+---------------+
| count(status) |
+---------------+
|             3 |
+---------------+ 
```



###### 11) Display the Status and the Count of Suppliers with that Status in the following format as shown below:- 



  Status       Count

  Ten              1 

  Twenty        2 

  Thirty           3 



select  cast(status as varchar( 20 )) , count( s_id)  " count " from supplier group by status;