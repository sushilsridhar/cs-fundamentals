# Subqueries

readable and easily understandable than joins   
majority of the queries written via joins can be written via subquery   

```
select * from students where psp > (
  select psp from students where id = 3 );
```

<ins>IN</ins>   
```
select * from students where id IN ( 
  select id from instructors );
```

<ins>ALL</ins>      
```
select * from students where psp > (
  select max(psp) from students where b_id = 3 );
  

select * from students where psp > ALL (
  select psp from students where b_id = 3 );
```

<ins>Co-related subqueries</ins>      
```
select * from students s where psp > (
  select avg(psp) from students group by batch_id having batch_id = s.batch_id );
```

<ins>EXISTS</ins>       
returns true if any row present    
```
select * from students s where EXISTS (
  select student_id from TA where s.id = student_id );
```

<ins>Subqueries in select</ins>   
```
select id, name, bid, ( select avg(psp) from students group by bid having bid = s.bid) as avg_psp from students s;
```

<ins>Subqueries in from</ins>   
```
select s.name, i.name from (
  select s.id, s.name, b.name, i.id, i.name 
  from students s
  join batches b
  on s.bid = b.id
  join instructors i
  on b.inst.id = i.id );
```

# Views

> Virtual table created for read operation

![Screenshot 2022-12-29 at 5 29 01 AM](https://user-images.githubusercontent.com/16437905/209886654-a9b2b8b2-3287-4741-9fe4-459015e81979.png)

```
# creating view

create view order_product_customer
as select o.order_id, c.customer_id, c.first_name, c.points, p.product_id, p.name, p.unit_price, p.quantity_in_stock
from orders o 
inner join customers c
on o.customer_id = c.customer_id
inner join order_itemorder_product_customers oi
on o.order_id = oi.order_id
inner join products p 
on oi.product_id = p.product_id order by o.order_id;


# select data from view

select customer_id, order_id, first_name, name from order_product_customer;

```
