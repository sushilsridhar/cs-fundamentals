# Keys

<ins>Super key</ins>: a set of attributes that uniquely identifies a row 

<ins>Candidate key</ins>: a key of minimum size that can uniquely identify a row,  
candidate key is a super key of minimum size   

<ins>Primary key</ins>: one of the candidate key is choosen as primary key  

<ins>Composite key</ins>: key with attributes >= 2  

<ins>Foreign key</ins>: a attribute in a table, which is a primary key in another table  

# Schema design

schema design is how my database will be structured,

1. how to decide what tables to create and it's attributes
2. how to model cardinality between tables
3. normalization


# MYSQL Data types

**<ins>Strings</ins>**   

<ins>char</ins>  
string of fixed max length,  
char(x), x -> {0, 255}

char(4) -> eg: "abcd"  

<ins>varchar</ins>  
string of variable length, varchar(x), range of x is from 0 to 2<sup>16</sup>  

varchar(4), estimated size is 4, but the actually size can be greater than 4 also,  
used by db for storage optimization, the first few bytes of the string contains the length of the string  

storing empty string: it occupies one byte to store size of the string as 0  

<ins>Text</ins>  
these can not be indexed, varchar can be indexed,   
tiny text - 255B   
text - 64KB  
medium text - 16MB  
long text - 4GB  

**<ins>Integers</ins>**  

tiny int - 1byte {-128, 127}  
unsigned tiny int - 1byte {0, 255}  
small int - 2bytes {-32K, 32K}  
medium int - 3bytes {-8M, 8M}  
int - 4bytes {-2B, 2B} --> commonly used  
big int - 8bytes {-9Z, 9Z}  

**<ins>Floating data type</ins>**  
1. decimal(p,s)  
where p is precision and s is scale, number of values after decimal  

305.02, can be saved as 30502 with p as 5, and s as 2  
max of decimal value is (p can have 1-65 digits) 10<sup>64</sup>  

decimal can store <ins>exact values</ins> as we use precision and scaler,

2. float - 4 bytes  
3. double - 8 bytes  

float and double store <ins>approximate values</ins>, need to write additional logic to hanlde the approximations


**<ins>Boolean</ins>**    
tinyint - 1byte,  
boolean is alias of tinyint  

**<ins>Enum</ins>**    
a set of constants, 


