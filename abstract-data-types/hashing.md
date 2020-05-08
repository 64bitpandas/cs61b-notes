# Hashing and Hash Tables

## Data Indexed Sets

* Essentially putting all data into a massive array and keeping track of the index based on the value

  **Benefits:**

  * Accessing a value at index is a constant-time operation

  **Concerns:**

  * Requires a large amount of memory
  * Need to ensure that no collisions between two items having the same index occur
  * Integer overflow for large indices

## Hash Codes and Hash Tables

**Definition of Hash Code:** a representation of a value from a set with many/infinite members using a value from a fixed/finite number of members

* Ideally would prevent collisions and integer overflow

**Pidgeonhole Principle** Collisions are inevitable if you have more values than indices available

* Solution for collision handling: could use a collection at each index to hold all values with the same index
* Using this solution, we can reduce the number of indices available by using a **reduce** algorithm that reduces values into N bins

**Runtime of Hash Tables**

* If we have a fixed number of buckets M and an arbitrary number of elements N: O\(N\) runtime
* If we have an arbitrary M that increases with N and double M at a N/M ratio threshold: O\(1\)

## Java Hash Tables

* Most popular implementation of sets and maps
* Great performance
* Does not require comparable
* Simple implementation
* In Java: HashMap and HashSet
* All Java objects have a `hashCode()` method
* Negative hash codes wrap back to the end
* Typical hash codes have a small prime base -&gt; more randomness

  **Warning:** Never store mutable objects in HashSet/HashMap

  * hash code changes -&gt; object will get lost

  **Warning:** Never override equals without overriding hashCode

  * HashMaps/Sets rely on equals to check hash codes

