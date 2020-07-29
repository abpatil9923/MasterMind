### **Assignment – 19**

#### \##Views.



###### 1) Create a view t_hat shows all of the customers who have the highest ratings.

```
CREATE VIEW h_rating * FROM customers WHERE rating=(SELECT max(rating)
 FROM customers);
```

```
SELECT * FROM h_rating;
```



###### 2) Create a view that shows the number of salespeople in each city.

```

CREATE VIEW no_salpeople_city AS SELECT city, count(city) "NO. OF SALES PEOPLE" FROM salespeople GROUP BY city;

 --View created.

SELECT * FROM no_salpeople_city;
```




###### 3) Create a view that shows the average and total orders for each salesperson after his or her name. Assume all names are unique.

```
CREATE VIEW AV_TOT_SAL AS SELECT sname,avg(onum) AVERAGE,count(onum) "TOTAL ORDERS"
FROM salespeople JOIN orders using(snum) GROUP BY sname;

 --View created.
 
SELECT * FROM AV_TOT_SAL;
```



###### 4) Create a view that shows each salesperson with multiple customers.

```
CREATE VIEW s_w_cut AS SELECT sname,cname FROM salespeople s JOIN customers c where s.snum = c.snum ;

 --View created.

SELECT * FROM s_w_cut;
```




