---
type: definition
title: Box Model (Twelvefold Way)
aliases: [box model, Fächermodell, twelvefold way, distribution problems, Verteilungsprobleme, balls and boxes, Bälle und Fächer]
tags: [combinatorics]
sources: [raw/kombinatorik_das.pdf]
created: 2026-09-30
updated: 2026-09-30
status: solid
---

# Box model

## Question

$n$ balls (*Bälle*) are distributed onto $k$ boxes (*Fächer*, box model = *Fächermodell*)
— equivalently: a map $\underline n \to \underline k$.

Two decisions fix the row (are the balls resp. the boxes distinguishable?), the kind of
map fixes the column. That gives $4\times4$ cells — the central table of the chapter.

## The table

| Balls / boxes distinguishable? | **injective** ($n\le k$) | **arbitrary** | **surjective** ($n\ge k$) | **bijective** ($n=k$) |
|---|---|---|---|---|
| **yes / yes** | $(k)_n$<br>$n$-permutations of $k$ | $k^n$<br>$n$-variations of $k$ | $k!\cdot S(n,k)$ | $n!$ |
| **yes / no** | $1$ | $\sum_{i=1}^{k} S(n,i)$<br>for $k=n$: $B(n)$ | $S(n,k)$<br>$k$-partition of $n$ | $1$ |
| **no / yes** | $\dbinom{k}{n}$<br>$n$-combinations of $k$ | $\dbinom{k+n-1}{n}$<br>$n$-repetitions of $k$ | $p(n,k)=\dbinom{n-1}{k-1}$<br>ordered $k$-integer partition | $1$ |
| **no / no** | $1$ | $\sum_{i=1}^{k} P(n,i)$ | $P(n,k)$<br>unordered $k$-integer partition | $1$ |

Here $S(n,k)$ is the **Stirling number of the second kind**, $B(n)$ the **Bell number**,
$P(n,k)$ and $p(n,k)$ the number of unordered resp. ordered integer partitions —
see [[partitions-and-stirling-numbers]].

## How to use the table

The exam problems are almost verbatim entries of this table. Procedure:

1. **What are the balls, what are the boxes?** For "maps from $A$ to $B$" the elements
   of $A$ are the balls ($n = |A|$) and those of $B$ are the boxes ($k = |B|$). The
   source writes $n$ and $k$ next to the sets in every problem — that's exactly why.
2. **Distinguishable?** For map problems it's always "yes/yes", i.e. the first row.
3. **Which column?** injective / arbitrary / surjective / bijective.

**Pitfall:** in the first row we have $(k)_n$ and $k^n$ — the roles of $n$ and $k$ are
**swapped** compared to the [[urn-model]], because the direction of the map is reversed
($\underline n \to \underline k$ instead of $\underline k \to \underline n$). This is the
most common mix-up.

| | Urn model | Box model |
|---|---|---|
| Map | $\underline k \to \underline n$ | $\underline n \to \underline k$ |
| all | $n^k$ | $k^n$ |
| injective | $(n)_k$ | $(k)_n$ |

## Why the rows look the way they do

**Row "yes/no" (boxes indistinguishable).** Injective: each ball alone in its box —
there is only *one* such image, hence $1$. Surjective: no box empty, the boxes are
indistinguishable → that is exactly a **set partition** into $k$ blocks, $S(n,k)$.
Arbitrary: sum over all block counts; for $k = n$ this is the Bell number $B(n)$.

**Row "no/yes" (balls indistinguishable).** Only the fill levels count. Injective: choose
$n$ of the $k$ boxes, $\binom kn$. Surjective: every box gets at least one ball — that is
an **ordered integer partition** (composition), $\binom{n-1}{k-1}$.

**Row "no/no".** Neither balls nor boxes distinguishable → only the multiset of fill
levels counts, i.e. an **unordered integer partition**.

**Column bijective.** $n = k$, every box gets exactly one ball. Only in "yes/yes" is
there any choice left ($n!$), otherwise everything is the same ($1$).

## Related

- [[urn-model]] — the coarser $2\times2$ table
- [[partitions-and-stirling-numbers]] — $S(n,k)$, $B(n)$, $P(n,k)$, $p(n,k)$
- [[multinomial-coefficient]] — words with a fixed letter profile
- [[counting-exercises]] — the table applied to exam problems
- [[permutation]] — $(n)_k$ and $n!$
- [[combinatorics]] — chapter overview

## Sources

- `raw/kombinatorik_das.pdf`, p. 2, p. 6
