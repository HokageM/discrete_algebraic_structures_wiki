---
type: definition
title: Urn Model
aliases: [urn model, Urnenmodell, drawing, Ziehen, combination, Kombination, variation, Variation, repetition, Repetition]
tags: [combinatorics]
sources: [raw/kombinatorik_das.pdf]
created: 2026-09-30
updated: 2026-09-30
status: solid
---

# Urn Model

## Question

Drawing $k$ balls from an urn with $n$ balls — equivalently: a mapping
$\underline{k} \to \underline{n}$.

Two binary choices give four cases:

| | without repetition (for $k \le n$) | with repetition |
|---|---|---|
| **ordered** | **permutation** $(n)_k$ | **variation** $n^k$ |
| **unordered** | **combination** $\dbinom{n}{k}$ | **repetition** $\dbinom{n+k-1}{k}$ |

## The four cases

**Permutation** $(n)_k = n(n-1)\cdots(n-k+1)$

Ordered drawing without replacement. Corresponds to the **injective** mappings
$\underline k \to \underline n$ — see [[permutation]].

**Variation** $n^k$

Ordered drawing with replacement. Corresponds to **all** mappings
$\underline k \to \underline n$, i.e. all **words** of length $k$ over an alphabet
with $n$ letters.

**Combination** $\binom{n}{k}$

Unordered drawing without replacement. Corresponds to the $k$-element **subsets** of
$\underline n$.

**Repetition** $\binom{n+k-1}{k}$

Unordered drawing with replacement — multisets.

## $k$-combinations as monotone words

The source gives a useful reinterpretation:

> $k$-combinations of $n$ = words $x_1x_2\dots x_k$ of length $k$ over the alphabet
> $\underline n$ with $x_1 < x_2 < \dots < x_k$ (**strictly monotone**). Count $\binom nk$.

The monotonicity condition replaces "unordered": out of all $k!$ arrangements of a
subset, exactly the sorted one is selected.

**Example: 3-combinations of 4** — four viewpoints of the same object:

| monotone word | subset | binary word (length 4, three ones) |
|---|---|---|
| $123$ | $\{1,2,3\}$ | $1110$ |
| $124$ | $\{1,2,4\}$ | $1101$ |
| $134$ | $\{1,3,4\}$ | $1011$ |
| $234$ | $\{2,3,4\}$ | $0111$ |

$$\binom43 = 4 \;✓$$

The **binary-word view** is the most important trick of the chapter: a $k$-subset of
$\underline n$ is the same as a binary word of length $n$ with $k$ ones (indicator).
This lets many seemingly different problems be translated into one another — see
[[counting-exercises]].

## Words and mappings

The source cleanly defines the word concept via mappings:

Let $A$ be an **alphabet**, $n \in \mathbb{N}_0$. A **word** is a mapping
$f : \underline n \to A$, written in two-line notation
$$f = \begin{pmatrix}1&2&\cdots&n\\ a_1&a_2&\cdots&a_n\end{pmatrix}
\quad\text{short}\quad f = a_1a_2\dots a_n$$

Example $A=\{a,b,c\}$, $n=2$: $aa, ab, ac, ba, bb, bc, ca, cb, cc$ — these are
$3^2 = 9$ words.

This is the same notation as for [[permutation]]; a permutation is exactly a word
without repetition.

## Related

- [[box-model]] — the finer classification (12 cases)
- [[multinomial-coefficient]] — words with prescribed letter frequencies
- [[permutation]] — $(n)_k$ and $n!$
- [[counting-exercises]] — worked-out exercises
- [[combinatorics]] — chapter overview

## Sources

- `raw/kombinatorik_das.pdf`, p. 2, p. 6, p. 8, p. 9
