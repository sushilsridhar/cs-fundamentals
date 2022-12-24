# Aggregates

Aggregate is grouping or combing values of multiple rows
```
select max(points) as max_points from customers;
select min(points) from customers;
select avg(points) from customers;
select sum(points) from customers;
select count(customer_id) from customers;
select count(distinct state) from customers;

select customer_number from orders group by customer_number order by count(order_number) desc limit 1;

```

<ins>Group by</ins>   
> combine selected rows to form different groups    

move few rows to group A and move few rows to group B and perform aggregate operation for group A and B individually,   

![Screenshot 2022-12-15 at 9 16 38 AM](https://user-images.githubusercontent.com/16437905/207767897-d7650af9-1834-4f34-93ec-af990cbb5e80.png)

<ins>Having</ins>   
> filtering on groups   

when we want to filter the results after grouping is done, use having   

```
select customer_id, count(order_id) from orders group by customer_id;
select status, count(order_id) from orders group by status;
select status, customer_id, count(order_id) from orders group by status, customer_id;

select invoice_id, sum(amount) from payments group by invoice_id having sum(amount) > 40;
```

# Built-in Functions

<ins>Functions</ins>    

```
MOD
select id, movie, description, rating from cinema where MOD(id, 2) != 0 and description != 'boring' order by rating desc;
```
```
IFNULL return 0 

select q.id, q.year, IFNULL(n.npv, 0) as npv from queries q left join npv n on q.id = n.id and q.year = n.year;
```
<ins>Date and time</ins>    
```
select now();
select curdate();
select curtime();

select year(curdate());
select month(now());
select dayname(now());

select date_add(curdate(), interval 1 day);
select date_add(now(), interval 10 minute);
select date_sub(now(), interval 1 day);


select * from invoices where invoice_date >= date_sub(now(), interval 4 year);

select * from invoices where invoice_date >= date_add(payment_date, interval 5 month);

select * from invoices where datediff(payment_date, invoice_date) >= 2;
```
