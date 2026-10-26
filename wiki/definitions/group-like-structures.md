---
type: definition
title: Group-like structures
aliases: [group-like structures, Gruppenartige Strukturen, semigroup, Halbgruppe, monoid, Monoid, group, Gruppe, abelian group, abelsche Gruppe]
tags: [algebraic-structures, group-theory]
sources: [raw/Algebraische_strukturen_das.pdf]
created: 2026-09-30
updated: 2026-09-30
status: solid
---

# Group-like structures $(G, \circ)$

## Definition

A set $G$ with **one** operation (*Verknüpfung*) $\circ$ is called, depending on which of
the [[properties-of-operations|properties]] hold:

| $(G,\circ)$ | closed | associative | identity $e$ | inverses | commutative |
|---|:---:|:---:|:---:|:---:|:---:|
| **semigroup** (*Halbgruppe*) | ✓ | ✓ | – | – | – |
| **monoid** (*Monoid*) | ✓ | ✓ | ✓ | – | – |
| **commutative monoid** | ✓ | ✓ | ✓ | – | ✓ |
| **group** (*Gruppe*) | ✓ | ✓ | ✓ | ✓ | – |
| **abelian group** (*abelsche Gruppe*) | ✓ | ✓ | ✓ | ✓ | ✓ |

("–" means: not required, but may hold.)

The table is **cumulative from top to bottom**: each row requires everything from the
row above plus one more property.
$$\text{semigroup} \supset \text{monoid} \supset \text{group} \supset \text{abelian group}$$

## Intuition

The structure is built property by property:

- **Semigroup**: you may compute and re-parenthesize, nothing more.
- **Monoid**: there is a "do-nothing" element $e$.
- **Group**: every operation is invertible — you can "compute backwards".
- **Abelian group**: additionally you may reorder freely.

The notation $(M, \circ, e)$ with the identity element given is common in the source,
e.g. $(\mathbb{N}_0, +, 0)$ or $(\mathbb{Q}^*, \cdot, 1)$.

## Examples

| Structure | Example from the source |
|---|---|
| Monoid | $(\mathbb{N}_0, +, 0)$ — no inverse, since $-n \notin \mathbb{N}_0$ |
| Monoid | $(\mathbb{Q}, \cdot, 1)$ — $0$ has no inverse |
| Monoid | $\left(\left\{\tfrac{a}{2^i} \mid a \in \mathbb{Z}, i \in \mathbb{N}_0\right\}, \cdot, 1\right)$, see [[submonoid-proofs]] |
| Group | $(\mathbb{Z}, +, 0)$ |
| Group | $(\mathbb{Q}^*, \cdot, 1)$ with $\mathbb{Q}^* = \mathbb{Q} \setminus \{0\}$ |
| Group | $S_n$, the symmetric group; $A_n$, the alternating group — see [[subgroup-proofs]] |
| Group | Klein four-group $V_4$ — see [[klein-four-group]] |

## Counterexamples

- $(\mathbb{N}_0, +, 0)$ is **not** a group: no additive inverse.
- $(\mathbb{Q}, \cdot, 1)$ is **not** a group: $0$ is not invertible. Only
  $\mathbb{Q}^* = \mathbb{Q}\setminus\{0\}$ is a group.
- $\left(\left\{\tfrac{a}{2^i}\right\}, \cdot, 1\right)$ is a monoid but not a group —
  only the elements with numerator $\pm 2^k$ are invertible. Worked out in
  [[submonoid-proofs]].
- $(\mathbb{R}, -)$ is not even a semigroup (subtraction is not associative), see
  [[checking-properties-of-operations]].

## Properties

- The usual proof "$X$ is a group" is rarely carried out directly. Instead one shows
  that $X$ is a **substructure** (*Unterstruktur*) of a known structure — see
  [[substructures]]. That is much shorter.
- The operation is written multiplicatively ($\cdot$, inverse $x^{-1}$) or additively
  ($+$, inverse $-x$) in the source; the structure is the same.

## Related

- [[properties-of-operations]] — the five building blocks of this table
- [[ring-like-structures]] — structures with **two** operations
- [[substructures]] — submonoid, subgroup
- [[permutation]] — $S_n$ as the most important example of a non-abelian group
- [[homomorphism]] — structure-preserving maps between these structures
- [[algebraic-structures]] — overall overview

## Sources

- `raw/Algebraische_strukturen_das.pdf`, p. 1 and p. 11 (overview table)
