---
type: definition
title: Hasse diagram
aliases: [Hasse diagram, Hasse-Diagramm, order relation, Ordnungsrelation, divisibility order, Teilbarkeitsordnung, partial order]
tags: [relations, order]
sources: [raw/relation_und_permutation_das.pdf]
created: 2026-09-30
updated: 2026-09-30
status: needs-review
---

# Hasse diagram

## Definition

A Hasse diagram is the graphical representation of an **order relation** (*Ordnungsrelation*)
(reflexive, transitive, antisymmetric). It arises from the [[relation|digraph]]
(*Digraph*) through three simplifications:

1. **Omit loops** (reflexivity is silently assumed) — the source notes: "Hasse diagram
   without $\circlearrowright$".
2. **Omit transitive edges** (from $x < y < z$ it follows that $x < z$, this need not be
   drawn).
3. **Omit arrowheads**: direction is expressed by height — larger elements are placed
   higher up.

What remains are only the **covering relations**: an edge $x - y$ exists exactly when
$x < y$ holds and nothing lies in between.

> [!inferred] not from the summaries
> The source defines neither "order relation" nor "covering" and does not mention the
> conditions (reflexive/transitive/antisymmetric) at this point either. It shows the
> Hasse diagram only through examples with the divisibility order. The definition above
> reconstructs the rules from these examples — check in the lecture if needed.

## Intuition

The Hasse diagram is the digraph with everything omitted that can be reconstructed
anyway from the order axioms. It shows only the "direct neighbors".

**Antisymmetry** is exactly the condition that makes drawing possible: without it there
would be double arrows and the elements could not be arranged into height levels.

## Examples: divisibility order

The source's standard problem is: "Draw the Hasse diagram of the natural-number
divisors of $n$", with the order $a \leq b :\Longleftrightarrow a \mid b$.

### $28 = 2^2 \cdot 7$

```
        28
       /  \
      4    14
      |   /  \
      2 --    7
       \     /
         \  /
          1
```
Edges: $1-2$, $1-7$, $2-4$, $2-14$, $7-14$, $4-28$, $14-28$.

### $36 = 2^2 \cdot 3^2$

Levels by number of prime factors:
$$1 \;\mid\; 2,\,3 \;\mid\; 4,\,6,\,9 \;\mid\; 12,\,18 \;\mid\; 36$$

### $72 = 2^3 \cdot 3^2$

$$1 \;\mid\; 2,\,3 \;\mid\; 4,\,6,\,9 \;\mid\; 8,\,12,\,18 \;\mid\; 24,\,36 \;\mid\; 72$$

Worked out in detail in [[hasse-diagrams-of-divisors]].

## Properties

- The source starts each of these problems with the **prime factorization**. That is the
  key: if $n = p^a q^b$, the diagram is a grid with $(a+1)\times(b+1)$ nodes — for
  $36 = 2^2 3^2$ a $3\times 3$ grid, for $72 = 2^3 3^2$ a $4 \times 3$ grid. The source
  hints at this "exponent grid" next to the diagram for $36$.
- The number of divisors is thus $(a+1)(b+1)\cdots$ — for $72$ that is $4 \cdot 3 = 12$.

## Related

- [[properties-of-homogeneous-relations]] — antisymmetry as a prerequisite
- [[equivalence-relation]] — the counterpart with symmetry
- [[laws-of-gcd]] — gcd and lcm are infimum and supremum in this order
- [[hasse-diagrams-of-divisors]] — worked-out examples

## Open questions

- Terms such as partial order, total order, maximal/minimal element, supremum/infimum do
  not appear in the source. Whether the module covers them is open.

## Sources

- `raw/relation_und_permutation_das.pdf`, p. 4 ($28$), p. 7 ($36$), p. 13 ($72$)
