# Bit wise operators  
```
& | ^ ~  >> <<     
```
byte a = 10 , binary = 0000 1010  
byte a = -10, binary = ?  

```
-a = (2's compliment of a) = (1's compliment of a) + 1 = ~a + 1  
-a = ~a + 1  
```

problem with 1's complement  
0 = 0 0 0 0 0 0 0 0   
-0= 0 0 0 0 0 0 0 0   

~a(a=0), 1 1 1 1 1 1 1 1, this is wrong  
add 1, 0 0 0 0 0 0 0 1, this will become, 0 0 0 0 0 0 0 0 , the added 1 will overflow  
1 1 1 1 1 1 1 1  
0 0 0 0 0 0 0 1   

![Screenshot 2023-01-18 at 5 29 58 AM](https://user-images.githubusercontent.com/16437905/213038494-3690c252-b765-40e6-a1f3-40cc55faffb4.png)


# Left and Right shift 
for left shift  <<, the MSD digit should be disguarded   
for right shift >>, the MSD digit should be retained   

to check if the ith bit is set or not  
```
return ((n >> i) & 1) == 1  
return (n & (1 << i)) != 0  
return (n & (1 << i)) == Math.pow(2, i)  
```

In general  
left shift operator means,    
> ( << : multiply by 2 )     

right shift operator means,     
> ( >> : divide by 2 )

# Tricks - Bitwise Operators are faster  
a = 10 , a = 13  

```
if(a&1 == 0) a is even  
if(a&1 == 1) a is odd  

if(a|1 == a+1) a is even  
if(a|1 == a) a is odd    

if(a^1 == a+1) a is even  
if(a^1 == a-1) a is odd    
```

# Power function
custom power function, pow(2, N, P) -> tc: O(n)  
a<<n = a * 2^n  (provided there is no overflow)  
if a = 1,   
a<<n = 2^n, tc: O(1) for bit manipulation  
always use a<<n to calculate the power, if n is within the 32 for int, and within limit for other data type   

# Commutative property    
```
a & b = b & a  
a | b = b | a  
a ^ b = b ^ a  
```

# Associative property  
```
a & b & c  =  a & c & b  =  b & a & c  
a | b | c  =  a | c | b  =  b | a | c  
a ^ b ^ c  =  a ^ c ^ b  =  b ^ a ^ c  
```
```
a ^ a = 0  
a ^ 0 = a  
0 ^ 0 = 0  
0 ^ 1 = 1
```
```
a & a = a  
a & 0 = 0  
a | a = a  
a | 0 = a 
```
