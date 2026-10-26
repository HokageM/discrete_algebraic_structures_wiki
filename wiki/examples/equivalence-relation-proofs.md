---
type: example
title: Proving equivalence relations
aliases: [proving equivalence relations, Äquivalenzklassen bestimmen, Äquivalenzrelationen nachweisen]
tags: [relations, example]
sources: [raw/relation_und_permutation_das.pdf]
created: 2026-09-30
updated: 2026-09-30
status: solid
---

# Proving equivalence relations

Two fully worked-out proofs on [[equivalence-relation]]. The scheme is always the same:
check off the three properties **reflexive, symmetric, transitive** one by one, then
give the [[equivalence-relation|equivalence classes (Äquivalenzklassen)]] and the
quotient set (Quotientenmenge).

## 1. Fiber relation: $xRy :\Leftrightarrow f(x) = f(y)$

**Problem.** Let $f : \mathbb{N}_0 \to \mathbb{N}_0$ be an arbitrary map. Show that
$$xRy \quad :\Longleftrightarrow \quad f(x) = f(y)$$
is an equivalence on $\mathbb{N}_0$.

**(i) reflexive.**
$$xRx \iff f(x) = f(x) \quad \checkmark$$

**(ii) symmetric.**
$$xRy \iff f(x) = f(y) \iff f(y) = f(x) \iff yRx \quad \checkmark$$

**(iii) transitive.**
$$xRy \wedge yRz \iff f(x) = f(y) \;\wedge\; f(y) = f(z)
\;\Rightarrow\; f(x) = f(z) \iff xRz \quad \checkmark$$

The whole proof is nothing but the reflexivity, symmetry and transitivity of
**equality** $=$ on the target set. This is the core insight: every map generates an
equivalence relation on its domain, the *fibers* of $f$.

**Equivalence classes for a concrete $f$.** With
$$f(x) = \begin{cases} 1 & x \text{ even} \\ 0 & \text{otherwise} \end{cases}$$
on $\mathbb{N}_0 = \{0,1,2,3,4,\dots\}$ the value pattern is $1,0,1,0,1,\dots$, giving
$$\overline{0} = \{0,2,4,6,\dots\} \quad (f = 1), \qquad
\overline{1} = \{1,3,5,7,\dots\} \quad (f = 0).$$
Two classes that disjointly cover $\mathbb{N}_0$ — exactly as
[[equivalence-relation|the class decomposition]] requires.

## 2. $aRb :\Leftrightarrow 3 \mid a^2 - b^2$ on $\mathbb{Z}$

**(i) reflexive.**
$$aRa \iff 3 \mid (a^2 - a^2) \iff 3 \mid 0 \quad \checkmark$$

**(ii) symmetric.**
$$aRb \iff 3 \mid (a^2-b^2) \iff 3 \mid -(a^2-b^2) \iff 3 \mid (b^2-a^2) \iff bRa \quad \checkmark$$

**(iii) transitive.** Let
$$aRb \iff a^2 - b^2 = 3h, \quad h \in \mathbb{Z},$$
$$bRc \iff b^2 - c^2 = 3\ell, \quad \ell \in \mathbb{Z}.$$
Then
$$a^2 - c^2 = \underbrace{(a^2-b^2)}_{=3h} + \underbrace{(b^2-c^2)}_{=3\ell} = 3h + 3\ell = 3(h+\ell),$$
so $3 \mid (a^2 - c^2)$, i.e. $aRc$. $\checkmark$

**Equivalence classes.** $3 \mid a^2 - b^2$ holds exactly when $a^2 \equiv b^2 \pmod 3$.
Squares modulo 3 are only $0$ or $1$:

| $a \bmod 3$ | $0$ | $1$ | $2$ |
|---|---|---|---|
| $a^2 \bmod 3$ | $0$ | $1$ | $1$ |

Hence there are **two** classes:
$$\overline{3} = \{0, \pm3, \pm6, \pm9, \dots\} \quad \text{(multiples of 3)},$$
$$\overline{1} = \{\pm1, \pm2, \pm4, \pm5, \pm7, \pm8, \dots\} \quad \text{(all the rest)},$$
$$\overline{A} = \{\overline{3}, \overline{1}\} \quad \text{quotient set.}$$

Notable: although the relation is defined via $\bmod 3$, it does **not** produce three
classes as in $\mathbb{Z}_3$ (cf. [[equivalence-relation]]), but only two — the residue
classes $1$ and $2$ merge, because $1^2 \equiv 2^2 \equiv 1$.

## Key points

- When asked to "show $R$ is an equivalence", never guess the classes — first the three
  properties, then the classes.
- For divisibility relations the trick is always the same: write $d \mid x$ as
  $x = d\cdot k$ with $k \in \mathbb{Z}$, then add/negate. See also
  [[laws-of-integers]].
- The classes are only determined once a set of representatives (Vertretermenge) can be
  given.

## Related

- [[equivalence-relation]] — definition, classes, quotient set
- [[properties-of-homogeneous-relations]] — the individual properties
- [[checking-relation-properties]] — when a property *fails*
- [[laws-of-integers]] — divisibility rules

## Sources

- `raw/relation_und_permutation_das.pdf`, p. 4 (problem 1.3), p. 10 (exercise 3.3), p. 12 (exercise 3.3)
