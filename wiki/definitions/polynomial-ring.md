---
type: definition
title: Polynomial ring and residue class ring K[x]_g
aliases: [polynomial ring, Polynomring, K[x]_g, polynomial residue class ring, Polynomrestklassenring]
tags: [polynomials, ring-theory]
sources: [raw/polynomring_das.pdf]
created: 2026-09-30
updated: 2026-09-30
status: solid
---

# Polynomial ring and residue class ring $K[x]_g$

## Polynomial ring $K[x]$

For a [[ring-like-structures|commutative ring]] or field $K$,
$$K[x] = \left\{\textstyle\sum_{i=0}^{n} a_i x^i \;\middle|\; a_i \in K,\ n \in \mathbb{N}_0\right\}$$
with the usual addition and multiplication is again a commutative ring.

**Degree** (*Grad*): $\deg(f) = $ the highest index with $a_i \neq 0$. We have
$$\deg(f\cdot g) = \deg(f) + \deg(g)$$

## Residue class ring $K[x]_g$

Completely analogous to [[residue-class-ring|$\mathbb{Z}_n$]] (*Restklassenring*): one
computes modulo a fixed polynomial $g$.

$$f_1 \equiv f_2 \pmod g \;:\Longleftrightarrow\; g \mid (f_1 - f_2)$$
$$K[x]_g = K[x]/{\equiv}$$

The elements are the residue polynomials of degree $< \deg(g)$.

| | $\mathbb{Z}_n$ | $K[x]_g$ |
|---|---|---|
| Base ring | $\mathbb{Z}$ | $K[x]$ |
| Modulus | number $n$ | polynomial $g$ |
| Representatives | $0,\dots,n-1$ | polynomials of degree $< \deg g$ |
| Count | $n$ | $|K|^{\deg g}$ (if $K$ finite) |
| Field $\iff$ | $n$ prime | $g$ irreducible |

## The computation rule: setting up the reduction formula

The decisive first step in every problem. Set $g = 0$ and solve for the highest power:

| $g$ | Reduction rule | one step higher |
|---|---|---|
| $x^3+1$ | $x^3 = -1$ | $x^4 = -x$ |
| $x^3+2$ | $x^3 = -2$ | $x^4 = -2x$ |
| $x^3-1$ | $x^3 = 1$ | $x^4 = x$ |
| $x^3-x^2+1$ | $x^3 = x^2-1$ | $x^4 = x^3-x = x^2-x-1$ |
| $x^4+x+1$ over $\mathbb{Z}_2$ | $x^4 = x+1$ | $x^5 = x^2+x$ |
| $x^4+x^3+1$ over $\mathbb{Z}_2$ | $x^4 = x^3+1$ | $x^5 = x^3+x+1$ |
| $x^2+x+1$ over $\mathbb{Z}_2$ | $x^2 = x+1$ | — |

The source notes this each time with "$\cdot x$" in the margin: the base rule is
multiplied by $x$ step by step, reducing immediately each time.

**Recipe for $f \cdot h$:**

1. Set up the reduction rule for $x^{\deg g}, x^{\deg g + 1}, \dots$
2. Multiply out $f\cdot h$ **normally**.
3. Replace all powers $\geq \deg(g)$ using the rule.
4. If $K = \mathbb{Z}_p$: finally reduce the coefficients modulo $p$.

Worked out in [[computing-in-polynomial-rings]].

## Two moduli at once

For $\mathbb{Z}_p[x]_g$ there are **two** independent reductions:

- **modulo $p$** on the coefficients,
- **modulo $g$** on the powers.

The source specifically highlights the $\boxed{\bmod 2}$ resp. $\boxed{\bmod 3}$ each
time. The order doesn't matter, but both must be applied — this is the most common
source of error.

**Typical example** ($\mathbb{Z}_3$): $-2x \equiv x$, $-1 \equiv 2$, $3x \equiv 0$. The
source notes: "For $-x$ you must add mod."

## Related

- [[irreducibility-and-fields]] — when $K[x]_g$ is a field
- [[quadratic-field-extension]] — $\mathbb{Q}[\sqrt{n}]$, the related case
- [[computing-in-polynomial-rings]] — worked-out problems
- [[finite-fields]] — $\operatorname{GF}(2^k)$, operation tables
- [[residue-class-ring]] — the number-theoretic model $\mathbb{Z}_n$
- [[ring-like-structures]] — ring, integral domain, field

## Sources

- `raw/polynomring_das.pdf`, p. 1, p. 4, p. 5, p. 6, p. 8
