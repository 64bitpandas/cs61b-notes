# Heaps

{% hint style="danger" %}
This page is incomplete. [Help make it better!](https://github.com/64bitpandas/cs61b-notes/pulls)
{% endhint %}

## What are Heaps?

A heap is a **specific order of storing data,** often in a list. Heaps are very similar to binary trees, but have some differences:

* Unlike trees, heaps **only care about the root node.** Usually, the root node is either the **largest** or **smallest** value in the heap \(corresponding with max-heaps and min-heaps\), and we don't care too much about the rest.
* Every element in the heap must be **larger than all its children** \(in a max-heap\) or **smaller than all its children** \(in a min-heap\). This is known as the **heap property.**

.

## The Heapify Algorithm

The most important heap algorithm is **heapify**, which converts any non-heap list into a heap. This algorithm is vital to most heap functions like insert or remove, since these functions often break the heap structure before fixing it with heapify.

**Here's how it works:**



## Practical Applications

[Lab 9](https://inst.eecs.berkeley.edu/~cs61b/sp20/materials/lab/lab9/index.html) is a fantastic resource for practicing heap implementations and working with the algorithms that are needed to work with heaps \(like heapify, insert, remove\). Since this lab goes into plenty of detail about how each of these algorithms work, I won't explain them too much here.

Heap sort relies on the heap structure to provide consistent nlogn sorting! I have more information about this on page 11 in my [sorting guide](https://docs.google.com/document/d/1dUfzdh5V3okrwFbB9o0PgtEBaLHyCqJFwpQWyQ53IeU/edit).



