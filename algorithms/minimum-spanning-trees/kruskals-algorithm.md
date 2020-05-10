---
description: Special thanks to Arin for writing this page!
---

# Kruskal's Algorithm

{% hint style="warning" %}
Before reading, review [Minimum Spanning Trees](./) and [Union Find \(Disjoint Sets\)](../../abstract-data-types/union-find-disjoint-sets.md) as they both make Kruskal's algorithm possible!
{% endhint %}

## Conceptual Overview

Kruskal's algorithm is another optimal way to construct a **minimum spanning tree**. It's benefits are that it is conceptually very simple, and easy to implement. The idea is that first we sort all the edges of the graph in order of increasing weight. Then, add the smallest edge to the MST we are constructing unless this creates a cycle in the MST. Repeat until V - 1 edges total.

## Detailed Breakdown

In order to optimally check if adding an edge to our MST creates a cycle, we will use a **WeightedQuickUnion** object. \(See [Union Find \(Disjoint Sets\)](../../abstract-data-types/union-find-disjoint-sets.md) for a recap on what this is.\) This is used because checking if a cycle exists using a WeightedUnionFind object boils down to one `isConnected()` call, which we know takes $$\Theta(\log(N))$$.

To run the algorithm, we start by adding all the edges into a [PriorityQueue](../../abstract-data-types/collections/stacks-and-queues.md). This gives us our edges in sorted order. Now, we iterate through the PriorityQueue by removing the edge with highest priority, checking if adding it forms a cycle, and adding it to our MST if it doesn't form a cycle.

## PseudoCode

```java
public class Kruskals() {

    public Kruskals() {
        PQ edges = new PriorityQueue<>();
        ArrayList<Edge> mst = new ArrayList<>();
    }

    public void doKruskals(Graph G) {
        for (e : G.edges()) {
            PQ.add(e);
        }
        WeightedQU uf = new WeightedQU(G.V());
        Edge e = PQ.removeSmallest();
        int v = e.from();
        int w = e.to();
        if (!uf.isConnected(v, w)) {
            uf.union(v, w);
            mst.add(e);
        }

    }
}
```

## Runtime Analysis

Left as an exercise to the reader 😉

{% hint style="info" %}
Someone's been reading too much [LADR](https://www.springer.com/gp/book/9783319110790)...  
\(The answer is $$\Theta(E\log(E))$$by the way. Try to convince yourself why!\)
{% endhint %}

