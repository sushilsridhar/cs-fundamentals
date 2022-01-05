# Bit wise operators  
& | ^ ~  

byte a = 10 , binary = 0000 1010  
byte a = -10, binary = ?  

-a = 2's compliment of a = 1's compliment of a + 1 = ~a + 1  
-a = ~a + 1  

# Left and Right shift 
for left shift  <<, the MSD digit should be disguarded   
for right shift >>, the MSD digit should be retained   

to check if the ith bit is set or not  
return ((n >> i) & 1) == 1  
return (n & (1 << i)) == Math.pow(2, i)

# tricks    
a = 10 , a = 13  

if(a&1 == 0) a is even  
if(a&1 == 1) a is odd  

if(a|1 == a+1) a is even  
if(a|1 == a) a is odd    

if(a^1 == a+1) a is even  
if(a^1 == a-1) a is odd    

# Commutative property    
a & b = b & a  
a | b = b | a  
a ^ b = b ^ a  

# Associative property  
a & b & c  =  a & c & b  =  b & a & c  
a | b | c  =  a | c | b  =  b | a | c  
a ^ b ^ c  =  a ^ c ^ b  =  b ^ a ^ c  

a ^ a = 0  
a ^ 0 = a  
0 ^ 0 = 0  
0 ^ 1 = 1
