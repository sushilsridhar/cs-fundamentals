# Queue

> First In First Out  

<ins>operations</ins>
1. add
2. poll
3. peek

Deletion and Insertion are done from two different ends i.e., front and rear ends respectively   

# Queue structure
![queue](https://user-images.githubusercontent.com/16437905/179653948-d6fca880-6774-4e2d-83b3-948255f583e8.png)

# When to use queue
> to maintain candidate list for potential answers,  
> when maintaining order is required


# Implementation

can be implemented using arrays and linkedlist,  

<ins>**Java Default implementation**</ins>    
All methods in Queue Interface are overridden in Deque Interface,    

<ins>Deque extends Queue</ins>  
This abstract interface is implemented by concrete classes, LinkedList class and ArrayDeque class  

<ins>LinkedList implements Deque</ins>  
Queue\<Integer> queue = new LinkedList<>();

<ins>ArrayDeque implements Deque</ins>  
Deque\<Integer> queue = new ArrayDeque<>(); 

# Time complexity

Best implementation is using linked list or ArrayDeque? check this    
but both have same time complexity  

| Operations | Queue implemented using linked list
:---: | :---:
add()          | O(1)
poll()         | O(1)
peek()         | O(1)
size()         | O(1)

# Types of Queues in Java
<ins>Circular Queue</ins>  
In Circular Queue the last position is connected back to the first position  

<ins>Doubly ended Queue</ins>  
Elements can be inserted and removed from both ends i.e. front and rear  

<ins>Priority Queue</ins>  
In Priority Queue, a collection of elements are associated in a specific order  

# Doubly Ended Queue

<ins>Structure</ins>  
![deque](https://user-images.githubusercontent.com/16437905/179668429-cb754a35-a9c4-4df1-ba3e-ca1111522376.png)

<ins>Operations</ins>:   
Deque Interface methods,  

1. offerFirst
2. pollFirst
3. peekFirst
4. offerLast
5. pollLast
6. peekLast


<ins>**Java Default Implementation**</ins>:  

<ins>Deque Interface</ins>  
This abstract interface is implemented by concrete classes, LinkedList class and ArrayDeque class,  

<ins>LinkedList implements Deque</ins>  
Deque\<Integer> deque = new LinkedList<>();

<ins>ArrayDeque implements Deque</ins>  
Resizable-array implementation of the Deque interface, 

Deque\<Integer> deque = new ArrayDeque<>();


# Why ArrayDeque is better than LinkedList? 
1. <ins>LinkedList has additional overhead</ins> for creating new node objects (new memory locations for data and address), which has a performance impact 
2. Elements in <ins>LinkedList are stored in a non-contiguous way, which does not help cache hits</ins>, however ArrayDeque uses arrays which is contiguous and helps cache hits


# Real world applications

1. Rabbitmq / kafka (messaging queue system)
2. Buffer for devices like keyboard
3. Applied as waiting lists for a single shared resource like CPU, Disk, Printer  
4. Priority Queues are used in scheduling the jobs in the operating system 


