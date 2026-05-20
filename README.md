# Post-Quantum Cryptography — Live Demo

An interactive browser demo comparing classical RSA encryption against post-quantum ML-KEM (NIST FIPS 203), including a simulated quantum attack on both algorithms.

Built as an internal education tool to demonstrate why post-quantum cryptography matters and what the transition looks like in practice.

---

## What it does

- Type any message and encrypt it simultaneously with RSA-2048 and ML-KEM
- See the public key, ciphertext, and decrypted output for both algorithms side by side
- Watch a simulated quantum attack (Shor's algorithm) break RSA and fail against ML-KEM
- Plain-language explainers underneath describe why each outcome happens

---

## How to run it

No installation or server required. Just open `index.html` in any modern browser (Chrome, Edge, Firefox, Safari).

---

## Important note on the simulation

The encryption shown is **simulated for demonstration purposes** — true ML-KEM requires a native cryptographic implementation such as [liboqs](https://github.com/open-quantum-safe/liboqs). The key sizes, algorithm names, attack vectors, and outcomes are accurate to real-world behaviour. This tool is intended for education, not production use.

---

## Background

### The threat
Current encryption standards (RSA, ECDH, ECDSA) rely on mathematical problems that classical computers cannot solve efficiently. Quantum computers running Shor's algorithm can solve these problems in hours. Nation-state adversaries are already collecting encrypted data today to decrypt once quantum hardware matures — a strategy known as **harvest now, decrypt later**.

### The standard
In August 2024, NIST finalized the first post-quantum cryptographic standards after an eight-year global competition:

| Standard | Algorithm | Replaces |
|----------|-----------|----------|
| FIPS 203 | ML-KEM (CRYSTALS-Kyber) | RSA / ECDH key exchange |
| FIPS 204 | ML-DSA (CRYSTALS-Dilithium) | ECDSA digital signatures |
| FIPS 205 | SLH-DSA (SPHINCS+) | Backup signature scheme |

### Why ML-KEM is quantum-resistant
ML-KEM is built on the Module Learning With Errors (MLWE) lattice problem. No known quantum algorithm — including Shor's or Grover's — provides a meaningful advantage against lattice problems. Breaking ML-KEM with a quantum computer is not computationally feasible.

---

## Further reading

- [NIST Post-Quantum Cryptography project](https://csrc.nist.gov/projects/post-quantum-cryptography)
- [FIPS 203 — ML-KEM standard](https://csrc.nist.gov/pubs/fips/203/final)
- [Open Quantum Safe project (liboqs)](https://openquantumsafe.org)
- [CISA Post-Quantum Cryptography guidance](https://www.cisa.gov/quantum)
