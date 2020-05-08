# Inheritance

{% hint style="warning" %}
This page is from my original notes and is not up to the latest quality standards. Read with care or [help make it better!](https://github.com/64bitpandas/cs61b-notes/pulls)
{% endhint %}

## Method Overloading

* When there are multiple methods with the same name, but different parameters
* A very crude solution towards generality:
  * Repetitive
  * Requires maintaining more code \(a change to one requires a change to the others\)
  * Doesn't handle data types outside of those specified

## Hypernyms and Hyponyms

* **Hypernym:** a more general word that can be used to replace a more specific one. A **Hyponym** is the opposite \(a specific word that can be replaced by a general one\)
* Example: A dog is a hypernym of poodle; a husky is a hyponym of dog. 
* A hyponym **is-a** hypernym: A dog **is-a** canine.

## Interfaces

* Declared in the same way as classes: `public interface InterfaceName {}`
* Specifies the methods and variables contained, but not their implementation 
  * Can use **default** keyword to go around this restriction, but not recommended \(**Implementation inheritance**\)
    * Harder to keep track of implementation
    * Overly complex
    * Breaks encapsulation rules
* Allows generic types to be used in methods without overloading \(as long as they have the same methods\)
* **Method Overriding:** redefining the same methods in subclass as in superclass.
  * Priority will be given to subclass methods
  * Optional `@Override` tag helps with error checking and readability
  * **IMPORTANT:** Overridden methods MUST have the same signature!
* **Interface inheritance:** Term for specifying capabilities of subclasses using an interface
  * Subclasses must implement/override **all** of the interface methods!!
* **If X is a superclass of Y, then a variable of type X can hold a reference to Y!**
  * Uses methods from subclass
  * **Dynamic method selection:** Dynamic \(runtime\) types take priority over Static \(compiled\) types
* Example:

  ```java
  public interface AnInterface<Item> {
    public void doStuff(Item x);
    public Item getItem();
    default public void defaultStuff() {
        // Do stuff
    }
    ...
  }

  public class Something implements AnInterface<Item> {
   @Override
   public void doStuff(Item x) {
       // implement method
   }

   @Override
   public void getItem() {
       // implement method
   }
  }

  public class MainClass {
    public static void main(String[] args) {
        AnInterface<String> smth = new AnInterface<>();
        AnInterface<String> smthElse = new Something<String>(); // Will not error!
        smth.getItem();
        ...
    }
  }
  ```

## Implementation Inheritance \(Extends\)

* Used to specify a **hyponym** of an interface
* Adds new functionality to a superclass
* What is inherited:
  * All instance and static variables
  * All methods
  * All nested classes
* What is NOT inherited:
  * Private variables/methods
  * Constructors
* Constructors will **automatically** run the constructor of superclasses even if it is not explicitly called!!!
  * Will not run twice if explicitly called: can access non-default constructors this way
* **IMPORTANT:** Any class which does not explicitly extend another class will implicitly extend the Object class

```java
public class A {
    public void doSomething() { ... }
}

public class B extends A {
    @Override
    public void doSomething() {
        super.doSomething();
        // Do more things
    }

    public void doSomethingElse() { ... }
}

public static void main(String[] args) {
    A aa = new A();
    aa.doSomething(); // OK
    aa.doSomethingElse(); // ERROR
    B bb = new B();
    bb.doSomething(); // OK
    bb.doSomethingElse(); // OK
}
```

## Compile-Time Type Checking

* Compiler is more conservative about type checking than is actually allowed based on dynamic type checking
* Example:

  ```java
  B bb = new B();
  A aa = bb; // ALLOWED at compile time, since B is a subclass of A
  aa.doSomethingElse(); // NOT ALLOWED at compile time even though this would work!
  B AnotherBB = aa; // NOT ALLOWED at compile time because aa is assigned type A, and a static-type subclass cannot be dynamically assigned a superclass!
  ```

* Can be resolved using **Casting:** Telling Java to treat an expression like having a different compile-time type. In the example above, the last line can be changed to

  ```text
  B AnotherBB = (B)aa;
  ```

  which tells Java to treat aa like a B type class. Since aa is indeed type B, it will compile and run as expected.

  However, aa cannot be casted into an unrelated type, e.g. `String`. Doing so will result in a `ClassCastException` at runtime.

## Subtype Polymorphism

**Polymorphism:** Providing a single interface to entities of different types

* Common example: making objects extend a 'comparable' interface which specifies greater than, equals, etc. behaviors

**Dynamic method selection:** When using polymorphisms, Java selects the correct behavior based on the dynamic type, not the static type

## Comparable

**Comparable:** Generic type that allows standardized comparisons between objects

Defining a Comparable subclass:

```java
public class MyComparable implements Comparable<MyComparable> {
    public int foo;
    ...

    /** Instance method that has nothing to do with comparable */
    public void doSomething() {
        ...
    }

    /** Comparable method used to compare objects of this type */
    public int compareTo(Object o) {
        MyComparable mc = (MyComparable) o;
        return ...
    }
}
```

* Many Java libraries already implement Comparable \(e.g. `Collection`, `String`\)
* Avoids casting

**Comparators**

* Used instead of higher order functions in order to provide a **callback** function to methods
* Interface is

  ```java
  public interface Comparable<T> {
   int compare(T o1, T o2);
  }
  ```

* Comparable is used to compare itself to other objects; a Comparator compares two other objects but not itself

