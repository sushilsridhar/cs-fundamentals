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
