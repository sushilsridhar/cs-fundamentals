> Comparator and Comparable does not support primitives types,   
> because generics does not supports primitives types

# Java Comparable

> Comparable provides a single sorting sequence, Ex: Sort either by id or name

> It means that the objects can be sorted based on a single data member

```
class Person implements Comparable<Person> {

    int id;

    public Person(int id) {
        this.id = id;
    }

    @Override
    public int compareTo(Person person) {
        if(this.id > person.id) {
            return 1;
        } else if(this.id < person.id) {
            return -1;
        }
        return 0;
    }
}

List<Person> personList = new ArrayList<>();

Collections.sort(personList); --> internally calls compareTo

```
# Java Comparator

> Comparator provides multiple sorting sequences, Ex. Sort by both id and name

<ins> When to use comparator?</ins>  
when the comparision logic needs to decoupled from the class, we can go for the comparator


Always think about a,

```
if a is greater return 1, the sort function will place a at the last and b at the first (increasing order)

if a is smaller return -1, the sort function will place a at the first and b at the last (increasing order)

if a and b are same return 0, the sort function will take care of what to do
```    

<ins>Functional Interface - Comparator</ins>    
```
@FunctionalInterface
public interface Comparator<T> {

    int compare(T o1, T o2);
} 
```
<ins>using anonymous inner class</ins>  
```
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
<ins>Lambda expression</ins>    
```
    Arrays.sort(integerArray, (a, b) -> {
     
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
    });

```


