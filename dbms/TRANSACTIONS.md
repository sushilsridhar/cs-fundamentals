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

Atomicity makes sure the system has Consistency,    
All transactions are isolated using isolation levels,   
committing the transactions, makes the system durable   

# Types of operations in transactions     

```
READ     : reads data        
WRITE    : writes data   

COMMIT   : commits the data (persists the data) to the database, if everything is goes well        
ROLLBACK : rollbacks the data to previous commited state, if any undesirable state occurs    
```

<ins>Queries</ins>    

If commit statement is not there, the data update will be temporary, it will not persist once you close the instance,   
any failure in any statements after start transaction, all of them will be rollback to previous state,    

```
start transaction;

update products set quantity_in_stock = quantity_in_stock + 10 where product_id = 1;
update products set quantity_in_stock = quantity_in_stock - 10 where product_id = 8;

commit;

start transaction;

update products set quantity_in_stock = 80 where product_id = 1;
update products set quantity_in_stock = 26 where product_id = 8;

rollback;
```

# Isolation level

> to handle concurrency in transactions


classic example of no isolation, Transaction t2 affects transaction t1,

![Screenshot 2022-12-18 at 10 32 31 AM](https://user-images.githubusercontent.com/16437905/208282351-02d59a53-7ac8-421f-bdf2-4ba2764b7f13.png)


<ins> Transaction isolation levels</ins>: in increasing order of severity        
1. Read uncommitted (most efficient isolation level)    
2. Read committed
3. Repeatable read
4. Serializable

> These isolation levels are applied and changed based on session to session, do not choose a single isolation level for the whole system      

<ins>Read uncommitted</ins>   
we read a data changed(written) in transaction t2 but not yet committed (possibility of a rollback in t2),    
we read that data in transaction t1 (dirty read)    

<ins>Read committed</ins>     
It is safeguard against dirty read, multiple transaction can write a data, but t1 transaction reads only data that is committed   

<ins>Repeatable read</ins>    
Within a transaction if you try to read a value again, it will be same as earlier,    
it does not depend on commit of other transactions    

```
T1 - repeatable reads

initial value quantity_in_stock = 94

line 1: start transaction;

line 2: select * from products where product_id = 5;

line 3: commit;

T2 - serializable

line 1: start transaction;

line 2: update products set quantity_in_stock = 942 where product_id = 5;

line 3: commit;
```

```
T1 and T2 starts at same time,  

T2 line 2 completes first, T1 line 2 executes, quantity_in_stock will be 94 within T1       

whatever the value of quantity_in_stock after the start of the transaction T1 will remain same inside T1, 
even if the value changes in other transactions

```

<ins>Serializable</ins>   
> Uses lock behind the scenes    

if one transaction acquires a lock over a db row, other transaction have to wait to even read the row    

<ins>Notes</ins>    
> In mysql, the default transaction isolation level is repeatable reads   

> all isolation levels have concurrency issues    

> there is no other way solve this problem but to have sequential transactions

```
set session transaction isolation level serializable;
show variables like 'transaction_isolation';
```

# Serializable

<ins>select query</ins>   
if one transaction is updating a row, other transaction must wait to update that row until first transactions completes updating, but other transactions can read that row,   

```
T1

line 1: start transaction;

line 2: update products set quantity_in_stock = 494 where product_id = 5;

line 3: commit;

T2
line 1: start transaction;

line 2: select * from products where product_id = 4;

line 3: select * from products where product_id = 5;

line 4: commit;

T1 executed line 2, T2 can execute line 2, since rows are different, line 3 waits until line 3 of T1 completes,   

```



<ins>select query with for update</ins>   
t1 -> select a row using for update query, other transactions can't even read that row until t1 commits or rollbacks,   

> for update -> locks the rows returned by the select query

![Screenshot 2022-12-26 at 1 19 35 PM](https://user-images.githubusercontent.com/16437905/209520651-296fdb8a-7979-46c9-a3f5-4efcbeaef393.png)

![Screenshot 2022-12-26 at 1 19 43 PM](https://user-images.githubusercontent.com/16437905/209520666-c0e431fa-ec76-4959-8e4f-e41fe895b659.png)



# Read further

locks     
shared locks    
Another transaction that tries to read the same data is permitted to read, but a transaction that tries to update the data will be prevented from doing so until the shared lock is released
Shared lock is also called read lock, used for reading data items only

exclusive locks   
When a statement modifies data, its transaction holds an exclusive lock on data that prevents other transactions from accessing the data.
This lock remains in place until the transaction holding the lock issues a commit or rollback
They can be owned by only one transaction at a time
With the Exclusive Lock, a data item can be read as well as written. Also called write lock


which isolation level - which lock is required - row lock or table lock in mysql - how to create database read only replica - it's usecases

app code acquires lock or there is a lock within mysql that manages it

types of locks

is one session for each transaction?

research on read only database, these are will isolation level read uncommited, hence faster      
analytics database, we dump data, it will not change, kibana and new relic like tools just read that data,

row wise locking  happens? check

https://www.scaler.com/topics/lock-based-protocol-in-dbms/      
https://www.scaler.com/topics/sql/lock-table/   
https://www.scaler.com/topics/dbms/   
https://www.scaler.com/topics/sql/    
https://www.mysqltutorial.org/mysql-table-locking/      
https://dev.mysql.com/doc/refman/8.0/en/innodb-locks-set.html   
https://www.google.com/search?safe=active&client=safari&rls=en&sxsrf=ALiCzsbW-kPrgnPiufi5T7eBTgf_EaldnA:1671597507101&q=which+queries+in+mysql+acquire+lock+on+row&spell=1&sa=X&ved=2ahUKEwjy2fj88Yn8AhUaSmwGHVOtCIoQBSgAegQIDxAB&biw=1920&bih=1000&dpr=1   
