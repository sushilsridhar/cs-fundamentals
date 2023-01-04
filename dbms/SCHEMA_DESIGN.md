# Keys

A attribute or a set of attributes that uniquely identifies a row is a key    

<ins>Super key</ins>: all keys are super key     

<ins>Candidate key</ins>: a key of minimum size that can uniquely identify a row,  
candidate key is a super key of minimum size   

<ins>Primary key</ins>: one of the candidate key is choosen as primary key  

<ins>Composite key</ins>: a key with attributes >= 2  

<ins>Foreign key</ins>: a attribute in a table, which is a primary key in another table  

# Schema design

schema design is how my database will be structured,

1. how to decide what tables to create and it's attributes
2. how to model cardinality between tables
3. normalization

<ins>Approach</ins>   
1. get all the requirements   

2. Find all the entities(anything that stores information) in requirement 

go line by line of requirements and spot all entities

![Screenshot 2023-01-04 at 5 24 33 AM](https://user-images.githubusercontent.com/16437905/210460634-79fb0399-fac6-4259-b667-915bf16c0df3.png)

3. name the table and attributes
4. decide the data type of attributes

Batches table and instructors table,    
current instructor attribute can id from instructor table, string name, decide using the cardinality

![Screenshot 2023-01-04 at 9 21 34 AM](https://user-images.githubusercontent.com/16437905/210481283-18614bb0-51b4-4fd6-90ac-78fbba371495.png)

<ins>Cardinality</ins>      
> if there is a relation between A and B entities, cardinality says how many of A are there in how many of B? 


![Screenshot 2023-01-04 at 9 25 48 AM](https://user-images.githubusercontent.com/16437905/210481670-80391008-9d98-4248-a3f3-e6e6667c6ef0.png)
![Screenshot 2023-01-04 at 9 26 26 AM](https://user-images.githubusercontent.com/16437905/210481730-2f210dab-e862-4bf2-a66a-489a25dc8cbc.png)

<ins>How to find Cardinality</ins>    
![Screenshot 2023-01-04 at 9 37 32 AM](https://user-images.githubusercontent.com/16437905/210482886-33831d7f-c57b-4535-a6d7-96d3b73aaaec.png)

![Screenshot 2023-01-04 at 9 37 39 AM](https://user-images.githubusercontent.com/16437905/210483216-ee3d861b-601d-44bb-81bb-8423adbd8abf.png)
![Screenshot 2023-01-04 at 9 37 52 AM](https://user-images.githubusercontent.com/16437905/210483224-4d4b65b2-0118-4ee6-89db-764880f6fe83.png)
![Screenshot 2023-01-04 at 9 38 25 AM](https://user-images.githubusercontent.com/16437905/210483230-2e49c611-9716-4af3-a467-60d9f78abad0.png)

<ins>Represent cardinality in database</ins>   
```
1-1  : put the id of one entity in another entity 

1-m 
m-1  : put the id of 1 side to m side 

m-m  : create a mapping table, to store ids of both the entities
```


