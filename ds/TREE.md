# Tree

> tree is a hierarchical data structure,  
> all other data structures are linear   
 
<ins>Node</ins>: entity that holds info  
<ins>Edge</ins>: connects two nodes  

<ins>Height</ins>: distance from the root to the farthest leaf node  
<ins>Depth</ins>: distance of that node from root node  

# Binary Tree

> Binary tree can have 0,1,2 children,   
> maximum two children    

<ins>Programming Paradigm</ins> - recursion  
<ins>Observation</ins> - left sub tree and right sub tree of binary tree are also binary trees    

<pre>
            1
       2         3
    4     5         6
</pre>

<ins>Time Complexity for Searching</ins>  
> O(n), need to visit all nodes to find

# Binary Search Tree

For every node, recursively, the value of 
1. all elements of LST <= root value  
2. all elements of RST > root value  

<ins>Valid Binary Search Tree</ins>  
> max on left subtree < node.val < min on right subtree
<pre>
            10
       5         11
    4     8          13
</pre>

<ins>Invalid Binary Search Tree</ins>
<pre>
            10
       5         11
    4     12          13
</pre>

<ins>Time Complexity for Searching</ins>  
> O(h), we can skip some part of the tree because of nature of BST, however at every step we go one level down until we reach the height of the tree

# Balanced Binary Search Tree
below tree, with no of nodes in LST ~~ approx equal to no of nodes in RST, is called balanced binary search tree (height balanced binary search tree)      

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


<ins>Time Complexity for Searching</ins>  
> O(logn),
> we are reducing the search space by half at every step, and since height is also balanced, it can't be a skewed tree  

# Skewed Tree  
below tree without a left side or right side is called skewed tree  

<ins>Time Complexity for Searching</ins>: O(n)

<pre>
1
  2
    3
      4
</pre>

# Traversal 
<ins>Pre-order traversal</ins>  
root -> left -> right , (root first)      
using stack: process root, put right in stack, assign the pointer to left  

<ins>In-order traversal</ins>  
left -> root -> right , (root middle)   
using stack: put root in stack, assign pointer to left, when pointer is null, pop and process root and assign pointer to right  

<ins>Post-order traversal</ins>  
left -> right -> root , (root last)  
using stack: process root, put left in stack, assign the pointer to right, when pointer is null pop and assign the node to pointer  
reverse the answer to get postorder     

<ins>Level-order traversal</ins>  
process nodes by level,  


      
# Real world application
1. DOM (Document Object Model)
2. computer folder directory
