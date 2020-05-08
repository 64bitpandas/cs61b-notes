# Arrays

{% hint style="warning" %}
This page is from my original notes and is not up to the latest quality standards. Read with care or [help make it better!](https://github.com/64bitpandas/cs61b-notes/pulls)
{% endhint %}

## Properties

* Fixed length
* Sequence of N blocks of memory
* Every value in array is the same type and holds the same amount of bits
* Zero-indexed
* Do not have methods
* Indices can be computed at runtime
* Retrieval is independent of size

**Instantiation:**

* `int[] a = {1, 2, 3, 4, 5};` assigns values
* `int b = new int[3];` creates array of provided length populated with default values

**Copying**

* Simply assigning `int[] c = b` will copy the **pointer** to array b! Not the values!
* Use `System.arraycopy(source, start, target, startTarget, amountToCopy)`
* `System.arraycopy(b, 0, x, 3, 2)` is equivalent to `x[3:5] = b[0:2]` in python

**Multidimensional Arrays** `int[][] 2d = new int[4][4];` or `int[][] 2d = new int[][] {{1}, {2, 3}, {4, 5, 6}};`

**Generic Arrays**

* Arrays of generic objects are NOT allowed!
* Must use `Type[] items = (Type[]) new Object[length]`

