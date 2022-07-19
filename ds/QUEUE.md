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

<ins>Queue Interface</ins>  
This abstract interface is implemented by LinkedList class and ArrayDeque class  

<ins>LinkedList</ins>  
Queue\<Integer> queue = new LinkedList<>();

<ins>ArrayDeque</ins>  
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

# Real world applications

1. Rabbitmq / kafka (messaging queue system)
2. Buffer for devices like keyboard
3. Applied as waiting lists for a single shared resource like CPU, Disk, Printer  
4. Priority Queues are used in scheduling the jobs in the operating system 


