# CRUD   

<ins>Database</ins>
```
create database har;
drop database har;
```

<ins>Table</ins>
```
select * from sql_store.customers;

insert into sql_store.customers
(customer_id, first_name, last_name, birth_date, phone, address, city, state, points) 
values(default, 'James', 'bond', '1986-03-28', '8888888888', 'vurve', 'Aringliton', 'Texas', default); 

update sql_store.customers set points = '110' where customer_id = 22;
update sql_store.customers set customer_id = '20' where customer_id = 11;

delete from sql_store.customers where customer_id=20;
```

# Reading data

```
select 1, James; -> prints 1 James      
select *; -> error    
```

<ins>Perform operation on returned data</ins>   
```
select customer_id, first_name, concat(city, ": CITY"), points + 10 from sql_store.customers;
```

<ins>Rename column name in returned data</ins>
```
select customer_id, first_name, concat(city, ": CITY"), points + 10 as increasedpoints from sql_store.customers;
```

<ins>Return distinct</ins>
```
select distinct first_name, points from sql_store.customers;
```

<ins>Is mysql case sensitive?</ins>   
> case insensitive while performing operation       
> case sensitive while inserting data

> user is source of truth for databases
```
select * from sql_store.customers where first_name = 'JAMES'; -> return 3 values

first_name
james
JAmes
JAMES
```

<ins>Multiple conditions in where</ins>
```
select first_name, city, points from sql_store.customers where points * points < 100000;

select * from sql_store.customers where birth_date >='1985-01-01' AND points >= 2000;
select * from sql_store.customers where birth_date >='1985-01-01' OR points >= 2000;
select * from sql_store.customers where NOT(birth_date >='1985-01-01' AND points >= 1000);

select * from sql_store.customers where (birth_date >='1985-01-01' OR (points >= 2000 AND state = 'TX'));
```

<ins>IN</ins>
```
select * from sql_hr.employees where office_id IN (1, 2);
```
