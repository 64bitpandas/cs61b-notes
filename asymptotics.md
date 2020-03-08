# Asymptotics

## How to Measure Programs

### Time
 - Measure execution time. Lower time = better
 - Use `time` command e.g. `time java Main args`
 - **Pros:**
    - Easy to measure
    - Obvious meaning
 - **Cons:**
    - Varies based on machine and input
    - May require lots of time

### Computational Cost
 - Count possible operations for a certain input N.
 - **Pros:**
    - Machine independent (for the most part)
    - Captured in a generalized model for all possible inputs
 - **Cons:**
    - Tedious to compute
    - Arbirary size N
    - No information on time

### Orders of Growth
 - General shape of a runtime function as N increases
 - Small numbers for N: runtime barely matters
 - Large numbers: difference between unsolvable problem (millions of years) to a trivial problem
 - **Simplifications:**
    1. Consider the worst case (which input would take the longest)
    2. Restrict attention to one operation, the **cost model** (all operations with the same order of growth are equally valid)
    3. Eliminate lower order terms (take n^3 over all n^2)
    4. Ignore multiplicative constants
 - **Steps:**
    1. Choose the cost model
    2. Intuitively select the order of growth
        - Nested for loop is n^2

## Bounds for Orders of Growth

**Big O**: Upper bound

**Big Omega**: Lower bound

**Big Theta**: Only exists if Big O is equal to Big Omega