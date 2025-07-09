# 🔒 RLWE-Based Polynomial Commitment Scheme in C++

This program demonstrates a simple **RLWE-based cryptographic commitment scheme** using modular polynomial arithmetic over the ring ℤ<sub>q</sub>[x]/(xⁿ + 1). It's built for educational purposes and showcases the mathematical simplicity and power behind post-quantum cryptography.

---

## 📄 File

- `rlwecommit.cpp`: Implements a lattice-based commitment using **Ring Learning With Errors (RLWE)** structure.

---

## 🔧 Overview

This scheme commits to a message polynomial `m(x)` using a key pair `(a(x), b(x))`:

\[
\text{Commit: } c(x) = a(x) \cdot m(x) + b(x) \cdot r(x) + e(x)
\]

Where:
- `a(x)`: public RLWE base polynomial (random)
- `b(x)`: public commitment key = `a(x) * s(x) + e₀(x)`
- `m(x)`: binary message polynomial
- `r(x), e(x)`: small random polynomials (noise)

---

## 🧠 What’s RLWE?

**Ring-LWE (RLWE)** is a lattice-based assumption used in post-quantum cryptography. This program operates over the polynomial ring:

\[
\mathbb{Z}_q[x]/(x^n + 1)
\]

Where `n` is a power of 2 and `q` is a prime modulus. The hardness of breaking the commitment lies in solving noisy polynomial equations under this ring structure.

---

## 📥 Inputs

- `n`: Degree of the ring modulus polynomial (`x^n + 1`)
- `q`: Prime modulus for coefficients
- Bitstring `m`: Binary message of length `< n` to commit

---

## ⚙️ How to Build and Run

### ✅ Build

```bash
g++ rlwecommit.cpp -o rlwecommit
