---
type: definition
title: Multinomial coefficient (words with a fixed letter profile)
aliases: [multinomial coefficient, Multinomialkoeffizient, variation of type, Variation vom Typ, anagram, Anagramm]
tags: [combinatorics]
sources: [raw/kombinatorik_das.pdf]
created: 2026-09-30
updated: 2026-09-30
status: solid
---

# Multinomial coefficient

## Definition

A **$k$-variation of type $1^{h_1}2^{h_2}\cdots n^{h_n}$** is a word of length $k$ over
the alphabet $\underline n$ in which letter $i$ occurs exactly $h_i$ times. Hence
$h_1 + h_2 + \dots + h_n = k$ must hold.

Their number is the **multinomial coefficient**

$$C(k; h_1, h_2, \dots, h_n) \;=\; \frac{k!}{h_1!\, h_2!\cdots h_n!}$$

**Derivation:** there are $k!$ arrangements if all letters are treated as distinct. But
the $h_i$ copies of letter $i$ are indistinguishable among themselves; their $h_i!$
permutations produce the same word — hence divide by $h_1!\cdots h_n!$.

For $n = 2$ this is the ordinary binomial coefficient:
$C(k; h, k-h) = \binom kh$.

## Recipe

1. Determine the word length $k$ (the number of **all** characters, with multiplicity).
2. Write down the frequency profile: each letter with its count.
3. **Check:** the sum of frequencies $=k$. If this fails, the problem is misstated or a
   miscount happened.
4. Divide $k!$ by the product of the factorials of the frequencies.

## Examples from the source

### MOJOJOJO

Profile: $\mathrm M^1 \mathrm O^4 \mathrm J^3$, length $1+4+3 = 8$.

$$C(8; 1,4,3) = \frac{8!}{1!\,4!\,3!} = \frac{40320}{1\cdot 24\cdot 6} = \frac{40320}{144} = 280$$

### SOMMERSEMESTER

Profile: $\mathrm S^3 \mathrm O^1 \mathrm M^3 \mathrm E^4 \mathrm R^2 \mathrm T^1$,
length $3+1+3+4+2+1 = 14$.

$$C(14; 3,1,3,4,2,1) = \frac{14!}{3!\,1!\,3!\,4!\,2!\,1!} = \frac{87\,178\,291\,200}{1728} = 50\,450\,400$$

### ABRAKADABRA

Profile: $\mathrm A^5 \mathrm B^2 \mathrm R^2 \mathrm K^1 \mathrm D^1$,
length $5+2+2+1+1 = 11$.

$$C(11; 5,2,2,1,1) = \frac{11!}{5!\,2!\,2!\,1!\,1!} = \frac{39\,916\,800}{480} = 83\,160$$

## Error in the source: words of length 10 from ABRAKADABRA

> [!warning] Error in the source (p. 10)
> For the question of words of **length 10** from the letters of ABRAKADABRA, the source
> writes $C(10; 5,2,2,1,1)$. This expression is **undefined**: $5+2+2+1+1 = 11 \ne 10$.
> A multinomial coefficient requires that the frequencies sum to the word length.

**Correct computation.** A word of length 10 arises by omitting exactly one letter. Sum
over the choice of the omitted letter:

| omitted | remaining profile | count |
|---|---|---|
| A | $\mathrm A^4\mathrm B^2\mathrm R^2\mathrm K^1\mathrm D^1$ | $\frac{10!}{4!2!2!1!1!} = 37\,800$ |
| B | $\mathrm A^5\mathrm B^1\mathrm R^2\mathrm K^1\mathrm D^1$ | $\frac{10!}{5!1!2!1!1!} = 15\,120$ |
| R | $\mathrm A^5\mathrm B^2\mathrm R^1\mathrm K^1\mathrm D^1$ | $\frac{10!}{5!2!1!1!1!} = 15\,120$ |
| K | $\mathrm A^5\mathrm B^2\mathrm R^2\mathrm D^1$ | $\frac{10!}{5!2!2!1!} = 7\,560$ |
| D | $\mathrm A^5\mathrm B^2\mathrm R^2\mathrm K^1$ | $\frac{10!}{5!2!2!1!} = 7\,560$ |
| | **Sum** | $\mathbf{83\,160}$ |

The result is **the same** as for length 11 — no coincidence: every word of length 10
extends uniquely to a word of length 11 by appending the one missing letter at the end.
This assignment is a bijection, so the counts are equal.

The number $83\,160$ in the source is thus correct — only the formula used to justify it
is not. (Presumably the result of part (i) was simply carried over.)

## Related

- [[urn-model]] — words as maps
- [[box-model]] — the large distribution table
- [[partitions-and-stirling-numbers]] — related decomposition numbers
- [[counting-exercises]] — further worked-out problems
- [[combinatorics]] — chapter overview

## Sources

- `raw/kombinatorik_das.pdf`, p. 3, p. 7, p. 10
