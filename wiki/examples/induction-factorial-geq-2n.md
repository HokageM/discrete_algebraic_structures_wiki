---
type: example
title: Induction — n! ≥ 2^n for n ≥ 4
aliases: [factorial inequality induction, Induktion n! >= 2^n]
tags: [induction, inequality, example, factorial]
sources: [raw/Induktion_das.pdf]
created: 2026-09-30
updated: 2026-09-30
status: solid
---

# Induction — $n! \geq 2^n$ for $n \geq 4$

## Problem

Tutorial 3b): Show for all $n \geq 4$:
$$n! \geq 2^n.$$

## Solution

**Base case** (Induktionsanfang) $n = 4$:
$$4! = 24 \geq 2^4 = 16 \quad ✓$$

**Induction hypothesis** (Induktionsvoraussetzung): For some fixed $n \geq 4$, assume $n! \geq 2^n$.

**Induction step** (Induktionsschluss) $n \mapsto n+1$: We must show $(n+1)! \geq 2^{n+1} = 2 \cdot 2^n$.

$$(n+1)! = (n+1) \cdot n! \;\overset{\text{IH}}{\geq}\; (n+1) \cdot 2^n$$

**Auxiliary inequality** (Hilfsungleichung, side computation in the source's margin):
$n + 1 \geq 2$ for $n \geq 4$. Hence:
$$(n+1) \cdot 2^n \;\geq\; 2 \cdot 2^n = 2^{n+1}$$
so
$$(n+1)! \geq 2^{n+1}. \qquad \square$$

## What it shows

- Same structure as [[induction-2n-geq-n-squared]], but noticeably simpler: the
  recursion $(n+1)! = (n+1)\cdot n!$ supplies the factor, the hypothesis replaces $n!$
  by $2^n$, and the auxiliary inequality $n+1 \geq 2$ finishes it off.
- Recurring pattern for inequalities: **split off the recursion step → substitute the
  hypothesis → estimate the remaining factor from below.**
- **Why $n_0 = 4$?** The auxiliary inequality $n+1 \geq 2$ already holds from $n = 1$ on;
  the bound $4$ comes solely from the problem statement / the base case.

> [!inferred] not from the summaries
> Indeed $n! \geq 2^n$ already holds from $n = 4$ on and not earlier: $3! = 6 < 8 = 2^3$.
> So the bound is tight, even though the source does not mention this.

- Scheme: see [[mathematical-induction]].

## Sources

- `raw/Induktion_das.pdf`, p. 4 (tutorial 3b, handwritten)
