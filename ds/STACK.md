# Stack

> Last in First out

<ins>Operations</ins>  
- push  
- pop  
- peek  
- size  

# When to use stacks

> To keep track of the lastest/last operation made,   
> add to the top and remove from the top  

# Implemenation

can be implemented using   
arrays, dynamic arrays, singly linked list, doubly linked list, queues  

**<ins>Java Default implementation</ins>**    

<ins>Stack</ins>  
> Stack class in java internally use Vector class which is a synchronised dynamic array   
  
Vector is used by Stack class because, Stack and Vector are legacy classes created before Arraylist   

<ins>ArrayDeque</ins>  

Deque<Integer> stack = new ArrayDeque<Integer>();  

> Java Doc says,  
> 
> A more complete and consistent set of LIFO stack operations is provided by the Deque   
> interface and its implementations, which should be used in preference to Stack class  


# Real world applications

1. Undo/Redo
2. Back button
3. Program/Function call stack
4. Compiler bracket checks
5. Expression evaluation
