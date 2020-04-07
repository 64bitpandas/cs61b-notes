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
