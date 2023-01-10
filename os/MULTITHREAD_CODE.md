
# Basics
[How to write Multithreaded code](https://github.com/sushilsridhar/cs-fundamentals/blob/main/os/THREADS_HARDWARE_RELATION.md#how-to-write-multi-threaded-program)

Threads can't be created for every request, we need to have a group of threads that can be reused

![Screenshot 2022-11-24 at 2 51 31 PM](https://user-images.githubusercontent.com/16437905/203745806-59504bc1-f491-44f2-a4bc-106bba03fb5b.png)


# Executors   

> Using Executors it is easy to manage a pool of threads, otherwise we need to write lot of boiler plate code   

In real world threads are created with executors in java, and the thread pool size is fixed according to number of cores,   
using this, we have a main thread, along the pool of worker threads,    

<ins>Task</ins>       
define task, what needs to be run independently and parallely  

<ins>Executor</ins>       
submit the task to executor, the executor knows how to run it efficiently 

<ins>Fixed thread pool</ins>    
Fixed thread pool size, 5 threads are reused for all the tasks
```
ExecutorService executorService = Executors.newFixedThreadPool(5);
```

<ins>Cached thread pool</ins>       
If any thread is free, it will be reused, if no threads are free for a new incoming task, new thread is created
```
ExecutorService executorService = Executors.newCachedThreadPool();
```

# Callables

> Like runnables, Callables are a way to define a task, unlike runnables, callables returns something back to the client    

<ins>Future</ins>   
a bucket(assurance) to give the real data when required

```
 Sorter leftSorter = new Sorter(leftArray, executorService);
Sorter rightSorter = new Sorter(rightArray, executorService);

Future<List<Integer>> leftArrayFuture = executorService.submit(leftSorter);
Future<List<Integer>> rightArrayFuture = executorService.submit(rightSorter);

List<Integer> leftSortedArray = leftArrayFuture.get();
List<Integer> rightSortedArray = rightArrayFuture.get();
```

