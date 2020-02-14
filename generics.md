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

**Generic Type Variable:** A value put in a generic class that can be used in a generic way (in the example above, `SomeType` is a generic type variable. Another convention is to use `T`)

**Actual Type Argument:** A type passed into an object during instantiation which specifies what actual type the generic type should assume. (In the example above, `String` is an actual type argument)