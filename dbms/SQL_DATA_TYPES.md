# Strings

<ins>char</ins>  
> string of fixed max length

char(x), x -> {0, 255}

char(4) -> eg: "abcd", 4 char space allocated even if not used      

<ins>varchar</ins>  
> string of variable length, varchar(x), range of x is from 0 to 2<sup>16</sup>  

eg: varchar(10)       
ab -> stores 2ab    
abcd -> stores 4abcd    

varchar(4), estimated size is 4, but the actually size can be greater than 4 also,  
used by db for storage optimization, the first few bytes of the string contains the length of the string  

storing empty string: it occupies one byte to store size of the string as 0  

<ins>Text</ins>  
> Text can't be indexed, varchar can be indexed   

tiny text - 255B   
text - 64KB - can be used to store blog post/ descriptions    

below types not used in real world, mainly used to store files which can be done in AWS CDN for fast access,           
medium text - 16MB  
long text - 4GB  

# Integers 

tiny int - 1byte {-128, 127}  
unsigned tiny int - 1byte {0, 255}      

small int - 2bytes {-32K, 32K}  
medium int - 3bytes {-8M, 8M}     

int - 4bytes {-2B, 2B} --> commonly used  
big int - 8bytes {-9Z, 9Z}  

# Floating data type
<ins>decimal(p,s)</ins>     
where p is precision and s is scale, number of values after decimal  

305.02, is internally stored as 30502 with p as 5, and s as 2  
max of decimal value is (p can have 1-65 digits) 10<sup>64</sup>  

> decimal can store exact values as we use precision and scale, 

used in finance/ money based applications   

<ins>float</ins>    
> approximate representation of value   
> used for scientific notation    

pi has 200 decimal places, it can't be stored with decimal (p <= 65 digits)   

size - 4 bytes

<ins>double</ins>   
> approximate representation of value   

can store 200 decimal places of pi, 

size - 8 bytes  

> float and double store approximate values, need to write additional logic to handle the approximations

# Boolean    
tinyint - 1byte,      
boolean is alias of tinyint     

# Enum    
a set of constants, 

car_type {SEDAN, HASHBACK, SUV}

<ins>Advantage</ins>    
1. type safety
2. incorrect data is not allowed


![Screenshot 2023-01-06 at 6 18 29 AM](https://user-images.githubusercontent.com/16437905/210907324-1fccbd82-30dd-4010-a063-14b141da6319.png)

<ins>Instead of Enum create a separate table</ins>    
more efficient 

![Screenshot 2023-01-06 at 6 22 02 AM](https://user-images.githubusercontent.com/16437905/210907629-9b5a3e38-550a-499d-9aa0-ba54d803533b.png)

# Blob

storing files or images   

tiny blob - 255 bytes
blob - 64 kb
medium blob - 16 mb
long blob - 4 gb

# Date and Time


