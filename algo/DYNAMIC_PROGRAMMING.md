# Dynamic Programming

> smart brute force

<ins>Fibonacci series</ins>  
recurrence relation: f(n) = f(n-1) + f(n-2)

```
  int f(int n) {
      if(n <= 2) return n-1;
      return f(n-1) + f(n-2);
  }
```
total number of function calls, 2^n  
total number of unique function calls, n 

![fibonacci tc](https://user-images.githubusercontent.com/16437905/180906541-f4f07a2e-250f-4193-a095-a9cd6adb8f57.png)

<ins>fibonacci with dp</ins>  
> by using dp we can reduce the time complexity of this problem to n,   
> by saving the results of unique function calls in a container   

![fbonacci dp](https://user-images.githubusercontent.com/16437905/180906809-d4d731c0-c34d-485d-ab9f-bbffbd9cf58e.png)


# When to use DP?

we can solve a problem using dp when the problem has,  

<ins>Optimal Substructure</ins>  
If the optimal answer of the problem can be obtained by the optimal answer of the subproblems  

<ins>Overlapping subproblems</ins> (not mandatory)  
reptition of subproblems  

we can use dp only for problems whose states are <ins> Directed Acyclic graphs</ins> (DAG)  
there should be no loop in states for calculating optimal answer of subproblems  

# Memoization

> Saving the results of states and using them in future  

<ins>usefull when</ins>  
> actuall function calls > number of unique function calls  

# Code structure
tc: O(n), sc: O(n)

```
int[] dp = new int[n+1]; --> initialized with {-1}

int fibonacci(int[] dp, int n) {

--> base condition       if(n < 2) {      
                              return n;
                         }  

--> check                if(dp[n] != -1) {
                              return dp[n];
                         }

--> calculate            int ans = fibonacci(dp, n-1) + fibonacci(dp, n-2);
--> store                dp[n] = ans;
--> return               return ans;

    }
```

# Two approaches to solve DP problems

<ins>Top-down way</ins>  
> recursion + memoization  

Look at n and try to divide it in to subproblems and try to find the solution for the subproblems,  

recurrence relation,  
> fib(n) = fib(n-1) + fib(n-2)  

```   
       fib(n)
    /          \ 
fib(n-1)      fib(n-2)
```

<ins>Bottom-up way</ins>  
> Iterative + tabulation  

start with subproblems, calculate their solutions and use them to calculate parent problem, keep doing until n is reached,  

```
int[] f = new int[n+1];
f[1] = 0;
f[2] = 1;
for(int i=3; i<=n; i++) {
    f[i] = f[i-1] + f[i-2]
}
```
Instead a f array, we can just use two variables, to reduce space complexity to O(1),  
In most cases, the Iterative approach will help to save space,   

> memoization and tabulation are same


