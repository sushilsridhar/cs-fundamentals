# Modular Arithmetic Formula  

<ins>Addition</ins>
> (a + b) % m = ((a % m) + (b % m)) % m  
  
> (a % m) = (a + m) % m    

<ins>Multiplicaiton</ins>  
> (a * b) % m = ((a % m) * (b % m)) % m  

<ins>Subtraction</ins>     
> (a - b) % m = ((a % m) - (b % m) + m) % m  

eg for 1: a=6, b=8, M=10, 14%10 = 4, (6%10 + 8%10) -> crossing the range, so (6%10 + 8%10) % 10 = 14%10 = 4    
eg for 2: (3%5 = 8%5 = 13%5 = 18%5), adding m to numerator    

# Explanation for Subtraction formula   
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

<ins>Division - below formula is wrong for fractions </ins>  
(a/b)%m = (a%m) / (b%m)

<ins>Division - the right formula</ins>
> (a/b)%m = (a * b^-1) % m  
> (a/b)%m = ((a % m) * (b^-1 % m)) % m  

> (b^-1 % m) is called inverse modulus of b with respect to m  
    
let the inverse mod of b = x,   
(b * x) % m = 1, (we know that - (b * b^-1) % m = 1)  

value of x will be of range 0 to m-1,  
eg: a = 10, m = 7  
assume x = 5,   
(10 * 5) % 7 = 1 --> a^-1 % m = 5, which is within the range 0 to m-1    

# Condition for inverse mod to exist

a^-1 % m 
> inverse mod exists only if a and m are co-prime,   
> that is, gcd(a,m) = 1  

<ins>co-prime means</ins>  
15 and 8, Factors of 15 are 1, 3, 5, 15 and factors of 8 are 1, 2, 4, 8  
The only common factor is 1 and hence they are co-prime

**<ins>Applicaton of Inverse mod</ins>**  
> some problems ask to return,  
> ans % (10^9 + 7), if ans is a fraction (ans = a/b), we need to use inverse mod  

# How to calculate Inverse mod 

**<ins>Brute force approach</ins>**  

we know that, (a * a^-1) % m = 1  
let a^-1 = x, if (a * x) % m = 1, then x is the inverse mod value  
the range of the x will be from 1 to m-1,  

tc: O(m)  

```
  for(1 to m-1) {  
    if((a * i) % m == 1) {  
      return i;  
    }  
  }  
```     

**<ins>Fermat's theorem</ins>**  

a^-1 % m , 
> for fermat's theorem to be valid, m should be a prime number

Statement, a^m-1 is congruent to 1 mod m  
congruent means, (a congruent b)%m means, a%m = b%m  

(a^m-1)%m = 1 % m, multiply by a^-1 on both sides,  
(a^m-1)%m * (a^-1)%m = a^-1 % m,  
(a^m-2) % m = a^-1 % m

<ins>Formula</ins>
> a^-1 % m = a^(m-2) % m   

<ins>Code</ins>  

calculate a^(m-2) using power fn,  

tc: O(log n)  
sc: O(log n)  
```
    private static int powerFunction(int a, int n, int m) {

        if(a == 0) {
            return 0;
        }

        if(n == 0) {
            return 1;
        }

        int halfPower = powerFunction(a, n/2, m);
        long power = 0;

        if(n%2 == 1) {
            power = ((long)halfPower%m * halfPower%m * (a%m + m)) % m;
        } else {
            power = ((long)halfPower%m * halfPower%m) % m;
        }

        return (int)power;
    }
```

**<ins>(10^9 + 7) is a prime number, apply Fermat's theorem</ins>**  
> some problems ask to return,  
> ans % m, if ans is a fraction (ans = a/b) and given m = (10^9 + 7), which is a prime number,  
> we can directly apply fermat's theorem
