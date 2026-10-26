---
type: definition
title: Units and Zero Divisors
aliases: [units and zero divisors, Einheiten und Nullteiler, unit, Einheit, zero divisor, Nullteiler, invertible, invertierbar]
tags: [ring-theory, number-theory]
sources: [raw/Zn_das.pdf, raw/Algebraische_strukturen_das.pdf]
created: 2026-09-30
updated: 2026-09-30
status: solid
---

# Units and Zero Divisors

## Definitions

Let $(R,+,\cdot,0,1)$ be a commutative [[ring-like-structures|ring]].

**Unit** (*Einheit*). $r \in R$ is called a unit $:\Longleftrightarrow r$ is invertible:
$$\exists\, s \in R: \; r\cdot s = 1, \qquad r^{-1} := s$$

**Zero divisor** (*Nullteiler*). $r \in R$ is called a zero divisor $:\Longleftrightarrow$
$$\exists\, s \in R,\, s \neq 0: \; r\cdot s = 0$$

The set of units is denoted $R^*$; together with $\cdot$ it forms a
[[group-like-structures|group]].

## The central criterion in $\mathbb{Z}_n$

> **Theorem.** In $\mathbb{Z}_n$, every element $\neq 0$ is **either** a unit **or**
> a zero divisor — never both, never neither. Specifically:
> $$\gcd(a,n) = 1 \;\Longrightarrow\; a \text{ is a unit}$$
> $$\gcd(a,n) > 1 \;\Longrightarrow\; a \text{ is a zero divisor}$$

**Proof of the zero-divisor direction** (as in the source):

Let $g = \gcd(a,n) > 1$. Write
$$a = g\cdot \ell, \qquad n = g\cdot h.$$
In $\mathbb{Z}_n$ we have $n \equiv 0$, so
$$0 \equiv n \cdot \ell = (g\cdot h)\cdot\ell = (g\cdot\ell)\cdot h = a\cdot h.$$
Since $g > 1$, $h = n/g < n$, so $h \not\equiv 0$. Thus $a\cdot h = 0$ with
$h \neq 0$ — $a$ is a zero divisor. $\square$

**Example from the source.** $a = 4$, $n = 6$: $g = \gcd(4,6) = 2$, $\ell = 2$, $h = 3$.
$$4 \cdot 3 = 12 \equiv 0 \pmod 6 \quad\text{with } 3 \neq 0$$

The unit direction follows from the [[laws-of-gcd|extended Euclidean algorithm]]: from
$\gcd(a,n)=1$ one gets $1 = xa + yn$, so $xa \equiv 1 \pmod n$ — see
[[computing-inverses]].

## Practical consequence

Factor $n$ into primes $n = p_1^{e_1}\cdots p_r^{e_r}$. Then

- $a$ is a **zero divisor** $\iff$ $a$ is divisible by **at least one** of the $p_i$,
- $a$ is a **unit** $\iff$ $a$ is divisible by **none** of the $p_i$.

That is the recipe with which the source solves every unit/zero-divisor problem in one
line — see [[determining-units-and-zero-divisors]].

**Special case $n = p$ prime.** Then every $a \neq 0$ is coprime to $p$, hence a unit:
$\mathbb{Z}_p$ is a **field**. For composite $n$, $\mathbb{Z}_n$ is not even
zero-divisor-free, hence not an [[ring-like-structures|integral domain]].

## Relation to the ring hierarchy

| $n$ | $\mathbb{Z}_n$ is |
|---|---|
| prime | field (all $a\neq0$ invertible) |
| composite | commutative ring **with** zero divisors |

Cf. the hierarchy in [[ring-like-structures]]: being zero-divisor-free is exactly the
condition that would make $\mathbb{Z}_n$ an integral domain.

## Pitfall

The source first writes, for $\mathbb{Z}_6$, "zero divisors: $0,2,3$" and later corrects
this to "$2,3,4$". The correct statement is: **$0$ does not count** (by the usual
convention $0$ is formally a zero divisor but is excluded from this classification), and
$4$ belongs to the list, since $4\cdot3 = 12 \equiv 0 \pmod 6$.

The correct answer for $\mathbb{Z}_6$:

| | |
|---|---|
| Units | $1, 5$ |
| Zero divisors | $2, 3, 4$ |

## Related

- [[residue-class-ring]] — the operation tables from which both can be read off
- [[euler-phi-function]] — counts the units
- [[computing-inverses]] — inverse via the extended Euclidean algorithm
- [[determining-units-and-zero-divisors]] — worked-out exercises
- [[ring-like-structures]] — integral domain, field
- [[irreducibility-and-fields]] — the analogue for polynomial rings
- [[laws-of-gcd]] — gcd laws

## Sources

- `raw/Zn_das.pdf`, p. 4, p. 8, p. 9
