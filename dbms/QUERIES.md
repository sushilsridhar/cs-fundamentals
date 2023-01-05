# CRUD   

<ins>Database</ins>
```
create database har;
drop database har;
```

<ins>Table</ins>
```
create table students (
    student_id int primary key,
    first_name varchar(20),
    last_name varchar(20)
);

drop table students;

alter table students add batch_id int;

create table batches (
    batch_id int primary key,
    name varchar(20)
);

alter table students 
    add constraint student_batch_id foreign key(batch_id) 
    references batches(batch_id);
```
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

<ins>Logical and Relational operations</ins>
```
select first_name, city, points from sql_store.customers where points * points < 100000;

select * from sql_store.customers where birth_date >='1985-01-01' AND points >= 2000;
select * from sql_store.customers where birth_date >='1985-01-01' OR points >= 2000;
select * from sql_store.customers where NOT(birth_date >='1985-01-01' AND points >= 1000);

select * from sql_store.customers where (birth_date >='1985-01-01' OR (points >= 2000 AND state = 'TX'));

<> is same as !=
select name from customer where referee_id <> 2 or referee_id IS NULL;
```

<ins>IN</ins>
```
select * from sql_hr.employees where office_id IN (1, 2);
```

<ins>Between a range</ins>    
inclusive of 1000 and 2000
```
select * from sql_store.customers where points between 1000 and 2000;
```

<ins>Like</ins>       
% -> any character can be present, %bond% means any character can be present before and after bond    
_ -> only single character should be present, \_bond% means only single character should be present before bond   

```
select * from sql_store.customers where last_name like '%bond%';

select patient_id, patient_name, conditions from patients where conditions like 'DIAB1%' or conditions like '% DIAB1%';
```

<ins>Is null?</ins>   
do not use phone = null, use IS NULL  
```
select * from sql_store.customers where phone IS NULL;

select * from sql_store.customers where phone IS NOT NULL;
```

<ins>Order by</ins>   
```
select * from sql_store.customers order by state desc, customer_id desc;

sort by state first, sort the result again by last_name,
select * from sql_store.customers order by state, last_name;
```

<ins>Limit</ins>  
return highest 5 points 
```
select * from sql_store.customers order by points desc LIMIT 5;
```
