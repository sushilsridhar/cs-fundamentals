# check

To solve arrays,

1) use HashSet or HashMap
2) two pointer approach, where inserting into same array (in-place questions)
   one index for iterating, other for tracking the lastNonZeroElementIndex (or any requirement)


# Think of

1. Carry forward : carring the previous subarray sum to new subarray
2. Contribution technique : Adding contribution of each and every element, finding the number of occurrence of one element in all subarrays, and adding them individually
3. Sliding window : for the new subarray, subtract the previous element of element at startindex and add the element of new end index
4. Prefix Sum : for problems with range queries, calculate sum from 0-4, 3-6 ranges      
pf[i] = pf[i-1] + a[i]

6. Two pointer : for removing duplicate element, using the same input array itself for processing, without extra space


