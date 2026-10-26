---
type: example
title: Determining units and zero divisors
aliases: [units and zero divisors exercises, Einheiten und Nullteiler bestimmen]
tags: [number-theory, example]
sources: [raw/Zn_das.pdf]
created: 2026-09-30
updated: 2026-09-30
status: solid
---

# Determining units and zero divisors

Exam problems of the type "Determine all units (Einheiten) and zero divisors
(Nullteiler) of the residue class ring $\mathbb{Z}_n$." Basis:
[[units-and-zero-divisors]].

## The recipe in three steps

1. **Factorize $n$**: $n = p_1^{e_1}\cdots p_r^{e_r}$.
2. **Zero divisors** = all $a \in \{2,\dots,n-1\}$ divisible by **any** $p_i$.
3. **Units** = the rest.

Check: the number of units must be $\varphi(n)$ — see
[[euler-phi-function]]. And units $+$ zero divisors $+ \{0\} = n$ elements.

## 1. $\mathbb{Z}_{16}$

$$16 = 2^4$$

Only prime factor: $2$. So all **even** numbers are zero divisors, all **odd** numbers
units.

| | |
|---|---|
| Units | $1, 3, 5, 7, 9, 11, 13, 15$ |
| Zero divisors | $2, 4, 6, 8, 10, 12, 14$ |

Check: $8$ units $= \varphi(16) = 16\cdot\frac12 = 8$ ✓.
$8 + 7 + 1 = 16$ ✓.

## 2. $\mathbb{Z}_{15}$

$$15 = 3\cdot 5$$

Zero divisors: multiples of $3$ ($3,6,9,12$) and of $5$ ($5,10$).

| | |
|---|---|
| Units | $1, 2, 4, 7, 8, 11, 13, 14$ |
| Zero divisors | $3, 5, 6, 9, 10, 12$ |

Check: $\varphi(15) = 15\cdot\frac23\cdot\frac45 = 8$ ✓. $8+6+1 = 15$ ✓.

## 3. $\mathbb{Z}_{20}$

$$20 = 4\cdot5 = 2^2\cdot5$$

The source phrases it exactly like this: "All $a \in \mathbb{Z}_{20}$ divisible by $2$
or $5$ are zero divisors."

| | |
|---|---|
| Units | $1, 3, 7, 9, 11, 13, 17, 19$ |
| Zero divisors | $2, 4, 5, 6, 8, 10, 12, 14, 15, 16, 18$ |

Check: $\varphi(20) = 20\cdot\frac12\cdot\frac45 = 8$ ✓. $8 + 11 + 1 = 20$ ✓.

## 4. $\mathbb{Z}_6$ — with the operation table (Verknüpfungstafel)

$$6 = 2\cdot3$$

| | |
|---|---|
| Units | $1, 5$ |
| Zero divisors | $2, 3, 4$ |

The source reads this directly off the multiplication table from
[[residue-class-ring]]:

- Row $1$: $0,1,2,3,4,5$ — contains $1$ → unit ($1\cdot1=1$).
- Row $5$: $0,5,4,3,2,1$ — contains $1$ → unit ($5\cdot5 = 25 \equiv 1$).
- Row $2$: $0,2,4,0,2,4$ — contains $0$ at $2\cdot3$ → zero divisor.
- Row $3$: $0,3,0,3,0,3$ → zero divisor.
- Row $4$: $0,4,2,0,4,2$ → zero divisor, $4\cdot3 = 12 \equiv 0$.

Computed explicitly:
$$2\cdot3 = 6 \equiv 0 \pmod 6, \qquad 4\cdot3 = 12 \equiv 0 \pmod 6$$

Check: $\varphi(6) = 2$ ✓.

## Summary

| $n$ | Factorization | #units $=\varphi(n)$ | #zero divisors |
|---|---|---|---|
| $6$ | $2\cdot3$ | $2$ | $3$ |
| $15$ | $3\cdot5$ | $8$ | $6$ |
| $16$ | $2^4$ | $8$ | $7$ |
| $20$ | $2^2\cdot5$ | $8$ | $11$ |

**Observation:** The "smoother" $n$ is (many distinct small prime factors), the fewer
units. For a prime power $p^e$, only every $p$-th element drops out.

## Error in the source

On p. 8, for $\mathbb{Z}_6$ it first states "zero divisors: $0,2,3$"; that is doubly
incomplete — $4$ is missing, and $0$ does not belong in the list. Two lines later the
correct answer "$2,3,4$ zero divisors" appears. Apparently a first, discarded attempt.

## Related

- [[units-and-zero-divisors]] — definitions and the $\gcd$ criterion
- [[euler-phi-function]] — count instead of list
- [[computing-inverses]] — computing the inverse for units
- [[residue-class-ring]] — operation tables

## Sources

- `raw/Zn_das.pdf`, p. 2 (problem 5.1), p. 3 (problem 5.1), p. 8 (exercise 10.1), p. 9 (exercise 10.1)
