# Dynamic Method Selection

{% hint style="warning" %}
This is a **very tricky topic**. Make sure you are comfortable with [inheritance](inheritance.md) and [access control ](access-control.md)before proceeding!
{% endhint %}

Inheritance is great and all, but it does have some issues. One of the biggest issues lies in overriding: **if two methods have exactly the same name and signature, which one do we call?**

In a standard use case, this is a pretty simple answer: whichever one is in the class we want!

```java
public class Dog {
    public void eat() { ... } // A
}

public class NotDog {
    public void eat() { ... } // B
}

public class Shiba {
    @Override
    public void eat() { ... } // C
}

```

{% tabs %}
{% tab title="Question 1" %}
Which is called when we run**:**

```java
Dog rarePupper = new Dog();
rarePupper.eat();
```
{% endtab %}

{% tab title="Answer" %}
Of course, it's A 😛 Wouldn't make any sense for Dog to do anything with NotDog since they're not related in any way.
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Question 2" %}
What about when we call:

```java
Shiba doge = new Shiba();
rarePupper.eat();
```
{% endtab %}

{% tab title="Answer" %}
This calls C! This should make intuitive sense because `Shiba` overrides `Dog` so all `Shibas` will use C instead of A.

![](../.gitbook/assets/image%20%288%29.png)
{% endtab %}
{% endtabs %}

## Things Get Wonky: Static vs Dynamic Types

There's an interesting case that actually works in Java:

```java
Dog confuzzled = new Shiba();
```

What??? Shouldn't this error because `Dog` is incompatible with `Shiba`?





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

