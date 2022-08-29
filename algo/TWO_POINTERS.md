# Two Pointers

> If array is sorted, think of two pointers  

generally denotes indexes in a array  

<ins>where to place pointers</ins>  

> the pointers should be placed such that, it provides a deterministic way of discarding elements,    

1. both pointers at the start   
2. both pointers at the end   
3. one at the start and another at the end  

<ins>both pointers at the start</ins>  
increasing j, increases result  
increasing i, decreases result  

![Screenshot 2022-08-20 at 4 05 23 PM](https://user-images.githubusercontent.com/16437905/185742175-9fb0bed7-18df-4cef-b05f-01ee330d9c46.png)


<ins>two pairs intuition</ins>  
place two pointers are different area and experiment, such that it provides a deterministic way of discarding elements  

<ins>three pairs intution</ins>  
fix one element using a for loop, use two pointers for finding the remaining pairs, 

<ins>duplicates</ins>  
use while loop internally to avoid duplicates or to count the duplicates   

<ins>two sorted arrays</ins>  
apply two pairs intuition with pointers at different arrays  

<ins>three sorted arrays</ins>   
have three pointers, the answer will increase or decrease by increasing or decreasing the value taken from any of the arrays  
