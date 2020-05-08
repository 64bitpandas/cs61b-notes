# Sets

## Basics

* Stores a set of values with **no duplicates**
* No order
* Functions:
  * add\(T x\)
  * contains\(T x\)
  * size\(\)
* Can be iterated over

## ArraySet

* Array-based solution to set implementation
* Objects get added to an array that gets resized when too full
* **How to enable iteration:**
  * One method is to use **iterators** which work very similarly to Python iterators

    ```java
    Iterator<Integer> seer = set.iterator();
    while (seer.hasNext()) {
      System.out.println(seer.next());
    }
    ```

  * Another method is to implement the `Iterator` and `Iterable` interface
    * Iterator must implement `hasNext()` and `next()` methods
    * Requires generic type
    * Iterable must implement `iterator()` method which returns the Iterable object
    * Allows usage of for/foreach loops

