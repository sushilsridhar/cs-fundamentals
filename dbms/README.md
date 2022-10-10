# Database Management System

<ins>Data</ins>  
> any information about something

<ins>Database</ins>   
> a collection of related data

also a place to store data,  
we will not store analytics data inside the db containing employee details, as db is a collection of related data,  

<ins>related data are stored together</ins>  
there are different databases created for a specific purpose, redshift/bigtable are optimized for running analytical queries,   
hence separating analytics data from other databases, will help in using different databases suited for their purpose  

<ins>DBMS</ins>  
> software to store data and provides a way to interact with that data 

OS file system, the first dbms

# Sql database

Databases that are based on relational model, this relational model represents data as a collections of relations (tables)  
eg: sql, mysql

# No sql database 

Databases that do not follow relational model of storing data

<ins>types</ins>  
  1. Graph database (neo4j)
  2. Column database (cassandra)
  3. Document database (mongodb, elastic search)
  4. key-value pair database (redis)
