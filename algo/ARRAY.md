# check

total number of subarray - n(n+1)/2

Arrays.toString();
cover arrays utils class 


To solve arrays,

1) use HashSet or HashMap
2) two pointer approach, where inserting into same array (in-place questions)
   one index for iterating, other for tracking the lastNonZeroElementIndex (or any requirement)


Array Techniques

1)Contribution technique - Adding contribution of each and every element, finding the number of occurrence of one element in all subarrays, and adding them individually
2)Carry forward - carring the previous subarray sum to new subarray
3)Sliding window - for the new subarray, subtract the previous element to startindex and add the element of new end index
4)Two pointer - for removing duplicate element, using the same input array itself for processing, without extra space
5)Prefix Sum - for problems with queries, Add X to array, from startIndex to endIndex, eg 4-8, add 9 , 0-4, add 14

