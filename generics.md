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

### Subtyping
 - If we know that T1<X> is a subtype of T1<Y>, then it follows that X MUST equal Y
    - Otherwise, would violate type safety
    - Example:
    ```java
    List<String> LS = new ArrayList<String>();
    List<Object> LO = LS;
    LO.add(42); // technically valid since LO is a List<Object>... but it is actually LS!
    String s = LS.get(0); // error - LS[0] is an int!!!
    ```
 - Subtypes having the same generic type are OK under normal inheritance rules
    - Example: `List<String> LS = new ArrayList<String>();`
 - Arrays do not follow these rules, instead throw ArrayStoreException if types are mismatched during runtime

### Type Bounds
 - Can specify that a generic type must fit within a **type bound**: T is some subtype of a specified type
 ```java
 class SomeClass<T extends Number> {
   // A method that takes a type parameter T and takes any SUPERCLASS of T as a list generic type
   static <T> void doSomething(List<? super T> L) { ... }
 }
 ```

### Limitations
 - `new List<X>() instanceof List<Y>` will always be true regardless of what X and Y are
 - Primitive types not allowed (autoboxing allowed but has performance penalties)