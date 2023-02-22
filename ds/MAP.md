# Why map?

> Map is part of Java collection framework, but it doesn't implement Collection class, as it saves data in Key-value pair   

array saves data sequentially, if we want to save data randomly in any slot in a space(optimizing space usage),   
as key and value format, use hashing

<ins>example</ins>    
maintain a booking register for a hotel, 1000 rooms are present,  

```
int[] register = new int[1000]; 

HashMap<RoomNumber, CustomerId> map = new HashMap<>();
```

if there are only 10 bookings, hashmap saves space  

<ins>Requirements</ins>    
> no memory wastage durning memory allocation

> O(1) average tc for check()

> O(1) average tc for update()


# Hashing

mapping data to a secret key, that can be used as a unique identifier for data    

<ins>Hash Function</ins>    

It employs a function that generates those keys from the data, this function is known as the Hash-function,     
and the output of this function (keys) is known as Hash-values    

we store it as key(Hash values) value(real data) pairs in an array called Hash-Table, which uses keys as indexes and values as the data to be stored at each index location

the given keys are converted into hash values (fixed length) using a hash function and these hash values are used as the index of the hash table to store the associated data

![Screenshot 2023-02-12 at 6 42 30 AM](https://user-images.githubusercontent.com/16437905/218287854-c8da66dc-7161-48fc-8ee4-a9d31e8f4ac5.png)

![Screenshot 2023-02-12 at 6 42 38 AM](https://user-images.githubusercontent.com/16437905/218287856-058f5d6f-290c-4f08-b9df-4d1eadfa6426.png)

# Internal working

<ins>Map Interface</ins>  
```
public interface Map<K,V> {

   interface Entry<K,V> {
   
   }
}
```

<ins>HashMap - Node implements Map.Entry</ins>    

```
 static class Node<K,V> implements Map.Entry<K,V> {
        final int hash;
        final K key;
        V value;
        Node<K,V> next;

        Node(int hash, K key, V value, Node<K,V> next) {
            this.hash = hash;
            this.key = key;
            this.value = value;
            this.next = next;
        }
}
```

<ins>Buckets - array of node objects</ins>  
```
 Node<K,V>[]
```
HashMap<K,V> manages an array of Node<K,V> objects, that will be replaced by another larger array if all of its elements has been assigned value  


![Screenshot 2023-02-22 at 8 04 31 AM](https://user-images.githubusercontent.com/16437905/220506430-d0527dfd-5471-4a24-a64d-a20e3eeebeef.png)



Internally, the HashMap is an array of nodes, HashMap makes use of array and LinkedList for storing key-value pairs  
a node has a structure similar to a linked list node, An array of these nodes is called Bucket  

<ins>step 1:</ins> calculate the hashvalue using hash function  
<ins>step 2:</ins> based on hashvalue decide which bucket the value should be placed    
<ins>step 3:</ins> if we get two same hashvalue for different key, use the linkedlist structure, to place data in the same bucket sequentially   
<ins>step 4:</ins> if the threshold for the hashmap is more than    

<ins>Load Factor:</ins> The capacity is expanded as the number of elements in the HashMap increases, The load factor is the measure that decides when to increase the capacity of the Map, The default load factor is 75% of the capacity

<ins>Rehashing:</ins> Rehashing is the process of re-calculating the hash code of already stored entries, When the number of entries in the hash table exceeds the threshold value, the Map is rehashed so that it has approximately twice the number of buckets as before

<ins>Collision:</ins> A collision occurs when a hash function returns the same bucket location for two different keys


# Map


hashmap

concurrent hashmap

why map is not part of collection

hashmap internal working

hashtable vs hashmap

treemap
linkedhashmap


collections util class

https://www.interviewbit.com/java-collections-interview-questions/

https://www.javatpoint.com/working-of-hashmap-in-java


# Java Implementation

HashTable 
HashMap



# Time Complexity


main use of hashmap , O(1) Average time complexity
- map.containsKey(key)  -> O(1)
- map.put(key, value)   -> O(1)
- map.get(key)          -> O(1)
- map.remove(key)       -> O(1)

