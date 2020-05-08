# Collections

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

