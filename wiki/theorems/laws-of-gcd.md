---
type: theorem
title: Laws of the Greatest Common Divisor
aliases: [gcd laws, laws of the gcd, ggT Rechenregeln, größter gemeinsamer Teiler, greatest common divisor]
tags: [foundations, algebraic-laws, number-theory, gcd]
sources: [raw/Rechengesetzte_das.pdf]
created: 2026-09-30
updated: 2026-09-30
status: solid
---

# Laws of the greatest common divisor (größter gemeinsamer Teiler, ggT)

## Notation

The source writes the greatest common divisor (ggT) of $a$ and $b$ using pair notation
(Paar-Schreibweise)
$$(a, b) := \operatorname{ggT}(a, b).$$
Careful: the same parenthesis notation elsewhere denotes an **ordered pair**. Which
meaning is intended follows only from context.

## Statement

For all integers $a$, $b$ and $c$ the following algebraic laws hold:

**Commutative law**
$$(a, b) = (b, a)$$

**Associative law**
$$(a, (b, c)) = ((a, b), c)$$

**Idempotent law**
$$(a, a) = \lvert a \rvert$$

**Laws for 0 and 1**
$$(0, a) = \lvert a \rvert \qquad (1, a) = 1$$

**Distributive law**
$$a \cdot (b, c) = (ab, ac)$$

**Absolute value law**
$$(a, b) = (\lvert a \rvert, \lvert b \rvert)$$

**Remainder law**
$$(a, b) = (b,\; a \bmod b), \quad b \neq 0$$

## Hypotheses

$a, b, c \in \mathbb{Z}$. For the remainder law, additionally $b \neq 0$.

## Proof idea

The source gives no proofs.

> [!inferred] not from the summaries
> Most rules follow directly from the fact that $(a,b)$ is the largest number dividing
> both $a$ and $b$: commutativity is symmetric in the definition, and the absolute value
> law follows from $d \mid a \iff d \mid -a$.
> The remainder law follows from $a = qb + r$: every common divisor of $a$ and $b$ also
> divides $r = a - qb$ and vice versa, so the sets of divisors coincide.

## Application / typical exam problem

- The **remainder law is the Euclidean algorithm** (Euklidischer Algorithmus): repeatedly
  applying $(a,b) = (b, a \bmod b)$ shrinks the arguments until the second entry becomes
  $0$; then $(0, a) = \lvert a \rvert$ gives the result. The remainder law and the law
  for $0$ together are thus the recursion step and the base case.
- The **absolute value law** allows removing signs in advance.
- $(1, a) = 1$ states that $1$ is coprime (teilerfremd) to every number.

## Remarks

- The gcd is **idempotent, commutative and associative** — it behaves more like $\cap$
  in [[laws-of-sets]] than like $\cdot$ in [[laws-of-integers]]. Fittingly:
  $(a,b)$ is the "greatest common part" of two numbers, just as $A \cap B$ is the
  greatest common part of two sets.
- $\lvert a \rvert$ instead of $a$ in the idempotent and zero laws: the gcd is by
  convention non-negative.
- The source states **no** De Morgan's law and **no** absorption law for the gcd. The
  counterpart to $\cup$ would be the lcm (kgV); the source does not cover it.

> [!inferred] not from the summaries
> Care is needed with the distributive law $a \cdot (b,c) = (ab, ac)$ when $a < 0$: the
> left side then becomes negative, while the right side, being a gcd, stays non-negative.
> The rule in this form is thus meant for $a \geq 0$. Check against the lecture if
> needed.

## Related theorems

- [[algebraic-laws]] — overview and comparison of all five domains
- [[laws-of-integers]] — the underlying arithmetic on $\mathbb{Z}$
- [[computing-inverses]] — the remainder law as the extended Euclidean algorithm
- [[units-and-zero-divisors]] — $\gcd(a,n)=1$ decides invertibility
- [[hasse-diagrams-of-divisors]] — gcd and lcm as infimum/supremum in the divisor lattice

## Sources

- `raw/Rechengesetzte_das.pdf`, p. 5
