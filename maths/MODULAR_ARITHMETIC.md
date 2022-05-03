# Modular Arithmetic Formula
- (a + b) % m = ((a % m) + (b % m)) % m  

- (a % m) = (a + m) % m  
  
- (a * b) % m = ((a % m) * (b % m)) % m  

- (a - b) % m = ((a % m) - (b % m) + m) % m

eg for 1: a=6, b=8, M=10, 14%10 = 4, (6%10 + 8%10) -> crossing the range, so (6%10 + 8%10) % 10 = 14%10 = 4    
eg for 2: (3%5 = 8%5 = 13%5 = 18%5), adding m to numerator    

# Explanation for formula 4   
(a - b) % m = ((a % m) - (b % m) + m) % m  

a%m range is 0 to m-1  
b%m range is 0 to m-1  

a - b  
a is max, b is min -> gives max range  
a is min, b is max -> gives min range   

range is (-(m-1), m-1), since the range is -ve, we add +m to make it +ve  
(-(m-1), m-1) % m, we are doing a mod on the range, to make it +ve, add m, refer negative number mod operation  

new range (1, 2m-1)

# Euclidean division    
For a/b, a = b * q + r  
where r is remainder and q is quotient, r = a - b * q  
Note: In Java, this work only on positive numbers, for negative number division, check Divide_Without_Operators code in algorithms-ds-java project.  

Remainder = Divident - Divisor * quotient  
Divisor * quotient -> greatest multiple of divisor <= Divident  

100%7 = 100 - 98: 7 * 14  
-40%7 = -40 - (greatest multiple of 7 <=-40 : -42<=-40) answer: -40 -(-42) = 2,   
but in Java the answer for -40%7 is: -5, which is wrong, so  

# to offset Java mod operation
a%b, if a<0, answer = a%b + b

# % modulus operator - it limits data to a given range  
35%10 = 5  
x%10 = {0-9} in this range  
{-infinity to infinity, any number} % M = {0 to M-1}, in this range  

# Divisibility rule of numbers - taking advantage of mod

3 - sum of all digits should be divisible by 3    
1%3=1, 10%3=1, 10^2%3=1, 10^x%3=1  

number is 4372, -> 4*10^3 + 3*10^2 + 7*10^1 + 2*10^0 , take mod on both sides  
4372%3 = (4*10^3 + 3*10^2 + 7*10^1 + 2*10^0)%3, -> apply Modular Arithmetic, take mod inside, (4 + 3 + 7 + 2)%3  

4 - sum of last two digits should be divisible by 4  
10^2%4 = 0, 10^3%4 = 0, 10^4%4 = 0  

number is 3484, -> 3*10^3 + 4*10^2 + 8*10^1 + 4*10^0 , take mod on both sides    
3484%4 = (3*10^3 + 4*10^2 + 8*10^1 + 4*10^0)%4, -> apply Modular Arithmetic, take mod inside, (80 + 4)%4, 84%4 

# Inverse modulus

(a/b)%m = (a%m) / (b%m) ---> THIS IS WRONG FOR FRACTIONS  

(a/b)%m = (a * b^-1) % m ---> ((a % m) * (b^-1 % m)) % m  

(b^-1 % m) is called inverse modulus of b with respect to m   
let the inverse mod of b = x,   
(b * x) % m = 1, (we know that - (b * b^-1) % m = 1)  

eg: a = 10, m = 7  
x = 5, (10 * 5) % 7 = 1 --> a^-1 % m = 5  

# How to calculate Inverse mod 

a^-1 % m , 
- inverse mod exists only if a and m are co-prime, 
- gcd(a,m) = 1  

**Brute force - O(m)**  

for(1 to m-1) {  
if(a * i % m == 1) {  
return i;  
}  
}  

**Fermat's theorem**  
a^-1 % m , 
- m should be a prime number

**formula**
- a^-1 % m = a^(m-2) % m   

calculate a^(m-2) using power fn, with O(logn)
