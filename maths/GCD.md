# GCD

> Greatest common divisor, Highest common factor (hcf)  
> both are same   

<ins>Definition</ins>  
gcd(a,b) is the greatest factor which divides both a and b    

gcd(15,25) is 5  

15 -> 1 3  5 15   
25 -> 1 5 25  

<ins>Divisor and Factors</ins>  
6/2 = 3, 2 * 3 are the factors, so the word divisor and factors are same  

<ins>Negative numbers</ins>  
gcd(10, -25) is 5, 

10  -> 1 2 5 10  
-25 -> -25 -5 -1 1 5 25    

-25 will have both positive and negative factors, in gcd we look for the greatest common factor,  
so answer is 5  

# Properties of GCD

<ins>one</ins>  
> gcd(a, b) = gcd( |a|, |b| )    

negative values of a and b will have only positive gcd  

<ins>two</ins>  
commutative property,  

> gcd(a, b) = gcd(b, a)   

<ins>three</ins>  
> gcd(0, x) is |x|,   

if x = 8,  
0 -> 1 2 3 4 5 6 7 8  
8 -> 1 2 4 8  

if x = 0, then gcd(0, 0) is undefined  

<ins>four</ins>  
associative property,  

> gcd(a, b, c) = gcd(gcd(a, b), c) = gcd(gcd(a, c), b) = gcd(gcd(b, c), a)  


# How to calculate GCD

<ins>brute force</ins>  

find all common factors for a and b,    
tc: O(minValue(a,b))
```
    private static int bruteForceGCD(int a, int b) {

        for(int i=Math.min(a,b); i>=1; i--) {
            if((a%i == 0) && (b%i == 0)) {
                return i;
            }
        }
        return 1;
    }
```

<ins>optimized</ins>  

only iterate over the factors of min(a, b), gcd will be same as greatest factor that divides a and b,   
tc: O(sqrt(min(a, b))  

```
    private static int gcd(int a, int b) {
        int x = Math.min(a,b);
        int y = Math.max(a,b);

        for(int i = (int) Math.sqrt(x); i>=1; i--) {
            if(x%i == 0) { 

                // 2 factors are there , if i is factor, x/i is also a factor,
                // since we are using sqrt root, we need to consider two factors in single iteration

                int anotherFactorOfX = x/i; // this factor will always be the greatest factor than i

                if(y%anotherFactorOfX == 0) {
                    return anotherFactorOfX;
                } else if(y%i == 0) {
                    return i;
                }
            }
        }

        return 1;
    }
```
  
# Euclidean Algorithm

> gcd(a, b) = gcd(a-b, b)    

<ins>proof</ins>  
consider a,b such that a >= b,  
if gcd(a,b) = x, it means a%x = 0, b%x = 0,     

x is a factor of a and factor of b, then x is also a factor of a-b    
a%x = b%x = 0 = (a-b)%x = 0  

we can conclude that,  
gcd(a,b) = x = gcd(a-b, b)  

a=25, b=15, a>=b,  
25 -> 1 5 25  
15 -> 1 3 5 15  

a-b = 25-15 = 10  
10 -> 1 2 5 10  

gcd(25, 15) = 5  
gcd(10, 25) = 5  
gcd(10, 15) = 5  

hence, gcd(25, 15) = gcd(10, 25) = gcd(10, 15) = gcd(a, b) = gcd(a-b, b) = x

gcd(25, 15) -> (15, 10) -> (10, 5) -> (5, 5) -> (5, 0) -> 5    

> continues substraction make a or b to reach 0,   
> then apply this property to gcd(0, x) is |x|, to get the gcd     

tc: O(log(max(a,b)))

```
    private static int gcd(int A, int B) {

        if(A < B) {
            int temp = B;
            B = A;
            A = temp;
        }

        if(B == 0) {
            return A;
        }

        return gcd(A-B, B);
    }
```

<ins>Euclidean algo equation</ins>  
> gcd(a,b) = gcd(b, a%b)    

TODO 

gcd(a, b) (a>b) -> gcd(b, a-b) -> recursive call -> gcd(b, a-2b) -> gcd(b, a-3b) -> gcd(b, a-xb)...    
xb is the max multiple of b which is less than a ( 18 - 5 * 3)  



``` 
int euclideanAlgo(int A, int B) {
        
        if(B == 0) {
            return A;
        }

        return euclideanAlgo(B, A%B);
    }
```

eg:  
gcd(6,21)  
gcd(21, 6%21)  
gcd(6,3)  
gcd(3,0)  

tc: O(log(max(a,b)))


