# Heaps

It is a kind of binary tree  
> structurally hierarchical, but    
> implementation is linear  

<ins>Definition of heap</ins>  

> Heap is a complete binary tree (CBT)  

<ins>conditions for complete binary tree</ins>    
1. fully filled up to 2nd last level  
2. is filled from left -> right for last level

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

<ins>Observations</ins>:  
root of the heap is at index 0,  
for a index i,  

1. left child is at index 2 * i + 1
2. right child is at index 2 * i + 2
3. it's parent is at index (i - 1)/2

# Types of Heap

<ins>Max Heap</ins>  
1. Must be CBT
2. Every node should be greater than it's children

<ins>Min Heap</ins>  
1. Must be CBT
2. Every node should be smaller than it's children

there is no relationships between the two children nodes   

