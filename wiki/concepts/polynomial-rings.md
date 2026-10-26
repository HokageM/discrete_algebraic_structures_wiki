---
type: concept
title: Polynomial Rings and Fields
aliases: [polynomial rings, Polynomringe und Körper, Kapitelübersicht Polynomringe]
tags: [hub, polynomials, fields]
sources: [raw/polynomring_das.pdf]
created: 2026-09-30
updated: 2026-09-30
status: solid
---

# Polynomial Rings and Fields

Hub page for the chapter. The guiding idea is an **analogy** that carries the whole
chapter:

$$\mathbb{Z} \;\longleftrightarrow\; K[x], \qquad
\mathbb{Z}_n \;\longleftrightarrow\; K[x]_g, \qquad
\text{prime} \;\longleftrightarrow\; \text{irreducible}$$

Everything that holds for $\mathbb{Z}_n$ in [[residue-class-rings]] carries over line by
line to polynomials.

## The analogy in detail

| | $\mathbb{Z}_n$ | $K[x]_g$ |
|---|---|---|
| Base set | $\mathbb{Z}$ | $K[x]$ |
| Modulus | number $n$ | polynomial $g$ |
| Residue classes | $0,\dots,n-1$ | degree $< \deg g$ |
| "Size" | absolute value | degree |
| Division with remainder | $a = qn+r$ | $f = qg+r$, $\deg r < \deg g$ |
| indecomposable | prime | irreducible |
| **field $\iff$** | $n$ prime | $g$ irreducible |
| zero divisor | $\gcd(a,n)>1$ | $f$ properly divides $g$ |

## Pages of this chapter

| Page | Content |
|---|---|
| [[polynomial-ring]] | $K[x]$, $K[x]_g$, reduction rule, two moduli |
| [[quadratic-field-extension]] | $\mathbb{Q}[\sqrt n]$, conjugates, inverse formula |
| [[irreducibility-and-fields]] | field criterion, degree theorem, exam rule |
| [[computing-in-polynomial-rings]] | $f+h$ and $f\cdot h$ over $\mathbb{Q}$, $\mathbb{Z}_3$, $\mathbb{Z}$ |
| [[finite-fields]] | $\operatorname{GF}(4)$ with tables, $\operatorname{GF}(16)$ |
| [[field-or-not]] | eleven rings checked |

## The four exam problem types

As with [[residue-class-rings|$\mathbb{Z}_n$]], the source contains the same problem
structure twice (problem 6, 18 points):

| # | Problem | Tool | Page |
|---|---|---|---|
| 1 | $a+b$, $a\cdot b$, $a^{-1}$ in $\mathbb{Q}[\sqrt n]$ | expand with conjugate | [[quadratic-field-extension]] |
| 2 | $f+h$, $f\cdot h$ in $\mathbb{Q}[x]_g$ | reduction rule from $g=0$ | [[computing-in-polynomial-rings]] |
| 3 | $f+h$, $f\cdot h$ in $\operatorname{GF}(16)$ | reduction **and** $\bmod 2$ | [[finite-fields]] |
| 4 | Are the rings fields? | root search | [[field-or-not]] |

Concretely asked:

| | Exam A | Exam B |
|---|---|---|
| 1 | $\mathbb{Q}[\sqrt{-5}]$ | $\mathbb{Q}[\sqrt{-7}]$ |
| 2 | $g = x^3+1$ | $g = x^3+2$ |
| 3 | $\operatorname{GF}(16)$, $g=x^4+x^3+1$ | $\operatorname{GF}(16)$, $g=x^4+x+1$ |
| 4 | $\mathbb{Z}_{51}$, $\mathbb{Q}[x]_{x^2-2}$, $\mathbb{Z}_2[x]_{x^3+1}$ | $\mathbb{Z}_{61}$, $\mathbb{Q}[x]_{x^3-2}$, $\mathbb{Z}_2[x]_{x^3+x^2+x+1}$ |

## The two basic techniques

**1. Set up the reduction rule.** From $g = 0$, isolate the highest power, then multiply
step by step by $x$. Everything else is substitution.

**2. Search for roots.** For $\deg g \le 3$, the existence of a root **within the
respective base domain** alone decides irreducibility — and thereby the field property.

## Cross-connections

- **To [[residue-class-rings]]:** the same construction, just with polynomials instead of
  numbers. $\mathbb{Z}_{51}$ appears in both chapters as a counterexample.
- **To [[ring-like-structures]]:** here the top level of the hierarchy — the field — is
  systematically tested.
- **To [[units-and-zero-divisors]]:** "not a field" is always backed up by **stating
  concrete zero divisors**.
- **To [[laws-of-integers]]:** distributivity and sign rules are the toolkit for
  multiplying out.

## Errors in the source

Two content-relevant errors, both recomputed and corrected during ingest:

| Page | Error | correct |
|---|---|---|
| p. 5 | $f\cdot h$ in $\operatorname{GF}(16)$: a $+1$ lost, result $x$ | $x+1$ |
| p. 10 | $g=x^3+x+2$ over $\mathbb{Z}_3$ labeled irreducible | $g(2)\equiv0$, **reducible** |

Plus two notation errors: on p. 7, for two inverses the conjugate is written on the left
side (results are correct); on p. 9, the zero divisors of $x^2-4$ are noted as
"$(x+2),(x+2)$" instead of $(x-2),(x+2)$.

**Both content errors arise from forgetting to reduce** — once $\bmod 2$, once $\bmod 3$.
Exactly the point the source itself repeatedly warns about.

## Sources

- `raw/polynomring_das.pdf` (10 pages)
