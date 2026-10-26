---
type: definition
title: Properties of homogeneous relations
aliases: [reflexive, reflexivity, Reflexivität, transitive, transitivity, Transitivität, symmetric, symmetry, Symmetrie, antisymmetric, antisymmetry, Antisymmetrie]
tags: [relations, foundations]
sources: [raw/relation_und_permutation_das.pdf]
created: 2026-09-30
updated: 2026-09-30
status: solid
---

# Properties of homogeneous relations

## Definition

Let $\rho$ be a homogeneous [[relation|relation]] (*Relation*) on $A$.

| Property | Formal | On the digraph |
|---|---|---|
| **Reflexivity** (*Reflexivität*) | $\forall x \in A\,[\,x \rho x\,]$ | **every** node has a loop $\circlearrowright$ |
| **Transitivity** (*Transitivität*) | $\forall x,y,z \in A\,[\,x\rho y \wedge y \rho z \Rightarrow x \rho z\,]$ | every **path of length 2** has its shortcut |
| **Symmetry** (*Symmetrie*) | $\forall x,y \in A\,[\,x \rho y \Rightarrow y \rho x\,]$ | all arrows are double arrows $\leftrightarrow$ |
| **Antisymmetry** (*Antisymmetrie*) | $\forall x,y \in A\,[\,x \rho y \wedge y \rho x \Rightarrow x = y\,]$ | **no** double arrows (loops are allowed) |

The mnemonics in the right column are from the source.

## Intuition

All four properties are checked on the **digraph**, not on the list of pairs:

- *reflexive?* If a loop is missing anywhere, it's already over.
- *transitive?* Go through every path $x \to y \to z$ and check whether $x \to z$ exists.
- *symmetric?* If there is a one-sided arrow, it is not symmetric.
- *antisymmetric?* If there is a double arrow between **different** nodes, it is not
  antisymmetric.

## Examples

$R = \{(1,2),(1,3),(2,4),(1,4)\}$ on $\{1,2,3,4\}$:

| | | Reasoning from the source |
|---|---|---|
| reflexive | ✗ | $\neg\, 1R1$ |
| transitive | ✓ | only path of length 2: $1R2 \wedge 2R4 \Rightarrow 1R4$ ✓ |
| symmetric | ✗ | $1R2$, but $\neg\, 2R1$ |
| antisymmetric | ✓ | only single arrows |

All further worked-out cases: [[checking-relation-properties]].

## Counterexamples and pitfalls

- **Symmetry and antisymmetry are not mutually exclusive.** The empty relation and the
  pure equality relation are both.
- **Symmetry + transitivity $\neq$ reflexivity.** The source (Ü3.2) shows
  $S = \{(1,4),(2,1),(2,3),(3,2),(4,1)\}$: symmetric, but not transitive, because
  $1R4 \wedge 4R1$ holds while $1R1$ is missing.
- **Vacuous premise.** For $R = \{(1,2)\}$, transitivity holds because there is *no*
  path of length 2 — the implication is vacuously true. In the source (p. 10) "No" is
  first written here, then crossed out and corrected to "Yes". A classic mistake.

## Related

- [[relation]] — basic concept and digraph
- [[equivalence-relation]] — reflexive + transitive + symmetric
- [[hasse-diagram]] — the counterpart: reflexive + transitive + antisymmetric (order)
- [[checking-relation-properties]] — worked-out examples

## Sources

- `raw/relation_und_permutation_das.pdf`, p. 3, p. 10, p. 11
