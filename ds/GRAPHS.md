# Graphs

> collection of vertices and edges, under the same context

vertices - people,  
edges - logical connection between them  

![Screenshot 2022-08-11 at 7 23 26 AM](https://user-images.githubusercontent.com/16437905/184052055-fb464b5e-3f7c-46c6-903d-d00a2083f319.png)

<ins>Directed Graph</ins>

![Screenshot 2022-08-11 at 7 28 41 AM](https://user-images.githubusercontent.com/16437905/184052633-eefa11a1-28cb-4b90-9a4e-7aa3e5bddd01.png)


<ins>Undirected Graph</ins>

![Screenshot 2022-08-11 at 7 29 18 AM](https://user-images.githubusercontent.com/16437905/184052705-11d5fece-0772-4ca3-8f2b-b058f345121c.png)

<ins>Weighted Graph</ins>

![Screenshot 2022-08-11 at 7 35 01 AM](https://user-images.githubusercontent.com/16437905/184053254-62dd8a0e-e21b-4248-a1ec-c043e9acd84c.png)


<ins>Cyclic Graph</ins>

> if we have a simple path from a node to itself via distinct edges 

![Screenshot 2022-08-11 at 7 52 07 AM](https://user-images.githubusercontent.com/16437905/184054548-9f5779e9-4f1e-405f-af7a-b1f0835b7b15.png)

> even if it has one cycle, it can be called as cyclic graph

![cyclic](https://user-images.githubusercontent.com/16437905/184057701-a133d8d3-a54b-496a-b35c-16a438c6e92b.png)


# DAG - Directed Acyclic Graph

![DAG](https://user-images.githubusercontent.com/16437905/184057672-31576826-7b53-4358-ad4f-e7e0572369bc.png)


# Connected component

> you have a path between any two nodes,  
> for undirected graphs, it is called connected component,      

from any node, we can go to any other node

<ins> Two connected components</ins>  

![Screenshot 2022-08-11 at 8 29 01 AM](https://user-images.githubusercontent.com/16437905/184058710-2489bab2-48e0-4063-8bde-14c90d77de7f.png)

# Strongly Connected component

> you have a path between any two nodes,  
> For directed graphs, it is called strongly connected component,     

from any node, we can go to any other node

![Screenshot 2022-08-11 at 8 42 17 AM](https://user-images.githubusercontent.com/16437905/184059232-7838270f-c1af-448e-acff-383d099f1cb7.png)


# Simple Graphs

> no self loop  
> no multiple edges to the same neighbour  

<ins>All Trees are Graphs</ins>  


# How to represent graphs

Graph -> { Vertices, edges }

<ins>Adjacency matrix</ins>  

<pre>
1 -> 2 -> 3
  <-
</pre>
| | 1 | 2 | 3 |
:---: | :---: | :---: | :---: |
1 | 0 | 1 | 0
2 | 1 | 0 | 1
3 | 0 | 0 | 0

sc: O(v^2)  

cons  
1. too much space
2. adding more node, each take O(n2) complexity  


<ins>Adjacency list</ins>     

<pre>
 1 - 2 
    / \
   3 - 4
</pre>

<pre>
Vertex | Edges
| 1 |  - 2
| 2 |  - 3 - 4 - 1
| 3 |  - 2 - 4 
| 4 |  - 2 - 3
</pre>

V: 1 2 3 4  
E: each edge makes two entry in edges list, so 2E

sc: O(V + 2E)


# Traversal in Graphs

<ins>Breadth First Search</ins>  
same as doing level order traversal in graphs,  

> explore the breadth first, explore all nodes in the same level or breadth first  

> use queue to maintain order of elements in same level  


<ins> Depth First Search</ins>  










