---
type: example
title: Homomorphism Proofs
aliases: [homomorphism proofs, Homomorphismus-Nachweise, determinant multiplicative, isomorphism N0 powers of two]
tags: [algebraic-structures, example, homomorphism]
sources: [raw/Algebraische_strukturen_das.pdf]
created: 2026-09-30
updated: 2026-09-30
status: solid
---

# Homomorphism Proofs

## 1. The determinant is multiplicative, but not additive

**Problem** (p. 5, problem 4.4): Show that
$$\det : \mathbb{Q}^{2\times 2} \to \mathbb{Q}, \quad
\begin{pmatrix} a & b \\ c & d \end{pmatrix} \mapsto ad - bc$$
is multiplicative, i.e. $\det(AB) = \det(A)\det(B)$. Is the map also additive?

### Multiplicativity

$$\begin{pmatrix} a & b \\ c & d \end{pmatrix}\begin{pmatrix} x & y \\ z & w \end{pmatrix}
= \begin{pmatrix} ax + bz & ay + bw \\ cx + dz & cy + dw \end{pmatrix}$$

$$\det(AB) = (ax+bz)(cy+dw) - (cx+dz)(ay+bw)$$
$$= acxy + adwx + bcyz + bdwz - acxy - adyz - bcwx - bdwz$$
$$= adwx + bcyz - adyz - bcwx$$

On the other hand:
$$\det(A)\det(B) = (ad - bc)(xw - yz) = adwx - adyz - bcxw + bcyz$$

Both terms agree $\Rightarrow$ **$\det$ is multiplicative ✓**

Note how the terms $acxy$ and $bdwz$ **cancel** — that is exactly what makes the proof
work.

### Additivity

$$\det(A + B) = \det\begin{pmatrix} a+x & b+y \\ c+z & d+w \end{pmatrix}
= (a+x)(d+w) - (b+y)(c+z)$$
$$= ad + aw + dx + xw - bc - bz - cy - yz$$

versus
$$\det(A) + \det(B) = (ad - bc) + (xw - yz)$$

The difference is $aw + dx - bz - cy$, which is in general $\neq 0$.
$\Rightarrow$ **$\det$ is not additive ✗**

Counterexample: $A = B = I_2$. Then $\det(A+B) = \det\begin{pmatrix}2&0\\0&2\end{pmatrix} = 4$,
but $\det A + \det B = 1 + 1 = 2$.

> [!inferred] not from the summaries
> The explicit counterexample is not in the source; it only notes "$\neq$, not additive".
> Likewise the source does not state that $\det$ is thus a homomorphism (Homomorphismus)
> of the **multiplicative** monoids $(\mathbb{Q}^{2\times2},\cdot)\to(\mathbb{Q},\cdot)$,
> but not a ring homomorphism — precisely because condition (i) from [[homomorphism]]
> (compatibility with $+$) is violated.

## 2. $(\mathbb{N}_0, +, 0) \cong (2^{\mathbb{N}_0}, \cdot, 1)$

**Problem** (p. 8, tutorial 8 ⑤): Show that the monoids (Monoide) $(\mathbb{N}_0, +, 0)$
and $(2^{\mathbb{N}_0}, \cdot, 1)$ with $2^{\mathbb{N}_0} = \{2^a \mid a \in \mathbb{N}_0\}$
are isomorphic.

Approach: $\alpha : \mathbb{N}_0 \to 2^{\mathbb{N}_0},\; x \mapsto 2^x$.

**Homomorphism** (criteria for monoids from [[homomorphism]]):

(i) Compatibility (Verträglichkeit): $\;\alpha(x + y) = 2^{x+y} = 2^x \cdot 2^y = \alpha(x)\cdot\alpha(y)$ ✓
(ii) Identity element (neutrales Element): $\;\alpha(0) = 2^0 = 1$ ✓

**Bijectivity:**

- *surjective*: For every $y \in 2^{\mathbb{N}_0}$ there is, by definition, some
  $x \in \mathbb{N}_0$ with $y = 2^x = \alpha(x)$ ✓
- *injective*: Assume $\alpha$ is not injective, i.e. $\alpha(x_1) = \alpha(x_2)$ with
  $x_1 \neq x_2$. Then $2^{x_1} = 2^{x_2}$, which implies $x_1 = x_2$ — contradiction.
  $\lightning$ So $\alpha$ is injective ✓

$\Rightarrow$ $\alpha$ is an **isomorphism**. $\square$

Rule of thumb: The power law $2^{x+y} = 2^x 2^y$ **is** the homomorphism property. An
addition is translated into a multiplication.

## What it shows

- **Multiplicative ≠ additive**: A map can be compatible with one operation
  (Verknüpfung) and not with the other. For a *ring* homomorphism you need both.
- The isomorphism proof splits into two separate parts: **homomorphism** (computation)
  and **bijective** (show injective + surjective).
- Both problems follow the definition in [[homomorphism]] point by point.

## Sources

- `raw/Algebraische_strukturen_das.pdf`, p. 5–6 (problem 4.4), p. 8 (tutorial 8 ⑤)
