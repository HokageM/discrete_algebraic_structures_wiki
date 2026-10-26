---
type: example
title: Finite fields GF(p^k)
aliases: [GF(16), GF(4), Galois field, endlicher Körper, finite field, Endliche Körper GF(p^k)]
tags: [polynomials, fields, example]
sources: [raw/polynomring_das.pdf]
created: 2026-09-30
updated: 2026-09-30
status: solid
---

# Finite fields $\operatorname{GF}(p^k)$

$$\operatorname{GF}(p^k) = \mathbb{Z}_p[x]_g \quad\text{with } g \in \mathbb{Z}_p[x]
\text{ irreducible of degree } k$$

The elements are the $p^k$ polynomials of degree $< k$ with coefficients from
$\mathbb{Z}_p$. Over $\mathbb{Z}_2$ this is especially pleasant: **all coefficients are
$0$ or $1$, and $+$ equals $-$**, since $2 \equiv 0$.

The source highlights $\boxed{\bmod 2}$ specially in every such problem — this is the
most important source of errors.

## $\operatorname{GF}(4) = \mathbb{Z}_2[x]_g$ with $g = x^2+x+1$

**Reduction:** $x^2 = -x-1 \equiv x+1 \pmod 2$. So all elements have degree at most 1:

$$\mathbb{Z}_2[x]_g = \{a+bx \mid a,b \in \mathbb{Z}_2\} = \{0,\ 1,\ x,\ x+1\}$$

**Addition table:**

| $+$ | $0$ | $1$ | $x$ | $x+1$ |
|---|---|---|---|---|
| $\mathbf{0}$ | $0$ | $1$ | $x$ | $x+1$ |
| $\mathbf{1}$ | $1$ | $0$ | $x+1$ | $x$ |
| $\mathbf{x}$ | $x$ | $x+1$ | $0$ | $1$ |
| $\mathbf{x+1}$ | $x+1$ | $x$ | $1$ | $0$ |

**Multiplication table:**

| $\cdot$ | $0$ | $1$ | $x$ | $x+1$ |
|---|---|---|---|---|
| $\mathbf{0}$ | $0$ | $0$ | $0$ | $0$ |
| $\mathbf{1}$ | $0$ | $1$ | $x$ | $x+1$ |
| $\mathbf{x}$ | $0$ | $x$ | $x+1$ | $1$ |
| $\mathbf{x+1}$ | $0$ | $x+1$ | $1$ | $x$ |

**Side calculations from the source:**
$$x\cdot x = x^2 = x+1$$
$$(x+1)\cdot x = x^2+x = (x+1)+x = 2x+1 = 1$$
$$(x+1)^2 = x^2+2x+1 = x^2+1 = (x+1)+1 = x$$

**Reading off:** In every row $\neq 0$ of the multiplication table, the $1$ appears
exactly once — every element $\neq 0$ has a unique inverse. So $\mathbb{Z}_2[x]_g$ is a
**field**, as predicted by [[irreducibility-and-fields]] ($g(0)=g(1)=1$, no root).

| Element | Inverse |
|---|---|
| $1$ | $1$ |
| $x$ | $x+1$ |
| $x+1$ | $x$ |

The addition table is notable: **every element is its own inverse**
($a+a=0$). This is typical of characteristic $2$.

## $\operatorname{GF}(16)$ with $g = x^4+x^3+1$

**Reduction:**
$$x^4 = -x^3-1 \equiv x^3+1 \pmod 2$$
$$x^5 = x\cdot x^4 = x^4+x = (x^3+1)+x = x^3+x+1$$

$f = x^3+x+1$, $h = x^2+x+1$.

**Sum** — in characteristic 2 this is simply the symmetric difference of the terms:
$$f+h = x^3+x+1+x^2+x+1 = x^3+x^2+2x+2 \equiv \boxed{x^3+x^2}$$

**Product:**
$$f\cdot h = (x^3+x+1)(x^2+x+1)$$
$$= (x^5+x^4+x^3) + (x^3+x^2+x) + (x^2+x+1)$$
$$= x^5+x^4+2x^3+2x^2+2x+1 \equiv x^5+x^4+1$$

Now reduce:
$$= (x^3+x+1) + (x^3+1) + 1 = 2x^3 + x + 3 \equiv \boxed{x+1}$$

> [!warning] Error in the source, p. 5
> At this point the source computes
> $$x^5+x^4+1 = (x^3+x+1)+(x^3+1) = 2x^3+x+2 \equiv x$$
> and thereby drops the **$+1$** from $x^5+x^4+\mathbf{1}$. The correct result is
> $$2x^3 + x + 3 \equiv 0 + x + 1 = x+1.$$
> The correct result is $f\cdot h = x+1$, not $x$.
>
> status: confirmed — re-checked during ingest 2026-09-30.

## $\operatorname{GF}(16)$ with $g = x^4+x+1$

The same field, **different** defining polynomial — the reduction rules change
completely:
$$x^4 = x+1, \qquad x^5 = x^2+x$$

$f = x^3+x+1$, $h = x^2+x$.

$$f+h = x^3+x+1+x^2+x = x^3+x^2+2x+1 \equiv \boxed{x^3+x^2+1}$$

$$f\cdot h = (x^3+x+1)(x^2+x) = (x^5+x^4) + (x^3+x^2) + (x^2+x)$$
$$= x^5+x^4+x^3+2x^2+x \equiv x^5+x^4+x^3+x$$
$$= (x^2+x) + (x+1) + x^3 + x = x^3+x^2+3x+1 \equiv \boxed{x^3+x^2+x+1}$$

Both polynomials $x^4+x+1$ and $x^4+x^3+1$ are irreducible over $\mathbb{Z}_2$ and yield
isomorphic fields with $2^4 = 16$ elements — but the computations look completely
different.

## Key points for characteristic 2

- $+$ and $-$ are the same. Signs can be ignored.
- $2x^k \equiv 0$: **identical terms cancel**. The sum of two polynomials is the
  symmetric difference of their term sets (XOR).
- When reducing $x^5+x^4+1$, take **all three summands** along — this is exactly where
  the source's error lies.
- Check: the result must have degree $< \deg g$.
- For verifying small cases, the operation table is worthwhile; from
  $\operatorname{GF}(16)$ (16 elements) on, it is too large.

## Related

- [[polynomial-ring]] — $K[x]_g$ in general
- [[irreducibility-and-fields]] — why $g$ must be irreducible
- [[computing-in-polynomial-rings]] — the same technique over $\mathbb{Q}$ and $\mathbb{Z}_3$
- [[field-or-not]] — field test
- [[residue-class-ring]] — the operation tables of $\mathbb{Z}_6$ for comparison

## Sources

- `raw/polynomring_das.pdf`, p. 1 (problem 6.3), p. 4 (problem 6.3), p. 5, p. 7 (exercise 11.2)
