---
type: definition
title: Substructures
aliases: [substructures, Unterstrukturen, submonoid, Untermonoid, subgroup, Untergruppe, subring, Unterring]
tags: [algebraic-structures, substructures]
sources: [raw/Algebraische_strukturen_das.pdf]
created: 2026-09-30
updated: 2026-09-30
status: solid
---

# Substructures

## Definition

Let $U \subseteq X$ be a **nonempty** subset of an algebraic structure $X$.

**Submonoid.** Let $(M, \circ)$ be a monoid. Then $(U, \circ)$ is a submonoid exactly
if

  (i) $\circ$ is closed in $U$
  (ii) the identity element $e_M \in U$.

**Subgroup.** Let $(G, \cdot)$ be a group. Then $(U, \cdot)$ is a subgroup exactly if

  (i) $\cdot$ is closed in $U$
  (ii) $(\,)^{-1}$ is closed in $U$.

**Subring.** Let $(R, +, \cdot)$ be a ring. Then $(U, +, \cdot)$ is a subring exactly if

  (i) $+$ and $-$ are closed in $U$
  (ii) $\cdot$ is closed in $U$
  (iii) the identity element $1_R \in U$.

## Intuition

Quote from the source:

> A main purpose of substructures is to make it easier to show whether something is a
> particular algebraic structure. They are closed under all operations and contain all
> distinguished elements of their overstructure, from which they then "inherit" the
> remaining properties.

That is the actual point: **associativity and commutativity do not need to be shown
again**, they are inherited from the overstructure. Only the two or three closure and
existence conditions remain.

## The checking scheme

Every proof in the source follows the same pattern:

```
Given: U ⊆ X, overstructure X known
(i)   Closure: take two arbitrary elements of U in general form, combine them,
      and show the result again has the form of U.
(ii)  Distinguished element or inverse: verify it lies in U.
⇒ U is a substructure, inherits the rest.
```

Example [[submonoid-proofs|($U = \{3n\}$ in $(\mathbb{N}_0,+,0)$)]]:
$3n + 3m = 3(n+m) \in U$ ✓ and $0 = 3 \cdot 0 \in U$ ✓.

## Why different conditions?

| Structure | required | why nothing more? |
|---|---|---|
| Submonoid | closure + $e \in U$ | inverses do not exist in a monoid anyway |
| Subgroup | closure + inverses | $e \in U$ follows from it: $x \in U \Rightarrow x^{-1} \in U \Rightarrow x \circ x^{-1} = e \in U$ (here $U \neq \emptyset$ is needed!) |
| Subring | $+,-,\cdot$ closed + $1 \in U$ | $-$ closed replaces the requirement of additive inverses; $0 \in U$ follows |

> [!inferred] not from the summaries
> The justification for why $e \in U$ need not be required for the subgroup (and why
> $U \neq \emptyset$ is indispensable for it) is not in the source.

## Examples

All worked-out proofs:

- [[submonoid-proofs]] — $\{3n\}$, $\left\{\tfrac{a}{4^i}\right\}$, $\left\{\tfrac{a}{2^i}\right\}$, idempotent elements
- [[subgroup-proofs]] — $\{1,-1\}$, even numbers, $A_n$, rotations of the triangle

## Counterexamples

- $\left(\left\{\tfrac{a}{2^i}\right\}, \cdot, 1\right)$ is a submonoid of
  $(\mathbb{Q}, \cdot, 1)$, but **not** a subgroup — condition (ii) fails.

## Related

- [[group-like-structures]], [[ring-like-structures]] — the overstructures
- [[properties-of-operations]] — what exactly is inherited
- [[homomorphism]] — the other standard technique of this chapter
- [[algebraic-structures]] — overall overview

## Sources

- `raw/Algebraische_strukturen_das.pdf`, p. 2 and p. 7
