### **Assignment - 21**

##### \##Grant and Revoke.



###### 1) Give Amit the right to change the ratings of the customers.

```

GRANT UPDATE ON customers TO Amit ;

--Grant succeeded
 
REVOKE UPDATE ON customers FROM Amit ;

 --Revoke succeeded.
```



###### 2) Give Manoj the right to give other users the right to query the Orders table.

```

GRANT SELECT ON orders TO sakshi WITH GRANT OPTION;

 --Grant succeeded.
 
GRANT update ON sakshi.orders TO prachi;

 --Grant succeeded.

```



###### 3) Take the INSERT privilege on Salespeople away from Ajita.

```
REVOKE INSERT ON salespeople FROM Ajita;
```



###### 4) Grant Abhijeet the right to insert or update the Customers table while keeping her possible rating values in the range of 100 to 500.

```

CREATE OR REPLACE VIEW range100 AS SELECT * FROM customers WHERE rating BETWEEN 100 AND 500 WITH CHECK OPTION;

 --View created.
 
GRANT UPDATE ON range100 TO Ajita;


INSERT INTO range100
VALUES(001,'rakesh','prachi',700,7888);

```





###### 5) Allow Vikram to query the Customers table, but restrict his access to those customers whose rating is the lowest.

```
create view not_low_rating AS ( select * from customers where rating  NOT IN (select min(rating) from customers));

 --View created.
 
GRANT SELECT ON not_low_rating TO Vikaram;
```