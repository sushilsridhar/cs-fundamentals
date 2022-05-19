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

# When to choose Linkedlist

> if you do not want O(1) random access time of array  
> if you want to use RAM memory efficiently, which is a scare resource for you  

# Time complexity


# Do not update HEAD pointer

Node head;   
Node pointer = head;  

head contains the address to the start of the linkedlist,  
for traversing the linkedlist, copy head to another variable and use it
