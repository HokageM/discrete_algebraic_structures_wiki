---
type: concept
title: Residue Class Rings Z_n
aliases: [modular arithmetic, Restklassenringe, modulare Arithmetik, Kapitelübersicht Zn]
tags: [hub, number-theory]
sources: [raw/Zn_das.pdf]
created: 2026-09-30
updated: 2026-09-30
status: solid
---

# Residue Class Rings $\mathbb{Z}_n$

Hub page for the chapter. $\mathbb{Z}_n$ is the place where almost all threads of the
module come together: an [[equivalence-relation|equivalence relation]] generates a
quotient set, this quotient set carries a [[ring-like-structures|ring structure]], and the
[[laws-of-gcd|Euclidean algorithm]] decides which elements are invertible.

## The chain

```
Equivalence relation a ≡ b (mod n)
    → residue classes ā = {a + kn}
    → quotient set Z_n = {0̄, …, n−1}
    → commutative ring (Z_n, +, ·, 0̄, 1̄)
        ├── gcd(a,n) = 1 → unit  → inverse via extended Euclid
        └── gcd(a,n) > 1 → zero divisor
    → #units = φ(n)
    → n prime ⇒ field ⇒ Fermat's little theorem
```

## Pages of this chapter

| Page | Content |
|---|---|
| [[residue-class-ring]] | congruence, residue class, quotient set, ring axioms, $\mathbb{Z}_6$ tables |
| [[units-and-zero-divisors]] | definitions + gcd criterion with proof |
| [[euler-phi-function]] | $\varphi(n) = n\prod(1-\frac1{p})$ |
| [[fermats-little-theorem]] | $n$ prime $\Rightarrow a^n \equiv a$ |
| [[determining-units-and-zero-divisors]] | $\mathbb{Z}_6, \mathbb{Z}_{15}, \mathbb{Z}_{16}, \mathbb{Z}_{20}$ |
| [[computing-inverses]] | extended Euclid, three problems with check |
| [[modular-exponentiation]] | square-and-multiply, order, Fermat |

## The four exam problem types

The source contains the same problem structure twice (problem 5, 16 points each) — the
chapter is thus fully covered by four problem types:

| # | Problem | Tool | Page |
|---|---|---|---|
| 1 | All units and zero divisors of $\mathbb{Z}_n$ | prime factorization of $n$ | [[determining-units-and-zero-divisors]] |
| 2 | Power $a^k$ in $\mathbb{Z}_n$ | square-and-multiply / Fermat | [[modular-exponentiation]] |
| 3 | Inverse of $a$ in $\mathbb{Z}_n$ | extended Euclid | [[computing-inverses]] |
| 4 | Number of units in $\mathbb{Z}_n$ | $\varphi(n)$ | [[euler-phi-function]] |

Concretely asked:

| | Exam A | Exam B |
|---|---|---|
| 1 | $\mathbb{Z}_{16}$ | $\mathbb{Z}_{15}$ |
| 2 | $83^{25}$ in $\mathbb{Z}_9$ → $2$ | $75^{25}$ in $\mathbb{Z}_{17}$ → $10$ |
| 3 | $23^{-1}$ in $\mathbb{Z}_{51}$ → $20$ | $33^{-1}$ in $\mathbb{Z}_{61}$ → $37$ |
| 4 | $\varphi(176) = 80$ | $\varphi(330) = 80$ |

**All eight results were independently recomputed and confirmed during ingest.**

## Prime factorization as the recurring thread

Notably: in **three of four** problem types, the first step is to factorize $n$.

- Type 1: determines which $a$ are zero divisors.
- Type 4: directly gives the factors $(1-\frac1{p_i})$.
- Type 2: decides whether Fermat is applicable ($n$ prime?).

Only type 3 does without it — the Euclidean algorithm doesn't need the factorization, it
finds the gcd on its own.

## Cross-connections

- **To [[algebraic-structures]]:** $\mathbb{Z}_n$ is the standard example showing that a
  commutative ring need **not** be an integral domain. For prime $n$ it is even a field —
  so the entire hierarchy from [[ring-like-structures]] can be illustrated with a single
  family.
- **To [[relations-and-permutations]]:** the congruence is *the* equivalence relation of
  the module. Cf. [[equivalence-relation-proofs]], where $3 \mid a^2-b^2$ is examined.
- **To [[laws-of-gcd]]:** the remainder law noted there is the backward phase of the
  extended Euclidean algorithm.
- **To [[group-like-structures]]:** $(\mathbb{Z}_n,+)$ is the cyclic group of order $n$,
  $(\mathbb{Z}_n^*,\cdot)$ the group of units of order $\varphi(n)$.
- **To [[polynomial-rings]]:** $K[x]_g$ is the exact transfer of $\mathbb{Z}_n$ to
  polynomials — division with remainder, residue classes, units via gcd; "$n$ prime"
  becomes "$g$ irreducible".

## Error density of this source

This chapter contains the most computational errors of all sources ingested so far — four
documented spots (p. 6, p. 8, p. 10, p. 12). All are slips in intermediate steps; the
final results are correct except for $67^{33} \bmod 13$ (first calculation on p. 12).
Consequence for the exam: **always double-check**, ideally via a second method.

## Sources

- `raw/Zn_das.pdf` (13 pages)
