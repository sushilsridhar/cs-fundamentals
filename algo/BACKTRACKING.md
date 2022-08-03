# Backtracking

<ins>Top Down</ins>  
solving a bigger problem by solving the smaller instance of the same given problem,  
mostly the code is recursive  

<ins>Bottom Up</ins>  
start with a smaller subproblem for which answer is known, from that try to build the answer of the bigger problem,  
mostly the code is iterative 

<ins>Exception</ins>
> Backtracking is bottom up approach, using recursion

![Screenshot 2022-08-02 at 8 38 13 AM](https://user-images.githubusercontent.com/16437905/182283500-bf9811ce-1a52-4713-bad2-72d65042d667.png)

# What is Backtracking?

> we came back from current state to previous state and found a new route,   
> we basically backtracked

![Screenshot 2022-08-02 at 9 08 41 AM](https://user-images.githubusercontent.com/16437905/182286775-af7e92ab-d6b3-4f50-b3e2-3b99f15daa88.png)

# Code structure

<ins>intuition</ins>  
intuition is trying out every combination like brute force, to generate a combinations  
there are two options in selection,  
either include that value or exclude that value in the ans container and move on to next index, when index is outofbound the base case is reached, process and return   

<ins>general time and space complexity</ins>  
O(2^n), where n is the total number of function calls that reaches the base case,   
for n=1, there are two choices, so two function calls, for n=2, there are 4 choices,  

total number of function calls is 2^0 + 2^1 + 2^2 ... 2^n ~ approx 2^n

space complexity is O(h), where h is the height of tree, at any point the max number of functions calls in the stack is n,  
if n=2, 2^n = 2^2 = 4 function calls are possible, due to sequencetial execution, in the stack there are only two levels of function calls, at any point,  
so space complexity is O(n)
    
<ins>pseudocode</ins>  
> do  
> function call  
> undo  

generate a state by adding something, process it and undo the addition to get back to previous state,    
from the previous state, generate a another new state by adding another thing  

generate binary array of size n,   

```
private static void backtracking(int index, int n, ArrayList<Integer> list) {

                if(index == n) {
                    for(int i: list) {
                        System.out.print(i+" ");
                    }
                    System.out.println("");
                    return;
                }

---> do         list.add(index, 0);
---> fn         backtracking(index+1, n, list);
---> undo       list.remove(index);

                list.add(index, 1);
                backtracking(index+1, n, list);
                list.remove(index);
    }

```
if n = 2, 
<pre>
output
0 0  
0 1  
1 0  
1 1  
</pre>
