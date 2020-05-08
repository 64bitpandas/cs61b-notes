# Graphs

{% hint style="warning" %}
This page is from my original notes and is not up to the latest quality standards. Read with care or [help make it better!](https://github.com/64bitpandas/cs61b-notes/pulls)
{% endhint %}

## Tree Traversals

Example:

```text
    D
B       F
```

A C E G

* **level order:** top to bottom, left to right: DBFACEG

  **Depth First Traversals**

  * Inorder: ABCDEFG
  * Preorder: DBACFEG
    * Good for printing directory listings
  * Postorder: ACBEGFD
    * Good for collecting file sizes

## Intro to Graphs

* Represents a set of relationships that is not necessarily hierarchical
* Consists of nodes \(vertices\) and connections \(edges\)

  **Simple Graph**

  * No loops \(a connection of a node to itself\)
  * No parallel edges \(two edges that connect the same two vertices\)
  * Most common form of graph

  **Graph Properties**

  * Directed vs Undirected: whether or not edges have arrows pointing to a direction
  * Cyclic vs Acyclic: whether or not the edges form a loop
  * Edge labels: used to denote length, etc
  * Weights: used to denote properties of vertices themselves

  **Terminology**

  * Adjacent: two vertices connected with one edge
  * Path: a sequence of vertices connected by edges
  * Cycle: path with the same first and last vertex
  * Connected: two vertices that have a path between them; refers to graphs that have all connected vertices

## Graph Queries

* Is there a path between two vertices? \(s-t path\)
* What is the shortest route between two vertices? \(shortest s-t path\)
* Are there cycles? \(cycle detection\)
* Can you visit each vertex/edge exactly once? \(Euler tour / Hamilton tour\)
* Is a graph connected? \(connectivity problem\)
* Is a vertex that disconnects the graph when removed? \(single point of failure / biconnectivity\)
* Are two graphs isomorphic?
* Can a graph bee drawn with no crossing edges? \(planarity\)

## Graph Traversals

**Depth first traversal:** Explore an entire subgraph before moving onto the next subgraph

* Keep an array of 'marks' \(true if node has been visited\) and, optionally, an edgeTo array that will automatically keep track of how to get to each connected node from a source node
* When each vertex is visited:
  * Mark the vertex
  * For each adjacent unmarked vertex:
    * Set edgeTo of that vertex equal to this current vertex
    * Call the recursive method on that vertex

