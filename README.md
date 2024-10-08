# COSC 273 Final Project: Parallel Primes

This repository contains the code for our final project for COSC 273, implementing Simon's algorithm in quantum computing. The project was completed in collaboration with Soyon Choi and Ris Paulino.

## Overview

This project focuses on computing prime numbers using a parallelized implementation of the **Sieve of Eratosthenes** (SoE). The goal was to generate as many prime numbers as possible within a one-second time frame by utilizing multithreading in Java. This approach maximizes the number of primes computed while ensuring the program handles interrupts and thread terminations gracefully.

The core of the project is split into two parts:

1. **Prime Generation**: Using the Sieve of Eratosthenes, we compute a boolean array that marks which numbers are prime and composite up to a given maximum.
2. **Parallelization**: To optimize performance, we implemented a parallel version of the SoE algorithm, dividing the work across multiple threads while ensuring they operate efficiently and without overlap.

## Files

- **ParallelPrimes.java**: Implements the multithreaded computation of prime numbers.
- **Primes.java**: Implements the core logic for the Sieve of Eratosthenes and utility methods for handling primes.
  
## Key Concepts

- **Sieve of Eratosthenes**: The method uses an array of boolean values to mark prime and composite numbers efficiently.
- **Multithreading**: We utilize Java’s `Executors` and thread pools to parallelize the task of finding primes over multiple ranges.
- **Interrupt Handling**: The program is designed to handle interrupts gracefully, ensuring that tasks are terminated within a set timeframe (1 second).

## Optimization Strategy

Our parallelized implementation follows this key optimization:
- We compute a small set of primes sequentially and use those small primes to compute larger primes in parallel across multiple threads.
- Tasks are broken into two types: one for computing blocks of primes and another for writing those primes in sequential order to maintain correctness.

The program will compute as many prime numbers as possible within a one-second window, using the parallel implementation of the Sieve of Eratosthenes.

## Project Team

- **Ania Serbina** (aserbina28)
- **Soyon Choi**
- **Ris Paulino**

This project was part of the COSC 273: Quantum Computing course, taught by Will Rosenbaum in 2023.
