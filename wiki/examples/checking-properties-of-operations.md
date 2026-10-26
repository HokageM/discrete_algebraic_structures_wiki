---
type: example
title: Checking operations for associativity and commutativity
aliases: [checking associativity and commutativity, Operationen auf Assoziativität und Kommutativität prüfen]
tags: [algebraic-structures, example, operation]
sources: [raw/Algebraische_strukturen_das.pdf]
created: 2026-09-30
updated: 2026-09-30
status: solid
---

# Checking operations for associativity and commutativity

## Problem

Examine various operations (Verknüpfungen) $\circ$ for associativity (Assoziativität) and
commutativity (Kommutativität).
(Source: exam problem 4.1 on p. 3 and p. 5, exercise 8 ① on p. 10 and p. 12.)

## Solution

The scheme is always the same:
$$\text{associative?} \quad x \circ (y \circ z) \overset{?}{=} (x \circ y) \circ z
\qquad\qquad \text{commutative?} \quad x \circ y \overset{?}{=} y \circ x$$
Substitute the definition **from the inside out** and compare the resulting terms.

### 1. $x \circ y = \tfrac{1}{2}xy$ on $\mathbb{Q}$

$$x \circ (y \circ z) = x \circ \tfrac12 yz = \tfrac12 x \cdot \tfrac12 yz = \tfrac14 xyz$$
$$(x \circ y) \circ z = \tfrac12 xy \circ z = \tfrac12 \cdot \tfrac12 xy \cdot z = \tfrac14 xyz$$
**associative ✓**. And $\tfrac12 xy = \tfrac12 yx$, so **commutative ✓**.

### 2. $x \circ y = x + y + 1$ on $\mathbb{Z}$

$$a \circ (b \circ c) = a + (b + c + 1) + 1 = a+b+c+2$$
$$(a \circ b) \circ c = (a+b+1) + c + 1 = a+b+c+2$$
**associative ✓**. And $a + b + 1 = b + a + 1$, so **commutative ✓**.

### 3. $x \circ y = x + y$ on $\mathbb{R}$

**associative ✓, commutative ✓** — this is exactly [[laws-of-integers]].

### 4. $x \circ y = x - y$ on $\mathbb{R}$

$$x \circ (y \circ z) = x - (y - z) = x - y + z \;\neq\; (x-y) - z = x - y - z$$
**not associative ✗**. And $x - y \neq y - x$, so **not commutative ✗**.

### 5. $x \circ y = x^y$ on $\mathbb{R}$

$$x^{(y^z)} \;\neq\; (x^y)^z = x^{yz}$$
**not associative ✗**. And $x^y \neq y^x$, so **not commutative ✗**.

### 6. $x \circ y = e^{x+y}$ on $\mathbb{R}$

$$x \circ (y \circ z) = e^{\left(x + e^{y+z}\right)} \;\neq\; e^{\left(e^{x+y} + z\right)} = (x \circ y) \circ z$$
**not associative ✗**. But
$$e^{x+y} = e^{y+x} \quad \text{— \textbf{commutative ✓}}$$

## What it shows

- **Commutative but not associative**: $e^{x+y}$ is the most instructive example. The
  two properties are independent of each other; both must be checked separately.
- For **associativity** a single counterexample suffices to disprove it. The source
  mostly argues with the general term shape ("$\neq$ for $\mathbb{R}$") instead of
  concrete numbers — a cleaner approach would be an explicit counterexample, e.g.
  $1 - (2 - 3) = 2 \neq -4 = (1-2)-3$.
- The operation $\tfrac12 xy$ is associative **and** commutative, but has no identity
  element (neutrales Element) in $\mathbb{Q}$ other than $2$ (since $x \circ 2 = x$) — so
  it is more than a semigroup (Halbgruppe). The source does not ask about this.
- Terms: [[properties-of-operations]]; the resulting structures:
  [[group-like-structures]].

## Sources

- `raw/Algebraische_strukturen_das.pdf`, p. 3 (problem 4.1), p. 5 (problem 4.1),
  p. 10 and p. 12 (exercise 8 ①)
