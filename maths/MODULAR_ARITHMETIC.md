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

For a/b, where is a is Divident and b is Divisor  
> a = b * q + r  
> where r is remainder and q is quotient,   

r = a - b * q    

Note: In Java, this work only on positive numbers, for negative number division, check Divide_Without_Operators code in algorithms-ds-java project.  

**<ins> In other words</ins>**  
> Remainder = Divident - Divisor * quotient  
> Divisor * quotient -> is greatest multiple of divisor <= Divident  

<ins>example</ins>  
100%7 = 100 - 98 , 98 is 7 * 14 (which is greatest multiple of 7 less than 100)  
-40%7 = -40 - (greatest multiple of 7 <=-40 : -42<=-40) answer: -40 -(-42) = 2,   

but in Java the answer for -40%7 is: -5, which is wrong, so  

## to offset Java mod operation
> a%b, if a<0, answer = a%b + b  

-40%7 = -5 + 7 = 2  

**<ins>formula for both positive and negative numbers</ins>**  
> a%b = (a%b + b)%b  

<ins>example:</ins>  
40%7 = (5 + 7)%7 = (13)%7 = 5   
-40%7 = (-5 + 7)%7 = 2%7 = 2  

# % modulus operator - it limits data to a given range  
> 35%10 = 5  
> x%10 = {0 to 9}, between this range   

{-infinity to infinity, any number} % M = {0 to M-1}, between this range  

# Divisibility rule of numbers - taking advantage of mod

<ins>number 3</ins>    
> 3 - sum of all digits should be divisible by 3        

we know that,   
1 % 3 = 1, 10 % 3 = 1, 10<sup>2</sup> % 3 = 1, 10<sup>x</sup> % 3 = 1     

number is 4372, can be represented as  
4372 = 4 * 10<sup>3</sup> + 3 * 10<sup>2</sup> + 7 * 10<sup>1</sup> + 2 * 10<sup>0</sup> , take mod on both sides  

4372 % 3 = (4 * 10<sup>3</sup> + 3 * 10<sup>2</sup> + 7 * 10<sup>1</sup> + 2 * 10<sup>0</sup>)%3,   

apply Modular Arithmetic, take mod inside, (4 + 3 + 7 + 2)%3  

<ins>number 4</ins>  
> 4 - sum of last two digits should be divisible by 4  
  
10<sup>2</sup> % 4 = 0, 10<sup>3</sup> % 4 = 0, 10<sup>4</sup> % 4 = 0  

number is 3484, can be represented as   
3484 = 3 * 10<sup>3</sup> + 4 * 10<sup>2</sup> + 8 * 10<sup>1</sup> + 4 * 10<sup>0</sup>, take mod on both sides      
3484%4 = (3 * 10<sup>3</sup> + 4 * 10<sup>2</sup> + 8 * 10<sup>1</sup> + 4 * 10<sup>0</sup>)%4,   

apply Modular Arithmetic, take mod inside, (80 + 4)%4, 84 % 4   

# Binary Exponentiation (fast power)  

a<sup>n</sup> = a * a * a * ... n times  

> a<sup>8</sup> = a<sup>4</sup> * a<sup>4</sup>, problem divided into half

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

<ins>Notes:</ins>      
[Java Operator Precedence Rules](https://math.hws.edu/eck/cs124/javanotes6/c2/s5.html)  
(long)halfPower % m, in this expression, Simply put, a cast takes precedence over a mod operation,  




# Inverse modulus

<ins>Division - below formula is wrong for fractions </ins>  
(a/b)%m = (a%m) / (b%m)

<ins>Division - the right formula</ins>
> (a/b)%m = (a * b<sup>-1</sup>) % m  
> (a/b)%m = ((a % m) * (b<sup>-1</sup> % m)) % m  

> (b<sup>-1</sup> % m) is called inverse modulus of b with respect to m  
    
let the inverse mod of b = x,   
(b * x) % m = 1, (we know that - (b * b<sup>-1</sup>) % m = 1)  

value of x will be of range 0 to m-1,  
eg: a = 10, m = 7  
assume x = 5,   
(10 * 5) % 7 = 1 --> a<sup>-1</sup> % m = 5, which is within the range 0 to m-1    

# Condition for inverse mod to exist

a<sup>-1</sup> % m 
> inverse mod exists only if a and m are co-prime,   
> that is, gcd(a,m) = 1  

<ins>co-prime means</ins>  
15 and 8, Factors of 15 are 1, 3, 5, 15 and factors of 8 are 1, 2, 4, 8  
The only common factor is 1 and hence they are co-prime

**<ins>Applicaton of Inverse mod</ins>**  
> some problems ask to return,  
> ans % (10<sup>9</sup> + 7), if ans is a fraction (ans = a/b), we need to use inverse mod  

# How to calculate Inverse mod 

**<ins>Brute force approach</ins>**  

we know that, (a * a<sup>-1</sup>) % m = 1  
let a<sup>-1</sup> = x, if (a * x) % m = 1, then x is the inverse mod value  
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

a<sup>-1</sup> % m , 
> for fermat's theorem to be valid, m should be a prime number

Statement, a<sup>m-1</sup> is congruent to 1 mod m  
congruent means, (a congruent b)%m means, a%m = b%m  

(a<sup>m-1</sup>)%m = 1 % m, multiply by a<sup>-1</sup> on both sides,  
(a<sup>m-1</sup>)%m * (a<sup>-1</sup>)%m = a<sup>-1</sup> % m,  
(a<sup>m-2</sup>) % m = a<sup>-1</sup> % m

<ins>Formula</ins>
> a<sup>-1</sup> % m = a<sup>(m-2)</sup> % m   

<ins>Code</ins>  

calculate a<sup>(m-2)</sup> using power fn,  

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


# Apply Fermat's theorem

**<ins>(10<sup>9</sup> + 7) is a prime number, apply Fermat's theorem</ins>**  
> some problems ask to return,  
> ans % m, if ans is a fraction (ans = a/b = a * b<sup>-1</sup>) and given m = (10<sup>9</sup> + 7), which is a prime number,  
> we can directly apply fermat's theorem  
> b<sup>-1</sup> % m = b<sup>(m-2)</sup> % m 

**<ins> Calculate b factorial in, a<sup>b!</sup> % m </ins>**

fermat's theorem  

> a<sup>m</sup> = a mod m  
> a<sup>m-1</sup> = 1 mod m  

we need to calculate a <sup>b!</sup>, if we can express a <sup>b!</sup> as a <sup>m-1</sup>  * a <sup>m-1</sup>....  

> a <sup>b!</sup> = (a <sup>m-1</sup> * a <sup>m-1</sup> * a <sup>m-1</sup> .. a<sup>x</sup> ) % m  
> a <sup>b!</sup> = (1 mod m) * (1 mod m) * ... a <sup>x</sup> % m  
> a <sup>b!</sup> = a <sup>x</sup> % m  

b! is expressed as m-1, the remaining left over number will be,  
x = b! % (m-1)  

find x and using fast exponential fn to calculate a <sup> x </sup>  
  
tc: O(B + log x)  
sc: O(log x)  

