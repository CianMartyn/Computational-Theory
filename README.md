# Computational Theory Tasks

This repository contains implementations of fundamental computational theory concepts, with a focus on cryptographic functions and algorithms. The tasks are based on FIPS 180-4, Secure Hash Standard (SHS).

## Tasks

### Task 1: Binary Representations
Implement and test the following bitwise operations:
- `rotl(x, n=1)`: Left rotation of 32-bit unsigned integer
- `rotr(x, n=1)`: Right rotation of 32-bit unsigned integer
- `ch(x, y, z)`: Bit selection based on x (y if x=1, z if x=0)
- `maj(x, y, z)`: Majority vote of bits (1 if at least two inputs are 1)

### Task 2: Hash Functions
Convert and analyse the K&R hash function:
```c
unsigned hash(char *s) {
    unsigned hashval;
    for (hashval = 0; *s != '\0'; s++)
        hashval = *s + 31 * hashval;
    return hashval % 101;
}
```
- Convert to Python
- Test implementation
- Explain choice of 31 and 101

### Task 3: SHA256 Padding
Implement SHA256 padding for files:
- Append '1' bit
- Add '0' bits until length is multiple of 512
- Append original length as 64-bit big-endian integer
- Output padding in hexadecimal format

### Task 4: Prime Number Generation
Calculate first 100 primes using two different algorithms:
- Implement and explain each algorithm
- Compare results and performance
- Document implementation details

### Task 5: Roots
Calculate fractional parts of square roots:
- Compute square roots of first 100 primes
- Extract first 32 bits of fractional part
- Convert to appropriate formats

### Task 6: Proof of Work
Find words with most leading zeros in SHA256 hash:
- Calculate SHA256 hashes of English words
- Count leading zero bits
- Provide dictionary validation
- Document findings

### Task 7: Turing Machines
Design Turing machine for binary addition:
- Start at leftmost non-blank symbol
- Add 1 to binary number
- Handle carry operations
- Example: 100111 → 101000

### Task 8: Computational Complexity
Analyze bubble sort complexity:
- Implement bubble sort with comparison counting
- Test on all permutations of [1,2,3,4,5]
- Document comparison counts
- Analyse results

## Requirements
- Python 3.x
- Jupyter Notebook
- Standard Python libraries:
  - math
  - hashlib
  - struct
  - os
  - itertools
  - numpy

## Usage
1. Install required dependencies
2. Open notebook in Jupyter
3. Run cells in sequence
4. Review test cases and results
5. Modify parameters as needed

## Notes
- Each task is self-contained
- Test cases provided for verification
- Detailed documentation included
- Results can be verified against standards