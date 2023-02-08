# Java Comparator

> Comparator does not support primitives types, because generics does not supports primitives types


```
 Always think about a,
  if a is greater return 1, the sort function will place a at the last and b at the first (increasing order)
  if a is smaller return -1, the sort function will place a at the first and b at the last (increasing order)
  if a and b are same return 0, the sort function will take care of what to do
    
 // using anonymous inner class
    Arrays.sort(integerArray, new Comparator<Integer>() {
        @Override
        public int compare(Integer a, Integer b) {

            if(Objects.equals(a, b)) {
                return 0;
            } else {
                int aFactorsCount = numberOfFactors(a);
                int bFactorsCount = numberOfFactors(b);

                if(aFactorsCount > bFactorsCount) {
                    return 1;
                } else if(aFactorsCount == bFactorsCount && a > b) {
                    return 1;
                }
            }
            return -1;
        }
    });
```
