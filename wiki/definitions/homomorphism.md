---
type: definition
title: Homomorphism
aliases: [homomorphism, Homomorphismus, isomorphism, Isomorphismus, monomorphism, Monomorphismus, epimorphism, Epimorphismus, endomorphism, Endomorphismus, automorphism, Automorphismus]
tags: [algebraic-structures, homomorphism]
sources: [raw/Algebraische_strukturen_das.pdf]
created: 2026-09-30
updated: 2026-09-30
status: solid
---

# Homomorphism

## Definition

Quote from the source:

> Homomorphisms are structure-preserving maps, i.e. they are compatible with all
> operations of a structure and transport all distinguished elements.

**Monoids.** $\alpha : M \to M'$ between $(M, \circ, e)$ and $(M', \circ', e')$ is a
homomorphism exactly when

  (i) compatibility: $\alpha(x \circ y) = \alpha(x) \circ' \alpha(y)$
  (ii) identity element: $\alpha(e) = e'$.

**Groups.** $\alpha : G \to G'$ between $(G, \circ, e)$ and $(G', \circ', e')$ is a
homomorphism exactly when

  (i) compatibility: $\alpha(x \circ y) = \alpha(x) \circ' \alpha(y)$.

**Rings.** $\alpha : R \to R'$ between $(R, +, \cdot, 0, 1)$ and
$(R', +', \cdot', 0', 1')$ is a homomorphism exactly when

  (i) compatibility with $+$: $\alpha(x + y) = \alpha(x) +' \alpha(y)$
  (ii) compatibility with $\cdot$: $\alpha(x \cdot y) = \alpha(x) \cdot' \alpha(y)$
  (iii) identity element: $\alpha(1) = 1'$.

## The morphism types

A homomorphism $\Phi : A \to B$ is called ___-morphism if it has the following
additional property:

| Name | Additional property |
|---|---|
| **Mono**morphism | injective |
| **Epi**morphism | surjective |
| **Iso**morphism | bijective |
| **Endo**morphism | $A = B$ |
| **Auto**morphism | $A = B$ **and** isomorphism |

## Intuition

A homomorphism translates between two structures without changing the computation: it
does not matter whether you **first combine and then translate** or **first translate
and then combine**.

An isomorphism means: the two structures are "the same thing written differently".

## Why only one condition for groups?

For monoids, $\alpha(e) = e'$ must be **required**; for groups it does **not**.

> [!inferred] not from the summaries
> Reason: in a group, $\alpha(e) = e'$ follows from compatibility, since
> $\alpha(e) = \alpha(e \circ e) = \alpha(e) \circ' \alpha(e)$, and multiplying by
> $\alpha(e)^{-1}$ gives $e' = \alpha(e)$. In a monoid this inverse is missing, so the
> condition is genuinely additional there. The source merely lists the three definitions
> side by side without commenting on the difference.

The same pattern as with [[substructures]]: the stronger the structure, the less needs
to be explicitly required.

## Examples

Worked out in [[homomorphism-proofs]]:

- $\det : \mathbb{Q}^{2\times 2} \to \mathbb{Q}$ is multiplicative, but **not** additive.
- $\alpha : \mathbb{N}_0 \to 2^{\mathbb{N}_0},\; x \mapsto 2^x$ is an **isomorphism** of
  the monoids $(\mathbb{N}_0, +, 0)$ and $(2^{\mathbb{N}_0}, \cdot, 1)$ — addition of
  exponents becomes multiplication of powers.
- The representation of $V_4$ as a permutation group in [[klein-four-group]] is also an
  isomorphism.

## Related

- [[group-like-structures]], [[ring-like-structures]] — source and target structures
- [[substructures]] — the chapter's other standard technique
- [[algebraic-structures]] — overall overview

## Open points

- The source does not treat the **kernel** and **image** of a homomorphism. Check when
  ingesting further sources whether they appear in the module.

## Sources

- `raw/Algebraische_strukturen_das.pdf`, p. 2 and p. 9
