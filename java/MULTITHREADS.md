# Volatile 

# Atomic 

<ins>Atomic Integer</ins>   


<ins>Atomic Reference</ins>   


# Thread local cache

opposite to sharing data between threads    


# Double checked locking 



# Executor Service


In practice ExecutorService is usually used to process many independent requests (aka transaction) concurrently, and fork-join when you want to accelerate one coherent job. +1 Fork-Join solves a specific type of problem. If you don't have this type of problem, use ExecutorService as this is what Fork-Join uses anyway.

