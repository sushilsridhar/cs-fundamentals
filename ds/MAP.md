# Why map?



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

```
 private static class Entry<K,V> implements Map.Entry<K,V> {
        final int hash;
        final K key;
        V value;
        Entry<K,V> next;

        protected Entry(int hash, K key, V value, Entry<K,V> next) {
            this.hash = hash;
            this.key =  key;
            this.value = value;
            this.next = next;
        }
 }

```
# Map
> Map is part of Java collection framework, but it doesn't implement Collection class, as it saves data in Key-value pair


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

