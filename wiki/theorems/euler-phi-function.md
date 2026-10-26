---
type: theorem
title: Euler's Totient Function
aliases: [phi, Euler function, totient, Eulersche Phi-Funktion, Anzahl der Einheiten, number of units]
tags: [number-theory, theorems]
sources: [raw/Zn_das.pdf]
created: 2026-09-30
updated: 2026-09-30
status: solid
---

# Euler's $\varphi$-function (Eulersche Phi-Funktion)

## Statement

$\varphi(n)$ counts the [[units-and-zero-divisors|units]] (Einheiten) of $\mathbb{Z}_n$,
i.e. the numbers in $\{1,\dots,n\}$ that are coprime (teilerfremd) to $n$:
$$\varphi(n) = \bigl|\mathbb{Z}_n^*\bigr| = \#\{a \mid 1 \le a \le n,\ \gcd(a,n)=1\}$$

**Product formula.** If $n = p_1^{e_1}\cdots p_r^{e_r}$ is the prime factorization, then
$$\varphi(n) = n\cdot\left(1-\frac{1}{p_1}\right)\cdots\left(1-\frac{1}{p_r}\right)$$

Only the **distinct** prime factors enter — the exponents $e_i$ are already contained
in the factor $n$.

## Recipe from the source

1. Factor $n$ into primes.
2. For each distinct prime factor $p$, form the factor $\left(1-\frac1p\right) = \frac{p-1}{p}$.
3. Multiply everything by $n$ and **cancel** — the denominators divide the prime
   factorization of $n$ evenly.

## Worked examples

### $\varphi(120)$

$$120 = 2\cdot60 = 2^2\cdot30 = 2^3\cdot15 = 2^3\cdot3\cdot5$$

$$\varphi(120) = 120\left(1-\tfrac12\right)\left(1-\tfrac13\right)\left(1-\tfrac15\right)
= 2^3\cdot3\cdot5\cdot\tfrac12\cdot\tfrac23\cdot\tfrac45$$

Cancel: $2^3 \cdot \frac12 = 4$, $3\cdot\frac23 = 2$, $5\cdot\frac45 = 4$:
$$= 4\cdot2\cdot4 = \boxed{32}$$

### $\varphi(176)$

$$176 = 2\cdot88 = 2\cdot8\cdot11 = 2^4\cdot11$$

$$\varphi(176) = 176\left(1-\tfrac12\right)\left(1-\tfrac{1}{11}\right)
= 2^4\cdot11\cdot\tfrac12\cdot\tfrac{10}{11} = 2^3\cdot10 = \boxed{80}$$

### $\varphi(330)$

$$330 = 3\cdot110 = 3\cdot10\cdot11 = 2\cdot3\cdot5\cdot11$$

$$\varphi(330) = 330\left(1-\tfrac12\right)\left(1-\tfrac13\right)
\left(1-\tfrac15\right)\left(1-\tfrac1{11}\right)$$

Step by step: $330 \cdot \tfrac12 = 165$, $\cdot\tfrac23 = 110$, $\cdot\tfrac45 = 88$,
$\cdot\tfrac{10}{11} = \boxed{80}$

Here $\varphi(176)$ and $\varphi(330)$ happen to have the same value — $\varphi$ is
far from injective.

### Check on small cases

| $n$ | Factorization | $\varphi(n)$ | Units |
|---|---|---|---|
| $6$ | $2\cdot3$ | $6\cdot\frac12\cdot\frac23 = 2$ | $1,5$ |
| $15$ | $3\cdot5$ | $15\cdot\frac23\cdot\frac45 = 8$ | $1,2,4,7,8,11,13,14$ |
| $16$ | $2^4$ | $16\cdot\frac12 = 8$ | $1,3,5,7,9,11,13,15$ |
| $20$ | $2^2\cdot5$ | $20\cdot\frac12\cdot\frac45 = 8$ | $1,3,7,9,11,13,17,19$ |

All match the lists in [[determining-units-and-zero-divisors]].

## Special cases

- $n = p$ prime: $\varphi(p) = p-1$ — all elements except $0$ are units.
- $n = p^e$: $\varphi(p^e) = p^e - p^{e-1} = p^{e-1}(p-1)$.
- $\varphi$ is **multiplicative**: $\gcd(m,n)=1 \Rightarrow \varphi(mn) = \varphi(m)\varphi(n)$.

> [!inferred] not from the summaries
> The special cases and multiplicativity are not in the summaries; they follow
> directly from the product formula and are good checks.

## Error in the source

On p. 6, $\varphi(176)$ is rewritten as
$$2^4\cdot11\cdot\left(-\tfrac12\right)\left(+\tfrac{10}{11}\right).$$
The minus sign is wrong — $\left(1-\frac12\right)$ gives $+\frac12$. The final result
$80$ is correct anyway; the sign is evidently a slip.

## Related pages

- [[units-and-zero-divisors]] — what is being counted
- [[determining-units-and-zero-divisors]] — the units listed explicitly
- [[fermats-little-theorem]] — special case $\varphi(p) = p-1$
- [[residue-class-ring]] — $\mathbb{Z}_n$
- [[laws-of-gcd]] — coprimality

## Sources

- `raw/Zn_das.pdf`, p. 4, p. 5, p. 6, p. 12
