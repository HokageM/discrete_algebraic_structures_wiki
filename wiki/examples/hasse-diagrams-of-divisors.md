---
type: example
title: Hasse Diagrams of Divisor Lattices
aliases: [divisor lattice, Hasse diagram of divisors, Hasse-Diagramme der Teilerverbände, Teilerdiagramm]
tags: [relations, order, example]
sources: [raw/relation_und_permutation_das.pdf]
created: 2026-09-30
updated: 2026-09-30
status: solid
---

# Hasse Diagrams of Divisor Lattices

Three worked problems on [[hasse-diagram|Hasse diagrams]]: the set of divisors of a number
$n$, ordered by the divisibility relation (Teilbarkeitsrelation) $\mid$.

**Procedure used by the source every time:**

1. Decompose $n$ into prime factors.
2. List all divisors as products $p_1^{a_1}\cdots p_r^{a_r}$ with $0 \le a_i \le e_i$.
3. Sort into levels — level $=$ sum of the exponents $a_1 + \dots + a_r$.
4. Draw edges only between **adjacent** levels (differ by exactly one prime factor).

Loops and transitive edges are omitted — the source explicitly notes "Hasse diagram
without $\circlearrowright$".

## 1. Divisors of $28 = 2^2 \cdot 7$

Divisors: $1, 2, 4, 7, 14, 28$ — that is $(2+1)(1+1) = 6$ of them.

```
        28
       /  \
      4    14
      |   /  \
      2 ─┘    7
       \     /
        \   /
          1
```

| Level | Divisors |
|---|---|
| 3 | $28 = 2^2\cdot7$ |
| 2 | $4 = 2^2$, $14 = 2\cdot7$ |
| 1 | $2$, $7$ |
| 0 | $1$ |

Edges: $1-2$, $1-7$, $2-4$, $2-14$, $7-14$, $4-28$, $14-28$.

## 2. Divisors of $36 = 2^2 \cdot 3^2$

Divisors: $1,2,3,4,6,9,12,18,36$ — $(2+1)(2+1) = 9$ of them.

```
         36
        /  \
      12    18
     /  \  /  \
    4     6     9
     \   / \   /
       2     3
        \   /
          1
```

| Level | Divisors |
|---|---|
| 4 | $36$ |
| 3 | $12 = 2^2\cdot3$, $18 = 2\cdot3^2$ |
| 2 | $4 = 2^2$, $6 = 2\cdot3$, $9 = 3^2$ |
| 1 | $2$, $3$ |
| 0 | $1$ |

The diagram is a **$3 \times 3$ lattice**, because both prime factors have exponent $2$.
The source draws exactly this exponent lattice (Exponentengitter) as a schema right
next to it.

## 3. Divisors of $72 = 2^3 \cdot 3^2$

Divisors: $1,2,3,4,6,8,9,12,18,24,36,72$ — $(3+1)(2+1) = 12$ of them.

| Level | Divisors |
|---|---|
| 5 | $72$ |
| 4 | $24 = 2^3\cdot3$, $36 = 2^2\cdot3^2$ |
| 3 | $8 = 2^3$, $12 = 2^2\cdot3$, $18 = 2\cdot3^2$ |
| 2 | $4 = 2^2$, $6 = 2\cdot3$, $9 = 3^2$ |
| 1 | $2$, $3$ |
| 0 | $1$ |

Edges (one more prime factor each time):
$1-2$, $1-3$; $2-4$, $2-6$, $3-6$, $3-9$; $4-8$, $4-12$, $6-12$, $6-18$, $9-18$;
$8-24$, $12-24$, $12-36$, $18-36$; $24-72$, $36-72$.

The diagram is a **$4 \times 3$ lattice** (exponents $0..3$ for $2$, $0..2$ for $3$).

## Pattern

For $n = p_1^{e_1}\cdots p_r^{e_r}$:

- Number of divisors: $\prod_i (e_i + 1)$.
- The Hasse diagram is always the **lattice** $\{0..e_1\}\times\dots\times\{0..e_r\}$,
  i.e. isomorphic to the exponent vector with componentwise order.
- Smallest element: $1$ (bottom). Largest: $n$ (top).
- Any two elements have a supremum ($\operatorname{lcm}$) and an infimum
  ($\operatorname{gcd}$) — cf. [[laws-of-gcd]]. The set of divisors is thus a
  *lattice* (Verband).

> [!inferred] not from the summaries
> The counting formula $\prod(e_i+1)$ and the notion of a lattice are not stated
> explicitly in the summaries; but they make visible the pattern behind the three
> diagrams drawn above.

## Related

- [[hasse-diagram]] — definition and construction rules
- [[properties-of-homogeneous-relations]] — $\mid$ is reflexive, transitive, antisymmetric
- [[laws-of-gcd]] — $\operatorname{gcd}$ and $\operatorname{lcm}$

## Sources

- `raw/relation_und_permutation_das.pdf`, p. 4 (problem 1.4), p. 7 (problem 2.4), p. 13 (tutorial 3.4)
