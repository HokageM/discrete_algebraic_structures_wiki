---
type: theorem
title: Laws of the Integers
aliases: [laws for integers, Rechenregeln für ganze Zahlen, Z Rechenregeln]
tags: [foundations, algebraic-laws, numbers]
sources: [raw/Rechengesetzte_das.pdf]
created: 2026-09-30
updated: 2026-09-30
status: needs-review
---

# Laws of the integers (ganze Zahlen)

> [!warning] This page contains [[#Contradictions|two suspected typos in the source]].

## Statement

For all integers $a$, $b$ and $c$ the following algebraic laws hold:

**Commutative law**
$$a + b = b + a \qquad a \cdot b = b \cdot a$$

**Associative law**
$$a + (b + c) = (a + b) + c \qquad a \cdot (b \cdot c) = (a \cdot b) \cdot c$$

**Laws for 0 and 1**
$$a + 0 = a \qquad a \cdot 1 = a$$

**Distributive law**
$$a \cdot (b + c) = a \cdot b + a \cdot c \qquad (a + b) \cdot c = a \cdot c + b \cdot c$$

**Cancellation laws**
$$a + b = a + c \;\Rightarrow\; b = c$$
$$a \cdot b = a \cdot c \;\Rightarrow\; b = c, \quad \text{if } a \neq 0$$

## Hypotheses

$a, b, c \in \mathbb{Z}$. For the multiplicative cancellation law, additionally $a \neq 0$.

## Contradictions

The source (p. 4) deviates in two places from the correct version noted above:

1. **Distributive law, second line.** The source writes
   $$(a + b) \cdot c = a \cdot c + a \cdot c$$
   This is a typo: the right side must read $a \cdot c + b \cdot c$. The source's
   version would assert $(a+b)\cdot c = 2ac$. Counterexample $a=1, b=2, c=1$:
   $(1+2)\cdot 1 = 3$, but $a\cdot c + a\cdot c = 1 + 1 = 2$. The parallel page
   [[laws-of-natural-numbers]] states the same rule correctly as
   $(l+m)\cdot n = l\cdot n + m\cdot n$, which confirms the typo.

2. **Laws for 0 and 1.** The source writes
   $$a \cdot 1 = a, \quad \text{if } a \neq 0$$
   The condition $a \neq 0$ is superfluous: $0 \cdot 1 = 0$ is true. The condition
   presumably slipped up from the cancellation law below it, where it belongs.

Both spots have been corrected above. If in doubt, check the original slide.

## Proof idea

The source gives no proofs.

## Application / typical exam problem

- Simplifying terms in $\mathbb{Z}$.
- The cancellation law $a \cdot b = a \cdot c \Rightarrow b = c$ for $a \neq 0$ states
  that $\mathbb{Z}$ has **no zero divisors** (nullteilerfrei). This property is needed
  later for [[laws-of-gcd]] and the polynomial ring.

## Remarks

- Compared to [[laws-of-natural-numbers]], the **laws for 0 and 1** (neutral elements)
  are added here.
- The source does not mention the **additive inverse** $-a$, even though it is the
  actual difference between $\mathbb{Z}$ and $\mathbb{N}$.
- Also not mentioned: that $\mathbb{Z}$ with these laws satisfies exactly the axioms of
  a commutative ring with unity. **→ added:** see [[ring-like-structures]]
  and [[algebraic-structures]]. The cancellation law corresponds to the absence of zero
  divisors, so $\mathbb{Z}$ is an integral domain.

## Related theorems

- [[algebraic-laws]] — overview and comparison of all five domains
- [[laws-of-natural-numbers]] — the same table for $\mathbb{N}$
- [[laws-of-gcd]] — builds on $\mathbb{Z}$
- [[mathematical-induction]] — uses these rules in the term manipulations of the induction step

## Sources

- `raw/Rechengesetzte_das.pdf`, p. 4
