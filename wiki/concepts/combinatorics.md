---
type: concept
title: Combinatorics
aliases: [Kombinatorik, Abzählen, combinatorics, Zählkoeffizient, counting coefficient]
tags: [combinatorics, chapter]
sources: [raw/kombinatorik_das.pdf]
created: 2026-09-30
updated: 2026-09-30
status: solid
---

# Combinatorics

Chapter overview for `raw/kombinatorik_das.pdf`. At its core the chapter consists of **two
tables** and **two exam problem types**.

## The two models

| | [[urn-model]] | [[box-model]] |
|---|---|---|
| Picture | drawing $k$ balls from an urn (*Urnenmodell*) with $n$ balls | distributing $n$ balls into $k$ boxes (*Fächermodell*) |
| Mapping | $\underline k \to \underline n$ | $\underline n \to \underline k$ |
| Table size | $2\times2$ (order? repetition?) | $4\times4$ (distinguishability × type of mapping) |
| Typical question | "How many subsets/words …?" | "How many mappings …?" |

The urn model is the first row of the box model in different packaging. **Caution:** the
roles of $n$ and $k$ are swapped between the two tables — in the urn model $n^k$, in the
box model $k^n$.

## Decision tree

1. **Is it about mappings?** → box model. Domain $=$ balls ($n$), codomain $=$ boxes
   ($k$). Then just read off injective / arbitrary / surjective / bijective.
2. **Is it about subsets or words?** → urn model. Order? Repetition?
3. **Is a letter profile given** (anagrams)? → [[multinomial-coefficient]].
4. **Is a number being partitioned or a set being partitioned?** →
   [[partitions-and-stirling-numbers]] ($P$, $p$, $S$, $B$).
5. **Is something forced** ("contains the 1", "starts with 1")? → fix the element,
   shrink both the base set and the selection by $1$ each.
6. **Several disjoint cases** (e.g. 1, 2, or 3 letters)? → sum rule, add the cases.

## The two exam problem types

| Type | Page | Points | What to do | Wiki page |
|---|---|---|---|---|
| List of short counting questions | p. 3, p. 4 | 1–2 each | only state the **counting coefficient**, don't evaluate it | [[counting-exercises]] |
| Existence of a set system | p. 3, p. 5, p. 7 | 4 | incidence matrix, double counting, check divisibility | [[double-counting]] |

Occasionally there is also "list all …" — then a complete enumeration is required (all
3-partitions of 4, all surjective mappings, all triangle symmetries). It helps to first
determine the count via a formula and then keep listing until that count is reached — that
is the built-in check.

## Pages of this chapter

- [[urn-model]] — $2\times2$ table, words as mappings, $k$-combinations
- [[box-model]] — the $4\times4$ table (twelvefold way)
- [[partitions-and-stirling-numbers]] — $P(n,k)$, $p(n,k)$, $S(n,k)$, $B(n)$
- [[multinomial-coefficient]] — anagrams, $C(k;h_1,\dots,h_n)$
- [[counting-exercises]] — both exam problem sets plus exercises 5/6
- [[double-counting]] — incidence-matrix argument

## Cross-connections

- [[permutation]] — $(n)_k$ and $n!$ are the same objects as in the relations and
  permutations chapter; the triangle symmetries in [[counting-exercises]] form the
  dihedral group $D_3\cong S_3$.
- [[relations-and-permutations]] — two-line notation, cycles, [[signum]]
- [[algebraic-structures]] — $S_n$ as a group, [[klein-four-group]]
- [[laws-of-gcd]] — divisibility arguments in [[double-counting]]
- [[laws-of-sets]] — subsets, power set

## Error density of this source

Three spots are erroneous, all on the exercise pages:

| Page | Error | corrected in |
|---|---|---|
| p. 1 | both kinds of partition denoted $P(n,k)$ | [[partitions-and-stirling-numbers]] |
| p. 3 | words over $\{0,1,2\}$ called "binary words" | [[counting-exercises]] |
| p. 9 | $r_1 = \begin{pmatrix}1&2&3\\1&2&1\end{pmatrix}$ is not a permutation | [[counting-exercises]] |
| p. 10 | $C(10;5,2,2,1,1)$ undefined ($\sum h_i = 11 \ne 10$) | [[multinomial-coefficient]] |

The two model tables (p. 2 and p. 6) were checked cell by cell and are correct in all
20 entries.

## Sources

- `raw/kombinatorik_das.pdf` (11 pages)
