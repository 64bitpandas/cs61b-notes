# Sorting

## Why sorting?
 - Easier for searching (e.g. binary search)
 - Easy to see if two items in list are equal (just compare neighbors)
 - Get nearest neighbors

## Properties of a Sorting Algorithm
 - Changes a sequence based on a **total order**
 - A sorting algorithm could be **stable**: does not change relative order of equivalent entries
    - Example: dictionary can have multiple definitions for a single word
 
 A total order is:
  - **Total:** All items can be compared with one another
  - **Reflexive:** An item can be compared to itself
  - **Antisymmetric:** x <= y AND y <= x IFF y == x
  - **Transitive:** If x <= y and y <= z, then x must be <= z

## Sorting Algorithm Classifications
 - **Internal sort:** Keeps all data in primary memory
 - vs. **External sort:** Processes data in batches, then merges them together at the end
 - **Comparison-based sort:** The only thing we know about keys are their relative orders
 - **Radix sort:** Uses information other than keys
 - **Insertion sort:** Insert items at their appropriate positions one at a time
 - **Selection sort:** Chooses items and places them in order

## Sorting in Java
```java
import static java.util.Arrays.*;
import static java.util.Collections.*;

String[] x = new String[] {"Vat", "Bat", "Cat"};

sort(x); // mutates x into Bat, Cat, Vat
sort(x, Collections.reverseOrder()); // mutates x into Vat, Cat, Bat
sort(x, 0, 2) // sorts the first two elements, leaving the rest unchanged (Cat, Vat, Bat)
```

## Insertion Sort

**The basic idea:**
 - start with empty output sequence
 - insert into output sequence one by one

 - Simple and good for small data sets
 - O(N^2)

```java
for (int i = 0; i < A.length; i += 1) {
    int j = 0;
    Object x = A[i];
    for (j = i-1; j >= 0; j -= 1) {
        if (A[j].compareTo(x) <= 0)
            break;
        A[j+1] = A[j];
    }
    A[j+1] = x;
}
```

## Inversions
 - Used as a measure for how sorted a list is
 - 0 inversion = perfectly sorted
 - N*(N-1)/2 inversions = reversed

## Shell Sort
 - Improve insertion sort by sorting **distant** elements first
 - Goal: reduce number of inversions
 - O(N^(3/2))
 1. Sort subsequences 2^k - 1 apart, where k is the largest number it can possibly be so that this value is less than N
    - e.g. if k=4, then sort 0 and 15
 2. Continue step 1, adding 1 until all values in array are addressed
 3. Subtract 1 from k
 4. Continue steps 1 and 2 until k==1
 3. Run a traditional insertion sort (should be very fast)

## Heap Sort
 - A type of selection sort
 - Idea: Keep selecting the smallest element (bad idea in a normal list, but find on heaps)
 - O(NlogN)
 - Separate list into heapified part and sorted part; heap decreases in size while sorted area increases
 - Better O(N) heapifying: (for a bushy heap)
 ```java
 int N = arr.length;
 for (int k = N/2; k >= 0; k -= 1) { //start in the middle
    for (int p = k, c = 0; 2*p + 1 < N; p = c) {
        // set c to the largest value in children (if in minheap)
        // swap c and k if necessary
        // heap will now be correct from point k downward in the heap so we can go up in the heap and only look at immediate children
        // e.g. reheapifyDown only, no need to reheapifyUp
    }
 }
 ```

## Merge Sort
 - Idea: divide data into 2 equal parts and recursively sort them. Then merge them together at the end
 - O(NlogN)
 - Good for external sorting

## Quicksort
 - Idea: speed through probability
 - O(NlogN) if good pivots, O(N^2) if bad pivot
 - Better for random sets, but not that good for nearly ordered sets
 1. Partition data into pieces based on a pivot value
    - e.g. pivot value could be median of first, middle, and last value
 2. Recursively divide into high and low pieces
 3. When the pieces are small enough, do insertion sort

 **Quick Selection:**
  - Select element #k in a sorted list using quick methods
  - Principle: choose a pivot. Since we know how many are less than and greater than k, we can adjust accordingly and throw away the other side
  - Continue until number is satisfied