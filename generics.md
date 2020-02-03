# Generic Types

Allows objects and methods to be created to support any types, including user-defined types.

 - **Note:** For primitives, use their corresponding reference types. `Integer, Double, Character, Boolean, Long...`

**Definition:**
```java
/**
  * Creates a type SomeClass that takes * in a generic SomeType. SomeType can * be named anything.
*/
public class SomeClass<SomeType> {
    private SomeType someThing;

    public void someMethod(SomeType stuff) {
        doStuff(stuff);
    }
}
```

**Usage:**
```java
SomeClass<String> aClass = new SomeClass<>(); // SomeType is not required during instantiation
```