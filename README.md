Overview

This repository contains a C implementation of a toy version of the Kyber Post-Quantum Public-Key Cryptosystem. The implementation uses polynomials from Z97/(X^4+1), representing polynomials modulo X^4+1 with coefficients modulo 97.

Files:

toy.h [Header file containing macro definitions for the toy cryptosystem.]

toy.c [Main source file implementing the toy cryptosystem.]

main.c [To run the code.]

Implementation Details:

Polynomial Multiplication

The polynomial multiplication is implemented using a naive approach, where each coefficient is computed individually according to the provided pseudocode.

Key Generation (toy_gen)

The key generation function generates a public key A and a private key s. The matrix-vector multiplication t = A.s + e is performed in Z97[X]/(X^4+1), where e is a vector of small random numbers.

Encryption (toy_enc)

The encryption function takes a public key (A, t) and a 4-bit plaintext, and outputs a ciphertext (u, v). It involves random vector generation, matrix-vector multiplication, and the addition of random polynomials.

Decryption (toy_dec)

The decryption function takes a private key s and a ciphertext (u, v), and outputs the decrypted plaintext. It involves polynomial subtraction and bit extraction based on the provided pseudocode.
