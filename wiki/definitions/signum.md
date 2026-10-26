---
type: definition
title: Signum of a Permutation
aliases: [signum, sgn, sign of a permutation, Vorzeichen, Signum einer Permutation]
tags: [permutations]
sources: [raw/relation_und_permutation_das.pdf]
created: 2026-09-30
updated: 2026-09-30
status: solid
---

# Signum of a Permutation

## Definition

Rules from the source:

- If $\sigma$ is a product of $n$ **transpositions** (2-cycles), then
  $$\operatorname{sgn}(\sigma) = (-1)^{n}.$$
- If $\tau$ consists of **one** $m$-cycle, then
  $$\operatorname{sgn}(\tau) = (-1)^{m-1}.$$
- **Product rule**:
  $$\operatorname{sgn}(\pi \cdot \tau) = \operatorname{sgn}(\pi)\cdot\operatorname{sgn}(\tau)$$

**Rule of thumb from the source:** "length of a cycle minus 1, and that goes into the
exponent of $-1$."

The reason for the second rule is also given in the source: an $m$-cycle decomposes into
$m-1$ transpositions,
$$\tau = (x_1 x_2 x_3 \dots x_m) = (x_1 x_2)(x_2 x_3)\cdots(x_{m-1} x_m).$$

## Computation procedure

For a permutation in cycle notation:

1. Consider each cycle individually, read off its length $m_i$.
2. Signum per cycle: $(-1)^{m_i - 1}$.
3. Multiply everything: $\operatorname{sgn} = \prod_i (-1)^{m_i-1} = (-1)^{\sum_i (m_i - 1)}$.

In short: **sum of all (cycle length $-1$)**, then $(-1)$ raised to this number.

## Examples

$\tau = (1\,9\,8\,7)(2\,3\,4)$: a 4-cycle and a 3-cycle
$$\operatorname{sgn}(\tau) = (-1)^{4-1}\cdot(-1)^{3-1} = (-1)^3 \cdot (-1)^2 = -1$$

$\tau = (2\,1\,3)(4\,7)(5\,6)$: a 3-cycle and two 2-cycles
$$\operatorname{sgn}(\tau) = (-1)^{3-1}\cdot(-1)^{2-1}\cdot(-1)^{2-1} = (+1)(-1)(-1) = +1$$

$\tau = (1\,2)(3\,4)(5\,6)(7\,8)$: four transpositions
$$\operatorname{sgn}(\tau) = (-1)^4 = +1$$

More in [[computing-with-permutations]].

## Properties

- $\operatorname{sgn}(\pi^{-1}) = \operatorname{sgn}(\pi)$ — the source verifies this on
  an example. Clear, since inverting does not change the cycle lengths.
- The product rule states that $\operatorname{sgn} : S_n \to \{+1,-1\}$ is a
  [[homomorphism]] of groups.
- Permutations with $\operatorname{sgn} = +1$ are called **even** and form the
  alternating group
  $$A_n = \{\pi \in S_n \mid \operatorname{sgn}(\pi) = 1\},$$
  whose subgroup property is proven in [[subgroup-proofs]] using exactly the product
  rule.

## Pitfall

The first rule of the source, $\operatorname{sgn}(\sigma) = (-1)^n$ for $n$
transpositions, and the second, $(-1)^{m-1}$ for an $m$-cycle, are **the same
statement** — an $m$-cycle *is* a product of $m-1$ transpositions. Both must not be
applied simultaneously to the same cycle.

In particular: a 2-cycle has $\operatorname{sgn} = (-1)^{2-1} = -1$, not $+1$.

## Related

- [[permutation]] — cycle notation and two-line notation
- [[computing-with-permutations]] — worked-out exercises
- [[subgroup-proofs]] — $A_n \leq S_n$
- [[homomorphism]] — $\operatorname{sgn}$ as a group homomorphism

## Sources

- `raw/relation_und_permutation_das.pdf`, p. 1 and p. 15
