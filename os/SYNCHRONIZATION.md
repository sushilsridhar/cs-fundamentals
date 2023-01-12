# Synchronization Problem

> same resource being shared between two or more threads and the threads are trying to modify it,      

if multiple threads read a value and doesn't change it, it is not sync problem at all

<ins>Critical section</ins>   
piece of code that creates the data inconsistency and that piece being executed by multiple threads at same time,   
that portion of code is called critical seciont   

![Screenshot 2023-01-10 at 4 38 22 PM](https://user-images.githubusercontent.com/16437905/211535813-4968b4fd-65cf-47b6-906e-95c9965a9106.png)

![Screenshot 2023-01-10 at 4 39 26 PM](https://user-images.githubusercontent.com/16437905/211536005-55f71652-e90c-4306-b894-a5ac9d2d8270.png)

<ins>Race condition</ins>   
more than one thread tries to enter or execute the critical section at the same   

<ins>Properties of good solution to synchronization problem</ins>     
```
1. mutual exclusion : only one thread allowed to enter the critical section at a time

2. progress : entire system should not hault, system should not wait, it should be progressing

3. bounded waiting : no thread should have infinite waiting time

4. no busy waiting : being busy by keep checking for CS availability, 
                     when a critical section is taken, another thread t2 should not keep checking for CS availability, 
                     t2 should be notified when CS is available
```

# Mutex

> Mutual Exclusion - only one thread is allowed to access critical section at a time    

lock notifies other waiting threads when t1 completes   

```
Lock lock = new ReentrantLock();

count is shared object
lock is shared object

@Override
    public void run() {
        for(int i=0; i<10000; i++) {
            lock.lock();
            count.value = count.value + 1; // critical section
            lock.unlock();
        }
    }
```

# Synchronized keyword

> implicit lock in every object

```
 @Override
    public void run() {
        for(int i=0; i<10000; i++) {
            synchronized (random) { 
                // convention is use count object as param but 
                // can use any object (random), but other threads modifying the count object must acquire lock on random
                count.value = count.value - 1;
            }
        }
    }
```
> use synchronized blocks rather than methods   

because we have control on where the synchronized block starts and ends, more readable regards to what object is being locked   

![Screenshot 2023-01-11 at 11 46 16 AM](https://user-images.githubusercontent.com/16437905/211731615-f8b4b225-c19b-4f8a-aa02-67a3775d080b.png)


# Locks vs Synchronized

> locks give more control to developers    

Locks can be implemented across the methods, you can invoke lock() in method1 and invoke unlock() in method2, this can't be done in synchronized    

```
Lock.lock();    
myMethod();
Lock.unlock();      
```
unlock() cant be executed in this code if any exception being thrown from myMethod(), synchronized release the lock automatically not requiring to write try catch finally   

# Semaphores

