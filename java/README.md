# Java

<ins>Java is pass by value</ins>  
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
