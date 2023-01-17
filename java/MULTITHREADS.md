# Volatile 

# Atomic 

<ins>Atomic Integer</ins>   


<ins>Atomic Reference</ins>   


# Thread local cache

opposite to sharing data between threads    


# Double checked locking 



# Executor Service

Executor Service is used to manage a pool of threads, otherwise lots of boiler plate code is needed to setup thread management    

[Executors and Callables](https://github.com/sushilsridhar/cs-fundamentals/blob/main/os/MULTITHREAD_CODE.md)

> general purpose thread pool    

In practice ExecutorService is usually used to process many independent requests (aka transaction) concurrently, and fork-join is used when you want to accelerate one coherent job


# ForkJoinPool

> special implementation of executor service, which uses divide and conquer approach        

> uses work-stealing pattern for efficient processing of tasks    

<ins>Fork</ins>   
recursively break the task into smaller independent subtasks until they are simple enought to run asynchronously

<ins>Join</ins>   
The results of all subtasks are recursively joined into a single result, In the case of a task that returns void, the program simply waits until every subtask runs

To provide effective parallel execution, the fork/join framework uses a pool of threads called the ForkJoinPool, This pool manages worker threads of type ForkJoinWorkerThread
