# Transactions

> a set of logically related operations

![Screenshot 2022-12-18 at 10 10 24 AM](https://user-images.githubusercontent.com/16437905/208281794-3d3b312c-29b9-48c2-8c88-064a47bfa95f.png)


# ACID

<ins>Atomicity</ins>      
A transaction should appear like a single step, the transaction either completes or fails, there is no inbetween    
step 1, 2, 3 of a transaction acts like a single unit   

<ins>Consistency</ins>    
A transaction should never leave the database in any inconsistent state, eg: money deducted from A(step 2) but not credited to B(step 5) causes inconsistent state, 


<ins>Isolation levels</ins> 


<ins>Durability</ins>


# Isolation level

> solves concurrency issues in transactions
