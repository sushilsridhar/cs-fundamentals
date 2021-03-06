# Combinatorics

Deals with the selection of objects according to some pattern and number of ways in which it can be done.  
- Permutation  
- Combination  

# Product rule - AND

If two events a1 and a2 can occur in m and n ways, then the number of ways of performing both (a1 AND a2) together is   
> m * n  

<ins>eg:</ins>  
  
delhi  
| | |   
jaipur  
 |  |   
jaisalmer    

f1,f2,f3 - flights    
t1, t2 - trains  

3 - flights, 2 - trains ways, total - 6 ways to reach jaisalmer 


# Addition rule - OR

If two events a1 and a2 can occur in m and n ways, then the number of ways of performing either (a1 OR a2) is  
> m + n   

<ins>eg:</ins>  
delhi  
f1 f2 f3 t1 t2  - there are 3 flights and 2 trains to reach jaipur  
jaipur  

total number of ways to reach jaipur is 3 + 2 = 5  

# Permutation

> Arrangement  

s1 s2 s3 -> arrange 3 people in the seats  

s1 - 3 possible people  
s2 - 2 possible people  
s1 - 1 possible people  


<ins>Permutation formula</ins>  
> n * n-1 * n-2 * .. n  
> n!

N distinct objects can be arranged on N distinct places in N! ways  

123456  
abcdef -> can be arranged in 6! ways  

123456  
aabbcc  

assume all are unique, can be arranged in 6! ways  
aa duplicate can be arranged in 2! ways, same for bb and cc  

6!/2! * 2! * 2!  

<ins>Permutation with duplicates formula</ins>
> total n elements, a repeats 1 time, b repeats 2 times, c - 3 times, d - 4 times  
> (n!)/(a! * b! * c! * d!)


# Selection and Arrangement - <sup>N</sup> P <sub> R </sub>

5 people are going to watch a movie, only 2 tickets are there  

5 * 4  
s1 s2  

select 2 people from 5 people, and arrange them  
N distinct elements  -> R positions ( N >= R )

> <sup>N</sup> P <sub> R </sub> , arranging N distinct elements in R distinct positions


<sup>N</sup> P <sub> N </sub>, arranging N distinct elements in N distinct positions is N!  
but we do not have N positions, we have only R positions available, so we need to nullify the rest of positions other than R, (N - R)  

<ins><sup>N</sup> P <sub> R </sub>formula</ins>
> <sup>N</sup> P <sub> R </sub> = N!/(N-R)!

> we are selecting R objects from available N objects and permutating them on the available R positions  


# Combinations - <sup> N </sup> C <sub> R </sub>

> selection  
> out of N possible objects, if you want to select R objects, that's called combination

<sup> N </sup> P <sub> R </sub> = (selection) (arrangement)  

<sup> N </sup> P <sub> R </sub> = (<sup> N </sup> C <sub> R </sub>) * (R!)  

<ins><sup> N </sup> C <sub> R </sub> formula </ins>
> <sup> N </sup> C <sub> R </sub> = N!/(R!) * (N-R)!

<ins>example:</ins>  

5 people are going to watch a movie, only 2 tickets are there  

5 * 4  = 20  
s1 s2   

<sup> 5 </sup> P <sub> 2 </sub> = (<sup> 5 </sup> C <sub> 2 </sub>) * (2!)  

<sup> 5 </sup> P <sub> 2 </sub> = (5! * 2!/2! * 3!) = 5!/3! = 20  


# Properties of combinations

- <sup> N </sup> C <sub> 0 </sub> = 1 , (0! = 1)

- <sup> N </sup> C <sub> 1 </sub> = N 

- <sup> N </sup> C <sub> 2 </sub> = (N * (N-1))/2

- <sup> N </sup> C <sub> R </sub> = <sup> N </sup> C <sub> N-R </sub>

- <sup> N </sup> C <sub> R </sub> + <sup> N </sup> C <sub> R+1 </sub> = <sup> N+1 </sup> C <sub> R+1 </sub>


# Calculate <sup> N </sup> C <sub> R </sub> % m

<sup> N </sup> C <sub> R </sub> % m = ( N!/(R! * (N-R)!) ) % m  

(N! % m) * ( R! <sup>-1</sup> % m ) * ( (N-R)! <sup>-1</sup> % m)  

**<ins>Conditions for using inverse modulus</ins>**
- if m is prime, apply fermat's theorem
- if m is not prime, and R! & m are co-prime , iterate from 1 to m-1 and find  

**<ins>Solution using combination properties</ins>**

> <sup> N </sup> C <sub> R </sub> + <sup> N </sup> C <sub> R+1 </sub> = <sup> N+1 </sup> C <sub> R+1 </sub>

replace N+1 with N, R+1 with R

<sup> N-1 </sup> C <sub> R-1 </sub> + <sup> N-1 </sup> C <sub> R </sub> = <sup> N </sup> C <sub> R </sub>


**<ins>Logical explanation</ins>**

 > <sup> N </sup> C <sub> R </sub> = <sup> N-1 </sup> C <sub> R </sub> + <sup> N-1 </sup> C <sub> R-1 </sub>
 
 <sup> N-1 </sup> C <sub> R-1 </sub> -> selecting R out of N  
 
 1 2 3 4 5 ... N  
 
 1 -> either select one or not select one, only two options  
 
 select 1     -> <sup> N-1 </sup> C <sub> R-1 </sub>  
 not select 1 -> <sup> N-1 </sup> C <sub> R </sub>


**<ins>Code</ins>**

solving a larger problem by solving a smaller sub problem using recursion  

<ins>Base case: using combination properties</ins>  
> <sup> N </sup> C <sub> 0 </sub> = 1  
> <sup> 1 </sup> C <sub> 1 </sub> = 1  
> <sup> N </sup> C <sub> 1 </sub> = N  


recursion solution causing TLE - find optimized approach using DP

```
  private int calculate(int n, int r, int m) {

        if(r == 0 || n == r) {
            return 1;
        }

        if(r == 1) {
            return n%m;
        }

        int x = calculate(n-1, r, m)%m;
        int y = calculate(n-1, r-1, m)%m;

        return (x+y)%m;
    }
```

<ins>DP solution</ins>  
```
  private static int dpSolution(int A, int B, int C) {

        int n = A;
        int r = B;
        int m = C;

        int minValue = Math.min(n, r);
        int[][] matrix = new int[n+1][r+1];

        for(int i=0; i<=n; i++) {
            for(int j=0; j<=minValue; j++) {

                if(j==0 || j==i) {
                    matrix[i][j] = 1;
                } else if(i==0) {
                    matrix[i][j] = 0;
                } else {
                    matrix[i][j] = matrix[i-1][j-1] + matrix[i-1][j];
                    matrix[i][j] = matrix[i][j]%m;
                }
            }
        }

        return matrix[n][r]%m;
    }
```
