---
type: example
title: Computing in polynomial residue class rings
aliases: [polynomial ring arithmetic, Rechnen in Polynomrestklassenringen]
tags: [polynomials, example]
sources: [raw/polynomring_das.pdf]
created: 2026-09-30
updated: 2026-09-30
status: solid
---

# Computing in polynomial residue class rings

Problems of the type "Let $f, h \in K[x]_g$. Compute $f+h$ and $f\cdot h$."
Basis: [[polynomial-ring]].

## Always the same procedure

1. Derive the reduction rule from $g = 0$, one level higher than needed.
2. Sum: simply add, then reduce.
3. Product: multiply out, **then** reduce.
4. For $\mathbb{Z}_p[x]$: coefficients modulo $p$.

## 1. $\mathbb{Q}[x]_g$ with $g = x^3+1$

$f = -x^2-3$, $h = x^2-5x+10$.

**Reduction:** $x^3 = -1$, times $x$: $x^4 = -x$.

$$f+h = (-x^2-3) + (x^2-5x+10) = \boxed{-5x+7}$$

$$f\cdot h = (-x^2-3)(x^2-5x+10)$$
$$= -x^4+5x^3-10x^2 \;-3x^2+15x-30$$
$$= -x^4+5x^3-13x^2+15x-30$$

Now $-x^4 = -(-x) = x$ and $5x^3 = 5\cdot(-1) = -5$:
$$= x - 5 - 13x^2 + 15x - 30 = \boxed{-13x^2+16x-35}$$

## 2. $\mathbb{Q}[x]_g$ with $g = x^3+2$

$f = 2x^2-3$, $h = 4x^2-2x-6$.

**Reduction:** $x^3 = -2$, $x^4 = -2x$.

$$f+h = \boxed{6x^2-2x-9}$$

$$f\cdot h = (2x^2-3)(4x^2-2x-6) = 8x^4-4x^3-12x^2 \;-12x^2+6x+18$$

With $8x^4 = 8(-2x) = -16x$ and $-4x^3 = -4(-2) = 8$:
$$= -16x + 8 - 24x^2 + 6x + 18 = \boxed{-24x^2-10x+26}$$

## 3. $\mathbb{Q}[x]_g$ with $g = x^3-x^2+1$

**Reduction:** $x^3 = x^2-1$, then
$$x^4 = x\cdot x^3 = x^3 - x = (x^2-1) - x = x^2-x-1$$

Note: $x^4$ must be reduced **twice**, because $x\cdot x^3$ again produces an $x^3$.
This is the difference from the simple cases $g = x^3 \pm c$.

$$(5x^2+1) + (-x^2-x-1) = \boxed{4x^2-x}$$

$$(x^2+1)(x^2-x-1) = x^4-x^3-x^2 \;+x^2-x-1 = x^4-x^3-x-1$$
$$= (x^2-x-1) - (x^2-1) - x - 1$$
$$= x^2-x-1-x^2+1-x-1 = \boxed{-2x-1}$$

## 4. The same $f, h$ in four different rings

$f = x^2-2x+1$, $h = x^2-1$. This problem shows how strongly the ring changes the
result.

**In $\mathbb{Z}[x]$** (no reduction):
$$f+h = 2x^2-2x$$
$$f\cdot h = (x^2-2x+1)(x^2-1) = x^4-x^2-2x^3+2x+x^2-1 = x^4-2x^3+2x-1$$

**In $\mathbb{Z}_3[x]$** (coefficients mod 3 only, $-2\equiv1$, $-1\equiv2$):
$$f+h = 2x^2-2x = \boxed{2x^2+x}$$
$$f\cdot h = x^4-2x^3+2x-1 = \boxed{x^4+x^3+2x+2}$$

**In $\mathbb{Z}[x]_g$ with $g = x^3-1$** ($x^3=1$, $x^4=x$):
$$f+h = 2x^2-2x$$
$$f\cdot h = x^4-2x^3+2x-1 = x - 2 + 2x - 1 = \boxed{3x-3}$$

**In $\mathbb{Z}_3[x]_g$ with $g = x^3-1$** (both reductions):
$$f+h = \boxed{2x^2+x}$$
$$f\cdot h = 3x-3 \equiv \boxed{0} \pmod 3$$

Notable: in the last ring, the product of two nonzero polynomials equals zero —
$f$ and $h$ are [[units-and-zero-divisors|zero divisors]]. This fits
[[irreducibility-and-fields]]: $g = x^3-1$ has the root $x=1$ in $\mathbb{Z}_3$, so it is
reducible.

## 5. $\mathbb{Z}_3[x]_g$ with $g = 2x^2+x+1$

Here the leading coefficient is not $1$ — it must first be removed.

$$2x^2 = -x-1 \equiv 2x+2 \pmod 3$$

Multiplying both sides by $2$, since $2 \cdot 2 = 4 \equiv 1$:
$$x^2 = 2(2x+2) = 4x+4 \equiv \boxed{x+1}$$
$$x^3 = x\cdot x^2 = x^2+x = (x+1)+x = 2x+1$$

$$(x+1)+(2x+1) = 3x+2 \equiv \boxed{2}$$

$$(2x+1)(x+1) = 2x^2+2x+x+1 = 2x^2+3x+1 \equiv 2x^2+1$$
$$= (2x+2)+1 = 2x+3 \equiv \boxed{2x}$$

## Key points

- **Set up the reduction rule first and completely** — up to $x^{2\deg g - 2}$,
  since that's how high the product of two reduced polynomials reaches.
- For $g$ with more than two terms ($x^3-x^2+1$) one must **iterate**: each
  multiplication by $x$ can again produce too high a power.
- **Don't reduce too early.** Multiply out fully first, then substitute — otherwise
  terms get lost.
- **Don't confuse the two moduli**: $\bmod p$ concerns coefficients, $\bmod g$ the
  powers. Both must be applied.
- The result must have degree $< \deg g$. A good final check.

## Related

- [[polynomial-ring]] — definitions and reduction table
- [[finite-fields]] — the same over $\mathbb{Z}_2$
- [[quadratic-field-extension]] — the case $g = x^2-n$
- [[irreducibility-and-fields]] — when zero divisors occur
- [[field-or-not]] — field test

## Sources

- `raw/polynomring_das.pdf`, p. 1 (problem 6.2), p. 4 (problem 6.2), p. 6 (exercise 10.5),
  p. 8 (exercise 12.2)
