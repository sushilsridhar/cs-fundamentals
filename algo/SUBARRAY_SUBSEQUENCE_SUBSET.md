# Consider an collection [1, 2, 3, 4]

# Subarray
any contiguous part of the collection   

[1, 2], [1, 2, 3] - has <ins>to be continous</ins> and <ins>should maintain relative order</ins> of elements  

example,  
<pre>
{1}
{1, 2}
{1, 2, 3}
{1, 2, 3, 4}
{2}
{2, 3}
{2, 3, 4}
{3}
{3, 4}
{4}
</pre>

<ins>Total number of subarrays present in array of size n</ins>    
<pre> n(n+1)/2 </pre>

<ins>Total number of subarrays of length k present in array of size n</ins>   
<pre> n-k+1 </pre>

![Screenshot 2023-01-19 at 5 01 32 AM](https://user-images.githubusercontent.com/16437905/213319477-dbd9b752-f44a-4425-951f-ed9c4a0da270.png)

# Subsequence 
[1, 2, 4] - is not continous but maintains relative order of elements  


# Subsets   
contains any possible combinations of the original collection, with unique permutation,  

[1, 3, 2] - may <ins>not be continous</ins> and <ins>may not maintain relative order</ins> of elements,  

> empty { } is also a subset  

[1, 3, 2] is same as [2, 1, 3],  
> all permutations of same elements are counted as 1 occurrence  

> total number of subset present is 2^n  

example, n = 4, size of the original array, total number of possible combinations with unique permutation = 2^n = 2^4 = 16,  
<pre>
{}
{1}
{2}
{3}
{4}
{1, 2}
{1, 3}
{1, 4}
{2, 3}
{2, 4}
{3, 4}
{1, 2, 3}
{1, 2, 4}
{1, 3, 4}
{2, 3, 4}
{1, 2, 3, 4}
</pre>
