# Linked Lists

A recursive data structure that allows storage and access of an arbitrary amount of data.

### Feature List
1. **Rebranding**- represents Node as an individual object rather than having one monolithic List type.
2. **Bureacracy:** Create an abstraction barrier so that users do not need to know how methods or Nodes work, only how to call them.
3. **Access Control:** Data cannot be accessed directly to prevent dangerous behavior; only the provided methods are used.
4. **Nested Class:** Nodes are nested within the List object since other classes do not need it.
5. **Caching:** The size of the list is incremented every time a node is added, so running size() is O(1) and traversal is not needed.
6. **Generalizing:** A **sentinel node** represents an empty list and remains the first node of the list. When getFirst() is called, the second node is actually returned (since the first node is always the sentinel).
7. **Doubly Linked:** Nodes have both first and last pointers for even faster traversal.
8. **Circular list:** Sentinel last pointer points to the last value in the node, allowing for fast removeLast().

### Method List
 - `addFirst(T x)` adds a node to the front of the list.
 - `getFirst()` returns the value at the first node.
 - `addLast(T x)` adds a node to the back of the list.
 - `size()` returns the number of nodes in the list.
 - `removeLast()` destroys the last node in the list.