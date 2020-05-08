# Dynamic Method Selection



{% hint style="warning" %}
This is a **very tricky topic**. Make sure you are comfortable with [inheritance](inheritance.md) and [access control ](access-control.md)before proceeding!
{% endhint %}



## Practice

Let's see how access control can get a bit convoluted with this example:

```java
package P;
public class A {
    int def; // Variable with default access
    protected int prot; // Variable with protected access
    private int priv; // Variable with private access
    
    static class NestedA { ... }
}

public class B extends A { ... }

===================
package Q;
public class C extends P.A { ... }
    
    

```

{% tabs %}
{% tab title="Question 1" %}
Which variables can be accessed in B?
{% endtab %}

{% tab title="Answer" %}
`def` and `prot` since B is in the same package as A.
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Question 2" %}
Which variables can be accessed in C?
{% endtab %}

{% tab title="Answer" %}
`prot` only, since C is in a different package but extends A.
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Question 3" %}
Which variables can be accessed in NestedA?
{% endtab %}

{% tab title="Answer" %}

{% endtab %}
{% endtabs %}

