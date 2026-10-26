---
type: definition
title: Residue Class Ring Z_n
aliases: [residue class ring, Restklassenring, residue class, Restklasse, congruence, Kongruenz, modulo, Z_n]
tags: [number-theory, ring-theory]
sources: [raw/Zn_das.pdf]
created: 2026-09-30
updated: 2026-09-30
status: solid
---

# Residue Class Ring $\mathbb{Z}_n$

## Construction

The starting point is an [[equivalence-relation|equivalence relation]] on $\mathbb{Z}$:

$$R_n \subseteq \mathbb{Z}\times\mathbb{Z}, \qquad
(a,b) \in R_n \;:\Longleftrightarrow\; a - b = k\cdot n \text{ for some } k \in \mathbb{Z}$$

Notation:
$$a \equiv b \pmod n$$

**Residue class** (*Restklasse*) of $a$:
$$\overline{a} = \{a + kn \mid k \in \mathbb{Z}\}$$

**Quotient set** (*Quotientenmenge*):
$$\mathbb{Z}_n = \mathbb{Z}/R_n = \{\overline{a} \mid a \in \mathbb{Z}\}
= \{\overline{0}, \overline{1}, \dots, \overline{n-1}\}$$

Example $n = 4$:

| $\overline{0}$ | $\overline{1}$ | $\overline{2}$ | $\overline{3}$ |
|---|---|---|---|
| $\dots,-4,0,4,8,12,\dots$ | $\dots,1,5,9,13,\dots$ | $\dots,2,6,10,14,\dots$ | $\dots,3,7,11,15,\dots$ |

$$\mathbb{Z}_4 = \{\overline{0},\overline{1},\overline{2},\overline{3}\}$$

## Division with remainder

The residue classes are exactly the possible remainders of integer division:
$$a = q\cdot n + r, \qquad q, r \in \mathbb{Z},\; 0 \le r < n$$

$$20 = 2\cdot7 + 6 \;\Longrightarrow\; 20 \equiv 6 \pmod 7$$
$$7 \equiv 3 \pmod 4, \quad 11 \equiv 3 \pmod 4, \quad 3 \equiv 3 \pmod 4$$

## $\mathbb{Z}_n$ is a commutative ring

$(\mathbb{Z}_n, +, \cdot, \overline{0}, \overline{1})$ satisfies all axioms from
[[ring-like-structures]], inherited from $(\mathbb{Z},+,\cdot,0,1)$:

- $(\mathbb{Z}_n, +, \overline{0})$ is an **abelian group**
- $(\mathbb{Z}_n, \cdot, \overline{1})$ is a **monoid**
- **Distributive law** $r(s+t) = rs + rt$

The source demonstrates this explicitly using the model $(\mathbb{Z},+,\cdot,0,1)$ — see
also [[laws-of-integers]].

**But:** $\mathbb{Z}_n$ is in general **not an integral domain**, since there can be
[[units-and-zero-divisors|zero divisors]].

## Operation tables for $\mathbb{Z}_6$

$$+$$

| $+$ | 0 | 1 | 2 | 3 | 4 | 5 |
|---|---|---|---|---|---|---|
| **0** | 0 | 1 | 2 | 3 | 4 | 5 |
| **1** | 1 | 2 | 3 | 4 | 5 | 0 |
| **2** | 2 | 3 | 4 | 5 | 0 | 1 |
| **3** | 3 | 4 | 5 | 0 | 1 | 2 |
| **4** | 4 | 5 | 0 | 1 | 2 | 3 |
| **5** | 5 | 0 | 1 | 2 | 3 | 4 |

$$\cdot$$

| $\cdot$ | 0 | 1 | 2 | 3 | 4 | 5 |
|---|---|---|---|---|---|---|
| **0** | 0 | 0 | 0 | 0 | 0 | 0 |
| **1** | 0 | 1 | 2 | 3 | 4 | 5 |
| **2** | 0 | 2 | 4 | 0 | 2 | 4 |
| **3** | 0 | 3 | 0 | 3 | 0 | 3 |
| **4** | 0 | 4 | 2 | 0 | 4 | 2 |
| **5** | 0 | 5 | 4 | 3 | 2 | 1 |

From the multiplication table one reads off directly:

- The rows of $1$ and $5$ contain the $1$ → **units**.
- The rows of $2, 3, 4$ contain a $0$ (outside column 0) → **zero divisors**.

The addition table is a **cyclic pattern** — every row is the previous one shifted by
one. $(\mathbb{Z}_n,+)$ is the cyclic group of order $n$.

## Related

- [[units-and-zero-divisors]] — which elements are invertible
- [[fermats-little-theorem]] — exponentiation in $\mathbb{Z}_p$
- [[euler-phi-function]] — number of units
- [[ring-like-structures]] — ring, integral domain, field
- [[equivalence-relation]] — the underlying relation
- [[relations-and-permutations]] — chapter context
- [[polynomial-ring]] — the same construction with polynomials instead of numbers

## Sources

- `raw/Zn_das.pdf`, p. 7, p. 8
