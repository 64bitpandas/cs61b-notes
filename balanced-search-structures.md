# Balanced Search Structures

## B Trees (2-4 Trees)

**The basic idea:**
 - Nodes can hold multiple values
 - When a node holds too many values, split it

**The algorithm**
 - Set a limit on the number of items allowed in a single node (e.g. 3)
 - If the limit is exceeded, give one value to the upper node
 - Then, turn one value to its own node such that the parent now has new children

**Characteristics:**
 - Searching a single node is constant runtime since limit is a constant
 - 2-4 tree means a node can have 2, 3, or 4 children
 - Guaranteed to be balanced/bushy regardless of insertion order, unlike BST's
 - All leaves must be the same distance from the source
 - A non-leaf node with k items has k + 1 children
 - Height is O(log N)
    - Worst case: All non-leaf nodes have 1 item
    - Best case: All nodes have L items
 - Overall runtime is O(L * log N) = O(log N) since L is a constant

## Red-Black Trees and Tree Rotation
 
 **The basic idea:**
  - You can move (rotate) a BST to any other possible configuration in 2n - 6 rotations or less.
  - Rotations can turn any tree into a balanced tree
  - Reperesent B trees as binary trees by having "red" connections that represent nodes with multiple values

 **Tree Rotation**
  - Changes a tree to a different configuration:
  - Termporarily merge a node with its child/parent
  - Move one of the nodes down to preserve binary tree characteristics

 **Left Leaning Red Black Trees**
  - Restriction: Red links can only be on the left
  - i.e. if a node in a 2-3 tree is [1 2], then 1 will be the left child of 2 in a LLRB tree

 **LLRB Insertion**
  - Always add values to leaf node as a red link first
  - If the link is leaning right, rotate the tree to make it left leaning
  - If a node already has a red link to the left, temporarily add it to the right also as a red link
    - Then, flip the color of all links connected to the node (if previously black, turn red; if previously red, turn black)
    - Might need to fix right-leaning red nodes that are created as a result
  - If a node has red links to both parent and child, rotate it such that it becomes the above case
  
 **Characteristics:**
  - One-to-one mapping with B trees
  - Structurally identical to BST's
  - No node has 2 red links
  - Every path must have the same number of black links to the root
  - Since LLRB's have no more than double the height than its corresponding B-tree, its height is also O(log N)