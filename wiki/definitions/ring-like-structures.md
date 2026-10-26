---
type: definition
title: Ring-like Structures
aliases: [ring-like structures, Ringartige Strukturen, ring, Ring, commutative ring, kommutativer Ring, integral domain, Integritätsring, field, Körper]
tags: [algebraic-structures, ring-theory, fields]
sources: [raw/Algebraische_strukturen_das.pdf]
created: 2026-09-30
updated: 2026-09-30
status: solid
---

# Ring-like Structures $(R, +, \cdot)$

## Definition

A set $R$ with **two** operations $+$ and $\cdot$ is called ring-like if three
conditions are satisfied:

**1. $(R, +)$ is an abelian group.**

| $+$ | closed | associative | identity $0$ | inverses | commutative |
|---|:---:|:---:|:---:|:---:|:---:|
| abelian group | ✓ | ✓ | ✓ | ✓ | ✓ |

**2. Multiplication is distributive over addition:**
$$\forall a, x, y \in R:\quad a \cdot (x + y) = a \cdot x + a \cdot y
\quad\text{and}\quad (x + y) \cdot a = x \cdot a + y \cdot a$$

**3. $(R, \cdot)$ forms — depending on the case — one of the following structures:**

| $\cdot$ | closed | associative | identity $1$ | inverses (of $\neq 0$) | commutative | yields |
|---|:---:|:---:|:---:|:---:|:---:|---|
| semigroup | ✓ | ✓ | – | – | – | *(ring without unity)* |
| monoid | ✓ | ✓ | ✓ | – | – | **ring\*** |
| monoid | ✓ | ✓ | ✓ | – | ✓ | **commutative ring\*** |
| group | ✓ | ✓ | ✓ | ✓ | – | *(division ring)* |
| abelian group | ✓ | ✓ | ✓ | ✓ | ✓ | **field** |

**\*** If in addition there are **no zero divisors** (except $0$), these are called
**zero-divisor-free ring** (*nullteilerfreier Ring*, English *domain*) resp.
**integral domain** (*Integritätsring*).

## Intuition

A ring is "$\mathbb{Z}$ as a structure": addition and subtraction always work,
multiplication works, division in general does not.

A field is "$\mathbb{Q}$ as a structure": in addition, every element except $0$ is
invertible, so one can divide.

The asymmetry between $+$ and $\cdot$ is essential: for $+$ the abelian group is
**always** required, while for $\cdot$ the requirement varies. This matches exactly the
observation from [[laws-of-integers]] that $\cdot$ distributes over $+$, but not vice
versa.

## Examples

- $(\mathbb{Z}, +, \cdot, 0, 1)$ is a commutative ring (p. 7 of the source). Even an
  integral domain, since $\mathbb{Z}$ is zero-divisor-free — exactly what the
  cancellation rule in [[laws-of-integers]] states.
- $\mathbb{Q}$, $\mathbb{R}$ are fields.
- $\mathbb{Z}_n$ is a ring; whether it is a field depends on $n$ — see the pages on
  $\mathbb{Z}_n$.

## Counterexamples

- $(\mathbb{N}_0, +, \cdot)$ is **not** a ring: $(\mathbb{N}_0, +)$ is not a group.
- $\mathbb{Z}$ is **not** a field: only $\pm 1$ are multiplicatively invertible.

## Properties

- **Zero divisor** (*Nullteiler*): $a \neq 0$ is called a zero divisor if there exists
  $b \neq 0$ with $a \cdot b = 0$. Being zero-divisor-free is the property that allows
  cancellation.
- Every field is an integral domain.
- The label "inverses of non-$0$ elements" in the table is important: $0$ is
  multiplicatively invertible in **no** ring.

## Related

- [[properties-of-operations]] — the building blocks
- [[group-like-structures]] — structures with one operation
- [[substructures]] — subring
- [[homomorphism]] — ring homomorphism
- [[laws-of-integers]] — the same axioms concretely for $\mathbb{Z}$
- [[residue-class-ring]] — $\mathbb{Z}_n$: commutative ring, a field for prime $n$
- [[polynomial-ring]] — $K[x]_g$: the same construction with polynomials
- [[irreducibility-and-fields]] — when a residue class ring is a field
- [[units-and-zero-divisors]] — the concepts behind "zero-divisor-free"
- [[algebraic-structures]] — overall overview

## Sources

- `raw/Algebraische_strukturen_das.pdf`, p. 1, p. 7 and p. 11
