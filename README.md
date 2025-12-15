# Computation Theory - SHA-256 Implementation

## Overview

This repository contains a complete implementation of the SHA-256 (Secure Hash Algorithm 256-bit) cryptographic hash function in Python, developed as part of the Computation Theory module assessment. The implementation follows the official [FIPS PUB 180-4 Secure Hash Standard](https://nvlpubs.nist.gov/nistpubs/FIPS/NIST.FIPS.180-4.pdf) specification.

The project demonstrates understanding of:
- Binary operations and bitwise manipulation
- Cryptographic hash function design
- Algorithm implementation from formal specifications
- Mathematical constant generation from prime numbers
- Message padding and block processing

## Purpose

The primary goal of this project is to implement SHA-256 from scratch, providing insight into how modern cryptographic hash functions work at a fundamental level. Rather than using pre-built libraries, this implementation builds each component step-by-step according to the standard specification.

## Repository Structure

```
.
├── README.md                 # This file - project documentation
├── problems.ipynb           # Main Jupyter notebook with all solutions
└── .gitignore              # Git ignore rules
```

## Getting Started

### Prerequisites

- Python 3.8 or higher
- Jupyter Notebook or JupyterLab / Github CodeSpaces
- Git (for cloning the repository)

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/RadoslawRodak/Computational-Theory.git
   cd Computational-Theory
   ```


### Running the Notebook

1. **Launch Jupyter Notebook:**
   ```bash
   jupyter notebook
   ```

2. **Open `problems.ipynb`** in your browser

3. **Run all cells** to see the complete SHA-256 implementation and tests

The notebook is fully self-contained and reproducible - all code cells can be executed in order from top to bottom.

## Problems Covered

### Problem 1: Binary Words and Operations
Implementation of the fundamental SHA-256 bitwise operations:
- `Parity(x, y, z)` - XOR-based parity function
- `Ch(x, y, z)` - Choice function
- `Maj(x, y, z)` - Majority function
- `Sigma0(x)` and `Sigma1(x)` - Upper case Sigma functions for hash compression
- `sigma0(x)` and `sigma1(x)` - Lower case sigma functions for message schedule

Each function includes detailed docstrings, explanations of the bitwise logic, and test cases.

### Problem 2: Fractional Parts of Cube Roots
Calculation of the 64 constant values (K₀ through K₆₃) used in SHA-256:
- Generation of the first 64 prime numbers
- Computing cube roots of these primes
- Extracting the first 32 bits of the fractional parts
- Verification against the official standard values

### Problem 3: Padding and Parsing
Implementation of message preparation for SHA-256:
- Message padding according to FIPS 180-4 specification
- Block parsing into 512-bit chunks
- Generator-based approach for memory efficiency

### Problem 4: Hash Function
The main SHA-256 hash computation:
- Message schedule generation (64 words per block)
- Compression function with working variables
- Integration of all previously implemented functions
- Complete end-to-end SHA-256 hashing

### Problem 5: Password Cracking
Password hash cracking demonstration:
- Cracking hashed passwords using dictionary attacks
- Successfully recovered 3/3 passwords
- Security analysis and implications

## Technical Details

**Language:** Python 3.x  
**Key Libraries:**
- NumPy (for 32-bit unsigned integer operations)
- Standard library modules only (no external crypto libraries)


## References

- [FIPS PUB 180-4: Secure Hash Standard (SHS)](https://nvlpubs.nist.gov/nistpubs/FIPS/NIST.FIPS.180-4.pdf) - Official specification
- Course materials and lecture notes

## How to Use

After installation, you can:

1. Run the complete notebook to see all implementations
2. Test individual functions with your own inputs
3. Hash any message using the final `sha256()` function
4. Compare results against online SHA-256 calculators

Example usage:
```python
# After running all cells in the notebook
message = b"Hello, World!"
hash_value = my_sha256(message)
print(hash_value)
```

## Development Notes

This project was developed incrementally throughout the semester with regular commits showing the evolution of the implementation. Each problem was tackled step-by-step, with testing and verification at each stage. 

