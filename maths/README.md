# Logarithms  
 8 -> 4 -> 2 -> 1 , how many times to divide 8 by 2 to get 1? 3 times,   
 log<sub>2</sub>(8) = 3    
 
 2^3 = 8, can be written as,  
 3 = log<sub>2</sub>(8)  

# Formula  

Sum of n natural numbers (1,2,3,4..)  
n(n+1)/2   

Sum of n-1 natural numbers (n-1, n-2, n-3, ... 0)  
n(n-1)/2  

Number of odd numbers between 1-N (1,3,5,7,..)  
(n+1)/2  

Number of even numbers between 1-N (2,4,6,8..)  
(n+1)/2  

Sum of n odd numbers is n^2   

<ins>Arithmetic Progression</ins>    
Sum of a particular sequence of numbers (ex: 5,6,7,8,9,10)  

Arithmetic progression formula = n/2 * [2a + (n-1) * d]     
where a is first term of AP and d is difference between two terms, which is 1 and n is total size  

# Numbers  
Decimal number is represented as,   
5649 = 5 thousand 6 hundred 40 nine = 5 * 10<sup>3</sup> + 6 * 10<sup>2</sup> + 4 * 10<sup>1</sup> + 9   

similiarly 8 bit binary number of 29 can be represented as,  
<pre>
  _    _    _    _    _    _    _    _    
-2^7  2^6  2^5  2^4  2^3  2^2  2^1  2^0


  0    0    0    1    1    1    0    1
  _    _    _    _    _    _    _    _    
-2^7  2^6  2^5  2^4  2^3  2^2  2^1  2^0


0 0 0 1 1 1 0 1  =  1 * 2<sup>0</sup> + 1 * 2<sup>2</sup> + 1 * 2<sup>3</sup> + 1 * 2<sup>4</sup>  =  29    
</pre>

<ins>Decimal</ins>  
each bit can contain numbers only between 0-9,  
max limit [0, 9] , eg: 76861879    

<ins>Octal</ins>  
each bit can contain numbers only between 0-7,   
max limit [0, 7]  

<ins>Terinary</ins>  
each bit can contain numbers only between 0-2,   
max limit [0, 2]  

<ins>Binary</ins>  
each bit can contain either 0 or 1,  
max limit [0, 1], eg: 10011001  

# Binary to Decimal, Decimal to Binary

2|29 - 1    
2|14 - 0    
2|7  - 1  
2|3  - 1  
2|1  - 1    

29 - 00011101  

<pre>

  0    0    0    1    1    1    0    1
  _    _    _    _    _    _    _    _    
-2^7  2^6  2^5  2^4  2^3  2^2  2^1  2^0 

1 * 2<sup>0</sup>  +     
0 * 2<sup>1</sup>  +   
1 * 2<sup>2</sup>  +   
1 * 2<sup>3</sup>  +   
1 * 2<sup>4</sup>   

= 29   
</pre>

# Size of Java Data Types

<ins>1byte (8 bits)</ins>      
<pre>

  _    _    _    _    _    _    _    _    
-2^7  2^6  2^5  2^4  2^3  2^2  2^1  2^0

last bit is called most significant bit (msb - it is used to represent negative numbers)  

  1    0    0    0    0    0    0    0
  _    _    _    _    _    _    _    _    
-2^7  2^6  2^5  2^4  2^3  2^2  2^1  2^0

<ins>limits</ins>  
min value is 10000000 = -128  
max value is 01111111 = 127  

</pre>

<ins>Generalized formula</ins>  
n = 8bits, range can be written as    

> [-2<sup>n-1</sup>, 2<sup>n-1</sup> -1]    

[-2<sup>7</sup>, 2<sup>7</sup> -1] = [-128, 127]  


<ins>Geometric Progression</ins>  
-2<sup>n-1</sup> can be written as, 
[2^0 + 2^1 + 2^2 + 2^3 + 2^4 + 2^5 + 2^6 + ... + 2^N-2],      
2^0 + 2^1 + 2^2 + 2^3 + 2^4 + 2^5 + 2^6 + ... + 2^N-2, is called Geometric progression   

formula  
first term, a = 2<sup>0</sup> = 1  
common ratio, r = 2  
total elements = 2<sup>0</sup> + 2<sup>N-2</sup> = 2<sup>N-1</sup>,     
> formula = a(r<sup>t</sup> -1)/r-1 , answer = (2<sup>N-1</sup>) -1  



<ins>byte range</ins>  
1 byte  =  8 bits  =  [-2<sup>8-1</sup>, 2<sup>8-1</sup> -1]  =  [-128, 127]  

<ins>short int range</ins>  
2 bytes = 16 bits = [-2<sup>16-1</sup>, 2<sup>16-1</sup> -1]  = [-32768, 32767]   

<ins>int range</ins>  
4 bytes = 32 bits = [-2<sup>32-1</sup>, 2<sup>32-1</sup> -1]  = [-2,147,483,648, 2,147,483,647]  


# Understanding Problem Constraints

> 2<sup>10</sup> = 1024 ~~ 1000 = 10<sup>3</sup>,  
> 2<sup>10</sup> ~~ 10<sup>3</sup>  

<ins>int range</ins>  

4 bytes = 32 bits = [-2<sup>32-1</sup>, 2<sup>32-1</sup> -1]  

[-2<sup>31</sup>, 2<sup>31</sup> -1]

<pre>
-2<sup>31</sup>   = -2  *  2<sup>10</sup>  *  2<sup>10</sup>  *  2<sup>10</sup>  
2<sup>31</sup> -1 =  2  *  2<sup>10</sup>  *  2<sup>10</sup>  *  2<sup>10</sup> -1  

[-2  *  10<sup>3</sup>  *  10<sup>3</sup>  *  10<sup>3</sup>,  2  *  10<sup>3</sup>  *  10<sup>3</sup>  *  10<sup>3</sup>  -1]   
</pre>


integer limit can also be written as approx,   

> [-2 * 10<sup>9</sup>, 2 * 10<sup>9</sup>]  

# Numbers Included and Excluded
[a-b]  - including a and b, there are total b-a+1 numbers  
(a-b]  - excluding a and including b, there are total b-a numbers  
(a-b)  - excluding a and b, there are total b-a-1 numbers  

<ins>example</ins>  
[3-10] - including 3 and 10, there are total 8 numbers, (10-3+1 = 8)    

