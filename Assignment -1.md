### Assignment -1 

### Creating sample tables and inserting values.





###### query for create database

```
create database Shop;
```



###### query for set database 

```
 use shop;
```



###### query for create the table :

###### 1) SALESPEOPLE

```
create table SALESPEOPLE(
Snum int(4),
Sname varchar(10),
City varchar(10),
Comm float(3,2));
```



###### 2) CUSTOMERS

```
 create table CUSTOMERS(
 Cnum int(4),
 Cname varchar(10),
 City varchar(10),
 Rating int(4),
 Snum int(4));
```



######  3)ORDERS

```
create table ORDERS(
 Onum int(4),
 Amt float(7,2),
 Odate date ,
 Cnum int(4),
 Snum int(4));
```



###### query for show the all tables which are present in current database 

```
show tables;
```



###### query for insert value in to table : 

###### 1) SALESPEOPLE

```
insert into SALESPEOPLE (SNUM,SNAME,CITY,COMM)
values (1001,'Peel','London',.12),
(1002,'Serres','SanJose',.13),
(1004,'Motika','London',.11),
(1007,'Rifkin','Barcelona',.15),
(1003,'Axelrod','NewYork',.10);
```



###### 2) CUSTOMERS

```
insert into CUSTOMERS(CNUM,CNAME,CITY,RATING,SNUM)
values (2001,'Hoffman','London',100,1001),
(2002,'Giovanni','Rome',200,1003),
(2003,'Liu','San Jose',200,1002),
(2004,'Grass','Berlin',300,1002),
(2006,'Clemens','London',100,1001),
(2008,'Cisneros','San Jose',300,1007),
(2007,'Pereira','Rome',100,1004);
```



######  3)ORDERS

```
insert into ORDERS (ONUM,AMT,ODATE,CNUM,SNUM)
values(3001,18.69,'1990-10-03',2008,1007),
(3003,767.19,'1990-10-03',2001,1001),
(3002,1900.10,'1990-10-03',2007,1004),
(3005,5160.45,'1990-10-03',2003,1002),
(3006,1098.16,'1990-10-03',2008,1007),
(3009,1713.23,'1990-10-04',2002,1003),
(3007,75.75,'1990-10-04',2004,1002),
(3008,4723.00,'1990-10-05',2006,1001),
(3010,1309.95,'1990-10-06',2004,1002),
(3011,9891.88,'1990-10-06',2006,1001);
```



###### query for select the tables

```
select * from SALESPEOPLE;

select * from CUSTOMERS;

select * from ORDERS;
```

