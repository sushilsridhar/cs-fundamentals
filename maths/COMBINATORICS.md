# Combinatorics

Deals with the selection of objects according to some pattern and number of ways in which it can be done.  
- Permutation  
- Combination  

# Product rule - AND

If two events a1 and a2 can occur in m and n ways, then the number of ways of performing both (a1 AND a2) together is   
- m * n  

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
- m + n   

delhi  
f1 f2 f3 t1 t2  - there are 3 flights and 2 trains to reach jaipur  
jaipur  

total number of ways to reach jaipur is 3 + 2 = 5  

# Permutation

- Arrangement  

s1 s2 s3 -> arrange 3 people in the seats  

s1 - 3 possible people  
s2 - 2 possible people  
s1 - 1 possible people  


- n * n-1 * n-2 * .. n  
- **Permutation = n!**  

N distinct objects can be arranged on N distinct places in N! ways  

123456  
abcdef -> can be arranged in 6! ways  

123456  
aabbcc  

assume all are unique, can be arranged in 6! ways  
aa duplicate can be arranged in 2! ways, same for bb and cc  

6!/2! * 2! * 2!  

- total n elements, a repeats 1 time, b repeats 2 times, c - 3 times, d - 4 times  
- **Permutation with duplicates = (n!)/(a! * b! * c! * d!)**  


# Selection and Arrangement - <sup>N</sup> P <sub> R </sub>

5 people are going to watch a movie, only 2 tickets are there  

5 * 4  
s1 s2  

select 2 people from 5 people, and arrange them  
N distinct elements  -> R positions ( N >= R )

- <sup>N</sup> P <sub> R </sub> , arranging N distinct elements in R distinct positions


<sup>N</sup> P <sub> N </sub>, arranging N distinct elements in N distinct positions is N!  
but we do not have N positions, we have only R positions available, so we need to nullify the rest of positions other than R, (N - R)  

- **<sup>N</sup> P <sub> R </sub> = N!/(N-R)!**

- we are selecting R objects from available N objects and permutating them on the available R positions  


# Combinations

- selection
- out of N possible objects, if you want to select R objects, that's called combination

<sup> N </sup> P <sub> R </sub> = (selection) (arrangement)  

<sup> N </sup> P <sub> R </sub> = (<sup> N </sup> C <sub> R </sub>) * (R!)  


**<sup> N </sup> C <sub> R </sub> = N!/(R!) * (N-R)!**

example:  

5 people are going to watch a movie, only 2 tickets are there  

5 * 4  = 20  
s1 s2   

<sup> 5 </sup> P <sub> 2 </sub> = (<sup> 5 </sup> C <sub> 2 </sub>) * (2!)  

<sup> 5 </sup> P <sub> 2 </sub> = (5! * 2!/2! * 3!) = 5!/3! = 20  
