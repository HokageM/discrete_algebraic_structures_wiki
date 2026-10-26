---
type: theorem
title: Laws of the Natural Numbers
aliases: [laws for natural numbers, Rechenregeln für natürliche Zahlen, N Rechenregeln]
tags: [foundations, algebraic-laws, numbers]
sources: [raw/Rechengesetzte_das.pdf]
created: 2026-09-30
updated: 2026-09-30
status: solid
---

# Laws of the natural numbers (natürliche Zahlen)

## Statement

For all natural numbers $l$, $m$ and $n$ the following algebraic laws hold:

**Commutative law**
$$m + n = n + m \qquad m \cdot n = n \cdot m$$

**Associative law**
$$l + (m + n) = (l + m) + n \qquad l \cdot (m \cdot n) = (l \cdot m) \cdot n$$

**Distributive law**
$$l \cdot (m + n) = l \cdot m + l \cdot n \qquad (l + m) \cdot n = l \cdot n + m \cdot n$$

**Cancellation laws**
$$l + m = l + n \;\Rightarrow\; m = n$$
$$l \cdot m = l \cdot n \;\Rightarrow\; m = n, \quad \text{if } l \neq 0$$

## Hypotheses

$l, m, n \in \mathbb{N}$. For the multiplicative cancellation law, additionally
$l \neq 0$ — without this condition it would be false, since $0 \cdot 3 = 0 \cdot 5$,
but $3 \neq 5$.

## Proof idea

The source gives no proofs.

> [!inferred] not from the summaries
> On $\mathbb{N}$ these laws are usually proved from the Peano axioms via
> **mathematical induction** (vollständige Induktion). When ingesting `Induktion_das.pdf`,
> check whether the module takes this route.

## Application / typical exam problem

- Rearranging and simplifying terms.
- The cancellation laws are the usual step for eliminating a factor or summand in an
  equation — the condition $l \neq 0$ must be checked explicitly.

## Remarks

- **No idempotent law, no absorption, no De Morgan.** This is the central difference to
  [[laws-of-propositional-logic]] and [[laws-of-sets]]: $2 + 2 \neq 2$.
- **Distributivity only in one direction**: $\cdot$ distributes over $+$, but $+$ does
  not distribute over $\cdot$. The source lists both variants (left- and
  right-distributive) separately, which is strictly redundant given commutative
  multiplication.
- **No additive inverse**: there is no subtraction on $\mathbb{N}$. $(\mathbb{N}_0, +, 0)$
  is thus only a commutative monoid, not a group — see [[group-like-structures]].
  This is exactly what changes in the transition to $\mathbb{Z}$ — see
  [[laws-of-integers]].
- The source lists **no** laws for $0$ and $1$ here, although they are listed for
  $\mathbb{Z}$.

## Related theorems

- [[algebraic-laws]] — overview and comparison of all five domains
- [[laws-of-integers]] — the same table for $\mathbb{Z}$, with laws for $0$ and $1$
- [[mathematical-induction]] — proof method for statements about $\mathbb{N}$; uses these rules when rearranging terms

## Sources

- `raw/Rechengesetzte_das.pdf`, p. 3
