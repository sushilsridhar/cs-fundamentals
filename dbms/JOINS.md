# Why Joins?

Student and Batch are two separate tables, if you want to get the student names along with their batch name, without joins,     
we need to fetch and iterate over students, use the batch id in the students table, make another network call to get batch details from batch table,      

[Latency Numbers](https://gist.github.com/jboner/2841832)

> two network calls is costly, instead we can join at the database end itself and get joined data   

![Screenshot 2022-12-09 at 12 13 44 PM](https://user-images.githubusercontent.com/16437905/206965641-dabf92ee-011c-485a-8aed-ca05078adbd8.png)

![Screenshot 2022-12-09 at 12 13 52 PM](https://user-images.githubusercontent.com/16437905/206965651-2575b6d1-3324-4603-96bb-23e9a0d98266.png)

![Screenshot 2022-12-12 at 11 24 56 AM](https://user-images.githubusercontent.com/16437905/206970649-dc328fad-8b53-4d4a-98f1-68e5e3a436a9.png)

# Inner Join or Join

same customer id should be present on both tables,    
if customer id from one row of a table is null or doesn't match, that row is ignored from results

```
select o.order_id, c.customer_id, o.status, o.shipped_date, c.first_name, c.phone 
from customers c
join orders o
on c.customer_id = o.customer_id;
```
<ins>Self join</ins>    
inner join with self       

```
select e.first_name, m.first_name
from employees e 
join employees m 
on e.reports_to = m.employee_id;
```

<ins>Delete query with self join</ins>    
```
delete p1 from person p1 inner join person p2 on p1.email = p2.email and p1.id > p2.id;
```

# Outer Join

<ins>left join</ins>  
include all rows from the left table, include rows from right table and merge rows only if conditions match    
```
select e.first_name, o.city
from employees e 
left join offices o
on e.office_id = o.office_id;
```

<ins>right join</ins>   
include all rows from the right table, include rows from left table and merge rows only if conditions match        
```
select e.first_name, o.city
from employees e 
right join offices o
on e.office_id = o.office_id;
```

<ins>full join</ins>        
include all rows from left and right table, merge them to one row if condition matches else keep the merged column value null       
union of left join and right join   

```
select e.first_name, o.city
from employees e 
left join offices o
on e.office_id = o.office_id
union
select e.first_name, o.city
from employees e 
right join offices o
on e.office_id = o.office_id;
```

<ins>Using clause</ins>   
if the column name of the tables that is used for condition is same, we can use using clause    
```
select e.first_name, o.city
from employees e 
right join offices o
using (office_id);
```

# Natural join - just clean syntax
same as other joins, but if the column name of the tables that is used for condition is same, we can totally skip using on or using keyword,   
instead do a natural join   

```
select e.first_name, o.city
from employees e 
natural right join offices o;

select e.first_name, o.city
from employees e 
natural join offices o;
```

# Cross join

inner join with no condition, all different combinations of rows in two tables

![Screenshot 2022-12-12 at 12 59 14 PM](https://user-images.githubusercontent.com/16437905/206986002-134912bb-e8dd-4e75-8f5b-635a77053a9e.png)

![Screenshot 2022-12-12 at 1 02 30 PM](https://user-images.githubusercontent.com/16437905/206986992-bb4d5e32-1fef-4c18-a2df-a5bfcf717fbe.png)

```
select e.first_name, o.city
from employees e 
cross join offices o;
```

