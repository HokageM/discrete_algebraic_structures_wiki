---
type: example
title: Deciding field or not
aliases: [field test, Körpertest, Körperkriterium Aufgaben, Körper ja/nein entscheiden]
tags: [polynomials, fields, example]
sources: [raw/polynomring_das.pdf]
created: 2026-09-30
updated: 2026-09-30
status: solid
---

# Deciding field or not

Exam problems of the type "Check whether the following residue class rings are fields
(Körper)." Basis: [[irreducibility-and-fields]].

## Checking scheme

```
Ring = Z_n ?
    └─ n prime?  → yes: field   no: not a field (give zero divisors!)

Ring = K[x]_g ?
    ├─ deg g ≤ 3?
    │   └─ look for a root in K
    │        K = Z_p  → plug in all p elements, reduce mod p!
    │        K = Q,R  → find roots, check membership
    └─ found → reducible, not a field (give factors as zero divisors)
       none    → irreducible, field
```

## Number rings

### $\mathbb{Z}_{19}$ — **field**
$19$ is prime, hence irreducible. ✓

### $\mathbb{Z}_{61}$ — **field**
$61$ is prime. ✓

### $\mathbb{Z}_{51}$ — **not a field**
$$51 = 3\cdot17$$
Reducible. Concrete [[units-and-zero-divisors|zero divisors]]: $3, 17 \neq 0$, but
$$3\cdot17 = 51 \equiv 0 \pmod{51}$$
The source explicitly gives the counterexample — this belongs with "not a field".

## Over $\mathbb{Q}$

### $\mathbb{Q}[x]_f$ with $f = x^2-2$ — **field**
$$x^2-2 = 0 \;\Longrightarrow\; x_{1,2} = \pm\sqrt2 \notin \mathbb{Q}$$
No root in $\mathbb{Q}$, degree $2 \le 3$, hence irreducible over $\mathbb{Q}$. ✓

This is exactly [[quadratische-koerpererweiterung|$\mathbb{Q}[\sqrt2]$]].

### $\mathbb{Q}[x]_f$ with $f = x^3-2$ — **field**
$$x^3 = 2 \;\Longrightarrow\; x = \sqrt[3]{2} \notin \mathbb{Q}$$
Degree $3 \le 3$, no rational root → irreducible. ✓

### $\mathbb{Q}[x]_f$ with $f = x^2-4$ — **not a field**
$$f = (x-2)(x+2), \qquad f(x) = 0 \text{ for } x \in \{-2, 2\} \subset \mathbb{Q}$$
The roots lie in $\mathbb{Q}$, so $f$ splits into degree-1 factors. In
$\mathbb{Q}[x]_f$ we have
$$(x-2)(x+2) = f \equiv 0$$
with both factors $\neq 0$ — zero divisors. ✗

*(The source accidentally writes "$(x+2),(x+2)$" here; $(x-2)$ and $(x+2)$ are meant.)*

## The underlying domain (Grundbereich) decides

### $\mathbb{R}[x]_f$ with $f = x^2-2$ — **not a field**
$$f = (x-\sqrt2)(x+\sqrt2), \qquad \pm\sqrt2 \in \mathbb{R}$$
Over $\mathbb{R}$ the factors exist, so $(x-\sqrt2)$ and $(x+\sqrt2)$ are zero divisors
in $\mathbb{R}[x]_f$. ✗

**Direct comparison** — the same $f$, two answers:

| | $\mathbb{Q}[x]_{x^2-2}$ | $\mathbb{R}[x]_{x^2-2}$ |
|---|---|---|
| roots $\pm\sqrt2$ | $\notin \mathbb{Q}$ | $\in \mathbb{R}$ |
| $f$ | irreducible | reducible |
| result | **field** | **not a field** |

This is exactly what the source warns about with "! pay attention to the domain
(Wertebereich) !".

## Over $\mathbb{Z}_2$

Here plug in all elements of $\mathbb{Z}_2 = \{0,1\}$.

### $\mathbb{Z}_2[x]_g$ with $g = x^3+1$ — **not a field**
$$g(0) = 0+1 = 1$$
$$g(1) = 1+1 = 2 \equiv 0 \pmod 2 \quad\text{← root!}$$
So $g = (x+1)(\dots)$, reducible. ✗

Explicitly: $x^3+1 = (x+1)(x^2+x+1)$ in $\mathbb{Z}_2[x]$.

### $\mathbb{Z}_2[x]_g$ with $g = x^3+x^2+x+1$ — **not a field**
$$g(0) = 1, \qquad g(1) = 1+1+1+1 = 4 \equiv 0$$
Reducible. ✗ (In fact $g = (x+1)^3$ over $\mathbb{Z}_2$.)

### $\mathbb{Z}_2[x]_g$ with $g = x^2+x+1$ — **field**
$$g(0) = 1, \qquad g(1) = 1+1+1 = 3 \equiv 1$$
No root, degree $2$ → irreducible. ✓

This is [[finite-fields|$\operatorname{GF}(4)$]]; there the field property is
additionally read off the operation table.

## Over $\mathbb{Z}_3$ — with a corrected result

### $\mathbb{Z}_3[x]_g$ with $g = x^3+x+2$ — **not a field**

Plug in all three elements of $\mathbb{Z}_3 = \{0,1,2\}$ and **reduce modulo 3**:

| $a$ | $g(a)$ | $\bmod 3$ |
|---|---|---|
| $0$ | $0+0+2 = 2$ | $2$ |
| $1$ | $1+1+2 = 4$ | $1$ |
| $2$ | $8+2+2 = 12$ | $\mathbf{0}$ ← root! |

$x = 2$ is a root, so $g$ is **reducible**:
$$x^3+x+2 = (x+1)(x^2+2x+2) \quad\text{in } \mathbb{Z}_3[x]$$

Check: $(x+1)(x^2+2x+2) = x^3+2x^2+2x + x^2+2x+2 = x^3+3x^2+4x+2 \equiv x^3+x+2$ ✓

So $(x+1)$ and $(x^2+2x+2)$ are zero divisors in $\mathbb{Z}_3[x]_g$ — **not a field**. ✗

> [!warning] Contradiction with the source
> The source (p. 10) lists the same values $g(0)=2$, $g(1)=4$, $g(2)=12$, but does
> **not** reduce them modulo 3 and incorrectly concludes "no roots ⇒ irreducible".
> See [[irreducibility-and-fields]].

## Overall summary

| Ring | Field? | Justification |
|---|---|---|
| $\mathbb{Z}_{19}$ | ✓ | prime |
| $\mathbb{Z}_{61}$ | ✓ | prime |
| $\mathbb{Z}_{51}$ | ✗ | $3\cdot17$ |
| $\mathbb{Q}[x]_{x^2-2}$ | ✓ | $\pm\sqrt2\notin\mathbb{Q}$ |
| $\mathbb{Q}[x]_{x^3-2}$ | ✓ | $\sqrt[3]2\notin\mathbb{Q}$ |
| $\mathbb{Q}[x]_{x^2-4}$ | ✗ | roots $\pm2\in\mathbb{Q}$ |
| $\mathbb{R}[x]_{x^2-2}$ | ✗ | $\pm\sqrt2\in\mathbb{R}$ |
| $\mathbb{Z}_2[x]_{x^2+x+1}$ | ✓ | no root |
| $\mathbb{Z}_2[x]_{x^3+1}$ | ✗ | $g(1)=0$ |
| $\mathbb{Z}_2[x]_{x^3+x^2+x+1}$ | ✗ | $g(1)=0$ |
| $\mathbb{Z}_3[x]_{x^3+x+2}$ | ✗ | $g(2)\equiv0$ ⚠️ |

## Key points

- **When "not a field", always give the zero divisors** — the source does this
  consistently and it earns points.
- **For $\mathbb{Z}_p$, reduce the function values!** $g(2)=12$ looks like "$\neq 0$",
  but is $0$ modulo 3. This is exactly where the source fails.
- **Name the underlying domain.** "$f$ is irreducible" without $K$ is a meaningless
  statement.
- The rule "reducible ⟺ has a root" holds **only up to degree 3**.

## Related

- [[irreducibility-and-fields]] — theorem, degree argument, exam rule
- [[polynomial-ring]] — $K[x]_g$
- [[finite-fields]] — $\operatorname{GF}(4)$, $\operatorname{GF}(16)$
- [[quadratic-field-extension]] — $\mathbb{Q}[\sqrt n]$
- [[determining-units-and-zero-divisors]] — the analog in $\mathbb{Z}_n$

## Sources

- `raw/polynomring_das.pdf`, p. 1 (problem 6.4), p. 2 (problem 6.4), p. 3, p. 4, p. 5,
  p. 9 (exercise 12.3), p. 10 (exercise 12.3)
