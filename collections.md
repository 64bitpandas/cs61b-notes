# Collections

**Collection** is an interface

**Sub-interfaces:**
 - List: indexed sequences with duplication
 - Set, SortedSet: No duplication or indices
 - Map, SortedMap: Dictionaries (key-value pairs)

**Functions and Behaviors**
 - Membership tests `contains()` and `containsAll()`
 - size
 - isEmpty
 - iterator()
 - toArray()
 - Optional: add, addAll, clear, remove, removeAll, retainAll (intersection)
    - Throws `UnsupportedOperationException` if not implemented