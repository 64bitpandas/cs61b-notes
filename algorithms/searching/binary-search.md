# Binary Search

{% hint style="danger" %}
This page is incomplete. [Help make it better!](https://github.com/64bitpandas/cs61b-notes/pulls)
{% endhint %}

## Binary Search

```java
public BST find(BST T, Key sk) {
    if (T == null) {
        return null;
    }
    if (sk.equals(T.key)) {
        return T;
    } else if (sk < T.key) {
        return find(T.left, sk);
    } else {
        return find(T.right, sk);
    }
}
```

* Very fast! O\(log n\)

