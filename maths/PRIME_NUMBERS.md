# Prime numbers

> A number divisible only by 1 and itself  
> number of factors is 2

negative numbers can't be prime  

**<ins>find total number of factors of a number</ins>**   
tc: O(sqrt(n))  

```
 for(int i=1; i*i<=n; i++) {
            if(n%i == 0) {
                count++;

                if(n/i != i) {
                    count++;
                }
            }
        }
```

if n%i == 0, 
> n is a factor,  
> then n/i is also a factor

Divisors - The divisor is any number that divides another number  
factors - A factor, however, is a divisor that divides the number entirely and leaves no remainder

So, all factors of a number are its divisors  

**<ins>co-prime definition</ins>**   
15 and 8, Factors of 15 are 1, 3, 5, 15 and factors of 8 are 1, 2, 4, 8  
The only common factor is 1 and hence they are co-prime

# Sieve of Eratosthenes



# Goldbach's conjecture 
 
> Goldbach's conjecture states that every even integer greater than 2 can be expressed as the sum of two primes    
> This conjecture is not proven yet but verified uptil 4 * 10<sup>18</sup> integers  
    

