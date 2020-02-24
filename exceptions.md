# Exceptions

### Basics
 - An **exception** occurs when something unintended occurs and the interpreter must exit. Causes the normal flow of code to stop
 - Can throw custom exceptions
 - All objects thrown must be a subtype of Throwable
 - All `Error` or `RuntimeException` are **unchecked**
   - Example: Index out of bounds, runtime casting errors
 - All other exceptions are **checked**
   - Example: Opening a file that does not exist
   - All checked exception must have `throws` in the method declaration. Example: `void test() throws IOException`
   - Parents must also declare throws if overriding a method that throws an exception

### Implicit Exception
 - Also known as "accidental" or "incidental" exception

### Creating Custom Exceptions
Throwing:
```java
throw new Exception("Error Message")
```

Catching:
TBD

 - Alternate to custom exceptions is to handle exception cases.
    - Example: Make code "null-safe" by checking to make sure inputs are not null before accessing them