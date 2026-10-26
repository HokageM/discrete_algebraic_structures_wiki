---
type: example
title: Induction — Telescoping Sum 1/((2k-1)(2k+1))
aliases: [telescoping sum induction, Induktion Teleskopsumme]
tags: [induction, summation-formula, example]
sources: [raw/Induktion_das.pdf]
created: 2026-09-30
updated: 2026-09-30
status: needs-review
---

# Induction — Telescoping Sum $\sum \frac{1}{(2k-1)(2k+1)}$

## Problem

Show that for all natural numbers $n \geq 1$:
$$\frac{1}{1 \cdot 3} + \frac{1}{3 \cdot 5} + \frac{1}{5 \cdot 7} + \dots +
\frac{1}{(2n-1)\cdot(2n+1)} = \frac{n}{2n+1}.$$

Use mathematical induction (vollständige Induktion). [6 points]

This problem appears **twice** in the source: as an exam problem (p. 2) and as tutorial
problem 1b) (p. 3). Both solutions are essentially identical.

## Solution

**Base case** (Induktionsanfang) $n = 1$:
$$\frac{1}{1 \cdot 3} = \frac{1}{3} = \frac{1}{2 \cdot 1 + 1} \quad ✓$$

**Induction hypothesis** (Induktionsvoraussetzung): For some fixed $n \geq 1$, assume
$\displaystyle\sum_{k=1}^{n} \frac{1}{(2k-1)(2k+1)} = \frac{n}{2n+1}$.

**Induction step** (Induktionsschluss) $n \mapsto n+1$:
$$\sum_{k=1}^{n+1} \frac{1}{(2k-1)(2k+1)}
= \frac{n}{2n+1} + \frac{1}{\bigl(2(n+1)-1\bigr)\bigl(2(n+1)+1\bigr)}
= \frac{n}{2n+1} + \frac{1}{(2n+1)(2n+3)}$$

Bring to the common denominator $(2n+1)(2n+3)$:
$$= \frac{n(2n+3) + 1}{(2n+1)(2n+3)} = \frac{2n^2 + 3n + 1}{(2n+1)(2n+3)}$$

The numerator factors as $2n^2+3n+1 = (2n+1)(n+1)$:
$$= \frac{(2n+1)(n+1)}{(2n+1)(2n+3)} = \frac{n+1}{2n+3} = \frac{n+1}{2(n+1)+1} \quad ✓$$

$\square$

**Alternative from the source** (p. 2, bottom): instead of factoring, the target equation
$$\frac{n(2n+3)+1}{(2n+1)(2n+3)} = \frac{n+1}{2n+3}$$
is multiplied through by $(2n+1)(2n+3)$ resp. $(2n+1)$, which leads to
$$2n^2 + 3n + 1 = 2n^2 + n + 2n + 1$$
— an obviously true identity.

## Contradictions

In the base case of the exam solution (p. 2), it says by hand
$$\frac{1}{1\cdot 3} = \frac{1}{3} = \frac{1}{2\cdot 1 + 3} = \frac{1}{3}$$
This is a slip of the pen (Verschreiber): $2 \cdot 1 + 3 = 5$, not $3$. What is meant is
the denominator $2n+1$ of the formula to be shown, i.e. $\frac{1}{2\cdot 1 + 1} = \frac{1}{3}$.
The tutorial solution on p. 3 correctly writes $\frac{1}{2\cdot 1 + 1}$ at the same spot.
The corrected version was adopted above.

## What it shows

- **Summation formula with fractions**: here the induction step is not multiplying out,
  but forming a common denominator, factoring the numerator, and cancelling.
- The final term must end up in the form $\frac{n+1}{2(n+1)+1}$, not merely
  $\frac{n+1}{2n+3}$ — only then is it visible that this really is the claim for $n+1$.
  The source makes this final rewriting step explicit in both solutions.
- Scheme: see [[mathematical-induction]].

## Note

> [!inferred] not from the summaries
> The name "telescoping sum" (Teleskopsumme) does not appear in the source. The sum can
> be written via partial fraction decomposition as
> $\frac{1}{(2k-1)(2k+1)} = \frac{1}{2}\left(\frac{1}{2k-1} - \frac{1}{2k+1}\right)$;
> then almost all terms cancel and one obtains the formula without induction. The source
> does not take this route.

## Sources

- `raw/Induktion_das.pdf`, p. 2 (exam problem 1) and p. 3 (tutorial 1b)
