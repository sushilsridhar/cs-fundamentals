
# Pass by value  
```
int a = 10;
function(a);

void function(int a) {
  a = a + 1; // -> a value is changed only within the scope of the function
}
```
variable arr stores the address(reference) of the array, which is passed as value to the function  

```
int[] arr = new int[];

void function(int[] arr) {
  arr[0] = 1; // -> modifies the original array 
}
```

# Immutability 

Immutability applies only to String and Wrapper classes, it makes no sense to talk about the primitive types being mutable,     
If you change the value of a variable like this
```
int x = 5;
x = 6;
```
That's not changing the number 5 - it's changing the value of x

<ins>String class</ins>   
String are immutable, so that they can be shared across mutliple threads  
[Strings in heap shared between multiple threads](https://github.com/sushilsridhar/cs-fundamentals/blob/main/ds/STRING.md#when-to-think-of-strings)

<ins>Wrapper class</ins>    
Generics does not support primitive types, so wrapper classes around the primitive types was created,

if wrapper classes were mutable, all three Foo objects will have wrong values,    
 ```
    static class Foo {
        Integer i;
        public Integer getI() { return i; }
        public void setI(Integer i) { this.i = i; }
    }
    public static void main(String[] args) {
        Foo foo1 = new Foo();
        Foo foo2 = new Foo();
        Foo foo3 = new Foo();
        Integer i = new Integer(1);
        foo1.setI(i);
        ++i;
        foo2.setI(i);
        ++i;
        foo3.setI(i);

        System.out.println(foo1.getI());
        System.out.println(foo2.getI());
        System.out.println(foo3.getI());
    }
    /*  1 2 3 */
 ```

# Where variables in java are stored?

where static variables are stored



# add these 
research on jvm       
why generics doesn't support primitive types      
type erasure      
why wrapper classes are created for primitive types     
autoboxing      

static class, what is the use of static class, linkedlist node static class         
enums, how enums are stored, what are enums   

string vs char[] array for storing password     
interface vs abstract class       
