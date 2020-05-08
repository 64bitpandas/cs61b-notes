# Tries

{% hint style="warning" %}
This page is from my original notes and is not up to the latest quality standards. Read with care or [help make it better!](https://github.com/64bitpandas/cs61b-notes/pulls)
{% endhint %}

## Main Ideas

* A specific implementation of a set and map \(like hash table or BST\)
* Short for Retrieval Tree
* If a set has a finite number of possible keys \(e.g. ASCII characters\), we can just represent a map as an array.
* Then, if keys are made up of those keys \(e.g. strings\), we can create a tree structure where each node is one character. Adding the characters for each node together forms the original key
* To handle values containing other values \(e.g. a vs. as\), mark each final node

## Characteristics

* Each node has k links \(k = number of chars in alphabet\), all are null except the ones that are used
  * In order to reduce the number of links, can use a hash table implementation instead of array implementation \(uses more time but less space\)
* Runtime: O\(1\) for add and contains \(independent on number of keys, only dependent on length of key\)
* Very good for special string operations \(e.g. prefix matching\)

