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

# Structure

> Built on top of Array and LinkedList      

<ins>Note:</ins>     
From Java 8 onward, Java has started using Self-Balancing BST instead of a linked list for chaining. The advantage of self-balancing BST is, in the worst case (when every key maps to the same slot) search time is O(Log n)    

![Screenshot 2023-02-22 at 8 04 31 AM](https://user-images.githubusercontent.com/16437905/220506430-d0527dfd-5471-4a24-a64d-a20e3eeebeef.png)


<ins>Map Interface</ins>  
```
public interface Map<K,V> {

   interface Entry<K,V> {
   
   }
}
```

<ins>HashMap - Node implements Map.Entry</ins>        
Node structure    
```
class HashMap<K, V> {

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
}
```

# Hashing

Hashing in Java is the technique that enables us to store the data in the form of key-value pairs, by modifying the original key using the hash function so that we can use these modified keys as the index of an array and store the associated data at that index location in the Hash table for each key

<ins>Hash Function</ins>    

keys are converted into hash values (fixed length) using a hash function and these hash values are used as the index of the hash table to store the associated data

Hash table uses hash values as the location index to store the associated data in the array

![Screenshot 2023-02-12 at 6 42 30 AM](https://user-images.githubusercontent.com/16437905/218287854-c8da66dc-7161-48fc-8ee4-a9d31e8f4ac5.png)

![Screenshot 2023-02-12 at 6 42 38 AM](https://user-images.githubusercontent.com/16437905/218287856-058f5d6f-290c-4f08-b9df-4d1eadfa6426.png)

# Internal working

```
HashMap<Integer, Integer> map = new HashMap<>();

map.put(key, value);
```
<ins>Initial capacity</ins>      
the default initial capacity is 16, set it to bigger number if you know there will be more values in hashmap, because rehashing is expensive    

<ins>step 1:</ins> 
calculate the hashvalue using hash function  

basic hash function,    
Hash(key) = key%10 -> limits the range to 0-10,       

![Screenshot 2023-02-22 at 9 25 57 AM](https://user-images.githubusercontent.com/16437905/220518025-187097e0-2174-4350-8f54-8af1eff082ca.png)


HashMap<K,V> manages an array of Node<K,V> objects, that will be replaced by another larger array if all of its elements has been assigned value  





Internally, the HashMap is an array of nodes, HashMap makes use of array and LinkedList for storing key-value pairs  
a node has a structure similar to a linked list node, An array of these nodes is called Bucket  

<ins>step 2:</ins> based on hashvalue, calculate the index inside the bucket at which the value should be placed    
<ins>step 3:</ins> if we get two same hashvalue for different keys, use the linkedlist structure, to place data in the same bucket sequentially   
<ins>step 4:</ins> if the size for the hashmap is more than load factor * capacity (threshold), increase size and do rehashing  

<ins>Load Factor:</ins> The capacity is expanded as the number of elements in the HashMap increases, The load factor is the measure that decides when to increase the capacity of the Map, The default load factor is 75% of the capacity

<ins>Rehashing:</ins> Rehashing is the process of re-calculating the hash code of already stored entries, When the number of entries in the hash table exceeds the threshold value, the Map is rehashed so that it has approximately twice the number of buckets as before

<ins>Collision:</ins> A collision occurs when a hash function returns the same bucket location for two different keys

Chaining: Although the hash function should minimize the collision, if it still happens then we can use an array of LinkedList as a hash table to store data, the fundamental idea is for each hash table slot to point to a linked list of records with the same hash value. This technique is called chaining type of hashing in java.


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

# Real world applications
1. key-value pair data
2. in-memory cache for static/near static values. All your system properties, static business data
3. distributed caching systems like Couchbase, membase, redis are sort of hashmaps extended to handle high concurrency and large scale data through replication and distribution
