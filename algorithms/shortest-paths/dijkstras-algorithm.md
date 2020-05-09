---
description: Special thanks to Arin for writing this page!
---

# Dijkstra's Algorithm

{% hint style="warning" %}
Before continuing, review [Graphs](../../abstract-data-types/graphs.md), [Stacks and Queues](../../abstract-data-types/collections/stacks-and-queues.md), and [Shortest Paths](./). This topic isn't for the faint of heart!
{% endhint %}

## Dijkstra's Algorithm

**One sentence overview:** Visit vertices in order of best-known distance from source; on visit, relax every edge from the visited vertex.

### Dijkstra's vs BFS

BFS returns the shortest paths in an unweighted graph, where the shortest path is just defined to be the fewest number of edges traveled along a path. In Djikstra's, we can generalize the breadth-first traversal to find the path with the lowest cost, where the cost is determined by different weights on the edges. Djikstras uses a PriorityQueue to maintain the path with lowest cost from the starting node to every other node.

## Properties of Dijkstra's Algorithm

**Dijkstra's Algorithm has some invariants \(things that must always be true\):**

1. edgeTo\[v\] always contains best known predecessor for v
2. distTo\[v\] contains best known distance from source to v
3. PQ contains all unvisited vertices in order of distTo

**Additionally, there are some properties that are good to know:**

* always visits vertices **in order of total distance from source**
* relaxation always **fails on edges to visited vertices**
* guarantees to work optimally **as long as** **edges are all non-negative**
* solution always creates a **tree form**, true for undirected graphs
* can think of as **union of shortest paths to all vertices**
* **edges in solution tree always has V-1 edges**, where V = the number of vertices. This is because every vertex in the tree except the root should have **exactly one input.**



## Pseudocode

```java
public void doDijkstras(Vertex sourceVertex) {
    PriorityQueue PQ = new PriorityQueue();
    PQ.add(sourceVertex, 0);
    for(v : allOtherVertices) {
        PQ.add(v, INFINITY);
        while (!PQ.isEmpty()) {
            Vertex p = PQ.removeSmallest();
            relax(P);
        }
    }
}

// Relaxes the edge connecting P to Q.
void relax(Vertex p, Vertex q) {
    if (distTo[p] + q < distTo[q]) {
        distTo[q] = distTo[p] + q;
        edgeTo[q] = p;
        PQ.changePriority(q, distTo[q]);
    }
}
```

## Runtime Analysis

**Unsimplified:**

$$
\theta(V * log(V) + V * log(V) + E * log(V))
$$

**Simplified:**

$$
\theta(E * log(V))
$$



**Explanation:**

* each add operation to PQ takes log\(V\), and perform this V times
* each removeFirst operation to PQ takes log\(V\) and perform this V times
* each change priority operation to PQ takes log\(V\), perform this as many times as there are edges
* everything else = O\(1\)
* usually, there are more or equal edges compared to the number of vertices.

