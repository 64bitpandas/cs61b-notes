# Inheritance

### Method Overloading
 - When there are multiple methods with the same name, but different parameters
 - A very crude solution towards generality:
    - Repetitive
    - Requires maintaining more code (a change to one requires a change to the others)
    - Doesn't handle data types outside of those specified

### Hypernyms and Hyponyms
 - **Hypernym:** a more general word that can be used to replace a more specific one. A **Hyponym** is the opposite (a specific word that can be replaced by a general one)
 - Example: A dog is a hypernym of poodle; a husky is a hyponym of dog. 
 - A hyponym **is-a** hypernym: A dog **is-a** canine.

### Interfaces
 - Declared in the same way as classes: `public interface InterfaceName {}`
 - Specifies the methods and variables contained, but not their implementation 
    - Can use **default** keyword to go around this restriction, but not recommended (**Implementation inheritance**)
        - Harder to keep track of implementation
        - Overly complex
        - Breaks encapsulation rules
 - Allows generic types to be used in methods without overloading (as long as they have the same methods)
 - **Method Overriding:** redefining the same methods in subclass as in superclass.
    - Priority will be given to subclass methods
    - Optional `@Override` tag helps with error checking and readability
    - **IMPORTANT:** Overridden methods MUST have the same signature!
 - **Interface inheritance:** Term for specifying capabilities of subclasses using an interface
    - Subclasses must implement/override **all** of the interface methods!!
 - **If X is a superclass of Y, then a variable of type X can hold a reference to Y!**
    - Uses methods from subclass
    - **Dynamic method selection:** Dynamic (runtime) types take priority over Static (compiled) types

 - Example:
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