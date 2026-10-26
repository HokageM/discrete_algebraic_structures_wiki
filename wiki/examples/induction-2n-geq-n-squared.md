---
type: example
title: Induction — 2^n ≥ n² for n ≥ 4
aliases: [2^n >= n^2 induction, Induktion 2^n >= n^2, inequality induction]
tags: [induction, inequality, example]
sources: [raw/Induktion_das.pdf]
created: 2026-09-30
updated: 2026-09-30
status: solid
---

# Induction — $2^n \geq n^2$ for $n \geq 4$

## Problem

Tutorial 3a): Show for all $n \geq 4$:
$$2^n \geq n^2.$$

## Solution

**Base case** (Induktionsanfang) $n = 4$:
$$2^4 \geq 4^2 \;\Longleftrightarrow\; 16 \geq 16 \quad ✓$$

**Induction hypothesis** (Induktionsvoraussetzung): For some fixed $n \geq 4$, assume $2^n \geq n^2$.

**Induction step** (Induktionsschluss) $n \mapsto n+1$: We must show $2^{n+1} \geq (n+1)^2 = n^2 + 2n + 1$.

$$2^{n+1} = 2 \cdot 2^n \;\overset{\text{IH}}{\geq}\; 2n^2 = n^2 + n^2$$

**Auxiliary inequality** (Hilfsungleichung, side computation in the source's margin):
$n^2 \geq 2n + 1$ for $n \geq 4$. Hence:
$$2 \cdot 2^n \;\geq\; n^2 + n^2 \;\geq\; n^2 + 2n + 1 = (n+1)^2$$
so
$$2^{n+1} \geq (n+1)^2. \qquad \square$$

## What it shows

- **Inequalities instead of equalities**: Instead of rearranging to equality, one
  **estimates**. The chain may only run in one direction; every step must be a $\geq$.
- The trick: write $2 \cdot 2^n$ as $n^2 + n^2$ and estimate the second summand against
  $2n+1$. Splitting the factor $2$ into "once for the hypothesis, once in reserve for the
  estimate" is the recurring pattern.
- **Why $n_0 = 4$?** The claim is false for $n = 3$: $2^3 = 8 < 9 = 3^2$. So the base case
  really does determine the range of validity here.

> [!inferred] not from the summaries
> The auxiliary inequality $n^2 \geq 2n+1$ already holds from $n = 3$ on (since
> $n^2 - 2n - 1 = (n-1)^2 - 2 \geq 0$ for $n \geq 1+\sqrt{2} \approx 2.41$). So the
> bound $n \geq 4$ does not come from the auxiliary inequality but from the base case.

- Scheme: see [[mathematical-induction]]. Compare
  [[induction-factorial-geq-2n]] — the same technique with a different
  auxiliary inequality.

## Sources

- `raw/Induktion_das.pdf`, p. 4 (tutorial 3a, handwritten)
