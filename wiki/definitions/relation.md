---
type: definition
title: Relation
aliases: [relation, Relation, homogeneous relation, homogene Relation, composition of relations, Relationsprodukt, inverse relation, inverse Relation, digraph, Digraph]
tags: [relations, foundations]
sources: [raw/relation_und_permutation_das.pdf]
created: 2026-09-30
updated: 2026-09-30
status: solid
---

# Relation

## Definition

A **homogeneous relation** (*homogene Relation*) on a set $A$ is a subset
$$\rho \subseteq A \times A = A^2.$$
Instead of $(x,y) \in \rho$ one writes $x \rho y$ or $xRy$.

**Composition of relations** (*Relationsprodukt*). For relations $R$ and $S$ on $A$:
$$R \circ S = \{(a,c) \mid \exists b\, [\,(a,b) \in R \;\wedge\; (b,c) \in S\,]\}$$

**Inverse relation** (*inverse Relation*).
$$R^{-1} = \{(b,a) \mid (a,b) \in R\}$$

## Intuition

A relation is a list of arrows. It is represented as a **digraph** (directed graph):
the elements of $A$ are nodes, and for every pair $(x,y) \in \rho$ an arrow $x \to y$ is
drawn. Pairs $(x,x)$ become loops.

The composition $R \circ S$ contains exactly the **paths of length 2**: first an arrow
from $R$, then an arrow from $S$. The inverse relation reverses all arrows.

The digraph is the working tool of the chapter — the
[[properties-of-homogeneous-relations|four properties]] can all be read directly off the
picture.

## Examples

On $A = \{a,b,c\}$ with
$R = \{(a,a),(a,b),(a,c),(b,b),(b,c)\}$ and $S = \{(c,b),(b,a),(b,c)\}$:
$$R \circ S = \{(a,a),(a,b),(a,c),(b,a),(b,b),(b,c)\}$$

More worked-out cases in [[checking-relation-properties]].

## Properties

- Composition of relations is **not commutative**: $R \circ S \neq S \circ R$ in general.
- Important special cases of relations:
  [[equivalence-relation|equivalence relations]] (reflexive + transitive + symmetric) and
  orders (reflexive + transitive + antisymmetric), depicted in the
  [[hasse-diagram]].

## Related

- [[properties-of-homogeneous-relations]] — reflexivity, transitivity, symmetry, antisymmetry
- [[equivalence-relation]] — equivalence classes and quotient set
- [[hasse-diagram]] — representation of order relations
- [[checking-relation-properties]] — worked-out examples

## Open questions

- **Heterogeneous** relations $\rho \subseteq A \times B$ are only implicitly hinted at
  in the source via composition; a definition is missing.
- The source denotes relations sometimes with $\rho$, sometimes with $R$ — both mean the
  same thing.

## Sources

- `raw/relation_und_permutation_das.pdf`, p. 3, p. 9, p. 11
