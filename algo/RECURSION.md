# Recursion

function calling itself   
> recursion is a technique of solving a problem using smaller instance of the same given problem

<ins>Steps for writing recursive code</ins>   
1. Assume that your code work
2. Identify recursive equation    
   main logic to solve bigger problems using smaller subproblems
3. Base condition,    
   when your code to should stop

> recursive code occupies stack space, which needs to be added to space complexity

# Recurrence Relation

<ins>Sum of n numbers</ins>

sum(n) = A<sub>1</sub> + A<sub>2</sub> + A<sub>3</sub> ... + A<sub>n</sub>

> Recursive equation : sum(n) = sum(n-1) + A<sub>n</sub>  

sum(n-1) is sum upto n-1 numbers + nth number, this is the recurrence relationship

tc: O(n), sc: O(n)  

<ins>Calculate Power</ins>  

A<sup>n</sup> = A<sup>n-1</sup> * A,   
A<sup>n</sup> is defined in terms of smaller subproblems  

> Recursive equation : power(A, n) = power(A, n-1) * A

tc: O(n), sc: O(n)  

a better recurrence relationship when   
n is even,  
A<sup>n</sup> = A<sup>n/2</sup> * A<sup>n/2</sup>   

n is odd,   
A<sup>n</sup> = A<sup>n/2</sup> * A<sup>n/2</sup> * A  

rewritten as when,  
n is even,  
> Recursive equation : A<sup>n</sup> = (A<sup>n/2</sup>)<sup>2</sup>   

n is odd,    
> Recursive equation : A<sup>n</sup> = (A<sup>n/2</sup>)<sup>2</sup> * A    

```
  int power(A, n) {
      if(n == 0) return 1;
      
      int x = power(A, n/2);
      if(n%2 == 0)
          return x * x;
      else 
          return x * x * A;
  }
```

n is divided into half for every function call, so the total number of function happens when n is divided by half on every step is log n,  
tc: O(log n), sc: O(log n)

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


sum of n numbers

