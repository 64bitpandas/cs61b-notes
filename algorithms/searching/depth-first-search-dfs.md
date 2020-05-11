# Depth First Search \(DFS\)



{% hint style="danger" %}
This page is incomplete. [Help make it better!](https://github.com/64bitpandas/cs61b-notes/pulls)
{% endhint %}



**Depth first traversal:** Explore an entire subgraph before moving onto the next subgraph

* Keep an array of 'marks' \(true if node has been visited\) and, optionally, an edgeTo array that will automatically keep track of how to get to each connected node from a source node
* When each vertex is visited:
  * Mark the vertex
  * For each adjacent unmarked vertex:
    * Set edgeTo of that vertex equal to this current vertex
    * Call the recursive method on that vertex

