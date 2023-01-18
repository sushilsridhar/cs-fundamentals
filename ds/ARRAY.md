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

> Vector is same as ArrayList, but synchronized (even get method is synchronized)

Vector is legacy class created before Arraylist, a Vector defaults to doubling the size of its array, while the ArrayList   
increases its array size by 50 percent  

```
ArrayList<Integer> list = new ArrayList<>();

Vector<Integer> vector = new Vector<>();
```

# When to choose Arrays

<ins>static array</ins>  
> when O(1) random access time is required    

<ins>dynamic array</ins>  
> variable size with O(1) random access

<ins>Vector</ins>  
> thread safe dynamic array  

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

[What is Subarray? Subsequence? Subset?](https://github.com/sushilsridhar/cs-fundamentals/blob/main/algo/SUBARRAY_SUBSEQUENCE_SUBSET.md)

total number of subarray - n(n+1)/2


# check

To solve arrays,

1) use HashSet or HashMap
2) two pointer approach, where inserting into same array (in-place questions)
   one index for iterating, other for tracking the lastNonZeroElementIndex (or any requirement)


Array Techniques

1)Contribution technique - Adding contribution of each and every element, finding the number of occurrence of one element in all subarrays, and adding them individually
2)Carry forward - carring the previous subarray sum to new subarray
3)Sliding window - for the new subarray, subtract the previous element to startindex and add the element of new end index
4)Two pointer - for removing duplicate element, using the same input array itself for processing, without extra space
5)Prefix Sum - for problems with queries, Add X to array, from startIndex to endIndex, eg 4-8, add 9 , 0-4, add 14

