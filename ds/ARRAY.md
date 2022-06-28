# Array

# Dynamic Array

# Java implementation

ArrayList  
Vector  

find out what are the ds that uses array internally?


Vectors are synchronized, ArrayLists are not.
Data Growth Methods
Use ArrayLists if there is no specific requirement to use Vectors.

Internally, both the ArrayList and Vector hold onto their contents using an Array. When an element is inserted into an ArrayList or a Vector, 
the object will need to expand its internal array if it runs out of room. 
A Vector defaults to doubling the size of its array, while the ArrayList increases its array size by 50 percent.


Applications
1. freq array to map between indexes and values
