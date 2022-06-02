# LinkedList

> Linkedlist overcomes the drawbacks of arrays/dynamic arrays  

<ins>Drawbacks of arrays/dynamic arrays</ins>  

> even if enough memory segments are available in RAM, array needs contiguous memory location to store,  
> which is not memory efficient

![dynamic arrays](https://user-images.githubusercontent.com/16437905/169188095-0e01d3ad-54b9-4eb1-b7d5-66131064310e.jpg)

# Linkedlist structure

Each box, 100, 200, 300 are segments in memory, which are not necessarily contiguous memory segments,  
since memory segments is not contiguous we lose random access (which is O(1) complexity)  

![ll_memory_segment](https://user-images.githubusercontent.com/16437905/169190533-00ebe3c0-c16d-4952-8212-bc8c38e5610b.png)

![ll](https://user-images.githubusercontent.com/16437905/169188814-584df4f0-c3ff-4a53-a92f-9ffa9f62f76e.png)

```
  class Node {
        int val;
        Node next;

        Node(int val) {
            this.val = val;
        }
    }
```  
val - occupies 4 bytes  
next - occupies 4 bytes (memory addresses are integers)  

Linkedlist requires 4bytes extra compared to arrays  

**<ins>Doubly Linked List</ins>**    

Java LinkedList is implemented using Doubly linked list  

> Can traverse in reverse  
> Operations can be performed if given a middle node instead of head  

![dll](https://user-images.githubusercontent.com/16437905/169951918-e8cd248d-b5e6-4cd8-94d2-c6ec520c375d.png)  

```
    private class Node<E> {
        E data;
        Node<E> prev;
        Node<E> next;

        Node(Node<E> prev, E data, Node<E> next) {
            this.data = data;
            this.prev = prev;
            this.next = next;
        }
    }
```
In case of integers,  
data - occupies 4 bytes    
prev - occupies 4 bytes  
next - occupies 4 bytes (memory addresses are integers)     

Doubly linked list requires extra memory than singly linked list  

# When to choose Linkedlist

> if you do not want O(1) random access time of array  
> if you want to use RAM memory efficiently, which is a scare resource for you  

# Time complexity

| Operations | Doubly linked list | Singly linked list |
:---: | :---: | :---: |
add()         | O(1)  | O(n)
addFirst()    | O(1)  | O(1)
addLast()     | O(1)  | O(n) or O(1) (with tail pointer)
add(k, data)  | O(k)  | O(k)
get(k)        | O(k)  | O(k)
getFirst()    | O(1)  | O(1)
getLast()     | O(1)  | O(n) or O(1) (with tail pointer)
remove(k)     | O(k)  | O(k)
removeFirst() | O(1)  | O(1)
removeLast()  | O(1)  | O(n)
set(k, data)  | O(k)  | O(k)


# Do not update HEAD pointer

Node head;   
Node pointer = head;  

head contains the address to the start of the linkedlist,  
for traversing the linkedlist, copy head to another variable and use it

# Edge cases 

dry run for,  
linkedlist size = 0, head is null  
linkedlist size 1,2,3  

# Real world applications

1. <ins>Implementation of stacks and queues</ins>
2. <ins>Implementation of graphs</ins> : Adjacency list representation of graphs is most popular which is uses linked list to store adjacent vertices
3. <ins>Image viewer – Previous and next images are linked</ins>, hence can be accessed by next and previous button
4. <ins>Previous and next page in web browser</ins> – We can access previous and next url searched in web browser by pressing back and next button since, they are linked as linked list
5. <ins>Music Player – Songs in music player are linked to previous and next song</ins>. you can play songs either from starting or ending of the list
