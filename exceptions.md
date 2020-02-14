# Exceptions

### Basics
 - An **exception** occurs when something unintended occurs and the interpreter must exit. Causes the normal flow of code to stop
 - Can throw custom exceptions

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