# Primes
### A simple sample program to demonstrate some conventions etc

### Some things to remember
 - Use `x += 1` and not `x++`
 - Comments should be `/** */` and not `//`
 - In documentation, params should be in `ALL_CAPS` to distinguish them from the rest of the comment
 - Floating point numbers are approximate. Make sure no rounding errors, etc occur.

```java
/** This can be run using `java Primes [n]` */
public class Primes {

    public static void Main(String[] args) {
        printPrimes(Integer.ParseInt(args[0])); // Main program assumes this is implemented correctly
    }

    private static void printPrimes(int max) {
        // Iterate through from 2 to limit
        // Keep track of linebreaks 
    }

    private static boolean isPrime(int x) {
        if (x <= 1)
            return false;
        else
            return !isDivisible(x, 2); // Use separation of concerns to keep program simple and modular
    }

    private static boolean isDivisible(int x, int k) {
        // Guarded commands: possibly correct responses are guarded by the conditions in which it is expected to work. Use in conjunction with recursion/iteration to continue on if no guarded conditions are met.
        if (k >= x)
            return false;
        else if (x % k == 0)
            return true;
        else 
            return isDivisible(x, k+1); // especially if there is no source code, rely on documentation and expect that a method works as it is described. (Recursive leap of faith)
    }
}
```