# Access Control

{% hint style="warning" %}
This page is from my original notes and is not up to the latest quality standards. Read with care or [help make it better!](https://github.com/64bitpandas/cs61b-notes/pulls)
{% endhint %}

![A chart comparing the different access modifiers. The black bar is the default \(&quot;package protected&quot;\).](../.gitbook/assets/image%20%284%29.png)

**Definition:** Specifying the specific level of access of methods and variables.

**Benefits**

* Self documenting
* Safe to change private methods without worrying about external calls
* Specifies to users that private code does not need to be understood or used by them

## Nested Classes

* Putting a class inside of another class
* Nested classes can be set to `private` in order to do access control
* Static classes cannot access the outside class



