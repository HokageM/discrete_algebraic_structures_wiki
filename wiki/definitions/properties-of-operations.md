---
type: definition
title: Properties of Operations
aliases: [properties of operations, Eigenschaften von Verknüpfungen, operation, binary operation, Verknüpfung, Operation, binäre Operation]
tags: [algebraic-structures, foundations]
sources: [raw/Algebraische_strukturen_das.pdf]
created: 2026-09-30
updated: 2026-09-30
status: solid
---

# Properties of Operations

## Definition

Let $\circ : X \times X \to X$ be an operation (*Verknüpfung*) on a set $X$ and let
$x, y, z \in X$. One distinguishes the following properties:

| Property | Condition |
|---|---|
| **Closure** (*Abgeschlossenheit*) | $x \circ y \in X$ |
| **Associativity** (*Assoziativität*) | $(x \circ y) \circ z = x \circ (y \circ z)$ |
| **identity element** (*neutrales Element*) | $\exists\, e \in X:\; x \circ e = x = e \circ x$ |
| **existence of inverses** (*Existenz von Inversen*) | $\exists\, x' \in X:\; x \circ x' = e = x' \circ x$ |
| **Commutativity** (*Kommutativität*) | $x \circ y = y \circ x$ |

These five properties are the **building blocks** from which all algebraic structures
are composed — see [[group-like-structures]] and [[ring-like-structures]].

## Intuition

For a given operation, these five questions are asked systematically. The more of them
answered "yes", the stronger the structure and the more theorems become available.

The order is not arbitrary: **inverses presuppose an identity element** (it appears
in the condition as $e$), and an identity element is only meaningful for a closed
operation. That is why the table in [[group-like-structures]] is built up from left to
right.

## Examples

All worked-out checks can be found in
[[checking-properties-of-operations]]. Summary:

| Operation on | $x \circ y$ | associative | commutative |
|---|---|:---:|:---:|
| $\mathbb{R}$ | $x + y$ | ✓ | ✓ |
| $\mathbb{R}$ | $x - y$ | ✗ | ✗ |
| $\mathbb{R}$ | $x^y$ | ✗ | ✗ |
| $\mathbb{R}$ | $e^{x+y}$ | ✗ | ✓ |
| $\mathbb{Q}$, $\mathbb{R}$ | $\tfrac{1}{2}xy$ | ✓ | ✓ |
| $\mathbb{Z}$ | $x + y + 1$ | ✓ | ✓ |

## Counterexamples

- $x \circ y = x - y$ on $\mathbb{R}$: neither associative nor commutative — the
  standard counterexample.
- $x \circ y = e^{x+y}$: commutative but **not** associative. Shows that the
  properties are independent of each other; commutativity does not imply associativity.

## Properties

- Associativity allows parentheses to be dropped: $x \circ y \circ z$ is unambiguous.
- If the operation is associative **and** commutative, terms may be reordered and
  regrouped arbitrarily. This is exactly what is recorded in [[laws-of-integers]] for
  $+$ and $\cdot$.
- The identity element, if it exists, is unique.

> [!inferred] not from the summaries
> The uniqueness of the identity element is not stated in the source. Proof: if $e, e'$
> are both identities, then $e = e \circ e' = e'$.

## Related

- [[group-like-structures]] — semigroup, monoid, group, abelian group
- [[ring-like-structures]] — ring, integral domain, field
- [[algebraic-laws]] — the same properties concretely for logic, sets, and numbers
- [[checking-properties-of-operations]] — worked-out checks

## Sources

- `raw/Algebraische_strukturen_das.pdf`, p. 1 and p. 11
