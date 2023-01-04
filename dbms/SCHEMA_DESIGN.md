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

