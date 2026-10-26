---
type: example
title: Submonoid Proofs
aliases: [submonoid proofs, Untermonoid-Nachweise]
tags: [algebraic-structures, example, substructures]
sources: [raw/Algebraische_strukturen_das.pdf]
created: 2026-09-30
updated: 2026-09-30
status: needs-review
---

# Submonoid Proofs

Four worked problems following the scheme from [[substructures]]:
(i) closure (Abgeschlossenheit), (ii) identity element (neutrales Element).

## 1. $U = \{3n \mid n \in \mathbb{N}_0\}$ in $(\mathbb{N}_0, +, 0)$

**(i) Closure.** Let $3n, 3m \in U$. Then
$$3n + 3m = 3(n+m) \in U \quad ✓$$
**(ii) Identity element.** $0 = 3 \cdot 0 \in U$ ✓

$\Rightarrow$ $U$ is a submonoid (Untermonoid). $\square$

Textbook example of the technique: set up elements in their **general form** and show
that the result again has this form.

## 2. $U = \left\{\tfrac{a}{4^i} \mid a \in \mathbb{Z},\, i \in \mathbb{N}_0\right\}$ in $(\mathbb{Q}, \cdot, 1)$

**(i) Closure.** Let $\tfrac{a}{4^i}, \tfrac{b}{4^j} \in U$. Then
$$\frac{a}{4^i} \cdot \frac{b}{4^j} = \frac{ab}{4^{\,i+j}} \in U \quad ✓$$
**(ii) Identity element.** $1 = \tfrac{1}{4^0} \in U$ ✓

**Which elements are invertible?** Let $\tfrac{b}{4^j}$ be the inverse of $\tfrac{a}{4^i}$:
$$\frac{a}{4^i} \cdot \frac{b}{4^j} = 1 \;\Longleftrightarrow\; ab = 4^{\,i+j}
\;\Longleftrightarrow\; b = \frac{4^{\,i+j}}{a}$$
This is solvable in $\mathbb{Z}$ precisely when $a$ is a divisor (Teiler) of a power of
four, i.e. a power of two. The source concludes:
$$\left\{\tfrac{a}{4^i} \in U \;\middle|\; a = 2^k,\, k \in \mathbb{N}_0\right\}
\text{ is the set of invertible elements.}$$

## 3. $U = \left\{\tfrac{a}{2^i} \mid a \in \mathbb{Z},\, i \in \mathbb{N}_0\right\}$ in $(\mathbb{Q}\setminus\{0\}, \cdot, 1)$

**(i)** $\tfrac{a}{2^i} \cdot \tfrac{b}{2^j} = \tfrac{ab}{2^{\,i+j}} \in U$ ✓
**(ii)** $1 = \tfrac{1}{2^0} \in U$ ✓

$\Rightarrow$ commutative (kommutativ) monoid.

**Is $(U, \cdot, 1)$ a group?** (tutorial 9 ④) No. For the inverse $\tfrac{b}{2^j}$ of
$\tfrac{a}{2^i}$ we would need
$$\frac{a}{2^i}\cdot\frac{b}{2^j} = 1 \;\Longleftrightarrow\; ab = 2^{\,i+j}
\;\Longleftrightarrow\; b = \frac{2^{\,i+j}}{a},$$
and this lies in $\mathbb{Z}$ only if $a$ is a (possibly negative) power of two. For
$a = 3$, for instance, there is no inverse in $U$. Moreover $U$ contains $0$, which is
never invertible in a multiplicative group.

$\Rightarrow$ $U$ is a monoid, but **not a group**. $\square$

## 4. Idempotent elements in a commutative monoid

Let $M$ be a commutative monoid. Show that
$$U = \{a \in M \mid a^n \text{ is idempotent for some } n > 1\}$$
is a submonoid of $M$. (An element $a$ is called **idempotent** if $a \cdot a = a$.)

**(i) Closure.** Let $a \in U$ with $a^h \cdot a^h = a^h$ for some $h > 1$ and
$b \in U$ with $b^l \cdot b^l = b^l$ for some $l > 1$. Choose $m = h \cdot l$:
$$(ab)^{hl} \cdot (ab)^{hl} = a^{2hl} \cdot b^{2hl} = a^{hl} \cdot b^{hl} = (ab)^{hl} \quad ✓$$
(Here **commutativity** (Kommutativität) is used to split $(ab)^n = a^n b^n$.)

**(ii) Identity element.** $e \cdot e = e$, so $e$ is idempotent and lies in $U$ ✓

$\square$

## Contradictions

Two spots in the source are erroneous:

1. **p. 4, closure for $\tfrac{a}{4^i}$.** The source writes
   $$\frac{a}{4^i} \cdot \frac{b}{4^j} = \frac{ab}{4^{\,i \cdot j}}$$
   The correct expression is $4^{\,i+j}$: when multiplying equal bases, the exponents are
   **added**, not multiplied. With $i = j = 0$ the error is not visible, but with
   $i = j = 1$ it is: $\tfrac{a}{4}\cdot\tfrac{b}{4} = \tfrac{ab}{16} = \tfrac{ab}{4^2}$,
   not $\tfrac{ab}{4^1}$. Corrected above.

2. **p. 4, invertible elements.** The source states $a = 2^k$ and overlooks the
   **negative** powers of two. $a = -2^k$ is also invertible, e.g. $-1 = \tfrac{-1}{4^0}
   \in U$ is invertible with inverse $-1$. The correct condition is $a = \pm 2^k$.

3. **p. 12, ambient structure.** The source names $(\mathbb{Q}\setminus\{0\}, \cdot, 1)$
   as the ambient structure of $U = \left\{\tfrac{a}{2^i}\right\}$. But because $a = 0$ is
   allowed, $U$ contains $0$ and is therefore not a subset of $\mathbb{Q}\setminus\{0\}$.
   Either $a \neq 0$ must be required, or the ambient structure is $(\mathbb{Q}, \cdot, 1)$
   — as on p. 4 in the analogous example.

4. **p. 14, justification for "not a group".** The source deduces from
   $b = \tfrac{2^i \cdot 2^j}{a}$ that $b \notin \mathbb{Q}$. This is wrong: for
   $a \neq 0$, this expression is **always** rational. The correct reason is that $b$
   must lie in $U$, i.e. $\tfrac{2^{i+j}}{a}$ must be of the form
   $\tfrac{\text{integer}}{2^k}$ — which fails as soon as $a$ is not a power of two.
   Corrected above.

## What it shows

- The proof is always two lines long, because associativity (Assoziativität) and
  commutativity are **inherited** from the ambient structure — that is the whole point of
  [[substructures]].
- Point 2 shows the typical follow-up question: "which elements are invertible?" The
  answer separates monoid from group, see [[group-like-structures]].
- Point 4 is the most demanding case: here the exponent $m = h\cdot l$ has to be
  constructed by hand.

## Sources

- `raw/Algebraische_strukturen_das.pdf`, p. 3 (problem 4.2), p. 4 (problem 4.4),
  p. 8 (tutorial 8 ④), p. 12 (tutorial 8 ③)
