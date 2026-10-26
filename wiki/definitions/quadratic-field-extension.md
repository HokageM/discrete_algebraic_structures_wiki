---
type: definition
title: Quadratic Field Extension Q[√n]
aliases: [Q[sqrt n], quadratic field extension, Quadratische Körpererweiterung, quadratische Erweiterung, conjugate, Konjugierte, norm, Norm]
tags: [fields, polynomials]
sources: [raw/polynomring_das.pdf]
created: 2026-09-30
updated: 2026-09-30
status: solid
---

# Quadratic Field Extension $\mathbb{Q}[\sqrt{n}]$

## Definition

For $n \in \mathbb{Q}$ whose root does not lie in $\mathbb{Q}$:
$$\mathbb{Q}[\sqrt{n}] = \{a + b\sqrt{n} \mid a, b \in \mathbb{Q}\}$$

This is a **field**. It arises as $\mathbb{Q}[x]_{x^2-n}$ — see
[[polynomial-ring]]: the residue classes modulo $x^2 - n$ are exactly the expressions
$a + bx$, and the reduction rule $x^2 = n$ is exactly $\sqrt{n}^2 = n$.

**Negative** $n$ are also allowed; $\mathbb{Q}[\sqrt{-5}]$ and $\mathbb{Q}[\sqrt{-7}]$
occur in the source. Then $\sqrt{n}$ is imaginary, but the computation rules stay
identical.

## Arithmetic

**Addition** — componentwise:
$$(a_1 + b_1\sqrt{n}) + (a_2 + b_2\sqrt{n}) = (a_1+a_2) + (b_1+b_2)\sqrt{n}$$

**Multiplication** — expand and substitute $\sqrt{n}^2 = n$:
$$(a_1 + b_1\sqrt{n})(a_2 + b_2\sqrt{n}) = (a_1a_2 + b_1b_2 n) + (a_1b_2 + a_2b_1)\sqrt{n}$$

**Inverse** — the central formula of the source:
$$\boxed{\;(a + b\sqrt{n})^{-1} = \frac{a - b\sqrt{n}}{a^2 - b^2 n}\;}$$

Derivation (as in the source): extend the fraction by the **conjugate**.
$$\frac{1}{a+b\sqrt n} = \frac{1}{a+b\sqrt n}\cdot\frac{a-b\sqrt n}{a-b\sqrt n}
= \frac{a-b\sqrt n}{a^2 - b^2 n}$$

The denominator $N(a+b\sqrt n) = a^2 - b^2 n$ is called the **norm**; it is a rational
number, so the result again lies in $\mathbb{Q}[\sqrt n]$. The inverse exists exactly
when the norm is $\neq 0$ — and that always holds for $\sqrt n \notin \mathbb{Q}$,
except at $a = b = 0$. That is why $\mathbb{Q}[\sqrt n]$ is a field.

## Examples from the source

### $a = 1 + 5\sqrt{-5}$, $b = 1 - 5\sqrt{-5}$ in $\mathbb{Q}[\sqrt{-5}]$

$$a + b = 2$$
$$a\cdot b = 1^2 - 5^2\cdot(-5) = 1 + 125 = 126$$
$$a^{-1} = \frac{1 - 5\sqrt{-5}}{1 - 25\cdot(-5)} = \frac{1-5\sqrt{-5}}{126}
= \frac{1}{126} - \frac{5}{126}\sqrt{-5}$$

Here $a$ and $b$ are **conjugates of each other** — that is why $a+b$ is rational and
$a\cdot b$ is exactly the norm. That is not a coincidence, but the construction of the
problem.

### $a = 1 - 3\sqrt{-7}$, $b = 1 - 4\sqrt{-7}$ in $\mathbb{Q}[\sqrt{-7}]$

$$a + b = 2 - 7\sqrt{-7}$$
$$a\cdot b = 1 - 4\sqrt{-7} - 3\sqrt{-7} + 12\cdot(-7) = -83 - 7\sqrt{-7}$$
$$a^{-1} = \frac{1 + 3\sqrt{-7}}{1^2 - 3^2\cdot(-7)} = \frac{1+3\sqrt{-7}}{64}
= \frac{1}{64} + \frac{3}{64}\sqrt{-7}$$

Careful with the sign: $b = -3$, so $-b^2 n = -9\cdot(-7) = +63$, and
$1 + 63 = 64$.

### From $\mathbb{Q}[\sqrt{3}]$ (Tutorial 12.1)

$$(5-\sqrt3) + \left(10 + \tfrac12\sqrt3\right) = 15 - \tfrac12\sqrt3$$

$$\left(1+\sqrt3\right)\left(-\tfrac12 + \tfrac12\sqrt3\right)
= -\tfrac12 + \tfrac12\sqrt3 - \tfrac12\sqrt3 + \tfrac12\cdot3 = -\tfrac12 + \tfrac32 = 1$$

So the two factors are inverse to each other.

$$(2-\sqrt3)^{-1} = \frac{2+\sqrt3}{4-3} = 2+\sqrt3$$

$$(1-6\sqrt{-5})^{-1} = \frac{1+6\sqrt{-5}}{1 - 36\cdot(-5)} = \frac{1+6\sqrt{-5}}{181}$$

## Points to remember

- **Sign in the denominator**: $a^2 - b^2 n$. For negative $n$ this becomes an addition —
  the denominator grows. This is the most common mistake.
- $b$ enters **squared**: the sign of $b$ does not matter for the denominator,
  but it does for the numerator.
- **Check**: $(a+b\sqrt n)\cdot(a+b\sqrt n)^{-1}$ must equal $1$.

## Note on the notation in the source

On p. 7 the **conjugate** is twice written on the left-hand side — e.g. it states
"$(2+\sqrt3)^{-1} = \frac{2-\sqrt3}{4-3} = 2+\sqrt3$", while the problem asks for
$(2-\sqrt3)^{-1}$. The **results** are each correct for the problem posed; only the
labeling of the left-hand side is swapped. The same happens on p. 7 for
$1-6\sqrt{-5}$.

## Related

- [[polynomial-ring]] — $\mathbb{Q}[\sqrt n] \cong \mathbb{Q}[x]_{x^2-n}$
- [[irreducibility-and-fields]] — why this is a field
- [[computing-in-polynomial-rings]] — more computation exercises
- [[ring-like-structures]] — field axioms

## Sources

- `raw/polynomring_das.pdf`, p. 1, p. 3, p. 4, p. 7
