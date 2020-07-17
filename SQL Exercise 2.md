### SQL Exercise 2



###### 1 )  Display the Supplier table in the descending order of CITY?

```
select * from Supplier order by city desc;

+------+-------+--------+--------+
| S_id | Sname | status | City   |
+------+-------+--------+--------+
| s1   | ram   | 20     | pune   |
| s3   | sita  | 10     | nashik |
| s2   | sham  | 30     | Abad   |
+------+-------+--------+--------+
```



###### 2) Display the Part Table in the ascending order of CITY and within the city in the ascending order of      Part names. 





###### 3)  Display all the Suppliers with a status between 10 and 20.

```
mysql> select * from Supplier where status between 10 and 20;
+------+-------+--------+--------+
| S_id | Sname | status | City   |
+------+-------+--------+--------+
| s1   | ram   | 20     | pune   |
| s3   | sita  | 10     | nashik |
+------+-------+--------+--------+
```



###### 4) Display all the Parts and their Weight, which are not in the range of 10 and 15. 

```
select weight from parts where weight < 10 or  weight >15;
+--------+
| weight |
+--------+
| 20     |
| 40     |
| 30     |
+--------+
```



###### 5) Display all the Part names starting with the letter ‘S’.

```
mysql> select  pname from parts where  LEFT(pname,1) = "s";

+-------+
| pname |
+-------+
| s     |
+-------+
```



###### 6) Display all the Suppliers, belonging to cities starting with the letter ‘p’. 



```
mysql> select * from supplier where Left(city,1) = "p";

+------+-------+--------+------+
| S_id | Sname | status | City |
+------+-------+--------+------+
| s1   | ram   | 20     | pune |
+------+-------+--------+------+
```





###### 7) Display all the Projects, with the third letter in JNAME as ‘y’. 

```
mysql> select  * from projects where  LEFT(jname,1) = 'y';

+------+-------+------+
| J_id | Jname | City |
+------+-------+------+
| j2   | yyy   | Abad |
+------+-------+------+
```



