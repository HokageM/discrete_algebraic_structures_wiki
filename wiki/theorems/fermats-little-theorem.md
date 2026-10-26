---
type: theorem
title: Fermat's Little Theorem
aliases: [little Fermat, Kleiner Satz von Fermat, Fermatscher Satz]
tags: [number-theory, theorems]
sources: [raw/Zn_das.pdf]
created: 2026-09-30
updated: 2026-09-30
status: solid
---

# Fermat's little theorem (Kleiner Satz von Fermat)

## Statement

> If $n$ is **prime**, then for all $a$:
> $$a^n \equiv a \pmod n$$

This is how the theorem is stated in the source. For $a$ coprime to $n$, this is
equivalent to the more familiar form
$$a^{n-1} \equiv 1 \pmod n.$$

## What it's for

It makes computing with large exponents in $\mathbb{Z}_p$ considerably shorter: the
exponent may be reduced **modulo $p-1$** (or one splits off blocks of size $p$).

## Application from the source: $67^{33} \bmod 13$

$13$ is prime, and $67 \equiv 2 \pmod{13}$ (since $67 = 5\cdot13 + 2$).

**Split the exponent into blocks of $13$:**
$$2^{33} = 2^{13 + 13 + 7} = 2^{13}\cdot 2^{13}\cdot 2^{7}$$

**Reduce each $2^{13}$ to $2$ via Fermat:**
$$\equiv 2 \cdot 2 \cdot 2^7 = 2^9$$

**The rest via a doubling table** — each row is the previous one times $2$:

| $k$ | $2^k$ | $\bmod 13$ |
|---|---|---|
| 2 | 4 | 4 |
| 3 | 8 | 8 |
| 4 | 16 | **3** |
| 5 | 6 | 6 |
| 6 | 12 | 12 |
| 7 | 24 | **11** |
| 8 | 22 | **9** |
| 9 | 18 | **5** |

$$\boxed{67^{33} \equiv 5 \pmod{13}}$$

The doubling table is the trick: instead of exponentiating each time, one doubles and
simply subtracts $13$ whenever the value exceeds $13$.

## Second application: $75^{25} \bmod 17$

$17$ is prime, $75 \equiv 7 \pmod{17}$.

$$7^{25} = 7^{17}\cdot 7^8 \equiv 7 \cdot 7^8 = 7^9$$

| $k$ | $7^k \bmod 17$ |
|---|---|
| 2 | $49 \equiv 15$ |
| 3 | $105 \equiv 3$ |
| 4 | $21 \equiv 4$ |
| 5 | $28 \equiv 11$ |
| 6 | $77 \equiv 9$ |
| 7 | $63 \equiv 12$ |
| 8 | $84 \equiv 16$ |
| 9 | $112 \equiv \mathbf{10}$ |

$$\boxed{75^{25} \equiv 10 \pmod{17}}$$

The source computes the same problem **additionally** via square-and-multiply
($25_{10} = 11001_2$) and arrives at the same result $10$ — see
[[modular-exponentiation]]. That is a good check.

## Which method when?

| | Requirement | Effort |
|---|---|---|
| **Fermat's little theorem** | $n$ **prime** | reduce exponent mod $n-1$, then small remainder |
| **Square-and-multiply** | always | $\approx \log_2(\text{exponent})$ squarings |

For prime $n$, apply Fermat first, then compute the remaining exponent via doubling or
square-and-multiply. For composite $n$, only square-and-multiply helps (or Euler's
theorem with $\varphi(n)$ — see [[euler-phi-function]]).

## Related pages

- [[modular-exponentiation]] — worked exponentiation problems, also without Fermat
- [[euler-phi-function]] — the generalization $a^{\varphi(n)} \equiv 1$
- [[residue-class-ring]] — computing in $\mathbb{Z}_n$
- [[units-and-zero-divisors]] — $\mathbb{Z}_p$ is a field

## Sources

- `raw/Zn_das.pdf`, p. 1, p. 3, p. 13
