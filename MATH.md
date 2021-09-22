# logarithms  
 8->4->2->1 , how many times we divide 8 by 2 to get 1, 3 times, log2(8) = 3  
 2^3 = 8, can be written as,  
 3 = log2(8)

# Numbers  
- Decimal - max limit [0,9] - 76861879 - each bit can contain numbers between 0-9
- Octal - max limit [0,7]
- Terinary - max limit [0,2]
- Binary - max limit [0,1] - 10011001 - each bit can contain either 0 or 1  

# Size of data type
- max value of 8 bit  _    _    _    _    _    _    _    _  
                    -2^7  2^6  2^5  2^4  2^3  2^2  2^1  2^0
- last bit is most
  significant bit (negative sign)
- min value is 10000000 = -128
- max value is 01111111 = 127 , can be written as [-2 power(n-1), (2 power(n-1)) -1]
- [-2^(n-1), 2^0 + 2^1 + 2^2 + 2^3 + 2^4 + 2^5 + 2^6 + ... + 2^N-2],    
- 2^0 + 2^1 + 2^2 + 2^3 + 2^4 + 2^5 + 2^6 + ... + 2^N-2 -> Geometric progression  
formula  
first term, a = 2^0 = 1  
common ratio, r = 2  
total elements = 2^0 + 2^N-2 = 2^N-1 , formula = a((r^t) -1)/r-1 , answer = (2^N-1) -1  

- 1 byte  = 8 bits  = [-2^N-1, 2^N-1 -1]    = [-128, 127] -> range for byte
- 2 bytes = 16 bits = [-2^16-1, -2^16-1 -1] = [-32768, 32767] -> range for short int  
- 4 bytes = 32 bits = [-2^32-1, 2^32-1 -1]  = [-2,147,483,648, 2,147,483,647] -> range for integer

2^10 = 1024 ~~ 1000 = 10^3,  
2^10 ~~ 10^3, cube on both sides, 2^30 ~~ 10^9, integer limit can also be written as ~~ [-2 * 10^9, 2 * 10^9]
