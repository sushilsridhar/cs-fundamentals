# Heaps

It is a kind of binary tree  
> structurally hierarchical, but    
> implementation is linear  

<ins>Definition of heap</ins>  

> Heap is a complete binary tree (CBT)  

<ins>conditions for complete binary tree</ins>    
1. fully filled up to 2nd last level  
2. is filled from left -> right for last level

height of the complete binary tree is O(logn)  

![cbt](https://user-images.githubusercontent.com/16437905/180133603-8cfb6792-6462-4c38-8799-2d8ed93a1778.png)

for a given number of nodes, structurally only one complete binary search tree is possible  
heaps enforces single structure  

h: { A, B, C, D, E, F, G, H }
<pre>
             A
       B            C
    D     E      F     G 
 H
</pre>

# Heap structure

> structurally hierarchical, but    
> implementation is linear 

logically represented as tree, the actuall implementation is using array    

![structure](https://user-images.githubusercontent.com/16437905/180140025-c238a029-27c2-4c2c-ae74-af13d74475e5.png)

<ins>Observations</ins>  
root of the heap is at index 0,  
for a index i,  

1. left child is at index 2 * i + 1
2. right child is at index 2 * i + 2
3. it's parent is at index (i - 1)/2

<ins>height of heap</ins>  
since heap is CBT, height of the heap is logn  

# Types of Heap

<ins>Max Heap</ins>  
1. Must be CBT
2. Every node should be greater than it's children

<ins>Min Heap</ins>  
1. Must be CBT
2. Every node should be smaller than it's children

there is no relationships between the two children nodes   

# Heapify 

> Algorithm to create a heap data structure with a given group of elements  
   
<ins>preconditions</ins>  
1. entire tree should be a complete binary tree
2. left subtree should be a MAX heap / MIN heap (depends on which heap is being built)
3. right subtree should be a MAX heap / MIN heap (depends on which heap is being built)

since heaps are represented in linear format with arrays,   
1, 8, 70, 80, 10, 5 - heaps  

by default the left and right subtree and entire subtree is a complete binary tree  

<ins>implementation</ins>  
<pre>
    1, 8, 70, 80, 10, 5

                1
           8            70
      80     10      5
</pre>

start with parent of last leaf node,    
check if parent is greater than both left and right nodes, if left is greater, swap left and parent,  
point the pointer to current position of parent after swapping, again check if parent is greater than left and right,  
keep doing until we reach the leaf node  

repeat this for next parent, starting with 70, then 8, then 1  

<ins>after heapify</ins>  
<pre>
    80, 10, 70, 8, 1, 5

               80
         10           70
      8     1       5
</pre>

<ins>heapify is not online</ins>  
heap is a online datastructure, where we add elements as need arises  

but certain algorithms are not online, we need to know all the elements before processing, like merge sort,  
we can not add elements on the fly, 

> the algorithm of creating heap using heapify is not online  

<ins>time and space complexity</ins>   
tc: O(n)    
sc: O(1)  

# When to choose heaps?

> when a particular order needs to be maintained for a group of elements,  
> even after removing or adding elements the order is maintained    

<ins>example</ins>  
if given a set of elements, find the max, find the second max, find the n max?  

A max heap will have the largest number at the top of it, Once the top number is removed, 
it will have the second-largest number at the top  
Once the second-largest number is removed, we will have the third-largest number at the top  

# Implementation

can be implemented using dynamic array,

<ins>**Java Implementation**</ins>  

PriorityQueue class implements Queue interface, this class provides the implementation of heaps in java,   
PriorityQueue internally uses dynamic array,  

**<ins>Ordering of elements in PriorityQueue</ins>**  

<ins>min heap</ins>  
min heap is the default settings for PriorityQueue, it is increasing order      

```
PriorityQueue<Integer> minHeap = new PriorityQueue<>();  
```

<ins>max heap</ins>   
to create max heap, we need to specify the ordering, which is decreasing order  

```
PriorityQueue<Integer> maxHeap = new PriorityQueue<>(Collections.reverseOrder());  
```

<ins>custom comparator</ins>  
Passing custom logic to handle the ordering of elements,  

```
 PriorityQueue<Points> minHeap = new PriorityQueue<>((p1, p2) -> {
            if(p1.getDistance() > p2.getDistance()) {
                return 1;
            } else if(p1.getDistance() < p2.getDistance()) {
                return -1;
            }
            return 0;
        });
```


# Time Complexity
  
| Operations | PriorityQueue
:---: | :---:
add()          | O(log n)
poll()         | O(log n)
peek()         | O(1)


