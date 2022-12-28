# Indexes

Indexing is all about minimizing disk access

<ins>Faster READ</ins>    
> prevents unneccessary disk fetches    

> leads to faster queries   

<ins>Slower WRITE</ins>       
> indexes are updated durning writes, which makes writes slower   
> indexes are updated for all C|U|D queries       

> extra storage required to store index tables    

<ins>When to create indexes?</ins>    

Do not create indexes when table is created, create only after analyzing the performance and load on that query,    

create it only when you see a latency with a particular query or there is more load on a particular query, and you want to improve performance,   

```
select * from students where batch_id = 1;    
```

if this query has more load and triggered so many times, we can create indexes with batch_id column,   
to reduce the latency 

<ins>Example</ins>    
systems like twitter and social media are read heavy systems, where number of post created by single user is less than number of post viewed by that user,   
indexes is best for read heavy systems,   

systems like are write heavy, indexes makes writes slow, so avoid uses indexes with write heavy systems   

# Problem 

the query, select * from students where batch_id = 1, fetch row by row from disk to RAM,    

> every row is a black box until it is bought to RAM, and condition is checked    

if the table has 1million, 1million rows are bought to RAM and checked, for every query and operation directly on disk is too costly and slow   

![Screenshot 2022-12-19 at 3 05 38 PM](https://user-images.githubusercontent.com/16437905/208394351-83cd95e7-c44f-49d9-b3ab-a7ac757b433d.png)

<ins>Cost</ins>   
![Screenshot 2022-12-19 at 3 18 22 PM](https://user-images.githubusercontent.com/16437905/208396974-cb77f6f7-78eb-4aca-b466-f8993bc25f99.png)

# Extra table in RAM   

In order to avoid 1million reads for a query, we create a extra table in RAM itself,     

we choose a specific column as index and the extra table is sorted by that column, this table contains the choosen column value     
and address of that row in original table inside disk   

> this extra table has been created for improved reads and is called indexes,   

> this index table is created and copied to RAM durning startup, it operates in RAM but persisted to disk (to save from system failure)    

instead of 1million reads, for select * from students where batch_id = 1 query, we make only 3 disk reads as we have the direct address in extra table,   

![Screenshot 2022-12-19 at 3 21 43 PM](https://user-images.githubusercontent.com/16437905/208397720-2720b71d-abda-4d26-b2a8-5283c7a8c71e.png)

![Screenshot 2022-12-19 at 3 21 59 PM](https://user-images.githubusercontent.com/16437905/208397757-eb7ee616-355a-465c-9d94-b94b2b8e25a1.png)


# Data structure for indexing   

<ins>Key</ins>    
sorted    
fast access

<ins>Value</ins>    
address of row in disk      

> Treemap has key value pair, maintains order and time complexity is log n   
    
> Internally Treemap is implemented using BST (Red-Black tree or AVL tree)

<ins>Data structure</ins>        
```
Treemap

key   - B tree    
value - B+ tree
```
![Screenshot 2022-12-28 at 7 30 02 AM](https://user-images.githubusercontent.com/16437905/209745578-4668209a-9aaf-4b02-85d4-e6ae3be2a6f2.png)
![Screenshot 2022-12-28 at 7 30 18 AM](https://user-images.githubusercontent.com/16437905/209745582-b474d4f7-22df-4d00-9fe7-d542af4a7423.png)


# Trade offs

index table needs space, we can increase the number of disk access to reduce the index table storage, and viceversa

![Screenshot 2022-12-28 at 9 30 59 AM](https://user-images.githubusercontent.com/16437905/209755299-c4474201-ad42-4813-9648-b6a3690253e1.png)


# Queries

```
select * from customers where points = 2273;

explain select * from customers where points = 2273; // disk fetch = total number of rows in that table

create index idx_customer_points on customers(points);
 
explain select * from customers where points = 2273; // disk fetch = number of rows whose points is 2273

```
```
create index idx_customer_points on customers(points);
drop index idx_customer_first_name on customers;

show indexes in customers;
```

# Full text indexes      

```
# disk fetch = number of rows matching condition
create index idx_customer_last_name on customers(last_name);
drop index idx_customer_last_name on customers;

explain select * from customers where last_name like '%sridhar%';

# output 5 rows but returns the output in one disk fetch
create fulltext index idx_customer_last_name on customers(last_name);

select * from customers where match(last_name) against('sridhar' in boolean mode);
explain select * from customers where match(last_name) against('sridhar' in boolean mode);

```

# Composite indexes

using two columns as indexes, eg: (name, batch_id) or (batch_id, name)              

use (name, batch_id), as the rows needs to be processed is lesser than (batch_id, name) index       

> choose the column that has more distinct values than other column 

![Screenshot 2022-12-28 at 12 12 38 PM](https://user-images.githubusercontent.com/16437905/209769854-a23db38a-d171-4977-a865-594c8f7e8798.png)

