---
type: example
title: Klein Four-Group V₄
aliases: [Klein four-group, V4, Kleinsche Vierergruppe, Vierergruppe]
tags: [algebraic-structures, example, group-theory, permutations]
sources: [raw/Algebraische_strukturen_das.pdf]
created: 2026-09-30
updated: 2026-09-30
status: solid
---

# Klein Four-Group $V_4$

## Problem

(p. 3, problem 4.3) Write the Klein four-group (Kleinsche Vierergruppe)
$V_4 = \{e, a, b, c\}$ as a permutation group (of left multiplications).

## Solution

**Operation table (Verknüpfungstafel) of $V_4$:**

| $\circ$ | $e$ | $a$ | $b$ | $c$ |
|---|---|---|---|---|
| $e$ | $e$ | $a$ | $b$ | $c$ |
| $a$ | $a$ | $e$ | $c$ | $b$ |
| $b$ | $b$ | $c$ | $e$ | $a$ |
| $c$ | $c$ | $b$ | $a$ | $e$ |

Characteristic: **every element is its own inverse** ($x \circ x = e$ for all
$x$), the diagonal consists only of $e$.

**Left multiplication (Linksmultiplikation).** Every $g \in V_4$ gives a map
$\lambda_g : V_4 \to V_4,\; x \mapsto g \circ x$. Reading it off row by row from the
table and writing it as a permutation (Permutation) of the four elements $\{e,a,b,c\}$:

| $g$ | row of the table | as permutation |
|---|---|---|
| $e$ | $e, a, b, c$ | $\mathrm{id}$ |
| $a$ | $a, e, c, b$ | $(e\,a)(b\,c)$ |
| $b$ | $b, c, e, a$ | $(e\,b)(a\,c)$ |
| $c$ | $c, b, a, e$ | $(e\,c)(a\,b)$ |

So
$$V_4 \;\cong\; \bigl\{\mathrm{id},\; (e\,a)(b\,c),\; (e\,b)(a\,c),\; (e\,c)(a\,b)\bigr\}
\;\leq\; S_4.$$

## What it shows

- **Every group can be written as a permutation group.** The construction via the left
  multiplications $\lambda_g$ is precisely the proof of this fact.

> [!inferred] not from the summaries
> This principle is called **Cayley's theorem**. The source does not give the name and
> only poses the problem for $V_4$. The reason it works: $\lambda_g$ is always bijective
> (with inverse $\lambda_{g^{-1}}$), and $g \mapsto \lambda_g$ is an injective
> [[homomorphism|homomorphism]] into the symmetric group.

- Every row of a group table is a **permutation** of the elements — each element occurs
  exactly once in every row and every column (Latin square).
- All three non-trivial permutations are products of two disjoint transpositions, hence
  have order $2$. That reflects $x \circ x = e$.
- $V_4$ is abelian (Abelian, abelsch) (the table is symmetric across the diagonal), see
  [[group-like-structures]].

## Related

- [[subgroup-proofs]] — further permutation groups ($S_3$, $A_n$)
- [[permutation]] — permutations as group elements
- [[homomorphism]] — $g \mapsto \lambda_g$ is an isomorphism onto its image

## Sources

- `raw/Algebraische_strukturen_das.pdf`, p. 3 (problem 4.3)
