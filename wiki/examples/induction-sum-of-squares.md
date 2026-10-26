---
type: example
title: Induction — Sum of Squares
aliases: [sum of squares induction, Induktion Summe der Quadratzahlen]
tags: [induction, summation-formula, example]
sources: [raw/Induktion_das.pdf]
created: 2026-09-30
updated: 2026-09-30
status: solid
---

# Induction — Sum of Squares

## Problem

Tutorial 1a): Show for $n \geq 1$:
$$1^2 + 2^2 + 3^2 + \dots + n^2 = \frac{n(n+1)(2n+1)}{6}.$$

## Solution

**Base case** (Induktionsanfang) $n = 1$:
$$1^2 = 1 = \frac{1 \cdot (1+1) \cdot (2 \cdot 1 + 1)}{6} = \frac{1 \cdot 2 \cdot 3}{6} = 1 \quad ✓$$

**Induction hypothesis** (Induktionsvoraussetzung): For some fixed $n \geq 1$, assume
$\displaystyle\sum_{i=1}^{n} i^2 = \frac{n(n+1)(2n+1)}{6}$.

**Induction step** (Induktionsschluss) $n \mapsto n+1$:
$$\sum_{i=1}^{n+1} i^2 = \frac{n(n+1)(2n+1)}{6} + (n+1)^2$$

We must show that this equals $\frac{(n+1)(n+2)(2n+3)}{6}$:
$$\frac{n(n+1)(2n+1)}{6} + \frac{6(n+1)^2}{6} = \frac{(n+1)(n+2)(2n+3)}{6} \qquad \Big| \cdot 6$$
$$n(n+1)(2n+1) + 6(n+1)^2 = (n+1)(n+2)(2n+3)$$
$$(n^2+n)(2n+1) + 6(n^2+2n+1) = (n^2+3n+2)(2n+3)$$
$$2n^3 + n^2 + 2n^2 + n + 6n^2 + 12n + 6 = 2n^3 + 3n^2 + 6n^2 + 9n + 4n + 6$$
$$2n^3 + 9n^2 + 13n + 6 = 2n^3 + 9n^2 + 13n + 6 \quad ✓$$

$\square$

## What it shows

- **Technique: multiply through by the denominator (durchmultiplizieren).** Instead of
  computing with fractions, the whole equation is multiplied by $6$; after that it's pure
  polynomial arithmetic. That is the cleaner route compared to
  [[induction-sum-of-odd-squares]], where the computation continues with thirds.
- The right-hand side for $n+1$ arises by substitution: $\frac{(n+1)\bigl((n+1)+1\bigr)\bigl(2(n+1)+1\bigr)}{6} = \frac{(n+1)(n+2)(2n+3)}{6}$.
  Performing this substitution *first* and then working toward equality is the usual
  structure.
- Scheme: see [[mathematical-induction]].

## Sources

- `raw/Induktion_das.pdf`, p. 3 (tutorial 1a, handwritten)
