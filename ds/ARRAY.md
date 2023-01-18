# Static Array

> Arrays are contiguous sections within memory  

> Random accessing of element is O(1), because of storing in contiguous section   

> Fixed size (need to define the size durning initialization)   

<ins>How array is created</ins>      
so to create an array you would need to reserve a chunk of memory which is of size n * sizeof(type), where n is the amount of items 
you would like to store and the sizeof(type) would return the size, in bytes which the JVM would need to represent that given type       

> You would then store a reference (pointer) to the first location of your memory segment,      
 
say 0x00, and then you use that as a base to know how much you need to move to access the elements,     
so a[n] would be equal to doing 0x00 + (n * sizeof(type))       

# Array structure


Assume you have to write a code that takes the marks of five students, Instead of creating five different variables, you can just create an array of    lengths of five, As a result, it is so easy to store and access data from only one place, and also, it is memory efficient   


![Screenshot 2023-01-18 at 1 32 46 PM](https://user-images.githubusercontent.com/16437905/213116371-49432122-ea0d-47f1-89fe-731c93285b05.png)

![Screenshot 2023-01-18 at 1 33 06 PM](https://user-images.githubusercontent.com/16437905/213116380-72c4828b-7338-41c7-a2ad-575ce5a940c4.png)


Static array is built in Java language,

```
int[] arr = new int[10];  
int[] arr = {1, 2, 3};
```

# Dynamic Array

> Built on top of static array, size can be increased or decreased as required    

```
private int capacity = 10; //default size is 10 in ArrayList - Java 8
private int length = 0;
private int[] internalArray = new int[capacity];

public void push(int element) {
    checkCapacityAndIncreaseIfRequired();
    internalArray[length] = element;
    length++;
}
```

to increase or decrease capacity, a new array of required size is created and all elements are copied to new array,    
using the native method System.arraycopy
  
```
System.arraycopy(original, 0, copy, 0, size);

tc: O(n), but takes half the time of copying with for loop    
```

<ins>Java implementation</ins>      

```


```

# When to choose Arrays

> when O(1) random access time is required    

# Time complexity

| Operations | Static Array | Dynamic Array |
:---: | :---: | :---: |
get                   | O(1)   | O(1)
add(element)          |  -     | O(1) or O(n) , O(1) Amortized   
add(index, element)   | O(n)   | O(n)
remove                | O(n)   | O(n)



# Subarray
Arrays.toString();
cover arrays utils class 

[SUBARRAY_SUBSEQUENCE_SUBSET](https://github.com/sushilsridhar/cs-fundamentals/blob/main/algo/SUBARRAY_SUBSEQUENCE_SUBSET.md)

total number of subarray - n(n+1)/2



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
