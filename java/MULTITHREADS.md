# Introduction

A thread doesn't have to keep variables in its local cache -- but it is allowed to, when you tell it

If you want to force a thread to share its state with other threads, you have to use synchronization of some sort (including synchronized blocks, volatile variables, etc)


# Volatile 
> The volatile modifier guarantees that any thread that reads a field will see the most recently written value, 

static variables may be cached for individual threads, In multi-threaded environment if one thread modifies its cached data, that may not reflect for other threads as they have a copy of it,    

volatile declaration makes sure that threads won't cache the data and uses the shared copy only

![volatile](https://user-images.githubusercontent.com/16437905/212918097-3afd94fc-374c-4def-8bad-473929a09f2d.png)


# Atomic 

<ins>Atomic Integer</ins>   


<ins>Atomic Reference</ins>   


# Thread local cache

If you want to prevent a thread from sharing its state with other threads, you have to use ThreadLocal (assuming the object that holds the variable is known to multiple threads -- if it's not, then everything is thread-local anyway)

opposite to sharing data between threads    

```
ThreadLocal<Long> b = new ThreadLocal<>();
b.set(11L + Thread.currentThread().getId()); // unique for each thread
```

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
