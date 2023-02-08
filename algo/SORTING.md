# Sorting

> arrangement of data, based on a property, in increasing or decreasing order

```
custom sorting or reverse order sorting can't be applied to primitive arrays

Arrays.sort() 

Collections.sort()

        Collections.sort(new ArrayList<Integer>(), (a, b)-> {
            return 1;
        });

```

# Best Sorting Algorithm


# Time complexity

| Name | Best | Average | Worst |
:---: | :---: | :---: | :---: |
Selection Sort	   | Ω(n^2)	       | θ(n^2)	        | O(n^2)
Bubble Sort	       | Ω(n)	         | θ(n^2)	        | O(n^2)
Insertion Sort	   | Ω(n)	         | θ(n^2)	        | O(n^2)
Heap Sort	         | Ω(n log(n))	 | θ(n log(n))	  | O(n log(n))
Quick Sort	       | Ω(n log(n))	 | θ(n log(n))	  | O(n^2)
Merge Sort	       | Ω(n log(n))	 | θ(n log(n))	  | O(n log(n))
Bucket Sort	       | Ω(n+k)	       | θ(n+k)	        | O(n^2)
Radix Sort	       | Ω(nk)	       | θ(nk)	        | O(nk)
Count Sort	       | Ω(n+k)	       | θ(n+k)	        | O(n+k)



check this https://www.geeksforgeeks.org/comparable-vs-comparator-in-java/

document this

which sorting has O(1) or O(n) space complexity
