# Collections

{% hint style="warning" %}
This page is from my original notes and is not up to the latest quality standards. Read with care or [help make it better!](https://github.com/64bitpandas/cs61b-notes/pulls)
{% endhint %}

![An overview of all the Collections in Java.](../../.gitbook/assets/image%20%286%29.png)

**Collection** is an interface for common abstract data types

**Abstract Data Type:** A data type that is defined purely by operations, not by their implementation

**Sub-interfaces:**

* List: indexed sequences with duplication
* Set, SortedSet: No duplication or indices
* Map, SortedMap: Dictionaries \(key-value pairs\)
* Stack:
  * push\(T x\): puts x on top of the stack
  * pop\(\): Removes and returns the top item from the stack

**Functions and Behaviors**

* Membership tests `contains()` and `containsAll()`
* size
* isEmpty
* iterator\(\)
* toArray\(\)
* Optional: add, addAll, clear, remove, removeAll, retainAll \(intersection\)
  * Throws `UnsupportedOperationException` if not implemented

