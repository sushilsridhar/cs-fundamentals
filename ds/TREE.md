# Tree

> all other data structures are linear,   
> tree have hierarchy  

# Binary Tree

> Binary tree can have 0,1,2 children,   
> maximum two children    

<ins>Programming Paradigm</ins> - recursion  
<ins>Observation</ins> - left sub tree and right sub tree of binary tree are also binary trees    

> searching tc: O(n)  
<pre>
            1
       2         3
    4     5         6
</pre>

# Binary Search Tree

For every node, the value of 
1. LST <= root value  
2. RST > root value  

> searching tc: O(n) 

there is a possibility of tree being skewed tree, so it is O(n)  

<pre>
            10
       5         11
    4     8          13
</pre>

# Balanced Binary Search Tree
below tree, with no of nodes in LST ~~ approx equal to no of nodes in RST, is called balanced binary search tree  

> searching tc: O(logn)

<pre>
            10
       5         11
    4     8          13
</pre>

<ins>condition for balanced binary search tree</ins>  
> | height(LST) - height(RST)| <= 1  


<ins>Self balanced binary search tree</ins>  
1. AVL Tree   
2. Red black Tree  

# Skewed Tree  
below tree without a left side or right side is called skewed tree. 
> searching tc: O(n)  

<pre>
1
  2
    3
      4
</pre>

# Traversal 
<ins>Pre-order traversal</ins>  
root -> left -> right , (root first)    

<ins>In-order traversal</ins>  
left -> root -> right , (root middle)   

<ins>Post-order traversal</ins>  
left -> right -> root , (root last)  

      
# Real world application
- DOM (Document Object Model)
- computer folder directory
