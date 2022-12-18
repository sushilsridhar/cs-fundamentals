# Transactions

> a set of logically related operations

![Screenshot 2022-12-18 at 10 10 24 AM](https://user-images.githubusercontent.com/16437905/208281794-3d3b312c-29b9-48c2-8c88-064a47bfa95f.png)


# ACID

<ins>Atomicity</ins>      
A transaction should appear like a single step, the transaction either completes or fails, there is no inbetween    
step 1, 2, 3 of a transaction acts like a single unit   

<ins>Consistency</ins>           
A transaction should never leave the database in any inconsistent state, eg: money deducted from A(step 2) but not credited to B(step 5) causes inconsistent state, 

<ins>Isolation</ins>    
Other transactions running in the system should not affect the given transaction, every transaction should be independent of other and product desired results, Isolation levels are used to solve this issue         

<ins>Durability</ins>   
After the transaction has ended, the results should persist (persist in hardware), then that transaction is durable       
eg:, A sent 500 to B, B balance is 1000 + 500, balance now is 500 but next day balance back to 1000 


<ins>ACID in short</ins>  
```
A - everything or nothing   
C - consistent before and after   
I - not affected by other transactions    
D - once succeeded, persist (no data loss)    
```
# Types of operations in transactions     

```
READ     : reads data        
WRITE    : writes data   

COMMIT   : commits the data (persists the data) to the database, if everything is goes well        
ROLLBACK : rollbacks the data to previous commited state, if any undesirable state occurs    
```

# Isolation level

> solves concurrency issues in transactions


classic example of no isolation, Transaction t2 affects transaction t1,

![Screenshot 2022-12-18 at 10 32 31 AM](https://user-images.githubusercontent.com/16437905/208282351-02d59a53-7ac8-421f-bdf2-4ba2764b7f13.png)
