---
type: concept
title: Mathematical Induction
aliases: [mathematical induction, Vollständige Induktion, Induktion]
tags: [foundations, proof-method, induction]
sources: [raw/Induktion_das.pdf]
created: 2026-09-30
updated: 2026-09-30
status: solid
---

# Mathematical Induction

## Core idea

A proof method for statements of the form "for all natural numbers $n \geq n_0$, $A(n)$
holds". Instead of checking infinitely many individual statements, two things are shown:

1. **Base case** (*Induktionsanfang*): $A(n_0)$ is true.
2. **Induction step** (*Induktionsschluss*): $A(n)$ implies $A(n+1)$, for every
   $n \geq n_0$.

The assumption $A(n)$ used in the step is called the **induction hypothesis**
(*Induktionsvoraussetzung*, abbreviated "Vor." in the sources). Together this yields a
chain $A(n_0) \Rightarrow A(n_0+1) \Rightarrow A(n_0+2) \Rightarrow \dots$ that reaches
every number $\geq n_0$.

## Connections

### Scheme of an induction proof

This is how all solutions in the source are structured:

```
Base case:              plug in n = n_0, evaluate both sides, equality ✓
Induction hypothesis:    A(n) holds for some fixed n ≥ n_0
Induction step:          n ↦ n+1
                         write down the claim A(n+1)
                         split the left side into "sum up to n" + "(n+1)-th term"
                         apply the hypothesis to the sum up to n
                         rearrange algebraically until the right side of A(n+1) appears
```

The decisive step is always the same: **splitting off the sum**
$$\sum_{k=1}^{n+1} a_k \;=\; \underbrace{\sum_{k=1}^{n} a_k}_{\text{apply the hypothesis}} \;+\; a_{n+1}$$
The induction hypothesis only enters at this single point. After that it's pure term
rearrangement, using the rules from [[laws-of-integers]].

### Two types of claims

| Type | Example pages | Special feature in the induction step |
|---|---|---|
| **Sum formula** (equation) | [[induction-sum-of-odd-squares]], [[induction-sum-of-squares]], [[induction-telescoping-sum]] | equivalence transformation; for fractions often multiplied through by the denominator |
| **Inequality** | [[induction-2n-geq-n-squared]], [[induction-factorial-geq-2n]] | estimating instead of rearranging; usually an **auxiliary inequality** is needed that only holds for sufficiently large $n$ |

### The base case is not always $n = 1$

For inequalities, induction often only starts at $n_0 = 4$, because the statement is
simply false for smaller $n$. In [[induction-2n-geq-n-squared]], $2^n \geq n^2$ is false
for $n = 3$ ($8 < 9$), but true from $n = 4$ on. So the base case fixes from where the
statement holds — it is not a mere formality.

### Auxiliary inequalities

In inequality proofs, a side calculation is carried out in the margin during the step,
e.g. $n^2 \geq 2n+1$ for $n \geq 4$ or $n+1 \geq 2$ for $n \geq 4$. These auxiliary
statements are the actual reason the bound $n_0$ has to be chosen the way it is.

## Examples in the wiki

- [[induction-sum-of-odd-squares]] — $\sum_{k=1}^n (2k-1)^2 = \frac{n}{3}(4n^2-1)$
- [[induction-sum-of-squares]] — $\sum_{i=1}^n i^2 = \frac{n(n+1)(2n+1)}{6}$
- [[induction-telescoping-sum]] — $\sum_{k=1}^n \frac{1}{(2k-1)(2k+1)} = \frac{n}{2n+1}$
- [[induction-2n-geq-n-squared]] — $2^n \geq n^2$ for $n \geq 4$
- [[induction-factorial-geq-2n]] — $n! \geq 2^n$ for $n \geq 4$

## Open questions

- The source contains **no** definition or justification of induction itself, only worked
  problems. Where the principle is introduced (Peano axioms? well-ordering principle?) is
  still open.
- **Strong induction** (*starke Induktion*, hypothesis for all $m \leq n$ instead of just
  $n$) does not appear in the source. Whether the module covers it is to be clarified —
  it is typically needed for the existence of prime factorization.
- The computation rules used during rearrangement are in [[laws-of-natural-numbers]];
  whether, conversely, those rules are proven by induction in the module is still open.

## Sources

- `raw/Induktion_das.pdf`, p. 1–4 (exam/exercise problems with handwritten solutions)
