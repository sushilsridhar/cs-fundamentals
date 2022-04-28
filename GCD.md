# GCD

Greatest common divisor, Highest common factor (hcf) -> both are same  

gcd(a,b) -> greatest factor which divides both a and b    

5 is the gcd   
15 -> 1 3  5 15   
25 -> 1 5 25  

6/2 = 3, 2 * 3 are the factors, so the word divisor and factors are same  

gcd(10, -25) is 5, -25 will have both positive and negative factors, -5 and 5, greatest is positive factor  

# Properties of GCD

- gcd(a,b) = gcd(|a|,|b|)
- gcd(a,b) = gcd(b,a) -> commutative 
- gcd(0,x) is |x|,  
  if x = 0, then gcd(0,0) is undefined
- gcd(a,b,c) = gcd(gcd(a,b), c) = gcd(gcd(a,c), b) = gcd(gcd(b,c), a)  
  associative  
  
# Euclidean Algorithm

if a,b such that a >= b,  

gcd(a,b) = x, assumption, then a%x = 0, b%x = 0, then    
gcd(a-b, b) = x  

gcd(a,b) = gcd(a-b, b)  

proof -> a%x = 0 = b%x -> (a-b)%x = 0 -> a%x = (a-b)%x  

gcd(23, 5) -> (18,5) -> (13,5) -> (8,5) -> (3,5)  
gcd(a, b) (a>b) -> gcd(b, a-b) -> recursive call -> gcd(b, a-2b) -> gcd(b, a-3b) -> gcd(b, a-xb)...    
xb is the max multiple of b which is less than a ( 18 - 5 * 3)  

euclidean algo -> gcd(a,b) = gcd(b, a%b)  

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


