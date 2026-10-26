---
type: example
title: Double counting (set systems)
aliases: [Doppeltes Abzählen, Inzidenzmatrix, double counting, Mengensystem, incidence matrix]
tags: [combinatorics, exam]
sources: [raw/kombinatorik_das.pdf]
created: 2026-09-30
updated: 2026-09-30
status: solid
---

# Double counting

## The problem type

> Is there a set system (Mengensystem) of $m$-element subsets of $\{1,\dots,n\}$ such that
> each of the numbers $1$ through $n$ is contained in exactly $r$ sets of the system?

This is the second, more elaborate sub-problem of the exam's combinatorics problem
(usually worth 4 points).

## The method

Set up the **incidence matrix (Inzidenzmatrix)**: rows $=$ the $k$ sets
$A_1,\dots,A_k$ of the system, columns $=$ the numbers $1,\dots,n$. Entry $1$ if the
number lies in the set, otherwise $0$.

|  | $1$ | $2$ | $3$ | $4$ | $\dots$ | $n$ |
|---|---|---|---|---|---|---|
| $A_1$ | 1 | 1 | 1 | 0 | | 0 |
| $A_2$ | 0 | 1 | 0 | 1 | | 0 |
| $\vdots$ | | | | | | |
| | $r$ | $r$ | $r$ | $r$ | | $r$ |

Now count the ones **in two ways**:

- **row-wise:** each set has $m$ elements, there are $k$ sets $\Rightarrow m\cdot k$
- **column-wise:** each of the $n$ numbers occurs $r$ times $\Rightarrow n\cdot r$

$$\boxed{\;m\cdot k \;=\; n\cdot r\;}$$

Since $k$ is the number of sets, $k = \dfrac{n\cdot r}{m}$ must be a **natural number**.
If it is not, no such set system exists.

> [!note] Important
> The condition is only **necessary**, not sufficient. If the division works out, that
> does not yet prove the system exists. In all problems of the source the division does
> *not* work out — the answer is always "No", and that is proven.

## Problem 1 (exam set A)

$9$-element subsets of $\{1,\dots,20\}$, each number in $7$ sets.

$$9\cdot k = 20\cdot 7 = 140$$
$$k = \frac{140}{9} = \frac{2^2\cdot 5\cdot 7}{9} \notin \mathbb N$$

$140$ does not contain the prime factor $3$, so $9 = 3^2$ cannot divide it.
**No, no such set system exists.**

## Problem 2 (exam set B)

$4$-element subsets of $\{1,\dots,11\}$, each number in $5$ sets.

$$5\cdot 11 = 4\cdot k \quad\Longrightarrow\quad 55 = 4k \quad\Longrightarrow\quad k = \frac{55}{4}\notin\mathbb N_0$$

$55$ is odd, $4$ cannot divide it. **No.**

## Problem 3 (exercise 5 ①)

$3$-element subsets of $\{1,\dots,8\}$, each number in $5$ sets.
Here the source calls the sought number $h$ instead of $k$ and sketches the system with
$A_1 = \{1,2,3\}$, $A_2 = \{2,4,5\}$, …

$$5\cdot 8 = 3\cdot h \quad\Longrightarrow\quad 40 = 3h \quad\Longrightarrow\quad h = \frac{40}{3}\notin\mathbb N$$

Digit sum of $40$ is $4$, so $40$ is not divisible by $3$. **No.**

## Model solution in four lines

1. Set up the incidence matrix (rows = sets, columns = numbers).
2. Count ones row-wise: $m\cdot k$.
3. Count ones column-wise: $n\cdot r$.
4. Equate, solve for $k$, check divisibility; answer in one sentence.

For step 4 a divisibility argument via [[laws-of-gcd|prime factors]] suffices —
no division is needed.

## Related

- [[counting-exercises]] — the first part of the same exam problem
- [[urn-model]], [[box-model]] — the formula tables
- [[combinatorics]] — chapter overview

## Sources

- `raw/kombinatorik_das.pdf`, p. 3, p. 5, p. 7
