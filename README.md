# Computational Theory Tasks

This repository contains implementations of fundamental computational theory concepts, with a focus on cryptographic functions and algorithms. The tasks are based on FIPS 180-4, Secure Hash Standard (SHS).

## Tasks


Task 1: Binary Representations
------------------------------

This task implements essential bitwise operations often used in cryptographic algorithms, aligned with FIPS 180-4 (Secure Hash Standard).

### Functions Implemented:

-   `**rotl(x, n)**`: Left-rotates a 32-bit integer by `n` positions.

-   `**rotr(x, n)**`: Right-rotates a 32-bit integer by `n` positions.

-   `**ch(x, y, z)**`: Chooses bits from `y` where `x` is 1, and from `z` where `x` is 0.

-   `**maj(x, y, z)**`: Returns the majority bit from the inputs.

Each function was tested using predefined binary values, and the output was verified visually against expected results.

* * * * *

Task 2: Hash Functions
----------------------

Converted and analyzed a C-style rolling hash function:

```
unsigned hash(char *s) {
    unsigned hashval;
    for (hashval = 0; *s != '\0'; s++)
        hashval = *s + 31 * hashval;
    return hashval % 101;
}
```

### Key Points:

-   Translated to Python and tested.

-   **Why 31?** A small prime that offers a good distribution.

-   **Why 101?** A prime modulus ensures uniform hash spreading and reduced collisions.

* * * * *

Task 3: SHA-256 Padding
-----------------------

Implements message padding for SHA-256 according to FIPS 180-4:

### Procedure:

1.  Append a `1` bit (0x80).

2.  Pad with `0`s until length is 56 mod 64.

3.  Append original length as a 64-bit big-endian integer.

Validated using a sample file (`test.txt`) with output printed in hex format.

* * * * *

Task 4: Prime Number Generation
-------------------------------

Computed the first 100 prime numbers using two different methods:

### Methods Used:

-   **Trial Division** (simple, O(n√(n)))

-   **Sieve of Eratosthenes** (efficient, O(n log log n))

Each method was implemented and tested independently. Results were compared for correctness.

* * * * *

Task 5: Square Root Fraction Extraction
---------------------------------------

Calculated the fractional part of square roots of the first 100 prime numbers.

### Procedure:

-   Compute √sqrt(prime)

-   Extract fractional part

-   Multiply by 2^32

-   Convert to binary and hexadecimal

This mirrors the process used for constant generation in SHA-2 algorithms.

* * * * *

Task 6: Proof of Work
---------------------

Simulated a basic proof-of-work algorithm by finding English words whose SHA-256 hash starts with the most leading zero bits.

### Steps:

1.  Read words from `words.txt`

2.  Hash each word using SHA-256

3.  Count leading zero bits in binary hash

4.  Output words with the highest count

This mimics the core idea behind cryptocurrency mining.

* * * * *

Task 7: Turing Machine for Binary Addition
------------------------------------------

Designed and implemented a simple Turing Machine that adds 1 to a binary number.

### Key Behavior:

-   Reads from left to right to find the end.

-   Performs addition with carry handling from right to left.

-   Halts once addition is complete.

### State Table:

| State | Read | Write | Move | Next State |
| q0 | 0/1 | 0/1 | R | q0 |
| q0 | □ | □ | L | q1 |
| q1 | 0 | 1 | N | HALT |
| q1 | 1 | 0 | L | q1 |
| q1 | □ | 1 | N | HALT |

Tested with input `100111` resulting in correct output `101000`.

* * * * *

Task 8: Computational Complexity of Bubble Sort
-----------------------------------------------

Evaluated the complexity of the Bubble Sort algorithm.

### Implementation Details:

-   Modified Bubble Sort to count comparisons.

-   Applied it to all 120 permutations of [1, 2, 3, 4, 5].

-   Printed each permutation with its comparison count.

### Observation:

All permutations resulted in exactly 10 comparisons, showcasing Bubble Sort's predictable comparison pattern on fixed-size input.

* * * * *


## Usage
1. Install required dependencies
2. Open notebook in Jupyter
3. Run cells in sequence
4. Review test cases and results
5. Modify parameters as needed
