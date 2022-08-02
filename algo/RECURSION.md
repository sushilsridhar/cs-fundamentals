# Time Complexity 

**Recurrence Relation**  
T(N) = T(N/2) + 1 --> tc: O(log N)  
- power function  
- binary search  


T(N) = 2T(N/2) + 1 --> tc: O(N)  
fn() {  
  fn(n/2)  
  fn(n/2)  
}  


T(N) = 2T(N/2) + O(N) --> tc: O(NlogN)  
fn() {  
  fn(n/2)  
  fn(n/2)    
  for(i to n)  
}  
- merge sort 
- quick sort

# Space Complexity

maximum size of the stack at any point of time  
max height of the recursion tree  

SumOfDigits: sc --> O(n)  
fibonacci:   sc --> O(n), n is the max height of the recursion tree  
power fn:    sc --> O(log n), where n is the power, eg: 2^n  
