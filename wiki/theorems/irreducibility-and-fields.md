---
type: theorem
title: Irreducibility and the Field Criterion
aliases: [irreducible, reducible, field criterion, Irreduzibilität, Körperkriterium, Körper]
tags: [polynomials, fields, theorems]
sources: [raw/polynomring_das.pdf]
created: 2026-09-30
updated: 2026-09-30
status: solid
---

# Irreducibility and the field criterion (Irreduzibilität und Körperkriterium)

## The criterion

> **Theorem.** A residue class ring (Restklassenring) is a **field** (Körper) if and
> only if the modulus is **irreducible** (irreduzibel, unzerlegbar):
>
> | Ring | Field $\iff$ |
> |---|---|
> | $\mathbb{Z}_n$ | $n$ is **prime** |
> | $K[x]_g$ | $g$ is **irreducible over $K$** |

The source summarizes both in one line:
$$n \text{ prime} \Rightarrow \text{irreducible} \Rightarrow \text{field}$$
$$n \text{ not prime} \Rightarrow \text{reducible} \Rightarrow \text{not a field}$$

**Why?** If $g = g_1\cdot g_2$ is a proper factorization, then in $K[x]_g$
$$g_1 \cdot g_2 = g \equiv 0 \quad\text{with } g_1, g_2 \not\equiv 0,$$
so $g_1, g_2$ are [[units-and-zero-divisors|zero divisors]] (Nullteiler). But a field has
no zero divisors. Exactly the same argument as for $\mathbb{Z}_{51}$: $3\cdot17 = 51 \equiv 0$.

## The degree theorem and the exam rule of thumb

From $\deg(g) = \deg(g_1) + \deg(g_2)$ it follows for proper factorizations (both
degrees $\ge 1$):

| $\deg g$ | possible factorizations | degree-1 factor required? |
|---|---|---|
| $2$ | $1+1$ | yes |
| $3$ | $1+2$ | yes |
| $4$ | $1+3$, $2+2$ | **no** |
| $5$ | $1+4$, $2+3$ | no |

> **Exam rule of thumb (Klausurregel).** Polynomials of degree $\le 3$ are **reducible
> if and only if they have a root in $K$.**

Reason: a degree-1 factor is $c(x - x_0)$, and $x_0$ is then a root. Only from degree
$4$ on are there factorizations with no linear factor at all (e.g.
$x^4+x^2+1 = (x^2+x+1)(x^2-x+1)$); there the rule fails.

## The test procedure

1. **$\deg g \le 3$?** Then search for roots.
2. **Which base field $K$?** The source warns explicitly: *"! watch the range of
   values !"* ("auf den Wertebereich achten") — the same factorization can fail over
   $\mathbb{Q}$ and succeed over $\mathbb{R}$.
3. **$K = \mathbb{Z}_p$ finite?** Then plug in **all** $p$ elements. This is a finite,
   exhaustive test.
4. **$K = \mathbb{Q}$ or $\mathbb{R}$?** Determine roots algebraically and check
   whether they **lie in $K$**.

## The crucial point: the base field

The same polynomial $f = x^2 - 2 = (x-\sqrt2)(x+\sqrt2)$:

| $K$ | roots in $K$? | $f$ | $K[x]_f$ |
|---|---|---|---|
| $\mathbb{Q}$ | $\pm\sqrt2 \notin \mathbb{Q}$ | irreducible | **field** |
| $\mathbb{R}$ | $\pm\sqrt2 \in \mathbb{R}$ | reducible | **not a field** |

Over $\mathbb{R}$, $(x-\sqrt2)$ and $(x+\sqrt2)$ are zero divisors in $\mathbb{R}[x]_f$.
Over $\mathbb{Q}$ these factors simply don't exist there.

Similarly $f = x^3 - 2$: $\sqrt[3]{2} \notin \mathbb{Q}$, so $\mathbb{Q}[x]_f$ is a
field — over $\mathbb{R}$ it would not be.

## Worked cases

Fully worked out in [[field-or-not]]. Overview:

| Ring | irreducible? | field? | reason |
|---|---|---|---|
| $\mathbb{Z}_{19}$ | yes | ✓ | $19$ prime |
| $\mathbb{Z}_{61}$ | yes | ✓ | $61$ prime |
| $\mathbb{Z}_{51}$ | no | ✗ | $51 = 3\cdot17$ |
| $\mathbb{Q}[x]_{x^2-2}$ | yes | ✓ | $\pm\sqrt2\notin\mathbb{Q}$ |
| $\mathbb{Q}[x]_{x^3-2}$ | yes | ✓ | $\sqrt[3]2\notin\mathbb{Q}$ |
| $\mathbb{Q}[x]_{x^2-4}$ | no | ✗ | $=(x-2)(x+2)$ |
| $\mathbb{R}[x]_{x^2-2}$ | no | ✗ | $\pm\sqrt2\in\mathbb{R}$ |
| $\mathbb{Z}_2[x]_{x^3+1}$ | no | ✗ | $g(1)=0$ |
| $\mathbb{Z}_2[x]_{x^3+x^2+x+1}$ | no | ✗ | $g(1)=0$ |
| $\mathbb{Z}_2[x]_{x^2+x+1}$ | yes | ✓ | $g(0)=g(1)=1$ |
| $\mathbb{Z}_3[x]_{x^3+x+2}$ | **no** | **✗** | $g(2)=12\equiv0$ ⚠️ |

The last row contradicts the source — see below.

## Contradictions

> [!warning] Error in the source, p. 10
> For $\mathbb{Z}_3[x]_g$ with $g = x^3+x+2$, the source computes
> $$g(0)=2,\quad g(1)=4,\quad g(2)=12$$
> and concludes: "$\Rightarrow$ no roots $\Rightarrow$ irreducible".
>
> This is **wrong**: the computation is in $\mathbb{Z}_3$, and
> $$g(2) = 12 \equiv 0 \pmod 3.$$
> So $x = 2$ is a root, $g$ is **reducible**, and $\mathbb{Z}_3[x]_g$ is **not a
> field**.
>
> The factorization is
> $$x^3+x+2 = (x+1)(x^2+2x+2) \quad\text{in } \mathbb{Z}_3[x].$$
> Check: $(x+1)(x^2+2x+2) = x^3+2x^2+2x+x^2+2x+2 = x^3+3x^2+4x+2 \equiv x^3+x+2$ ✓
>
> The second factor $x^2+2x+2$ is itself irreducible ($h(0)=2$, $h(1)=2$,
> $h(2)=1$).
>
> **Cause of the error:** the function values were not reduced modulo $3$. This is
> exactly what the source itself warns about two pages earlier.
>
> status: confirmed — verified during ingest on 2026-09-30.

On p. 9, for $f = x^2-4$ the zero divisors are also given as "$(x+2),(x+2)$"; the
correct pair is $(x-2)$ and $(x+2)$. Evidently a slip.

## Related pages

- [[field-or-not]] — all cases worked out
- [[polynomial-ring]] — $K[x]_g$
- [[finite-fields]] — $\operatorname{GF}(p^k)$
- [[units-and-zero-divisors]] — zero divisors as the obstruction
- [[ring-like-structures]] — the ring hierarchy
- [[quadratic-field-extension]] — the case $g = x^2-n$

## Sources

- `raw/polynomring_das.pdf`, p. 3, p. 4, p. 5, p. 9, p. 10
