---
type: example
title: Induction — Sum of Odd Squares
aliases: [sum of odd squares induction, Induktion Summe der ungeraden Quadratzahlen]
tags: [induction, summation-formula, example]
sources: [raw/Induktion_das.pdf]
created: 2026-09-30
updated: 2026-09-30
status: solid
---

# Induction — Sum of Odd Squares

## Problem

Show that for all natural numbers $n \geq 1$:
$$\sum_{k=1}^{n} (2k-1)^2 = \frac{n}{3}\left(4n^2 - 1\right).$$

Use mathematical induction (vollständige Induktion). [6 points]

## Solution

**Base case** (Induktionsanfang) $n = 1$:
$$(2 \cdot 1 - 1)^2 = \tfrac{1}{3}(4 \cdot 1 - 1) \;\Longleftrightarrow\; 1 = 1 \quad ✓$$

**Induction hypothesis** (Induktionsvoraussetzung): For some fixed $n \geq 1$, assume
$$\sum_{k=1}^{n} (2k-1)^2 = \frac{n}{3}(4n^2 - 1).$$

**Induction step** (Induktionsschluss) $n \mapsto n+1$: We must show
$$\sum_{k=1}^{n+1} (2k-1)^2 = \frac{n+1}{3}\left(4(n+1)^2 - 1\right).$$

Split the sum into the sum up to $n$ plus the term for $k = n+1$; apply the hypothesis
to the sum up to $n$:
$$\frac{n}{3}(4n^2-1) + \bigl(2(n+1)-1\bigr)^2 \;=\; \frac{n+1}{3}\left(4(n^2+2n+1) - 1\right)$$
$$\frac{n}{3}(4n^2-1) + (2n+1)^2 \;=\; \frac{n+1}{3}\left(4n^2 + 8n + 3\right)$$

Multiply out both sides:
$$\frac{4}{3}n^3 - \frac{n}{3} + 4n^2 + 4n + 1 \;=\; \frac{4}{3}n^3 + \frac{4}{3}n^2 + \frac{8}{3}n^2 + \frac{8}{3}n + n + 1$$

$\frac{4}{3}n^3$ and $+1$ appear on both sides and cancel:
$$4n^2 + \frac{11}{3}n \;=\; \frac{12}{3}n^2 + \frac{11}{3}n \quad ✓$$

(on the right-hand side, $\frac{4}{3}n^2 + \frac{8}{3}n^2 = \frac{12}{3}n^2 = 4n^2$ and
$\frac{8}{3}n + n = \frac{11}{3}n$; on the left, $-\frac{n}{3} + 4n = \frac{11}{3}n$).

So the claim holds for $n+1$, and the induction is complete. $\square$

## What it shows

- A standard case of a **summation formula** (Summenformel) following the scheme from
  [[mathematical-induction]].
- The only place the hypothesis is used is replacing $\sum_{k=1}^{n}(2k-1)^2$ by
  $\frac{n}{3}(4n^2-1)$. Everything afterward is term manipulation per
  [[laws-of-integers]].
- Technique: multiply out both sides completely and cancel identical terms, rather than
  trying to "derive" the right-hand side directly.
- Compare [[induction-sum-of-squares]] — there, one instead multiplies through by the
  denominator $6$, which avoids working with fractions.

## Sources

- `raw/Induktion_das.pdf`, p. 1 (exam problem 1 with handwritten solution)
