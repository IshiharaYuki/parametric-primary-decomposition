# Parametric Primary Decomposition

This repository contains an implementation of algorithms for parametric primary decomposition in polynomial rings, specifically focusing on the Hilbert subset computation. Implementations for the parametric primary decomposition will be uploaded in the future. 

## Overview

The main functionality is implemented in `hilbert_primary.rr`, which provides algorithms for computing semi-Hilbert subsets for prime/primary ideals in polynomial rings with parameters.

## Main Functions

### `hilbert_primary(Q, A, V)`
Computes a semi-Hilbert subset for a prime/primary ideal Q. Here, QQ denotes the rational field.

**Input:**
- `Q`: A prime/primary ideal in K[V]
- `A`: A list of parameters
- `V`: A list of variables

**Output:**
- `[F, [C, J]]`: A semi-Hilbert subset for Q, where:
  - F is an irreducible polynomial of QQ[V,A]
  - C = Q∩QQ[A] is the condition ideal of Q
  - J is an ideal in QQ[A]
  such that the specilization \phi_\alpha(Q) at \alpha is a prime/primary ideal for any \alpha\in V(C)\setminus V(J) if F(\alpha,X) is irreducible over QQ

## Usage

The code is written in Risa/Asir, a computer algebra system. To use this implementation:

1. Ensure you have Risa/Asir installed
2. Load the `hilbert_primary.rr` file
3. Call the functions with appropriate input ideals and parameter/variable lists

## Example

Consider a prime ideal Q=<(a-2)*x+y^3+a*y,y^2-a> in QQ[a,x,y] where a is the parameter and x,y are ordinal variables

load("hilbert_primary.rr");
hilbert_primary([(a-2)*x+y^3+a*y,y^2-a],[a],[x,y]);
[y^2-a,[[0],[-a+2]]]

This implies that \phi_\alpha(Q)=<(\alpha-2)*x+y^3+\alpha*y,y^2-\alpha> is prime for any QQ\setminus V(a-2) if y^2-\alpha is irreducible in QQ[y]

## Dependencies

- Risa/Asir computer algebra system
- The `noro_pd` package for primary decomposition

## Note

This implementation is particularly useful for studying the behavior of ideals under specialization and for computing (semi-)Hilbert subsets in parametric polynomial rings.