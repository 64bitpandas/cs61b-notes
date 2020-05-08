# References, Objects, and Types in Java

{% hint style="warning" %}
This page is from my original notes and is not up to the latest quality standards. Read with care or [help make it better!](https://github.com/64bitpandas/cs61b-notes/pulls)
{% endhint %}

## Primitive Variables

* **There are 8 primitive types in Java:** byte, short, int, long, float, double, boolean, char
* Different types require different amounts of memory- e.g. ints take 32 bits, doubles take 64 bits
* Internal table maps names to locations in memory
* Uninitialized variables **cannot** be accessed
* Variable data is stored in binary

## Golden Rule of Equals

* For primitives, `y = x` means "**copy** the bits from y into a new location, then call them x"
* For reference types, the **address** gets copied to a new location. Both addresses point to the same location
* For passing parameters, all parameters are also copied to the new scope \(_pass by value_\)

## Reference Types

* A **reference type** is any non-primitive type \(e.g. arrays, strings\)
* Reference types are **objects**
* Each instance variable takes up a set amount of memory, and the object points to where these variables may be found in memory
* Reference can be set to _null_ \(all 0's\) or a specific 64-bit address returned by the **new** keyword
* Objects can be _lost\*_ if an address is reassigned to something else and no longer points to the previous object

## The Object Class

* **All classes are hyponyms of Object.**
* Object has these methods:
  * String toString\(\): By default, prints out the class name followed by the memory address \(e.g. `Object@192c38f`\)
  * boolean equals\(Object obj\): By default, checks if the two objects are actually the same object \(same memory address\).
  * Class&lt;?&gt; getClass\(\)
  * int hashCode\(\)
  * Others: clone, finalize, notify, notifyAll, wait
* To override these, use the `@Override` tag

