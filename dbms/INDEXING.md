# Indexes

> prevents unneccessary disk fetches    
> leads to faster queries
> indexes are updated durning writes, which makes writes slower

indexes are updated for all C|U|D queries

<ins>When to create indexes?</ins>    

Do not create indexes when table is created, create only after analyzing the performance and load on that query,    

create it only when you see a latency with a particular query or there is more load on a particular query, and you want to improve performance,   

```
select * from students where batch_id = 1;    
```

if this query has more load and triggered so many times, we can create indexes with batch_id column,   
to reduce the latency 

<ins>Example</ins>    
systems like twitter and social media are read heavy systems, where number of post created by single is less than number of post viewed by that user,   
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
and address of that row in original table

this extra table has been created for improved reads and is called indexes,   

instead of 1million reads, for select * from students where batch_id = 1 query, we make only 3 disk reads as we have the direct address in extra table,   

![Screenshot 2022-12-19 at 3 21 43 PM](https://user-images.githubusercontent.com/16437905/208397720-2720b71d-abda-4d26-b2a8-5283c7a8c71e.png)

![Screenshot 2022-12-19 at 3 21 59 PM](https://user-images.githubusercontent.com/16437905/208397757-eb7ee616-355a-465c-9d94-b94b2b8e25a1.png)


# Data structure for indexing   




# others
wjat is stored in cache l1 l2


java hashmap treemap linkedhashmap btree 
api latency got for indexing
