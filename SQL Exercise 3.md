## SQL Exercise 3



###### 1) Display all the Supplier names with the initial letter capital. 

```
mysql> select concat(upper(substr(sname,1,1)),lower(substr(sname,2))) from supplier;

+---------------------------------------------------------+
| concat(upper(substr(sname,1,1)),lower(substr(sname,2))) |
+---------------------------------------------------------+
| Ram                                                     |
| Sham                                                    |
| Sita                                                    |
| Lara                                                    |
+---------------------------------------------------------+
```



###### 2) Display all the Supplier names in upper case. 

```
mysql> select  upper(sname) from supplier;
+--------------+
| upper(sname) |
+--------------+
| RAM          |
| SHAM         |
| SITA         |
+--------------+
```



###### 3 ) Display all the Supplier names in lower case. 

```
mysql> select  lower(sname) from supplier;
+--------------+
| lower(sname) |
+--------------+
| ram          |
| sham         |
| sita         |
+--------------+
```



###### 4 ) Display all the Supplier names padded to 25 characters, with spaces on the left.  

```
 mysql> select  lpad(sname,25,' ') from supplier;
+---------------------------+
| lpad(sname,25,' ')        |
+---------------------------+
|                       ram |
|                      sham |
|                      sita |
+---------------------------+
```



###### 5) Display all the Supplier names (with ‘la’ replaced by ‘ro’). HINT: REPLACE. 

```
mysql> select replace(sname,'la','ro') from supplier;
+--------------------------+
| replace(sname,'la','ro') |
+--------------------------+
| ram                      |
| sham                     |
| sita                     |
| rora                     |
+--------------------------+
```



###### 6)  Implement the above command such that ‘l’ is replaced with ‘r’ and ‘a’ is replaced with ‘o’



```
mysql> select replace(replace(sname,'l','r'),'a','o') from supplier;
+-----------------------------------------+
| replace(replace(sname,'l','r'),'a','o') |
+-----------------------------------------+
| rom                                     |
| shom                                    |
| sito                                    |
| roro                                    |
+-----------------------------------------+
```



###### 7) Display the Supplier names and the lengths of the names. 

```
mysql> select sname,length(sname) from supplier;

+-------+---------------+
| sname | length(sname) |
+-------+---------------+
| ram   |             3 |
| sham  |             4 |
| sita  |             4 |
| lara  |             4 |
+-------+---------------+
```



8) . Use the soundex function to search for a supplier by the name of ‘BLOKE’



```
mysql> select * from supplier where soundex(sname) = soundex('lar');

+------+-------+--------+--------+
| S_id | Sname | status | City   |
+------+-------+--------+--------+
| s4   | lara  | 2      | mumbai |
+------+-------+--------+--------+
```

