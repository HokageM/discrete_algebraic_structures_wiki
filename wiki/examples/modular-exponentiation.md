---
type: example
title: Computing Powers in Z_n
aliases: [modular exponentiation, Potenzen in Z_n berechnen, square-and-multiply]
tags: [number-theory, example]
sources: [raw/Zn_das.pdf]
created: 2026-09-30
updated: 2026-09-30
status: solid
---

# Computing Powers in $\mathbb{Z}_n$

Exam problems of the type "compute the power $a^k$ in the residue class ring
(Restklassenring) $\mathbb{Z}_n$." Never multiply it all out — there are three
techniques.

## The three techniques

**0. Reduce the base.** Always first: $a \bmod n$. From $83^{25}$ in $\mathbb{Z}_9$ we get
$2^{25}$.

**1. Square-and-multiply.** Decompose the exponent in binary, then square and multiply by
the base at every $1$-bit. Cost $\approx \log_2 k$ steps.

**2. Fermat's little theorem** (kleiner Fermat, only if $n$ is **prime**): $a^n \equiv a$,
so blocks of $n$ may be pulled out of the exponent. See [[fermats-little-theorem]].

**3. Search for the order.** Build a table of powers until a $1$ appears; after that
everything repeats cyclically. Often the fastest route for small $n$.

## 1. $83^{25}$ in $\mathbb{Z}_9$

$$83 = 81 + 2 \;\Longrightarrow\; 83 \equiv 2 \pmod 9$$

$$25 = 16 + 8 + 1 \quad (= 11001_2)$$

Table of powers of $2$ modulo $9$:

| $k$ | 1 | 2 | 3 | 4 | 5 | 6 |
|---|---|---|---|---|---|---|
| $2^k \bmod 9$ | 2 | 4 | 8 | 7 | 5 | **1** |

After six steps we are back at $1$ — the **order of $2$ is $6$**. Hence
$$2^{25} = 2^{24}\cdot2 = (2^6)^4\cdot2 \equiv 1^4\cdot2 = \boxed{2}$$

The source computes this the same way via $2^6 = 64 \equiv 1 \pmod 9$ and uses
$1^{2^a} = 1$.

## 2. $75^{25}$ in $\mathbb{Z}_{17}$ — both routes

$$75 = 68 + 7 \;\Longrightarrow\; 75 \equiv 7 \pmod{17}$$

**Route A: square-and-multiply**, $25_{10} = 11001_2$.
Read from left to right this gives the bracketing
$$7^{25} = \bigl(((7^2\cdot7)^2)^2\bigr)^2\cdot7$$

| Step | Computation | $\bmod 17$ |
|---|---|---|
| $7^2$ | $49$ | $15$ |
| $\cdot\,7$ | $15\cdot7 = 105$ | $3$ |
| $(\ )^2$ | $3^2 = 9$ | $9$ |
| $(\ )^2$ | $9^2 = 81$ | $13$ |
| $(\ )^2$ | $13^2 = 169$ | $16$ |
| $\cdot\,7$ | $16\cdot7 = 112$ | $\mathbf{10}$ |

**Route B: Fermat's little theorem**, since $17$ is prime:
$$7^{25} = 7^{17}\cdot7^{8} \equiv 7\cdot7^8 = 7^9$$
and from the table of powers $7^9 \equiv 10$.

$$\boxed{75^{25} \equiv 10 \pmod{17}}$$

Both routes agree — precisely why the source computes them side by side.

## 3. $25^{99}$ in $\mathbb{Z}_{17}$

$$25 \equiv 8 \pmod{17}, \qquad 99 = 64+32+2+1$$

| Computation | $\bmod 17$ |
|---|---|
| $8^2 = 64$ | $13$ |
| $13\cdot8 = 104$ | $2$ |
| $2^2 = 4$ | $4$ |
| $4^2 = 16$ | $16$ |
| $16^2 = 256$ | $1$ |

$$\boxed{25^{99} \equiv 2 \pmod{17}}$$

**Cross-check via the order:** $8 = 2^3$, so $8^{99} = 2^{297}$. Since
$2^4 = 16 \equiv -1$, we get $2^8 \equiv 1$, i.e. the order of $2$ is $8$. With
$297 = 37\cdot8 + 1$ it follows that $2^{297} \equiv 2$ ✓

## 4. $52^{18}$ in $\mathbb{Z}_9$

$$52 \equiv 7 \pmod 9, \qquad 18 = 16 + 2$$

| Computation | $\bmod 9$ |
|---|---|
| $7^2 = 49$ | $4$ |
| $4^2 = 16$ | $7$ |
| $7\cdot4 = 28$ | $1$ |
| $1^2$ | $1$ |

$$\boxed{52^{18} \equiv 1 \pmod 9}$$

**Cross-check:** The order of $7$ modulo $9$ is $3$ ($7, 4, 1$), and $3 \mid 18$ ✓

## 5. $67^{33}$ in $\mathbb{Z}_{13}$

$$67 \equiv 2 \pmod{13}$$

Via Fermat ($13$ prime): $2^{33} = 2^{13}\cdot2^{13}\cdot2^7 \equiv 2\cdot2\cdot2^7 = 2^9$,
and from the doubling table $2^9 = 512 \equiv 5$.

$$\boxed{67^{33} \equiv 5 \pmod{13}}$$

Worked out in detail in [[fermats-little-theorem]].

> [!warning] Error in the source
> On p. 12, the same problem is computed twice. The **first** computation uses
> $33 = 32+1$ and arrives at $6$ — this is **wrong**. The correct value is $2^{32} \equiv 9$
> and hence $2^{33} \equiv 18 \equiv 5$. The **second** computation on the same page
> correctly yields $5$.
>
> On p. 10, in the $\mathbb{Z}_{17}$ computation, the line reads
> "$16^2 = 256 \equiv 1 \bmod 13$" — this should read $\bmod\ 17$. The value $1$ happens
> to be correct in both cases.
>
> On p. 13 it says at the end "$2^9 = 18 = 5 \bmod 13 = 67^{13}$"; this should read
> $67^{33}$.

## Key points

- **Reduce the base first** — saves half the work.
- **Reduce after every step**, never carry large numbers along.
- For prime $n$: reduce the exponent modulo $n-1$ (Fermat).
- For composite $n$: reduce the exponent modulo $\varphi(n)$, provided
  $\gcd(a,n)=1$ — see [[euler-phi-function]].
- **Searching for the order almost always pays off**: as soon as a $1$ shows up in the
  table of powers, the problem shrinks to a remainder computation in the exponent.
- Computing two independent routes is the best error control — the source demonstrates
  exactly that in example 2, and example 5 shows what happens without such a check.

## Related

- [[fermats-little-theorem]] — the shortcut for prime $n$
- [[euler-phi-function]] — the generalization
- [[residue-class-ring]] — computing in $\mathbb{Z}_n$
- [[computing-inverses]] — the other major computational technique

## Sources

- `raw/Zn_das.pdf`, p. 1, p. 2 (problem 5.2), p. 3 (problem 5.2), p. 10 (tutorial 10.3),
  p. 12 (tutorial 12.5), p. 13
